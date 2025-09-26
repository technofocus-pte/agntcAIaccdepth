# Exercício 5: Plugins do Semantic Kernel

### Duração Estimada: 50 minutos

Este laboratório prático explora o poder dos plugins para aprimorar o desenvolvimento com LLMs usando o Semantic Kernel. Projetado para quem é novo na extensibilidade de IA, o laboratório orienta você na criação e integração de plugins para expandir as capacidades do seu chatbot. Você implementará um plugin de horário e um plugin de obtenção de clima, permitindo que sua IA acesse dados em tempo real e contextuais além do seu escopo de treinamento. Além disso, você aprenderá a desenvolver plugins do Semantic Kernel em Python e a utilizar o Auto Function Calling para encadeá-los de forma fluida.

**Observação:** Este laboratório está implementado em **C#** e **Python**. Você pode realizar os exercícios na **linguagem com a qual se sentir mais confortável** — os conceitos principais são os mesmos. Para visualizar as instruções de uma linguagem específica:

- Clique no pequeno **ícone de seta** (▶) ao lado do nome da linguagem.
- Isso revelará as instruções passo a passo para essa linguagem.

Escolha sua linguagem preferida e comece agora!

## Objetivos

Neste exercício, você realizará as seguintes tarefas:

- Tarefa 1: Testar o aplicativo sem o Plugin de Horário
- Tarefa 2: Criar e importar o Plugin de Horário
- Tarefa 3: Criar e importar o Plugin de Geocodificação
- Tarefa 4: Criar e importar o Plugin de Clima

## Tarefa 1: Testar o aplicativo sem o Plugin de Horário

Nesta tarefa, você irá explorar os diferentes tipos de fluxo no Azure AI Foundry executando o aplicativo sem o Plugin de Horário, para observar seu comportamento padrão.

1. Inicie seu aplicativo de Chat com IA em qualquer uma das linguagens e envie o seguinte prompt:

   ```
   Que horas são?
   ```
2. Como a IA não tem capacidade de fornecer informações em tempo real, você receberá uma resposta semelhante à seguinte:

   ```
   Não posso fornecer informações em tempo real, incluindo a hora atual. Você pode verificar a hora no seu dispositivo ou através de várias fontes online.
   ```

   ![](./media/image_043.png)

## Tarefa 2: Criar e importar o Time Plugin

Nesta tarefa, você explorará diferentes tipos de fluxos no Azure AI Foundry criando e importando o **Time Plugin** para aprimorar a funcionalidade do aplicativo.

<details>
<summary><strong>Python</strong></summary>

1. Navegue até o diretório `Python>src>plugins` e crie um novo arquivo chamado **time_plugin.py (1)**.

   ![](./media/image_044.png)

2. Adicione o seguinte código ao arquivo:

   ```python
   from datetime import datetime
   from typing import Annotated
   from semantic_kernel.functions import kernel_function

   class TimePlugin:
       @kernel_function()
       def current_time(self) -> str:
           return datetime.now().strftime("%Y-%m-%d %H:%M:%S")

       @kernel_function()
       def get_year(self, date_str: Annotated[str, "The date string in format YYYY-MM-DD"] = None) -> str:
           if date_str is None:
               return str(datetime.now().year)
           
           try:
               date_obj = datetime.strptime(date_str, "%Y-%m-%d")
               return str(date_obj.year)
           except ValueError:
               return "Invalid date format. Please use YYYY-MM-DD."

       @kernel_function()
       def get_month(self, date_str: Annotated[str, "The date string in format YYYY-MM-DD"] = None) -> str:
           if date_str is None:
               return datetime.now().strftime("%B")
           
           try:
               date_obj = datetime.strptime(date_str, "%Y-%m-%d")
               return date_obj.strftime("%B")  # Full month name
           except ValueError:
               return "Invalid date format. Please use YYYY-MM-DD."

       @kernel_function()
       def get_day_of_week(self, date_str: Annotated[str, "The date string in format YYYY-MM-DD"] = None) -> str:
           if date_str is None:
               return datetime.now().strftime("%A")
           
           try:
               date_obj = datetime.strptime(date_str, "%Y-%m-%d")
               return date_obj.strftime("%A")  # Full weekday name
           except ValueError:
               return "Invalid date format. Please use YYYY-MM-DD."
   ```

3. Salve o arquivo.

4. Navegue até o diretório `Python>src` e abra o arquivo **chat.py**.

   ![](./media/image_030.png)

5. Adicione o seguinte código na seção `#Import Modules` do arquivo:

   ```python
   from semantic_kernel.connectors.ai.open_ai.prompt_execution_settings.azure_chat_prompt_execution_settings import (
       AzureChatPromptExecutionSettings,
   )
   from plugins.time_plugin import TimePlugin
   ```

   ![](./media/image_045.png)

6. Adicione o seguinte código na seção `#Challenge 03 - Create Prompt Execution Settings` do arquivo:

   ```python
   execution_settings = AzureChatPromptExecutionSettings()
   execution_settings.function_choice_behavior = FunctionChoiceBehavior.Auto()
   logger.info("Automatic function calling enabled")
   ```

   ![](./media/image_046.png)

7. Adicione o seguinte código na seção `# Placeholder for Time plugin` do arquivo:

   ```python
   time_plugin = TimePlugin()
   kernel.add_plugin(time_plugin, plugin_name="TimePlugin")
   logger.info("Time plugin loaded")
   ```

   ![](./media/placeholder.png)

8. Pesquise (usando Ctrl+F) e remova o seguinte trecho de código do arquivo, pois ativamos a chamada automática de funções e ele não será mais necessário:

   ```python
   execution_settings = kernel.get_prompt_execution_settings_from_service_id("chat-service")
   ```

   > **Nota**: Você deve remover este trecho de dois blocos de código — um estará dentro da função **def initialize_kernel():** e outro no bloco de código **global chat_history**.

9. Caso encontre erros de indentação, utilize o código da seguinte URL:

   ```
   https://raw.githubusercontent.com/CloudLabsAI-Azure/ai-developer/refs/heads/prod/CodeBase/python/lab-03_time_plugin.py
   ```

10. Salve o arquivo.

11. Clique com o botão direito em `Python>src` no painel à esquerda e selecione **Open in Integrated Terminal**.

    ![](./media/image_035.png)

12. Use o seguinte comando para executar o app:

    ```
    streamlit run app.py
    ```

13. Se o aplicativo não abrir automaticamente no navegador, acesse manualmente usando o seguinte **URL**:

    ```
    http://localhost:8501
    ```

14. Envie o seguinte prompt:

    ```
    What time is it?
    ```

15. Como a IA possui o **Time Plugin**, ela será capaz de fornecer informações em tempo real. Você receberá uma resposta semelhante a:

    ```
    The current time is 3:43 PM on January 23, 2025.
    ```

    ![](./media/image_048.png)

</details>

<details>
<summary><strong>C Sharp (C#)</strong></summary>

1. Navegue até o diretório `Dotnet>src>BlazorAI>Plugins` e crie um novo arquivo chamado **TimePlugin.cs**.

   ![](./media/image_049.png)

2. Adicione o seguinte código no arquivo:

   ```csharp
   using System;
   using System.ComponentModel;
   using System.Globalization;
   using Microsoft.SemanticKernel;

   namespace BlazorAI.Plugins
   {
       public class TimePlugin
       {        
           [KernelFunction("current_time")]
           [Description("Gets the current date and time from the server. Use this directly when the user asks what time it is or wants to know the current date.")]
           public string CurrentTime()
           {
               return DateTime.Now.ToString("yyyy-MM-dd HH:mm:ss");
           }

           [KernelFunction("get_current_time")]
           [Description("Gets the current date and time from the server's system clock. Use this directly without asking the user for their location.")]
           public string GetCurrentTime()
           {
               return DateTime.Now.ToString("yyyy-MM-dd HH:mm:ss");
           }
           
           [KernelFunction("get_year")]
           [Description("Extract the year from a date string or get the current year from the system clock. Examples: 'What year is it now?' or 'What year is 2023-05-15?'")]
           public string GetYear(
               [Description("The date string. Accepts formats like YYYY-MM-DD, MM/DD/YYYY, etc. If not provided, uses the server's current date.")] 
               string? dateStr = null)
           {
               if (string.IsNullOrEmpty(dateStr))
               {
                   return DateTime.Now.Year.ToString();
               }

               DateTime date;
               if (TryParseDate(dateStr, out date))
               {
                   return date.Year.ToString();
               }
               
               return $"Could not parse '{dateStr}' as a valid date. Please provide a date in a standard format like YYYY-MM-DD or MM/DD/YYYY.";
           }
           
           [KernelFunction("get_month")]
           [Description("Extract the month name from a date string or get the current month from the system clock. Examples: 'What month is it now?' or 'What month is 2023-05-15?'")]
           public string GetMonth(
               [Description("The date string. Accepts formats like YYYY-MM-DD, MM/DD/YYYY, etc. If not provided, uses the server's current date.")] 
               string? dateStr = null)
           {
               if (string.IsNullOrEmpty(dateStr))
               {
                   return DateTime.Now.ToString("MMMM");
               }
               
               DateTime date;
               if (TryParseDate(dateStr, out date))
               {
                   return date.ToString("MMMM"); // Nome completo do mês
               }
               
               return $"Could not parse '{dateStr}' as a valid date. Please provide a date in a standard format like YYYY-MM-DD or MM/DD/YYYY.";
           }
           
           [KernelFunction("get_day_of_week")]
           [Description("Get the day of week from the server's system clock or for a specific date. Examples: 'What day is it today?' or 'What day of the week is 2023-05-15?'")]
           public string GetDayOfWeek(
               [Description("The date string. Accepts formats like YYYY-MM-DD, MM/DD/YYYY, etc. If not provided, uses the server's current date.")] 
               string? dateStr = null)
           {
               if (string.IsNullOrEmpty(dateStr))
               {
                   return DateTime.Now.ToString("dddd");
               }
               
               DateTime date;
               if (TryParseDate(dateStr, out date))
               {
                   return date.ToString("dddd"); // Nome completo do dia
               }
               
               return $"Could not parse '{dateStr}' as a valid date. Please provide a date in a standard format like YYYY-MM-DD or MM/DD/YYYY.";
           }

           private bool TryParseDate(string dateStr, out DateTime result)
           {
               string[] formats = { 
                   "yyyy-MM-dd", "MM/dd/yyyy", "dd/MM/yyyy", 
                   "M/d/yyyy", "d/M/yyyy", "MMM d, yyyy", 
                   "MMMM d, yyyy", "yyyy/MM/dd", "dd-MMM-yyyy"
               };
               
               return DateTime.TryParseExact(
                   dateStr, 
                   formats, 
                   CultureInfo.InvariantCulture,
                   DateTimeStyles.None, 
                   out result) || DateTime.TryParse(dateStr, out result);
           }
       }
   }
   ```

3. Salve o arquivo.

4. Navegue até o diretório `Dotnet>src>BlazorAI>Components>Pages` e abra o arquivo **Chat.razor.cs**.

   ![](./media/image_038.png)

5. Adicione o seguinte código na seção `// Import Models` do arquivo:

   ```csharp
   using Microsoft.SemanticKernel.Connectors.OpenAI;
   using BlazorAI.Plugins;
   using System;
   ```

   ![](./media/image_050.png)

6. Procure por **private Kernel? kernel;** (usando Ctrl+F) e adicione o seguinte código logo abaixo:

   ```csharp
   private OpenAIPromptExecutionSettings? promptSettings;
   ```

   ![](./media/image_051.png)

7. Procure por **chatHistory = [];** (usando Ctrl+F) e atualize a linha com o seguinte código:

   ```csharp
   chatHistory = new ChatHistory();
   ```

   ![](./media/image_052.png)

8. Adicione o seguinte código na seção `// Challenge 03 - Create OpenAIPromptExecutionSettings` (1) do arquivo:

   ```csharp
   promptSettings = new OpenAIPromptExecutionSettings
   {
       ToolCallBehavior = ToolCallBehavior.AutoInvokeKernelFunctions,
       Temperature = 0.7,
       TopP = 0.95,
       MaxTokens = 800
   };
   ```

   ![](./media/image_053.png)

9. Adicione o seguinte código na seção `// Challenge 03 - Add Time Plugin` do arquivo:

   ```csharp
   var timePlugin = new Plugins.TimePlugin();
   kernel.ImportPluginFromObject(timePlugin, "TimePlugin");
   ```

   ![](./media/image_054.png)

10. Procure por **var assistantResponse = await chatCompletionService.GetChatMessageContentAsync** (usando Ctrl+F) e adicione a seguinte linha entre chatHistory e kernel:

```csharp
executionSettings: promptSettings,
```

> **Nota**: O código final será semelhante ao seguinte:

```csharp
var assistantResponse = await chatCompletionService.GetChatMessageContentAsync(
    chatHistory: chatHistory,
    executionSettings: promptSettings,
    kernel: kernel);
```

![](./media/image_055.png)

11. Caso enfrente algum problema de indentação, use o código no link abaixo:

```
https://raw.githubusercontent.com/CloudLabsAI-Azure/ai-developer/refs/heads/prod/CodeBase/c%23/lab-03_time_plugin.cs
```

12. Salve o arquivo.

13. Clique com o botão direito em `Dotnet>src>Aspire>Aspire.AppHost` no painel esquerdo e selecione **Open in Integrated Terminal**.

![](./media/image_040.png)

14. Use o seguinte comando para executar o aplicativo:

```
dotnet run
```

15. Abra uma nova aba no navegador e acesse o link do **blazor-aichat**, ou seja: **https://localhost:7118/**

16. Envie o seguinte prompt:

```
What time is it?
```

17. Como a IA possui o **Time Plugin**, ela conseguirá fornecer informações em tempo real. Você verá uma resposta semelhante a:

```
A hora atual é 15:43 do dia 23 de janeiro de 2025.
```

![](./media/image_056.png)

</details>

## Tarefa 3: Criar e importar o Plugin de Geocodificação

Nesta tarefa, você irá explorar diferentes tipos de fluxo no Azure AI Foundry, criando e importando o Plugin de Geocodificação para habilitar funcionalidades baseadas em localização.

1. Abra uma nova aba no navegador, acesse o portal da [Geocoding API](https://geocode.maps.co/) e clique no botão **Free API key** no topo da página.

   ![](./media/image_057.png)

2. Insira seus dados e clique em **Create Account (1)**.

   ![](./media/image_058.png)

   > **Nota**: Use seu e-mail pessoal ou corporativo para se registrar.

3. Você receberá um e-mail; clique no link contido nele para verificar seu endereço de e-mail.

4. Você receberá sua **chave de API de geocodificação gratuita**, salve-a em um bloco de notas para uso posterior.

<details>
<summary><strong>Python</strong></summary>

1. Navegue até o diretório `Python>src` e abra o arquivo **.env**.

   ![](./media/image_026.png)

2. Cole a chave da API de geocodificação que você acabou de receber por e-mail ao lado de `GEOCODING_API_KEY`.

   ![](./media/image_059.png)

   > **Nota**: Certifique-se de que todos os valores no arquivo **.env** estejam entre **aspas duplas (")**.

3. Salve o arquivo.

4. Navegue até o diretório `Python>src` e abra o arquivo **chat.py**.

   ![](./media/image_030.png)

5. Adicione o seguinte código na seção `#Import Modules` do arquivo:

   ```python
   from plugins.geo_coding_plugin import GeoPlugin
   ```

   ![](./media/image_030.png)

6. Adicione o seguinte código na seção `# Placeholder for Time plugin`, logo após o plugin de tempo no arquivo:

   ```python
   kernel.add_plugin(
       GeoPlugin(),
       plugin_name="GeoLocation",
   )
   logger.info("GeoLocation plugin loaded")
   ```

   ![](./media/image_061.png)

7. Caso encontre algum erro de indentação, use o código do seguinte URL:

   ```
   https://raw.githubusercontent.com/CloudLabsAI-Azure/ai-developer/refs/heads/prod/CodeBase/python/lab-03_geo_coding.py
   ```

8. Salve o arquivo.

9. Clique com o botão direito em `Python>src` no painel à esquerda e selecione **Open in Integrated Terminal**.

   ![](./media/image_035.png)

10. Use o seguinte comando para executar o aplicativo:

    ```bash
    streamlit run app.py
    ```

11. Se o app não abrir automaticamente no navegador, acesse pelo seguinte **URL**:

    ```
    http://localhost:8501
    ```

12. Envie o seguinte prompt:

    ```
    What are the geo-coordinates for Tampa, FL
    ```

13. Como a IA possui o **Plugin de Geocodificação**, ela será capaz de fornecer informações em tempo real. Você verá uma resposta semelhante a:

    ```
    As coordenadas geográficas de Tampa, FL são:

    Latitude: 27.9477595  
    Longitude: -82.458444
    ```

    ![](./media/image_062.png)

</details>

<details>
<summary><strong>C Sharp (C#)</strong></summary>

1. Navegue até o diretório `Dotnet>src>BlazorAI` e abra o arquivo **appsettings.json**.

   ![](./media/image_028.png)

2. Cole a chave da API de geocodificação que você acabou de receber por e-mail ao lado de `GEOCODING_API_KEY`.

   ![](./media/image_063.png)

   > Nota: Certifique-se de que todos os valores no arquivo **appsettings.json** estejam entre **aspas duplas (")**.

3. Salve o arquivo.

4. Navegue até o diretório `Dotnet>src>BlazorAI>Components>Pages` e abra o arquivo **Chat.razor.cs**.

   ![](./media/image_038.png)

5. Adicione o seguinte código na seção `// Challenge 03 - Add Time Plugin`, logo após o plugin de tempo no arquivo:

   ```csharp
   var geocodingPlugin = new GeocodingPlugin(
       kernel.Services.GetRequiredService<IHttpClientFactory>(), 
       Configuration);
   kernel.ImportPluginFromObject(geocodingPlugin, "GeocodingPlugin");
   ```

   ![](./media/image_064.png)

6. Caso encontre algum erro de indentação, use o código do seguinte URL:

   ```
   https://raw.githubusercontent.com/CloudLabsAI-Azure/ai-developer/refs/heads/prod/CodeBase/c%23/lab-03_geo_coding.cs
   ```

7. Salve o arquivo.

8. Clique com o botão direito em `Dotnet>src>Aspire>Aspire.AppHost` no painel à esquerda e selecione **Open in Integrated Terminal**.

   ![](./media/image_040.png)

9. Use o seguinte comando para executar o aplicativo:

   ```bash
   dotnet run
   ```

10. Abra uma nova aba no navegador e acesse o link do **blazor-aichat**, ou seja https://localhost:7118/

11. Envie o seguinte prompt:

    ```
    What are the geo-coordinates for Tampa, FL
    ```

12. Como a IA possui o **Plugin de Geocodificação**, ela será capaz de fornecer informações em tempo real. Você verá uma resposta semelhante a:

    ```
    As coordenadas geográficas de Tampa, FL são:

    Latitude: 27.9477595  
    Longitude: -82.458444
    ```

    ![](./media/image_065.png)

</details>

## Tarefa 4: Criar e importar o Plugin de Clima

Nesta tarefa, você irá explorar diferentes tipos de fluxo no Azure AI Foundry criando e importando o **Plugin de Clima** para integrar funcionalidades relacionadas ao clima.

<details>
<summary><strong>Python</strong></summary>

1. Navegue até o diretório `Python>src>plugins` e crie um novo arquivo chamado **weather\plugin.py**.

   ![](./media/image_066.png)

2. Adicione o seguinte código ao arquivo:

   ```python
   from typing import Annotated
   import requests
   from semantic_kernel.functions import kernel_function
   import json
   from datetime import datetime, timedelta

   class WeatherPlugin:
       @kernel_function(description="Get weather forecast for a location up to 16 days in the future")
       def get_forecast_weather(self, 
                               latitude: Annotated[float, "Latitude of the location"],
                               longitude: Annotated[float, "Longitude of the location"],
                               days: Annotated[int, "Number of days to forecast (up to 16)"] = 16):
           
           # Ensure days is within valid range (API supports up to 16 days)
           if days > 16:
               days = 16
           
           url = (f"https://api.open-meteo.com/v1/forecast"
               f"?latitude={latitude}&longitude={longitude}"
               f"&daily=temperature_2m_max,temperature_2m_min,precipitation_sum,precipitation_probability_max,weather_code"
               f"&amp;current=temperature_2m,relative_humidity_2m,apparent_temperature,precipitation,weather_code,wind_speed_10m"
               f"&temperature_unit=fahrenheit&wind_speed_unit=mph&precipitation_unit=inch"
               f"&forecast_days={days}&timezone=auto")
           
           try:
               response = requests.get(url)
               response.raise_for_status()
               data = response.json()
               
               daily = data.get('daily', {})
               times = daily.get('time', [])
               max_temps = daily.get('temperature_2m_max', [])
               min_temps = daily.get('temperature_2m_min', [])
               precip_sums = daily.get('precipitation_sum', [])
               precip_probs = daily.get('precipitation_probability_max', [])
               weather_codes = daily.get('weather_code', [])
               
               forecasts = []
               for i in range(len(times)):
                   # Convert date string to datetime object for day name
                   date_obj = datetime.strptime(times[i], "%Y-%m-%d")
                   day_name = date_obj.strftime("%A, %B %d")
                   
                   weather_desc = self._get_weather_description(weather_codes[i])
                   
                   forecast = {
                       "date": times[i],
                       "day": day_name,
                       "high_temp": f"{max_temps[i]}°F",
                       "low_temp": f"{min_temps[i]}°F",
                       "precipitation": f"{precip_sums[i]} inches",
                       "precipitation_probability": f"{precip_probs[i]}%",
                       "conditions": weather_desc
                   }
                   forecasts.append(forecast)
               
               result = {
                   "location_coords": f"{latitude}, {longitude}",
                   "forecast_days": len(forecasts),
                   "forecasts": forecasts
               }
               
               # For more concise output in chat
               return json.dumps(result, indent=2)
           except Exception as e:
               return f"Error fetching forecast weather: {str(e)}"
       
       def _get_weather_description(self, code):
           weather_codes = {
                0: "Clear sky",
                1: "Mainly clear", 2: "Partly cloudy", 3: "Overcast",
                45: "Fog", 48: "Depositing rime fog",
                51: "Light drizzle", 53: "Moderate drizzle", 55: "Dense drizzle",
                56: "Light freezing drizzle", 57: "Dense freezing drizzle",
                61: "Slight rain", 63: "Moderate rain", 65: "Heavy rain",
                66: "Light freezing rain", 67: "Heavy freezing rain",
                71: "Slight snow fall", 73: "Moderate snow fall", 75: "Heavy snow fall",
                77: "Snow grains",
                80: "Slight rain showers", 81: "Moderate rain showers", 82: "Violent rain showers",
                85: "Slight snow showers", 86: "Heavy snow showers",
                95: "Thunderstorm", 96: "Thunderstorm with slight hail", 99: "Thunderstorm with heavy hail"
           }
           return weather_codes.get(code, "Unknown")
   ```

3. Salve o arquivo.

4. Navegue até o diretório `Python>src` e abra o arquivo **chat.py**.

   ![](./media/image_030.png)

5. Adicione o seguinte código na seção `#Import Modules` do arquivo:

   ```python
   from plugins.weather_plugin import WeatherPlugin
   ```

   ![](./media/image_067.png)

6. Adicione o seguinte código na seção `# Placeholder for Time plugin`, logo após o **plugin de geocodificação**:

   ```python
   kernel.add_plugin(
       WeatherPlugin(),
       plugin_name="Weather",
   )
   logger.info("Weather plugin loaded")
   ```

   ![](./media/image_068.png)

7. Caso encontre algum erro de indentação, utilize o código no seguinte URL:

   ```
   https://raw.githubusercontent.com/CloudLabsAI-Azure/ai-developer/refs/heads/prod/CodeBase/python/lab-03_weather.py
   ```

8. Salve o arquivo.

9. Clique com o botão direito em `Python>src` no painel à esquerda e selecione **Abrir no Terminal Integrado**.

   ![](./media/image_035.png)

10. Use o seguinte comando para executar o app:

    ```
    streamlit run app.py
    ```

11. Se o app não abrir automaticamente no navegador, você pode acessá-lo através da seguinte **URL**:

    ```
    http://localhost:8501
    ```

12. Envie o seguinte prompt:

    ```
    What is today's weather in San Francisco?
    ```

13. Você receberá uma resposta semelhante à mostrada abaixo:

    ![](./media/image_069.png)

    A IA realizará o seguinte plano para responder à pergunta, embora possa fazê-lo em outra ordem ou com outro conjunto de funções:

    1️⃣ A IA solicitará ao Semantic Kernel que chame a função GetDate no plugin de tempo para obter a data de hoje, a fim de calcular quantos dias faltam até a próxima quinta-feira.

    2️⃣ Como a previsão do tempo requer latitude e longitude, a IA solicitará ao Semantic Kernel que chame a função GetLocation no plugin de geocodificação para obter as coordenadas de San Francisco.

    3️⃣ Por fim, a IA pedirá ao Semantic Kernel que chame a função GetWeatherForecast no plugin de clima, passando a data atual e as coordenadas (Lat/Long), para obter a previsão do tempo da próxima quinta-feira (expressa em número de dias à frente) para as coordenadas de San Francisco.

    Um diagrama de sequência simplificado entre o Semantic Kernel e a IA é mostrado abaixo:

    ![](./media/seq_diag.png)

</details>

<details>  
<summary><strong>C Sharp (C#)</strong></summary>

1. Navegue até o diretório `Dotnet>src>BlazorAI>Plugins` e crie um novo arquivo chamado **WeatherPlugin.cs**.

   ![](./media/image_070.png)

2. Adicione o seguinte código no arquivo:

   ```csharp
   using System;
   using System.Collections.Generic;
   using System.ComponentModel;
   using System.Globalization;
   using System.Net.Http;
   using System.Text.Json;
   using System.Threading.Tasks;
   using Microsoft.SemanticKernel;

   namespace BlazorAI.Plugins
   {
       public class WeatherPlugin
       {
           private readonly IHttpClientFactory _httpClientFactory;

           public WeatherPlugin(IHttpClientFactory httpClientFactory)
           {
               _httpClientFactory = httpClientFactory;
           }

           [KernelFunction("GetWeatherForecast")]
           [Description("Get weather forecast for a location up to 16 days in the future")]
           public async Task<string> GetWeatherForecastAsync(
               [Description("Latitude of the location")] double latitude,
               [Description("Longitude of the location")] double longitude,
               [Description("Number of days to forecast (up to 16)")] int days = 16)
           {
               // Ensure days is within valid range (API supports up to 16 days)
               if (days > 16)
                   days = 16;

               var url = $"https://api.open-meteo.com/v1/forecast" +
                         $"?latitude={latitude}&longitude={longitude}" +
                         $"&daily=temperature_2m_max,temperature_2m_min,precipitation_sum,precipitation_probability_max,weather_code" +
                         $"&current=temperature_2m,relative_humidity_2m,apparent_temperature,precipitation,weather_code,wind_speed_10m" +
                         $"&temperature_unit=fahrenheit&wind_speed_unit=mph&precipitation_unit=inch" +
                         $"&forecast_days={days}&timezone=auto";

               try
               {
                   var httpClient = _httpClientFactory.CreateClient();
                   var response = await httpClient.GetAsync(url);
                   response.EnsureSuccessStatusCode();
                   
                   var content = await response.Content.ReadAsStringAsync();
                   var data = JsonDocument.Parse(content);
                   
                   // Extract daily forecast data
                   var dailyElement = data.RootElement.GetProperty("daily");
                   var times = dailyElement.GetProperty("time").EnumerateArray().ToArray();
                   var maxTemps = dailyElement.GetProperty("temperature_2m_max").EnumerateArray().ToArray();
                   var minTemps = dailyElement.GetProperty("temperature_2m_min").EnumerateArray().ToArray();
                   var precipSums = dailyElement.GetProperty("precipitation_sum").EnumerateArray().ToArray();
                   var precipProbs = dailyElement.GetProperty("precipitation_probability_max").EnumerateArray().ToArray();
                   var weatherCodes = dailyElement.GetProperty("weather_code").EnumerateArray().ToArray();
                   
                   // Build a readable forecast for each day
                   var forecasts = new List<object>();
                   for (int i = 0; i < times.Length; i++)
                   {
                       // Convert date string to DateTime object for day name
                       var dateStr = times[i].GetString();
                       var dateObj = DateTime.Parse(dateStr!);
                       var dayName = dateObj.ToString("dddd, MMMM dd", CultureInfo.InvariantCulture);
                       
                       var weatherDesc = GetWeatherDescription(weatherCodes[i].GetInt32());
                       
                       var forecast = new
                       {
                           date = dateStr,
                           day = dayName,
                           high_temp = $"{maxTemps[i]}°F",
                           low_temp = $"{minTemps[i]}°F", 
                           precipitation = $"{precipSums[i]} inches",
                           precipitation_probability = $"{precipProbs[i]}%",
                           conditions = weatherDesc
                       };
                       
                       forecasts.Add(forecast);
                   }
                   
                   var result = new
                   {
                       location_coords = $"{latitude}, {longitude}",
                       forecast_days = forecasts.Count,
                       forecasts
                   };
                   
                   // For more concise output in chat
                   return JsonSerializer.Serialize(result, new JsonSerializerOptions { WriteIndented = true });
               }
               catch (Exception ex)
               {
                   return $"Error fetching forecast weather: {ex.Message}";
               }
           }
           
           [KernelFunction("GetForecastWithPlugins")]
           [Description("Gets weather forecast for any location by coordinating with Time and Geocoding plugins.")]
           public async Task<string> GetForecastWithPluginsAsync(
               [Description("The kernel instance to use for calling other plugins")] Kernel kernel,
               [Description("The location name (city, address, etc.))")] string location,
               [Description("The day of the week to get forecast for, or number of days in future")] string daySpec = "0")
           {
               try
               {
                   // Step 1: Get current date from Time Plugin
                   var dateResult = await kernel.InvokeAsync("Time", "GetDate");
                   string? todayStr = dateResult.GetValue<string>();
                   if (todayStr == null)
                   {
                       return "Could not determine the current date.";
                   }
                   DateTime today = DateTime.Parse(todayStr);
                   
                   // Step 2: Calculate target day based on specification
                   int daysInFuture;
                   if (int.TryParse(daySpec, out daysInFuture))
                   {
                       // If daySpec is a number, use it directly
                   }
                   else if (Enum.TryParse<DayOfWeek>(daySpec, true, out var targetDay))
                   {
                       // Calculate days until the next occurrence of the target day
                       daysInFuture = ((int)targetDay - (int)today.DayOfWeek + 7) % 7;
                       if (daysInFuture == 0) daysInFuture = 7; // If today is the target day, get next week
                   }
                   else
                   {
                        return $"Invalid day specification: {daySpec}. Please provide a day name or number of days.";               
                   }
                   
                   // Step 3: Get location coordinates from Geocoding Plugin
                   var locationResult = await kernel.InvokeAsync("Geocoding", "GetLocation", new() { ["location"] = location });
                   string? locationJson = locationResult.GetValue<string>();
                   
                   if (locationJson == null)
                   {
                       return $"Could not get location data for: {location}";
                   }
                   
                   var locationData = JsonDocument.Parse(locationJson);
                   double latitude, longitude;
                   
                   try {
                       latitude = locationData.RootElement.GetProperty("latitude").GetDouble();
                       longitude = locationData.RootElement.GetProperty("longitude").GetDouble();
                   }
                   catch (Exception)
                   {
                       return $"Could not extract coordinates for location: {location}";
                   }
                   
                   // Passo 4: Obter previsão do tempo
                   return await GetWeatherForecastAsync(latitude, longitude, daysInFuture + 1);
               }
               catch (Exception ex)
               {
                   return $"Error coordinating weather forecast: {ex.Message}";
               }
           }

           private string GetWeatherDescription(int code)
           {
               var weatherCodes = new Dictionary<int, string>
               {
                    { 0, "Clear sky" },
                    { 1, "Mainly clear" }, { 2, "Partly cloudy" }, { 3, "Overcast" },
                    { 45, "Fog" }, { 48, "Depositing rime fog" },
                    { 51, "Light drizzle" }, { 53, "Moderate drizzle" }, { 55, "Dense drizzle" },
                    { 56, "Light freezing drizzle" }, { 57, "Dense freezing drizzle" },
                    { 61, "Slight rain" }, { 63, "Moderate rain" }, { 65, "Heavy rain" },
                    { 66, "Light freezing rain" }, { 67, "Heavy freezing rain" },
                    { 71, "Slight snow fall" }, { 73, "Moderate snow fall" }, { 75, "Heavy snow fall" },
                    { 77, "Snow grains" },
                    { 80, "Slight rain showers" }, { 81, "Moderate rain showers" }, { 82, "Violent rain showers" },
                    { 85, "Slight snow showers" }, { 86, "Heavy snow showers" },
                    { 95, "Thunderstorm" }, { 96, "Thunderstorm with slight hail" }, { 99, "Thunderstorm with heavy hail" }
               };
               
               return weatherCodes.TryGetValue(code, out var description) ? description : "Unknown";
           }
       }
   }
   ```

3. Salve o arquivo.

4. Navegue até o diretório `Dotnet>src>BlazorAI>Components>Pages` e abra o arquivo **Chat.razor.cs**.

   ![](./media/image_038.png)

5. Adicione o seguinte código na seção `// Challenge 03 - Add Time Plugin`, após o plugin de geocoding no arquivo:

   ```csharp
   var weatherPlugin = new WeatherPlugin(
       kernel.Services.GetRequiredService<IHttpClientFactory>());
   kernel.ImportPluginFromObject(weatherPlugin, "WeatherPlugin");
   ```

   ![](./media/image_071.png)

6. Caso encontre erros de indentação, use o código do seguinte URL:

   ```
   https://raw.githubusercontent.com/CloudLabsAI-Azure/ai-developer/refs/heads/prod/CodeBase/c%23/lab-03_weather.cs
   ```

7. Salve o arquivo.

8. Clique com o botão direito em `Dotnet>src>Aspire>Aspire.AppHost` no painel esquerdo e selecione **Open in Integrated Terminal**.

   ![](./media/image_040.png)

9. Use o comando a seguir para rodar o app:

   ```
   dotnet run
   ```

10. Abra uma nova aba no navegador e acesse o link para **blazor-aichat**, ou seja, **https://localhost:7118/**.

11. Envie o seguinte prompt:

    ```
    What is today's weather in San Francisco?
    ```

12. Você receberá uma resposta similar à mostrada abaixo:

    ![](./media/image_072.png)

    A IA seguirá o seguinte plano para responder a pergunta, embora possa executar em outra ordem ou conjunto diferente de funções:

    1️⃣ A IA deve solicitar ao Semantic Kernel que chame a função GetDate no plugin de Tempo para obter a data atual e calcular o número de dias até a próxima quinta-feira.

    2️⃣ Como a previsão do tempo exige Latitude e Longitude, a IA deve instruir o Semantic Kernel a chamar a função GetLocation no plugin de Geocoding para obter as coordenadas de San Francisco.

    3️⃣ Finalmente, a IA deve pedir ao Semantic Kernel para chamar a função GetWeatherForecast no plugin de Weather, passando a data/hora atual e as coordenadas para obter a previsão para a próxima quinta-feira (expressa como número de dias no futuro).

    Um diagrama de sequência simplificado entre o Semantic Kernel e a IA está mostrado abaixo:

    ![](./media/seq_diag.png)

</details>

## Revisão

Neste exercício, utilizamos **plugins do Semantic Kernel** para aprimorar as capacidades do LLM, estendendo a funcionalidade de um chatbot. Desenvolvemos e integramos um **plugin de tempo** e um **plugin de consulta do clima** para permitir respostas em tempo real e contextuais, além dos dados de treinamento do modelo. Além disso, construímos plugins em Python e utilizamos o **Auto Function Calling** para encadear esses plugins de forma integrada. Isso aprimorou nossa habilidade em construir soluções de IA extensíveis e inteligentes usando o Semantic Kernel.

Tarefas concluídas com sucesso para estender as **capacidades do LLM** usando **plugins do Semantic Kernel**:

- Desenvolvemos e integramos um **plugin de tempo** e um **plugin de consulta do clima** para respostas contextuais em tempo real.
- Utilizamos o **Semantic Kernel** para ampliar a funcionalidade do chatbot além dos dados de treinamento do modelo.
- Implementamos o **Auto Function Calling** para encadear múltiplos plugins de forma fluida.
- Construímos e implantamos **plugins baseados em Python** para ampliar as capacidades da IA.

## Vá para o próximo laboratório clicando na navegação.
