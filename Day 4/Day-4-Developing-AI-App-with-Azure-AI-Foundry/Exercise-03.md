# Exercise 3: Evaluation Flow Setup

## Lab Overview
In this lab, you will set up an automated evaluation pipeline using built-in evaluation metrics and configure manual evaluation for deeper insights. You will begin by leveraging built-in metrics such as accuracy, precision, recall, and F1-score to assess model performance automatically. Then, you will set up a manual evaluation process where human reviewers can provide qualitative feedback on model outputs. This hands-on exercise will help you understand the integration of automated and manual evaluation methods to improve model accuracy and reliability.

## Lab Objectives
In this lab, you will perform the following:
- Task 1: Setup Manual Evaluation
- Task 2: Setup Automated Evaluation with Built-in Evaluation Metrics

## Task 1: Setup Manual Evaluation

Set up manual evaluation by defining criteria, collecting human feedback, and analyzing model accuracy and biases to improve performance.

1. From the left navigation menu, under the **Protect and govern** section, select **Evaluation (1)**. On the **Assess and compare AI application performance** select **Manual evaluations (2)** tab. Select **+ New manual evaluation (3)**.

    ![](./media/evaluation-1a-1.png)

1. A new window opens with your previous **system message** already populated and your deployed model selected.

    ![](./media/d50.png)

1. In the **Manual evaluation result** section, you'll add five inputs for which you will review the output. Enter the following five questions as five separate inputs by selecting **+ Add Inputs**:

   `Can you provide a list of the top-rated budget hotels in Rome?`

   `I'm looking for a vegan-friendly restaurant in New York City. Can you help?`

   `Can you suggest a 7-day itinerary for a family vacation in Orlando, Florida?`

   `Can you help me plan a surprise honeymoon trip to the Maldives?`

   `Are there any guided tours available for the Great Wall of China?`

1. Select **Run** from the top bar to generate outputs for all questions you added as inputs.

    ![](./media/image-20.png)

1. You can now manually review the **Outputs** for each question by selecting the thumbs up or down icon at the bottom right of a response. Rate each response, ensuring you include at least one thumbs up and one thumbs down response in your ratings.

    ![](./media/d51.png)

    > **Note:** If you receive an error in any of the output while executing the run "exceeded token rate limit of your current AIService", then please rerun the failed ones after couple of minutes.

1. Select **Save results (1)** from the top bar. Enter **manual_evaluation_results (2)** as the name for the results, and select **Save (3)**.

    ![](./media/gpt-4-demo18.png)
   
1. Using the menu on the left, navigate to **Evaluations (1)**. Select the **Manual evaluations (2)** tab to find the manual evaluations you just saved **(3)**. Note that you can explore your previously created manual evaluations, continue where you left of, and save the updated evaluations.

    ![](./media/manual-1.png)

## Task 2: Setup Automated Evaluation with Built-in Evaluation Metrics

In this task, you will configure automated evaluation using built-in metrics to measure model performance quickly and accurately.

1. From the left navigation menu, under the **Protect and govern** section, select **Evaluation (1)**. On the **Assess and compare AI application performance** select **Automated evaluations (2)** tab. Select **+ New evaluation (3)**.

    ![](./media/pg20ex3t1.png)

1. On the **+ New evaluation** pane, select **Ecaluate an existing query-response dataset (1)** and click on **Next (2)**.

    ![](./media/evsnsdn2-1.png)

1. Open a new tab and paste the new link +++https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-studio/main/data/travel-qa.jsonl+++ JSONL file. Press **Ctrl A** and **Ctrl C** to select the contents of of the file.
  
    - Search for **Visual Studio Code (1)** in the Windows search bar of the vm and select **Visual Studio Code (2)**.

    ![](./media/vsc.png)

    - From the **File (1)** menu, select **New Text File (2)**, 

    ![](./media/d8.png)

    - **Paste the copied code**.

    - Navigate to **File (1)** and click on **Save as (2)**.    

    ![](./media/d9.png)    

    > **Note:** This error can be disregarded as the **"Save as type"** will be chosen in the next step.

    - Click on **Desktop (1)**, Enter the File name as **Sample (1)** select **JSON Lines (3)** for Save as type and then click on **Save (4)**.

    ![](./media/d10.png)

    > **Note:** Make sure to select the correct file type. The AI Foundry portal only accepts files in the **JSON Lines** format. If any other file type is selected, the file will not be accepted.

1. Navigate back to **Azure AI foundry**, where you were **creating a new evaluation**.
   
    - **Configure test data**: select **Upload new dataset**
  
    ![](./media/uplddata.png)

    - Navigate to **Desktop (1)**, select the file **Sample.jsonl** **(2)** and click on **Open** **(3)**.

    ![](./media/dex30.png)   

    - Select **Next**. 

    - **Configure Evaluators**: Click on **+ Add** and select **Likert-scale evaluator**.

    ![](./media/addecallas.png)
      
    ![](./media/linksss.png)
      
    - Provide the name as **Coherence (1)** for Criteria Name, **Coherence (2)** for presets, scroll down and select **{{item.query}}** **(3)** for query, select **${item.response}** **(4)** for Response and click on **Add (5)**.

    ![](./media/pg20t2-1.png)

    - **Configure Evaluators**: Click on **+ Add** and select **Likert-scale evaluator**
	
    ![](./media/addecallas-1.png)
      
    ![](./media/linksss.png)

    - Provide the name as **Fluency (1)** for Criteria Name, **Fluency (2)** for presets, scroll down and select **{{item.query}}** **(3)** for query, select **${item.response}** **(4)** for Response and click on **Add (5)**.

    ![](./media/pg20t2-2.png)

    - Once added, click on Next.

    ![](./media/addededddd-1.png)

   - Now, update model evaluation name to  **Modelevaluation-<inject key="DeploymentID" enableCopy="false"/> (1)** and click on **Submit (2)**.
     
    ![](./media/submiteeddd-1.png)
        
1. Wait until the evaluation status changes to **Completed**. If the status shows **Queued** or **Running**, you may need to refresh the page to see the latest update.

    ![](./media/refreshhhh-1.png)

1. Select **Evaluation (1)** from the left navigation menu, and under **Automated Evaluation (2),** choose the newly created evaluation run **(3)**.

    ![](./media/dex34-1.png)

1. Under the **Report** tab, scroll down to explore the **Metric dashboard**.

    ![](./media/metricdatass.png)

1. Navigate to **Data (1)** tab from the top menu to view the **Detailed metrics results (2)**.    

    ![](./media/passseddd.png)

## Review
In this lab you have completed the following tasks:
- Set Up Manual Evaluation
- Setup Automated Evaluation with Built-in Evaluation Metrics

### You have successfully completed the lab. Click on **Next >>** to procced with next exercise.
