# agntcAIaccdepth
Agentic AI Accelerator Workshop
This hands-on workshop series is designed to help you deepen your skills in AI-driven development, automation, and building intelligent applications using Microsoft Copilot Studio and Azure AI services. Each day offers practical, guided experiences—from designing AI agents to deploying full-scale AI solutions. By the end of this workshop, you'll walk away with hands-on expertise in creating scalable, intelligent solutions that boost employee engagement, streamline business operations, and enhance customer experiences.

## Objectives
- Learn to design and deploy AI agents with Microsoft Copilot Studio and Azure AI services.
- Gain hands-on experience in multi-agent orchestration using the Azure AI Agent Service SDK and Semantic Kernel.
- Build custom Retrieval-Augmented Generation (RAG) applications with Azure AI Foundry and integrate Semantic Kernel plugins.
- Evaluate, fine-tune, and deploy AI models using Prompt Flow for real-world use cases.
- Construct intelligent escalation systems using conversational interfaces, event-driven architecture, and AI-powered workflows.

## Day-by-Day Breakdown:

### Day 1: Build Agents with Copilot Studio
This hands-on lab offers you how to use Microsoft 365 Copilot and Copilot Studio to enhance the employee experience through AI-driven creativity and automation. You'll create visual content, streamline employee transitions, automate onboarding, and implement recognition systems to boost engagement and productivity.

### Day 2: Azure AI Agents
This hands-on lab offers a comprehensive introduction to building AI agents using the Azure AI Agent Service SDK and Semantic Kernel. You will begin by creating AI agents with the Azure AI Agent Service and leveraging Semantic Kernel to orchestrate them in a multi-agent system. Throughout the lab, you will explore techniques for agent collaboration, automation, and task execution. By the end of this experience, you will have hands-on expertise in designing, deploying, and managing AI agents to build intelligent, scalable, and efficient AI-driven applications.

### Day 3: Developing a Custom RAG App Using Azure AI Foundry and Explore Semantic Kernel
This hands-on lab offers a practical introduction to building a custom Retrieval-Augmented Generation (RAG) application using the Azure AI Foundry SDK. You'll start by provisioning the necessary Azure resources and configuring the AI Foundry environment. From there, you will implement an end-to-end RAG pipeline that indexes and retrieves relevant data to enrich AI-generated responses.
As part of the lab, you’ll also explore the integration of Semantic Kernel to create dynamic, prompt-based interactions and incorporate useful plugins—such as time and weather utilities—to extend your chatbot’s functionality.
By the end of the session, you will have hands-on experience in building a scalable RAG solution that harnesses the power of Azure AI and the Semantic Kernel plugin ecosystem for advanced knowledge retrieval and intelligent response generation.

### Day 4: Developing AI Applications with Azure AI Foundry
This hands-on lab is intended for AI developers, data scientists, AI Enthusiasts, Cloud Engineers, AI Engineers, aiming to enhance their skills in model evaluation and fine-tuning using Azure AI Foundry Prompt Flow. Participants will gain practical experience in developing custom AI models, evaluating their performance, and refining them for better results. The lab also addresses the integration of chat flows and essential tools, ensuring responsible AI practices through content safety measures.

<!-- ### Day 5: Smart Escalation System for Conversational Support
​In this challenge, you'll work with a Chainlit-based application that utilizes Dapr's publish-subscribe messaging to manage customer service escalations through AI agents. The solution integrates Azure services such as OpenAI, Cosmos DB, and Service Bus to provide intelligent and scalable interactions. When AI agents cannot resolve user inquiries, the system escalates the issue to a human agent via Logic Apps, which sends an approval email for further action. This hands-on experience demonstrates how conversational interfaces, event-driven architecture, and AI-powered workflows can be combined to enhance customer support.  -->

## Getting Started with the lab

Welcome to your Azure Agentic AI Workshop, Let's begin by making the most of this experience:

## Accessing Your Lab Environment

Once you're ready to dive in, your virtual machine and **Guide** will be right at your fingertips within your web browser.

![Access Your VM and Lab Guide](Day-2-Azure-AI-Agents/media/LabVMEng.png)

## Lab Guide Zoom In/Zoom Out

To adjust the zoom level for the environment page, click the **A↕ : 100%** icon located next to the timer in the lab environment.

![](Day-2-Azure-AI-Agents/media/agg2.png)

## Virtual Machine & Lab Guide

Your virtual machine is your workhorse throughout the workshop. The lab guide is your roadmap to success.

## Exploring Your Lab Resources

To get a better understanding of your lab resources and credentials, navigate to the **Environment** tab.

![Explore Lab Resources](Day-2-Azure-AI-Agents/media/agg3.png)

## Utilizing the Split Window Feature

For convenience, you can open the lab guide in a separate window by selecting the **Split Window** button from the Top right corner.

![Use the Split Window Feature](Day-2-Azure-AI-Agents/media/agg4.png)

## Managing Your Virtual Machine

Feel free to **start, stop, or restart (2)** your virtual machine as needed from the **Resources (1)** tab. Your experience is in your hands!

![Manage Your Virtual Machine](Day-2-Azure-AI-Agents/media/agg5.png)

<!-- ## Lab Duration Extension

1. To extend the duration of the lab, kindly click the **Hourglass** icon in the top right corner of the lab environment.

    ![Manage Your Virtual Machine](Day-2-Azure-AI-Agents/media/gext.png)

    >**Note:** You will get the **Hourglass** icon when 10 minutes are remaining in the lab.

2. Click **OK** to extend your lab duration.

   ![Manage Your Virtual Machine](Day-2-Azure-AI-Agents/media/gext2.png)

3. If you have not extended the duration prior to when the lab is about to end, a pop-up will appear, giving you the option to extend. Click **OK** to proceed. -->

> **Note:** Please ensure the script continues to run and is not terminated after accessing the environment.

## Let's Get Started with Azure Portal

1. On your virtual machine, click on the Azure Portal icon.
2. You'll see the **Sign into Microsoft Azure** tab. Here, enter your credentials:

   - **Email/Username:** <inject key="AzureAdUserEmail"></inject>

     ![Enter Your Username](Day-2-Azure-AI-Agents/media/gt-5.png)

3. Next, provide your password:

   - **Password:** <inject key="AzureAdUserPassword"></inject>

     ![Enter Your Password](Day-2-Azure-AI-Agents/media/gt-4.png)

4. If **Action required** pop-up window appears, click on **Ask later**.
5. If prompted to **stay signed in**, you can click **No**.
6. If a **Welcome to Microsoft Azure** pop-up window appears, simply click **"Cancel"** to skip the tour.

## Steps to Proceed with MFA Setup if "Ask Later" Option is Not Visible

1. At the **"More information required"** prompt, select **Next**.

1. On the **"Keep your account secure"** page, select **Next** twice.

1. **Note:** If you don’t have the Microsoft Authenticator app installed on your mobile device:

   - Open **Google Play Store** (Android) or **App Store** (iOS).
   - Search for **Microsoft Authenticator** and tap **Install**.
   - Open the **Microsoft Authenticator** app, select **Add account**, then choose **Work or school account**.

1. A **QR code** will be displayed on your computer screen.

1. In the Authenticator app, select **Scan a QR code** and scan the code displayed on your screen.

1. After scanning, click **Next** to proceed.

1. On your phone, enter the number shown on your computer screen in the Authenticator app and select **Next**.
1. If prompted to stay signed in, you can click "No."

1. If a **Welcome to Microsoft Azure** pop-up window appears, simply click "Maybe Later" to skip the tour.

## Support Contact

The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels tailored specifically for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.

Learner Support Contacts:

- Email Support: [cloudlabs-support@spektrasystems.com](mailto:cloudlabs-support@spektrasystems.com)
- Live Chat Support: https://cloudlabs.ai/labs-support

Click **Next** from the bottom right corner to embark on your Lab journey!

![Start Your Azure Journey](Day-2-Azure-AI-Agents/media/agg6.png)

Now you're all set to explore the powerful world of technology. Feel free to reach out if you have any questions along the way. Enjoy your workshop!