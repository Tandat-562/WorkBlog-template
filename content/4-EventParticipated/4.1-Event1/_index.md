```markdown
---
title: "AWS First Cloud AI Journey Community Day 2026"
date: 2026-05-23
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

## Event Information

| Category | Details |
| --- | --- |
| Event name | AWS First Cloud AI Journey Community Day 2026 |
| Date | May 23, 2026 |
| Venue | 26th Floor, Bitexco Financial Tower, 02 Hai Trieu Street, Sai Gon Ward, Ho Chi Minh City |
| My role at the event | Attendee |
| Brief description of the main content and activities | The event was organized to share practical knowledge and experience related to AWS, cloud computing, and artificial intelligence. It included presentations from various speakers covering topics such as AI, Amazon Q, Amazon CloudFront, large language models, multi-agent systems, and product development during a hackathon. |
| Outcomes and value gained | By attending the event, I gained a more practical understanding of how AI and cloud technologies are applied in business environments. I also expanded my knowledge of Amazon Bedrock, Amazon Q, CloudFront, LLMs, multi-agent systems, teamwork, and the process of developing real-world technology products. |
| Significance of participating in the event | Participating in this event demonstrated my proactive attitude toward learning during my internship. It also allowed me to broaden my professional knowledge, strengthen my soft skills, and gain practical insights from the technology community. |

---

## Event Overview

AWS Vietnam Community Day is a technology community event focusing on sharing new knowledge and practical experience related to AWS, cloud computing, and artificial intelligence. The event brought together several speakers who presented a wide range of topics.

Each presentation addressed a different aspect of modern technology, including context engineering for AI, the use of Amazon Q in enterprises, the capabilities of Amazon CloudFront, the non-deterministic behavior of large language models, and the implementation of multi-agent systems.

Through this event, I had the opportunity to understand more clearly how AI and cloud technologies are applied to real-world problems, particularly in enterprise environments and product development processes.

The main presentations included:

- **Context Is Everything** – analyzing the importance of context when working with AI.
- **Friendly AI Assistant with Amazon Q Suite** – introducing Amazon Q Suite for enterprise use.
- **From Edge to Origin: CloudFront as Your Foundation** – explaining the role and extended capabilities of Amazon CloudFront.
- **36 hrs with LotusHacks: Building UTMorpho** – sharing the experience of developing a product during a hackathon.
- **Non-Determinism of “Deterministic” LLM Settings** – explaining why LLMs may still generate different outputs under the same configuration.
- **Enterprise-Grade Multi-Agent System: Startup Credit Scoring** – introducing a multi-agent system designed to evaluate startup creditworthiness.

---

## Event Objectives

The main objectives of the event were:

- To explore emerging trends in AI and cloud computing on AWS.
- To understand how AWS services are used to solve real-world problems.
- To expand participants’ knowledge of Amazon Bedrock, Amazon Q, CloudFront, and multi-agent systems.
- To learn from speakers and teams that have developed practical technology products.
- To gain additional ideas for applying AI to study, work, and personal projects.

---

## Speakers and Main Topics

### 1. Tinh Truong – Context Is Everything

Tinh Truong’s presentation focused on the factors that enable AI systems to generate more accurate and relevant answers. According to the speaker, although modern AI models have become highly capable, the quality of their outputs still depends significantly on the information and context provided by users.

When a request is clearly written and supported by sufficient background information and specific objectives, the AI model has a stronger basis for producing an appropriate response. In contrast, short, vague, or overly general questions often result in answers that lack depth and relevance.

The speaker also introduced the idea of developing a system similar to a “second brain” for AI. Such a system would be able to store, retrieve, and reuse previously collected information, allowing AI to understand users more effectively and generate responses that are better suited to different situations.

### 2. Hai Anh – Friendly AI Assistant with Amazon Q Suite

Hai Anh’s presentation introduced **Amazon Q Suite**, a collection of artificial intelligence solutions developed by AWS to support enterprise activities.

Amazon Q can assist employees with various tasks, including searching for documents, summarizing information, creating content, taking meeting notes, drafting emails, and supporting data analysis.

One significant advantage of Amazon Q is its ability to connect with multiple internal business data sources. This allows the system to generate responses based on the organization’s actual information rather than relying only on the general knowledge of an AI model.

However, to deploy Amazon Q effectively, enterprises must also establish appropriate access control and data governance mechanisms. These controls help ensure that employees can only access information that is relevant to their responsibilities and level of authorization.

### 3. Nguyen Tuan Thinh – CloudFront as Your Foundation

This was one of the more technically detailed presentations at the event, focusing on **Amazon CloudFront**.

Before attending the presentation, I mainly understood CloudFront as a content delivery network used to improve website loading speed. However, the presentation helped me recognize that CloudFront can also serve as a foundational component for optimizing and protecting web systems.

CloudFront can reduce the workload placed on origin servers, deliver content to users more quickly, help protect systems against distributed denial-of-service attacks, and contribute to the optimization of operating costs.

The presentation also introduced several related services and features, including AWS WAF, AWS Shield, Origin Shield, Signed URLs, and HTTP/3. Combining these capabilities can help a web system achieve better performance, security, and operational stability.

### 4. Team VIB – 36 hrs with LotusHacks: Building UTMorpho

Team VIB’s presentation described its experience participating in LotusHacks 2026 and developing a product called **UTMorpho** within 36 hours.

At the beginning of the competition, the team did not have a clearly defined idea. After several discussions, the members decided to start with a real problem they had experienced in their daily work and develop a solution around it.

One of the most notable aspects of the presentation was that it did not focus exclusively on technology. It also highlighted the importance of teamwork and coordination. During the development process, the team faced several difficulties, including excessive AI-generated content, token limitations, time pressure, and exhaustion as the final presentation approached.

Despite these challenges, the team successfully completed the product by dividing responsibilities and agreeing on a shared direction. From this experience, I learned that valuable ideas often come from real-world problems. I also realized that team alignment and cooperation are often more important than generating numerous ideas that cannot be implemented effectively.

### 5. Duc Dao – Non-Determinism of “Deterministic” LLM Settings

Duc Dao’s presentation discussed an important technical characteristic of large language models.

Many users assume that setting the temperature parameter to zero will always cause an AI model to generate exactly the same answer. However, the speaker demonstrated that this assumption is not entirely correct. In some situations, even when the prompt and configuration remain unchanged, the model may still produce different results.

These variations can be caused by several technical factors, including floating-point calculations performed by GPUs, differences in processing order, request batching, and minor variations in the operating infrastructure.

From this presentation, I learned that developers should not assume that an LLM will always generate identical results in every execution. Instead, systems should be designed to accept a reasonable level of variation and include appropriate evaluation, validation, or retry mechanisms when necessary.

### 6. Vy Lam – Enterprise-Grade Multi-Agent System: Startup Credit Scoring

Vy Lam’s presentation introduced a **multi-agent system** designed to support credit scoring for startup companies.

Evaluating the creditworthiness of a startup is often difficult because a newly established business may not have a complete credit history, substantial collateral, or stable revenue comparable to that of a long-established company.

To address this challenge, the speaker proposed using multiple AI agents, with each agent responsible for analyzing a different category of information. For example, one agent may evaluate financial performance, another may analyze market conditions, and another may assess the capabilities of the founding team. Other agents may focus on risk and regulatory compliance.

This model can be understood as a virtual credit assessment committee. Each agent acts as a specialist in a particular area, and their assessments are later combined to generate the final evaluation.

The presentation also emphasized that selecting a powerful AI model is only one part of deploying AI in an enterprise environment. The complete system must also include security, monitoring, data management, access control, and clear validation procedures.

---

## Key Highlights

### AI Quality Depends Heavily on Context

One idea repeated across several presentations was that the effectiveness of AI does not depend only on the power of the underlying model. The context, input data, and way in which users describe their requests also directly influence the quality of the generated responses.

When users submit only a general question, AI may produce a broad answer that does not examine the topic in sufficient depth. In contrast, when users provide relevant data, clear objectives, supporting documents, and specific examples, the result is usually more accurate and useful.

### Enterprise AI Requires Effective Control Mechanisms

The presentations on Amazon Q Suite and multi-agent systems demonstrated that implementing AI in an enterprise is much more complex than simply interacting with a chatbot.

When integrating AI into actual business operations, enterprises need to determine:

- Which data sources the system is permitted to use.
- Who is authorized to access each category of information.
- How incorrect AI-generated outputs will be handled.
- How confidential and sensitive organizational data will be protected.
- How the system’s outputs can be monitored, traced, and evaluated.

These elements are essential for ensuring that an AI system operates safely and remains aligned with organizational objectives.

### CloudFront Provides More Than CDN Functionality

The presentation on Amazon CloudFront helped me understand that this service is not limited to distributing content and improving page-loading speed.

CloudFront can also reduce direct traffic to the origin server, strengthen system security, reduce the impact of cyberattacks, and improve the user experience across different geographical regions.

Therefore, CloudFront can be considered an important component in the architecture of web applications deployed on AWS.

### LLM Outputs May Vary Between Executions

The presentation on LLM non-determinism showed that AI models may generate different responses even when the input and configuration remain unchanged.

This means that developers should implement methods for evaluating generated outputs rather than relying entirely on a single response. In some situations, the system may need to rerun the model, compare multiple outputs, or apply additional validation before making a decision.

### Multi-Agent Systems Are Suitable for Complex Problems

For complex problems such as credit assessment, a single AI model may not be able to analyze every relevant factor comprehensively.

Dividing a large problem into smaller tasks and assigning each task to a specialized agent can make the process more structured. The final result can then be produced by combining multiple perspectives, improving both interpretability and decision support.

---

## Main Lessons Learned

### 1. Providing Sufficient Context Improves AI Performance

When working with AI, users should not provide only a short request and expect the model to understand the entire problem automatically. Providing background information, objectives, relevant data, and specific requirements enables AI to generate more suitable responses.

### 2. AI-Generated Results Must Be Reviewed

AI can support people in completing many types of tasks, but its outputs should not automatically be considered completely accurate.

Human review remains especially important in high-risk areas such as finance, cybersecurity, and business decision-making. People must continue to evaluate the results and take responsibility for final decisions.

### 3. AI and Cloud Computing Are Closely Connected

The presentations demonstrated that many modern AI applications are developed and operated using cloud computing platforms.

Services such as Amazon Bedrock, Amazon Q, CloudWatch, Amazon ECR, API Gateway, and CloudFront can be integrated to form a complete system. Together, they can support model development, API creation, application deployment, system monitoring, and security.

### 4. Product Development Requires More Than Technical Skills

From Team VIB’s experience, I learned that building a product does not depend solely on programming ability.

A development team must correctly understand the user’s problem, select an appropriate solution, manage its available time, coordinate among members, and prioritize the most important features within limited resources.

### 5. Deploying AI to Production Requires Comprehensive Preparation

An AI product intended for real-world use must include supporting components such as security, monitoring, access management, output evaluation, and error handling.

A system that performs well in a testing environment may not necessarily meet the requirements of actual users. Therefore, moving an AI application from a demonstration stage to production requires careful preparation.

---

## Important Terminology

### Context Engineering

Context engineering is the process of selecting, preparing, and organizing input information so that an AI system can clearly understand the request, relevant background, and intended objective.

### Second AI Brain

A second AI brain refers to the idea of creating a system that can remember, store, search for, and reuse existing information to help AI generate more relevant responses.

### Amazon Bedrock

Amazon Bedrock is an AWS service that allows users to access and build applications with various generative AI foundation models without directly managing the underlying model infrastructure.

### Amazon Q Suite

Amazon Q Suite is a collection of AI assistant tools provided by AWS to support tasks and workflows within enterprise environments.

### Amazon CloudFront

Amazon CloudFront is AWS’s content delivery network service. It helps deliver content to users more quickly, reduces the workload on origin servers, and provides additional protection for applications.

### AWS WAF

AWS WAF is a web application firewall service. It helps identify and block requests that appear dangerous or violate predefined security rules.

### Multi-Agent System

A multi-agent system consists of multiple AI agents working together. Each agent is normally responsible for a specific task or area of analysis.

### Guardrails

Guardrails are rules and control layers designed to limit AI behavior, reduce inaccurate outputs, and prevent the exposure of sensitive information.

### Prompt Injection

Prompt injection is a type of attack in which malicious instructions are inserted into the input to manipulate an AI system or cause it to perform unintended actions.

### Temperature

Temperature is a parameter that affects the randomness and diversity of AI-generated content. Higher values usually produce more varied responses, while lower values generally guide the model toward more stable outputs.

---

## Application to Study and Work

After participating in the event, I can apply the knowledge and experience gained in the following ways:

- When using AI, I will provide clearer context and more specific requirements instead of submitting short and incomplete questions.
- In AI projects, I will pay attention to data quality, security, access control, and output evaluation rather than focusing only on the model.
- When designing web applications on AWS, I will consider using CloudFront to improve access speed and strengthen system protection.
- During teamwork, I will prioritize identifying the actual problem before selecting technologies or developing solutions.
- When developing applications that use LLMs, I will remember that model outputs may vary and should be validated before use.
- When working on a large problem, I can divide it into smaller tasks and consider using multiple agents or processing stages.

---

## My Experience at the Event

Attending AWS Vietnam Community Day gave me an opportunity to gain practical knowledge related to artificial intelligence and cloud computing.

The presentations did not only introduce services and technologies. They also demonstrated how these technologies are used in enterprises, product development processes, and situations involving real-world requirements.

What impressed me most was that the current applications of AI have expanded far beyond basic question-and-answer interactions. AI can support internal information retrieval, data analysis, workflow automation, software development, and cooperation among multiple agents to solve complex problems.

However, the event also helped me understand that AI should not be used in a completely uncontrolled manner. To use AI effectively, users need to describe their requirements clearly, provide appropriate data, and carefully review the outputs generated by the model.

In addition to knowledge about AI, the event gave me a broader understanding of the AWS ecosystem. Services such as Amazon Bedrock, Amazon Q, CloudFront, CloudWatch, API Gateway, and Amazon ECR have different functions, but they can be integrated to build and operate a modern technology system.

---

## Lessons After the Event

After participating in the program, I identified several important lessons:

- AI requires sufficient context to generate high-quality responses.
- When developing an AI application, data and the way the model is used are just as important as the model’s capabilities.
- AI systems deployed in real environments require security, monitoring, and output control mechanisms.
- Amazon CloudFront can simultaneously improve speed, scalability, and security for web systems.
- LLMs do not always generate identical results, even when the prompt and configuration remain unchanged.
- Effective cooperation among team members plays an important role in product development.
- Valuable solutions often begin with the identification of a genuine real-world problem.
- Multi-agent systems are a suitable approach for problems involving multiple components and specialized analysis.

---

## Conclusion

AWS Vietnam Community Day was a valuable event for my learning and professional development. It helped me understand more clearly how AWS, cloud computing, and artificial intelligence are applied in real-world systems and business activities.

Through the presentations, I realized that AI is gradually becoming an important component of enterprise systems rather than being used only for experimentation or simple conversations.

However, to implement AI effectively, organizations must prepare appropriate context, data, security measures, access controls, monitoring systems, and output validation methods. A powerful model alone is not sufficient to create an effective system without suitable operational and control components.

The event also provided me with additional knowledge and ideas that can be applied to my studies and project development, particularly in areas related to Amazon Bedrock, Amazon Q, Amazon CloudFront, LLMs, and multi-agent systems.
```
