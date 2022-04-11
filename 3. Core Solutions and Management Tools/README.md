# Core Solutions and Management Tools
## Contents Page
  - [Azure IoT Services](#azure-iot-services)
    - [Identify the Product Options](#identify-the-product-options)
    - [Decision Criteria](#decision-criteria)
  - [AI Services](#ai-services)
    - [Identify the Product Options](#identify-the-product-options-1)
    - [Decision Criteria](#decision-criteria-1)
  - [Azure Serverless Technology](#azure-serverless-technology)
    - [Identify the Product Options](#identify-the-product-options-2)
    - [Decision Criteria](#decision-criteria-2)
  - [Microsoft Tools and Services](#microsoft-tools-and-services)
    - [Understand your Product Options](#understand-your-product-options)
    - [Decision Criteria](#decision-criteria-3)
  - [Azure Management and Configuration Tools](#azure-management-and-configuration-tools)
    - [Identify the Product Options](#identify-the-product-options-3)
    - [Decision Criteria](#decision-criteria-4)
  - [Monitoring Services](#monitoring-services)
    - [Identify the Product Options](#identify-the-product-options-4)
    - [Decision Criteria](#decision-criteria-5)
## Azure IoT Services
### Identify the Product Options
- IoT enables devices to gather and then relay information for data analysis, over the internet
- Smart devices are equipped with sensors that collect data, examples are:
  - Environmental sensors that capture temperature and humidity levels    
  - Barcode, QR code, or optical character recognition (OCR) scanners
  - Accelerometer and tilt sensors
- Devices could send their sensor readings to a specific endpoint in Azure via a message or Azure IoT services could send software updates the each device
- Azure IoT Hub: send and recieve messages
  - A managed service, hosted in the cloud and that acts as a central message hub for bi-directional communication between your IoT application and the devices
  - Used to build IoT solutions with reliable and secure communications between millions of IoT devices
  - IoT Hub monitoring helps you maintain the health of your solution by tracking events
- Azure IoT Central: provides monitoring (dashboard) features
  - Built on top of IoT Hub by adding a dashboard that allows you to connect, monitor, and manage your IoT devices
  - You can set up alerts that send notifications when a specific device needs maintenance (software updates remotely)
  - Developers still need to create code to run on the devices, and that code must match the device template specification
- Azure Sphere: security is critical
  - Creates an end-to-end, highly secure IoT solution for customers that encompasses everything (Hardware, OS, Messages)
  - The first part is the Azure Sphere micro-controller unit (MCU), which is responsible for processing the OS and signals from attached sensors
  - The second part is a customized Linux OS that handles communication with the security service and can run the vendor's software
  - The third part is Azure Sphere Security Service (AS3), that checks to ensure that the device hasn't been tampered with
### Decision Criteria
- Is it critical to ensure that the device is not compromised? Azure Sphere (ATM vs Washing Machine)
- Do I need a dashboard for reporting and management? Azure IoT Central

## AI Services
### Identify the Product Options
- AI is a broad classification of computing that allows a software system to perceive its environment and take action that maximizes its chance of successfully achieving its goals
- The goal of AI is to create a software system that adapts, or learns something on its own without being explicitly programmed to do it
  - Deep Learning: system modeled on the neural network of the human mind, enabling it to discover, learn, and grow through experience
  - Machine Learning: data science technique that uses existing data to train a model, test it, and then apply the model to new data to forecast future behaviors, outcomes, and trends
- Forecasts or predictions from machine learning can make apps and devices smarter
- Azure Machine Learning: a platform for making predictions
  - It consists of tools and services to connect to data that trains and tests models to find one that most accurately predict future results
  - With Azure Machine Learning, you can:
    - Create a process that defines how to obtain data, handle missing/bad data, split the data into training/test sets, and deliver the data to the training process
    - Train and evaluate predictive models using tools and programming languages familiar to data scientists
    - Create pipelines that define where and when to run the compute-intensive experiments that are required to score the algorithms (training data vs test data)
    - Deploy the best-performing algorithm as an API to an endpoint so it can be used in real time
  - Choose Azure Machine Learning when your data scientists need complete control over the design and training of an algorithm using your own data
- Azure Cognitive Services: prebuilt machine learning models
  - You don't need special machine learning or data science knowledge to use these services, just access the APIs and write a few lines of code
  - Provides pretrained models so that you can bring in your live data to get predictions on
  - Azure Cognitive Services can be divided into the following categories:
    - Language: allow your apps to process natural language with prebuilt scripts, evaluate sentiment, and learn how to recognize what users want
    - Speech: convert speech into text and text into natural-sounding speech, translate from one language to another, and enable speaker verification and recognition
    - Vision: add recognition and identification capabilities when you're analyzing pictures, videos, and other visual content
    - Decision: add personalized recommendations for each user that automatically improve as they're used, moderate content, and detect abnormalities in you data
  - Use Azure Cognitive Services to solve general problems, such as analyzing text for emotional sentiment or analyzing images to recognize objects or faces
- Azure Bot Service: bot that understands and replies to questions
  - Azure Bot Service creates a virtual agent that can intelligently communicate with humans
  - Behind the scenes, the bot uses other Azure services, such as Azure Cognitive Services
  - Users converse with a bot by using text, interactive cards, and speech
  - A bot interaction can be a quick question and answer, or it can be a sophisticated conversation that intelligently provides access to services
### Decision Criteria
- Are you building a virtual agent that interfaces with humans via natural language? Azure Bot Service
- Do you need a service that can understand images, video, or audio, or that can translate text into a different language? Azure Cognitive Service
- Do you need to predict user behavior or provide users with personalized recommendations in your app? Azure Cognitive Service (Personalizer Service)
- Will your app predict future outcomes based on private historical data? Azure Machine Learning
- Do you need to build a model by using your own data or perform a different task than those listed above? Azure Machine Learning

## Azure Serverless Technology
### Identify the Product Options
- Serverless computing is a term used to describe an execution environment that's set up and managed for you by Azure
- Azure Functions: runs your code when it's triggered
  - You can host a single method by using a programming language in the cloud that runs in response to an event (REST request, timer, message from another Azure service)
  - Azure Functions scales automatically, and charges accrue only when a function is triggered. A solid choice when demand is variable
  - An Azure function is a stateless environment, it behaves as if it's restarted every time it responds to an event
  - If state is required, the function can be connected to an Azure storage account
  - Azure Functions can perform orchestration tasks by using Durable Functions, which allow developers to chain functions together while maintaining state (Stateful)
  - It is ideal when you're concerned only with the code that's running your service and not the underlying platform or infrastructure
- Azure Logic Apps: execute logic triggered by event, without writing any code
  - Logic Apps is a low-code/no-code development platform hosted as a cloud service
  - Azure Logic Apps is designed in a web-based designer and can execute logic that's triggered by Azure services without writing any code
  - You build an app by linking triggers (timer) to actions with connectors
  - Actions include working with variables, decision statements and loops, and tasks that parse and modify data (task that can execute)
- Differences between Functions and Logic Apps:
  - Azure Functions is a serverless compute service, and Azure Logic Apps is intended to be a serverless orchestration service
  - Although you can use Azure Functions to orchestrate a business process that involves various connections
  - Azure Functions pricing is based on the number of executions and the running time of each execution
  - Logic Apps pricing is based on the number of executions and the type of connectors that it utilizes
### Decision Criteria
- Do you need to perform an orchestration across well-known APIs? Azure Logic Apps
- Do you need to execute custom algorithms or perform specialized data parsing and data lookups? Azure Functions
- Do you have existing automated tasks written in an imperative programming language? Azure Functions
- Do you prefer a visual workflow (declarative) or writing code (imperative)? Azure Logic Apps or Azure Functions

## Microsoft Tools and Services
### Understand your Product Options
- DevOps is a concept that combines philosophies and practices to facilitate technical teams as they work toward common goals
- Tooling automates and enforces most of the practices and processes, making it both difficult and unnecessary to work around
- Microsoft tools enable source-code management, continuous integration and continuous delivery (CI/CD), and automate the creation of testing environments
- Azure DevOps Services: suite of services that address every stage of the SDLC
  - Azure Repos: a centralized source-code repository where professionals can publish their code for review and collaboration
  - Azure Boards: an agile project management suite that includes Kanban boards, reporting, and tracking ideas
  - Azure Pipelines: a CI/CD pipeline automation tool
  - Azure Artifacts: a repo for hosting artifacts, such as compiled source code, which can be fed into testing or deployment pipeline steps
  - Azure Test Plans: an automated test tool that can be used in a CI/CD pipeline to ensure quality before a software release
- GitHub and GitHub Actions: used for open-source software
  - Git is a decentralized source-code management tool, and GitHub is a hosted version of Git that serves as the primary remote
  - Includes tools that enable developers to perform code reviews of the source code before it can be merged into the main branch
  - It facilitates project management, including Kanban boards
  - It features CI/CD pipeline automation tooling
  - It includes a wiki for collaborative documentation and can be run on-prem or from the cloud
  - GitHub Actions enables workflow automation with triggers for many lifecycle events, such as automating a CI/CD toolchain
  - A toolchain is a combination of software tools that aid in the delivery, development, and management of software applications
  - The output of one tool in the toolchain is the input of the next tool in the toolchain
- Azure DevTest Labs: manages VMs for testing
  - Azure DevTest Labs provides an automated means of building, setting up, and tearing down VMs that contain your software builds
  - Anything you can deploy in Azure via an ARM template can be provisioned through DevTest Labs
  - After the testing is complete, DevTest Labs can shut down and deprovision the VM, which saves money
### Decision Criteria
- Do you need to automate and manage test-lab creation? Azure DevTest Labs
- Are you building open-source software? GitHub and GitHub Actions
- What level of granularity do you need for permissions? Azure DevOps (granular permissions)
- How sophisticated does your project management and reporting need to be? Azure DevOps
- How tightly do you need to integrate with third-party tools? Azure DevOps (Azure Pipelines)/GitHub (GitHub Actions)

## Azure Management and Configuration Tools
### Identify the Product Options
- Visual tools provide full, visually friendly access to all the functionality of Azure
- To quickly set up and configure Azure resources, a code-based tool is usually the better choice
- They can be saved into files and used repeatedly as needed
- This approach to managing hardware and cloud resources is referred to as infrastructure as code:
  - Imperative Code: details each individual step that should be performed to achieve a desired outcome
  - Declarative Code: details only a desired outcome, and it allows an interpreter to decide how to best achieve that outcome (more robust)
- Azure Portal: a web-based user interface
  - Using the Azure portal you can access virtually every feature of Azure
  - The Azure portal provides a friendly, GUI to view all the services you're using, create new services, configure your services, and view reports
- Azure Mobile App: provides iOS/Android access to your Azure resource
  - Can be used to monitor the health and status of your Azure resources
  - Check for alerts, quickly diagnose and fix issues, and restart a web app or VM
  - Run the Azure CLI or Azure PowerShell commands to manage your Azure resources
- Azure PowerShell: shell to execute commands (cmdlets)
  - The commands executed call the Azure REST API to perform every possible management task in Azure
  - Cmdlets can be executed independently or combined into a script file and executed together to orchestrate:
    - The routine setup, teardown, and maintenance of a single resource or multiple connected resources
    - The deployment of an entire infrastructure, which might contain dozens or hundreds of resources, from imperative code
  - Capturing the commands in a script makes the process repeatable and automatable
- Azure CLI: can execute commands in Bash
  - The commands call the Azure REST API to perform every possible management task in Azure
  - You can run the commands independently or combined into a script and executed together for the routine setup, teardown, and maintenance of a single resource or an entire environment
  - In many respects, the Azure CLI is almost identical to Azure PowerShell in what you can do with it
  - The primary difference is the syntax you use
- Azure Resource Manager (ARM) Templates: describe the resources you want to use (declarative)
  - Using ARM, you can describe the resources you want to use in a declarative JSON format
  - The entire ARM template is verified before any code is executed to ensure that the resources will be created and connected correctly
  - Ultimately, the developer only needs to define the desired state and configuration of each resource in the ARM template, and the template does the rest
  - Templates can even execute PowerShell and Bash scripts before or after the resource has been set up
### Decision Criteria
- Do you need to perform one-off management, administrative, or reporting actions? Azure PowerShell/Azure CLI/Azure Portal/Azure Mobile App
- Do you need a way to repeatedly set up one or more resources and ensure that all the dependencies are created in the proper order? ARM Templates
- When you're scripting, do you come from a Windows administration or Linux administration background? Azure PowerShell or Azure CLI

## Monitoring Services
### Identify the Product Options
- There are several solutions that help you react quickly to outages, research intermittent issues, optimize your usage, and be proactive in handling future planned downtime
- Azure Advisor: makes recommendations to cut costs
  - Azure Advisor evaluates your Azure resources and makes recommendations to help improve reliability, security, and performance, and reduce costs
  - The recommendation service includes suggested actions you can take right away, postpone, or dismiss
  - The recommendations are available via the Azure portal and the API, and you can set up notifications to alert you to new recommendations
  - The recommendations are divided into five categories:
    - Reliability: used to ensure and improve the continuity of your business-critical applications
    - Security: used to detect threats and vulnerabilities that might lead to security breaches
    - Performance: used to improve the speed of your applications
    - Cost: used to optimize and reduce your overall Azure spending
    - Operational Excellence: used to help you achieve process and workflow efficiency, resource manageability, and deployment best practices
- Azure Monitor: tracks Azure services performance
  - Azure Monitor is a platform for collecting, analyzing, visualizing, and potentially taking action based on the metric and logging data from your entire Azure and on-premises environment
  - You can use the data to help you react to critical events in real time, through alerts delivered to teams via SMS, email, and so on
  - You can use thresholds to trigger autoscaling functionality to scale up or down to meet the demand
  - Azure Application Insights, a service for sending telemetry information from application source code to Azure, uses Azure Monitor under the hood
  - With Application Insights, your developers can use the data-analysis platform in Azure Monitor to gain deep insights into an application's operations and diagnose errors before they are reported
- Azure Service Health: monitors the status of Azure services
  - Azure Service Health provides a personalized view of the health of the Azure services, regions, and resources you rely on
  - Azure Service Health displays both major and smaller, localized issues that affect you
  - You can set up alerts that help you triage outages and planned maintenance
  - After an outage, Service Health provides official incident reports, called root cause analyses (RCAs), which you can share with stakeholders
  - Service Health helps you keep an eye on several event types:
    - Service Issues: problems in Azure, such as outages, that affect you right now
    - Planned Maintenance: scheduled event can affect your availability
    - Health Advisories: issues that require you to act to avoid service interruption
### Decision Criteria
- Do you need to analyze how you're using Azure to reduce costs, improve resilience, or harden your security? Azure Advisor
- Do you want to monitor Azure services or your usage of Azure? Azure Service Health/Azure Monitor
- Do you want to measure custom events alongside other usage metrics? Azure Monitor
- Do you need to set up alerts for outages or when autoscaling is about to deploy new instances? Azure Monitor