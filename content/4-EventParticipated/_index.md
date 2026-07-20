```markdown
---
title: "Mini Meetup – First Cloud AI Journey"
date: 2026-06-06
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

## Event Information

| Category | Details |
| --- | --- |
| Event name | Mini Meetup – First Cloud AI Journey |
| Date | June 6, 2026 |
| Venue | 26th Floor, Bitexco Financial Tower, 02 Hai Trieu Street, Sai Gon Ward, Ho Chi Minh City |
| My role at the event | Attendee |
| Brief description of the event | The Mini Meetup – First Cloud AI Journey was a technology-sharing session covering various topics related to cloud computing, cybersecurity, DevOps, artificial intelligence, real-time systems, teamwork, and career development in the IT industry. The program consisted of six presentations, with each speaker introducing a different technical or professional topic. |
| Knowledge and value gained | Through the event, I gained practical knowledge of Docker, containerization, AWS WAF, machine learning for cyberattack detection, real-time application development with WebSocket, AWS Lambda, DynamoDB, GraphRAG, and Amazon Neptune. I also gained useful insights into teamwork, communication, career planning, and the importance of building a practical portfolio. |
| Significance of participating | Participating in the meetup allowed me to broaden my knowledge beyond AI and cloud computing. It also helped me better understand the range of technical and interpersonal skills required to develop a successful career in information technology. |

---

## Event Overview

Mini Meetup – First Cloud AI Journey was a community meetup designed to share practical knowledge and professional experience across several areas of information technology.

Unlike an event that focuses on only one specific technology, this meetup covered a broad range of topics, including containerization, cloud security, machine learning, real-time application development, teamwork, career development, and knowledge graph–based retrieval systems.

The program included six presentations. Each presentation introduced a different subject and provided practical examples from real projects or workplace experiences.

The main topics presented during the meetup were:

- Docker and containerization in modern application development.
- Combining AWS WAF with machine learning to identify cyberattacks.
- Developing a real-time multiplayer game using Godot and AWS WebSocket.
- Improving collaboration and communication within a development team.
- The career journey from IT Helpdesk to Senior System Administrator.
- Building GraphRAG applications with Amazon Neptune.

Through these presentations, I gained a broader view of how different technologies can be integrated to develop, secure, and operate modern information systems.

---

## Event Objectives

The meetup aimed to achieve the following objectives:

- Introduce practical technologies currently used in cloud and software projects.
- Help participants understand the benefits of Docker and containerization.
- Present the role of AWS WAF and machine learning in cybersecurity.
- Demonstrate how AWS services can support real-time applications.
- Share practical lessons about teamwork and communication.
- Provide career guidance for students and junior IT professionals.
- Introduce GraphRAG and graph database applications using Amazon Neptune.

---

## Main Presentations and Topics

### 1. Docker and Containerization

One of the presentations introduced Docker and the concept of containerization.

Docker allows developers to package an application together with its libraries, dependencies, and runtime configuration into a container. This helps ensure that the application operates consistently across different environments.

Without containerization, an application may run correctly on one computer but encounter errors when transferred to another system because of differences in operating systems, installed libraries, or configuration settings.

Docker helps reduce this problem by creating a standardized environment for an application. As a result, developers can build, test, and deploy software more efficiently.

The presentation also helped me understand several important concepts, including Docker images, Docker containers, Dockerfiles, ports, volumes, and container registries.

From this topic, I learned that Docker is not only a development tool but also an important component of modern DevOps and cloud deployment processes.

### 2. AWS WAF and Machine Learning for Cyberattack Detection

Another presentation focused on using **AWS WAF** together with machine learning to improve web application security.

AWS WAF is a web application firewall that can inspect incoming requests and block traffic that matches predefined security rules. It can help protect applications from common threats such as malicious bots, SQL injection, cross-site scripting, and unusual traffic patterns.

However, cyberattacks are constantly changing, and fixed rules may not always detect every new form of suspicious behavior. The presentation therefore introduced the idea of applying machine learning to analyze request data and identify abnormal patterns.

Machine learning models can examine factors such as request frequency, source address, access behavior, and unusual input structures. When a request appears suspicious, the system can generate a warning or apply additional protection.

This presentation helped me understand that modern cybersecurity systems often combine rule-based tools with data-driven detection methods. AWS WAF provides an important first layer of protection, while machine learning can help identify more complex or previously unseen attack patterns.

### 3. Building a Real-Time Multiplayer Game with Godot and AWS WebSocket

The third technical topic presented a real-time multiplayer game developed with the Godot game engine and AWS services.

Real-time games require information to be exchanged continuously between players and the server. Traditional HTTP requests may not be suitable for this purpose because they normally follow a request-and-response model.

WebSocket provides a persistent two-way connection between the client and the server. This allows data to be transmitted immediately whenever an event occurs, such as when a player moves, performs an action, or changes the game state.

The system introduced during the presentation used several AWS services, including:

- **API Gateway WebSocket API** to maintain real-time connections.
- **AWS Lambda** to process events and game actions.
- **Amazon DynamoDB** to store connection information and game data.
- **Amazon CloudWatch** to monitor logs and system activity.

This presentation helped me understand how serverless AWS services can be combined to build an application that responds to users in real time.

Although the example involved a multiplayer game, the same architecture can also be used for chat applications, live notifications, online collaboration platforms, tracking systems, and real-time dashboards.

### 4. Effective Teamwork in Technology Projects

In addition to technical knowledge, the meetup included a presentation about teamwork.

Technology projects often require people with different responsibilities to work together, including developers, designers, testers, project managers, and cloud engineers. Even if every member has strong technical skills, a project can still face difficulties when communication and coordination are ineffective.

The speaker emphasized several important elements of successful teamwork:

- Defining responsibilities clearly.
- Communicating progress and difficulties regularly.
- Listening to the opinions of other team members.
- Providing constructive feedback.
- Sharing information and documentation.
- Focusing on the common objective of the project.
- Resolving disagreements professionally.

This presentation reminded me that technical ability alone is not enough to complete a project successfully. Team members also need communication skills, responsibility, flexibility, and respect for one another.

### 5. From IT Helpdesk to Senior System Administrator

One presentation shared the speaker’s career journey from an IT Helpdesk position to becoming a Senior System Administrator.

The speaker explained that working in IT Helpdesk can provide a strong foundation for an IT career. Helpdesk employees regularly encounter problems involving operating systems, networks, user accounts, software, hardware, and information security.

By solving these issues, they can gradually develop troubleshooting skills and gain a better understanding of how organizational IT systems operate.

To progress into a system administration position, IT professionals need to continue developing their knowledge of areas such as:

- Computer networking.
- Windows and Linux operating systems.
- Server administration.
- Virtualization.
- Cloud computing.
- Cybersecurity.
- Automation and scripting.
- System monitoring and backup.

The presentation also emphasized that career development is a gradual process. Professionals need to continuously learn, gain experience, document their work, and accept increasingly complex responsibilities.

From this presentation, I learned that an entry-level position can become an important starting point when a person has a clear learning plan and a willingness to improve.

### 6. GraphRAG with Amazon Neptune

The final major topic introduced **GraphRAG** and its implementation with **Amazon Neptune**.

Traditional Retrieval-Augmented Generation systems often search for text passages based on semantic similarity. This approach is useful, but it may not fully capture the relationships among different entities.

GraphRAG combines large language models with graph-based data. In a graph database, information is represented through nodes and relationships. For example, a graph may connect customers, products, companies, transactions, documents, and locations.

Amazon Neptune is a fully managed graph database service provided by AWS. It supports applications that need to store and query highly connected data.

By using Amazon Neptune in a GraphRAG system, an application can retrieve not only individual pieces of information but also the relationships among them. This can help an AI system answer questions that require several reasoning steps.

For example, instead of only finding a document containing a person’s name, the system may also identify the person’s organization, projects, colleagues, and related documents.

This presentation helped me understand that GraphRAG can improve the retrieval and reasoning capabilities of AI applications, particularly when the underlying data contains many important relationships.

---

## Key Highlights

### Containerization Improves Application Consistency

Docker helps package applications and their dependencies into standardized containers. This reduces differences between development, testing, and production environments.

As a result, teams can deploy applications more consistently and reduce configuration-related errors.

### Cybersecurity Requires Multiple Protection Layers

The presentation on AWS WAF demonstrated that security should not depend on a single tool.

Rule-based protection can block known attack patterns, while machine learning can help identify unusual behavior. Combining both approaches can create a more flexible and effective security system.

### AWS Supports Real-Time Serverless Applications

The multiplayer game example demonstrated how API Gateway WebSocket, Lambda, and DynamoDB can be combined to build a real-time application without maintaining traditional servers.

This architecture can automatically scale according to demand and can be applied to many different types of interactive applications.

### Teamwork Has a Direct Impact on Project Results

Strong technical knowledge does not automatically guarantee project success. Poor communication, unclear responsibilities, and incomplete documentation can create delays and misunderstandings.

Effective teamwork requires regular communication, clearly assigned tasks, and a shared commitment to project objectives.

### Career Growth Requires Continuous Learning

The career journey from IT Helpdesk to Senior System Administrator showed that professional development takes place over time.

Practical experience, self-study, technical certifications, personal projects, and a strong portfolio can all contribute to long-term career growth.

### GraphRAG Can Improve Relationship-Based Retrieval

GraphRAG is particularly useful when questions require an understanding of connections among multiple pieces of information.

By combining graph data with language models, the system can retrieve information more systematically and provide answers with stronger contextual relationships.

---

## Important Lessons Learned

### 1. Docker Is an Essential Tool in Modern Development

Docker helps create stable and repeatable environments for applications. It also supports collaboration among development teams and simplifies the deployment process.

### 2. Security Should Be Included from the Beginning

Security should not be treated as an additional step after an application has already been completed.

Services such as AWS WAF, monitoring systems, access controls, and machine learning detection methods should be considered during the system design process.

### 3. Serverless Services Can Support Real-Time Systems

AWS Lambda, API Gateway WebSocket, and DynamoDB can be combined to build scalable real-time applications.

This approach allows development teams to focus more on application logic instead of spending significant effort managing servers.

### 4. Communication Is an Important Professional Skill

In technology projects, communicating clearly is just as important as completing technical tasks.

Team members need to explain problems, share progress, document their work, and coordinate their responsibilities effectively.

### 5. A Practical Portfolio Supports Career Development

A portfolio containing projects, documentation, source code, and technical achievements can demonstrate a candidate’s actual abilities more effectively than a list of technologies alone.

Personal projects also allow learners to apply theoretical knowledge to real problems.

### 6. Graph Databases Are Useful for Highly Connected Data

Graph databases are appropriate when relationships among data entities are an important part of the problem.

When combined with RAG and large language models, graph databases can support more advanced search and reasoning capabilities.

---

## Important Terminology

### Docker

Docker is a platform used to package and run applications inside containers.

### Container

A container is a lightweight and isolated environment that includes an application and the dependencies required for it to operate.

### Docker Image

A Docker image is a reusable template used to create containers.

### Dockerfile

A Dockerfile contains instructions for building a Docker image.

### AWS WAF

AWS WAF is a web application firewall that helps protect web applications from malicious requests and common cyberattacks.

### Machine Learning–Based Detection

Machine learning–based detection uses data and trained models to identify unusual behavior or possible threats.

### WebSocket

WebSocket is a communication protocol that creates a persistent two-way connection between a client and a server.

### AWS Lambda

AWS Lambda is a serverless computing service that runs code in response to events without requiring users to manage servers.

### Amazon DynamoDB

Amazon DynamoDB is a fully managed NoSQL database service designed for applications requiring low-latency access and high scalability.

### Amazon Neptune

Amazon Neptune is a managed graph database service used to store and query highly connected data.

### GraphRAG

GraphRAG is an approach that combines graph-based information retrieval with large language models to generate answers based on both data and relationships.

### DevOps

DevOps is a set of practices that brings software development and IT operations together to improve application delivery and system reliability.

---

## Application to Study and Work

After participating in the meetup, I can apply the knowledge gained in several ways:

- I can use Docker to create consistent development environments for personal and team projects.
- I can learn how to write Dockerfiles and manage container images more effectively.
- When designing web applications, I can consider security services such as AWS WAF from the beginning.
- I can explore how machine learning supports the detection of abnormal traffic and cybersecurity threats.
- I can use API Gateway WebSocket, Lambda, and DynamoDB to experiment with real-time applications.
- I can improve communication and task coordination when working in a team.
- I can build practical projects and document them as part of my professional portfolio.
- I can study Amazon Neptune and GraphRAG for AI applications that involve connected data.

---

## My Experience at the Event

Participating in the Mini Meetup – First Cloud AI Journey gave me the opportunity to explore several technology areas within a single event.

The presentations combined technical knowledge with practical project experience and career advice. This made the event useful not only for learning about AWS services but also for understanding how technology professionals work and develop their careers.

The topic I found especially interesting was the use of AWS WebSocket services to build a real-time multiplayer game. It showed how cloud services can be integrated to process user events quickly without relying on a traditional server architecture.

I was also interested in the presentation about AWS WAF and machine learning. It demonstrated that artificial intelligence can be used not only for chatbots or content generation but also for cybersecurity and threat detection.

The teamwork and career presentations were also valuable. They helped me understand that long-term success in the IT industry requires more than technical knowledge. Communication, collaboration, continuous learning, practical experience, and career planning are equally important.

---

## Lessons After the Event

After attending the meetup, I identified the following key lessons:

- Docker helps applications operate consistently across different environments.
- Containerization is an important part of modern software development and DevOps.
- AWS WAF can provide an effective security layer for web applications.
- Machine learning can support the detection of unusual and malicious traffic.
- WebSocket is suitable for applications that require continuous real-time communication.
- Serverless AWS services can be combined to create scalable real-time systems.
- Effective teamwork requires clear communication and well-defined responsibilities.
- Career growth in IT requires continuous learning and practical experience.
- A strong portfolio can demonstrate technical skills and problem-solving ability.
- GraphRAG and Amazon Neptune are useful for AI applications involving highly connected information.

---

## Conclusion

Mini Meetup – First Cloud AI Journey was a valuable event that expanded my understanding of cloud computing, cybersecurity, DevOps, real-time systems, artificial intelligence, and career development.

Through the six presentations, I learned how Docker supports application deployment, how AWS WAF and machine learning can help identify cyberattacks, and how AWS services can be used to build real-time applications.

The event also introduced me to GraphRAG and Amazon Neptune, which provided a new perspective on how AI systems can retrieve and analyze relationships among data.

In addition to technical knowledge, the meetup emphasized the importance of teamwork, communication, continuous learning, and practical portfolios. These lessons will help me improve both my professional skills and my preparation for a future career in information technology.
```
