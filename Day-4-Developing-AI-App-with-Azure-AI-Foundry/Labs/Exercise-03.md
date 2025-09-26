# Exercício 3: Configuração do Fluxo de Avaliação

## Visão Geral do Laboratório

Neste laboratório, você configurará um pipeline de avaliação automatizado usando métricas de avaliação integradas e também configurará uma avaliação manual para obter insights mais profundos. Você começará aproveitando métricas integradas como acurácia, precisão, recall e F1-score para avaliar automaticamente o desempenho do modelo. Em seguida, você configurará um processo de avaliação manual, onde revisores humanos poderão fornecer feedback qualitativo sobre as saídas do modelo. Este exercício prático ajudará você a entender a integração de métodos de avaliação automatizados e manuais para melhorar a precisão e a confiabilidade do modelo.

## Objetivos do Laboratório

Neste laboratório, você realizará as seguintes tarefas:

- Tarefa 1: Configurar Avaliação Manual  
- Tarefa 2: Configurar Avaliação Automatizada com Métricas de Avaliação Integradas

## Tarefa 1: Configurar Avaliação Manual

Configure a avaliação manual definindo critérios, coletando feedback humano e analisando a precisão e os vieses do modelo para melhorar o desempenho.

1. No menu de navegação à esquerda, sob a seção **Acessar e Melhorar**, selecione **Avaliação (1)**. Na tela **Avaliar e comparar desempenho de aplicações de IA**, selecione a aba **Avaliações manuais (2)**. Clique em **+ Nova avaliação manual (3)**.

   ![](../../pt-media/day-4/ex-3/01.png)

2. Uma nova janela será aberta com sua **mensagem de sistema** anterior já preenchida e o modelo implantado selecionado.

   ![](../../pt-media/day-4/ex-3/02.png)

   
3. Na seção **Manual evaluation result**, adicione cinco entradas para revisar as saídas. Insira as seguintes perguntas clicando em **+ Add Inputs**:


   `Você pode fornecer uma lista dos hotéis econômicos mais bem avaliados em Roma?`

   `Estou procurando um restaurante vegano em Nova York. Você pode ajudar?`

   `Pode sugerir um roteiro de 7 dias para férias em família em Orlando, Flórida?`

   `Pode me ajudar a planejar uma viagem surpresa de lua de mel para as Maldivas?`

   `Existem passeios guiados disponíveis para a Grande Muralha da China?`


4. Selecione **Executar** na barra superior para gerar as saídas para todas as perguntas.

   ![](../../pt-media/day-4/ex-3/03.png)

5. Revise manualmente as **saídas** de cada pergunta selecionando o ícone de polegar para cima ou para baixo. Avalie cada resposta, garantindo pelo menos uma avaliação positiva e uma negativa.

   ![](../../pt-media/day-4/ex-3/04.png)

> **Nota:** Se aparecer o erro "exceeded token rate limit of your current AIService", tente novamente após alguns minutos.

6. Selecione **Salvar resultados (1)** na barra superior. Insira **manual_evaluation_results (2)** como nome dos resultados e clique em **Salvar (3)**.

   ![](../../pt-media/day-4/ex-3/05.png)

7. No menu à esquerda, vá para **Evaluations (1)**, selecione a aba **Manual evaluations (2)** e encontre a avaliação salva **(3)**. É possível continuar avaliações anteriores e salvar alterações.

   ![](../../pt-media/day-4/ex-3/06.png)

## Tarefa 2: Configurar Avaliação Automatizada com Métricas de Avaliação Integradas

1. No menu à esquerda, sob a seção **Protect and govern**, selecione *Avaliação (1)** Vá para a aba **Avaliações automatizadas (2)**. e clique em  **Criar nova avaliação (3)**.

   ![](../../pt-media/day-4/ex-3/07.png)

2. No painel **Create a new evaluation**, selecione **Evaluate an existing query-response dataset (1)**.

   ![](../../pt-media/day-4/ex-3/08.png)

3. Abra a URL a seguir em uma nova aba:  
`https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-studio/main/data/travel-qa.jsonl`  
Pressione **Ctrl + A** e **Ctrl + C** para copiar tudo.

   ![](../../pt-media/day-4/ex-3/09.png)

- Abra o **Visual Studio Code**, vá em **File > New Text File**, e cole o conteúdo.
- Em seguida, vá em **File > Save As**.
- Salve como `Sample.jsonl` na área de trabalho, e selecione o tipo **JSON Lines**.

   ![](../../pt-media/day-4/ex-3/10.png)

   ![](../../pt-media/day-4/ex-3/11.png)

> **Nota:** O portal só aceita arquivos no formato JSON Lines.

4. Volte para o portal **Azure AI Foundry**.

   - Em **Configure test data**, clique em **Upload new dataset**.
   - Selecione `Sample.jsonl` da área de trabalho e clique em **Open**.
   - Clique em **Next**.

      ![](../../pt-media/day-4/ex-3/12.png)


5. Em **Configure Evaluators**, clique em **+ Add**, selecione **Likert-scale evaluator**, escolha **Coherence**, insira:

   - Query: `{{item.query}}`
   - Response: `${item.response}`
   - Clique em **Add**.

      ![](../../pt-media/day-4/ex-3/19.png)

      ![](../../pt-media/day-4/ex-3/20.png)

      ![](../../pt-media/day-4/ex-3/21.png)

6. Adicione outro avaliador:

   - Clique em **+ Add**, selecione **Likert-scale evaluator**
   - Escolha **Fluency**
   - Query: `{{item.query}}`
   - Response: `${item.response}`
   - Clique em **Add**

     ![](../../pt-media/day-4/ex-3/22.png)

     ![](../../pt-media/day-4/ex-3/23.png)

     ![](../../pt-media/day-4/ex-3/24.png)

7. Clique em **Next**, renomeie a avaliação para  
`Modelevaluation-{suffix}`  
e clique em **Submit**.

8. Aguarde até que o status seja **Completed**. Se necessário, atualize a página.

9. Vá em **avaliação > Avaliações automatizadas**, e selecione a execução recém-criada.

   ![](../../pt-media/day-4/ex-3/27.png)

10. Na aba **Report**, explore o **painel de métricas**.

    ![](../../pt-media/day-4/ex-3/28.png)

11. Vá para a aba **Data** para ver os **resultados detalhados das métricas**.

    ![](../../pt-media/day-4/ex-3/29.png)

## Revisão

Neste laboratório, você concluiu as seguintes tarefas:

- Configurou Avaliação Manual  
- Configurou Avaliação Automatizada com Métricas Integradas

### Você concluiu com sucesso o laboratório. Clique em **Next >>** para prosseguir para o próximo exercício.

