---
title: "Event 1"
date: 2026-07-25
weight: 4
chapter: false
pre: " <b> 4.1. </b> "
---

# Summary Report: FCAJ Hackathon Showcase – Product Presentation Day

*Note: exact event name, date, and location to be filled in.*

### Event Objectives

- Listen to seniors from the FCAJ program present the products they built during the Hackathon
- Understand how their solutions were designed and what results they achieved after the competition
- Learn from their real experience of building a product under a hackathon's time pressure
- Get inspiration and guidance for my own upcoming project/hackathon (if any)

### Speakers

- **3KA Team** – presented an AI-agent-based product for real-time video/incident processing on AWS
- **Dream AI Team** – presented a multi-agent orchestration platform built with Amazon Bedrock and agent runtimes
- **Plan V Team** – presented an automation platform combining Terraform-provisioned infrastructure, containerized services, and generative AI features
- **One Team** – presented a customer service chatbot system connecting messaging channels (Zalo, WhatsApp, and a future mobile app) to an AI agent backend built on Amazon Bedrock AgentCore, with supporting memory, data, and admin-monitoring layers

### Key Highlights

#### Four different products, one shared foundation

Even though each team solved a different problem, all of their products were built on a similar set of AWS building blocks: API Gateway, Lambda, container services (ECS/Fargate), storage (S3, DynamoDB, PostgreSQL), and security/monitoring services (WAF, Cognito, IAM, CloudWatch). The fourth team's chatbot system added another angle to this: connecting external messaging channels to an AI agent through an ingestion layer (WAF, API Gateway, Lambda, SQS), then routing conversations into Amazon Bedrock AgentCore with its own memory and data layers. Seeing this side by side with the other three products made it clear that the same set of services can be combined in very different ways depending on the product's purpose.

#### Generative AI used as a real part of the product, not just a demo feature

Several teams integrated generative AI (Amazon Bedrock, AI agents) directly into their core product logic, rather than adding it on as an extra. This showed how AI services can be combined with traditional cloud components to solve an actual problem, not just to impress in a demo.

#### Lessons from having gone through a hackathon already

Because the presenters had already been through the hackathon and were now sharing the outcome, their talks focused not only on the architecture but also on what they learned from the process itself — what worked, what they would do differently, and how the product evolved from the original hackathon submission.

### Key Takeaways

- **Showing up is already half the battle.** Committing to start and staying in the process matters more than waiting for the perfect idea.
- **Small, finished work beats big, broken ideas.** A simple solution that actually runs end-to-end is more valuable than an ambitious one that never gets completed.
- **The people you meet matter more than the prize.** The connections, mentorship, and shared learning during the hackathon outweigh the competition result itself.

### Applying to Work

- Prioritize building a minimal working version first, then iterate, instead of trying to design the "perfect" system from day one.
- Look for practical, targeted ways to integrate AI-assisted tools into a project, following the examples shared by the seniors.
- Be more intentional about networking with mentors and teammates during team-based programs — treat those conversations as part of the learning outcome, not a side activity.

### Event Experience

Attending the **FCAJ x AABW** product presentation was extremely valuable, giving me a much more concrete view of how a hackathon idea turns into a real, working product once teams have time to reflect on it. Key experiences included:

#### Learning from teams who had lived through the process

* The seniors from 3KA, Dream AI, Plan V, and One Team shared honest reflections on their hackathon journey — not just the final architecture, but what worked, what didn't, and what they would change next time.
* Through their real product stories, I gained a deeper understanding of how AI agents, event-driven integrations, and infrastructure-as-code are applied to actual problems, not just theoretical examples.

#### Exposure to a range of technical approaches

* Watching four teams solve four different problems helped me visualize how the same AWS building blocks — API Gateway, Lambda, container services, managed databases — can be arranged in very different ways depending on the product.
* Learned how AI agents can be orchestrated and connected to external channels (as in One Team's chatbot) or embedded directly into a processing pipeline (as in 3KA's video/incident system).
* Understood the trade-offs each team made between speed, scope, and technical depth under hackathon time pressure.

#### Leveraging modern AI-assisted tools

* Explored how Amazon Bedrock and AgentCore were used across multiple products as a practical foundation for building AI agents, rather than a standalone experiment.
* Learned how teams combined generative AI with more traditional cloud services (queues, storage, monitoring) to keep their products reliable, not just impressive in a demo.

#### Networking and discussions

* The event offered a chance to talk directly with the presenting teams and other attendees, exchanging questions about design choices and lessons learned.
* Hearing several perspectives side by side reinforced the idea that there's no single "correct" way to build a product — only choices suited to a team's goals and constraints.

#### Lessons learned

* Showing up and starting the work matters more than waiting for a perfect idea.
* A small, finished product is more valuable than an ambitious one that never gets completed.
* The connections and shared learning from an event like this often outweigh the competition result itself.
* AI tools like Amazon Bedrock AgentCore can meaningfully speed up building real functionality when integrated thoughtfully into a product's architecture.


#### Event photos
![Event](images/event1.jpg)
