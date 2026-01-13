## Breaking a Monolithic Node.js Application into Microservices

In this lab, I worked on migrating a monolithic Node.js message board application to a containerized microservices architecture using AWS services. The original application handled users, threads, and posts within a single Node.js service, which made scaling and maintenance difficult.

I first ran the monolithic application on a standard Node.js server and tested its REST APIs locally. After understanding the codebase and request flow, I containerized the monolithic application using Docker and pushed the image to Amazon Elastic Container Registry (ECR). The containerized monolith was then deployed to Amazon Elastic Container Service (ECS) using EC2 launch type and exposed through an Application Load Balancer.

Next, I refactored the monolithic application into three independent microservices: Users, Threads, and Posts. Each microservice handled a single business capability and had its own Docker image and ECR repository. I built and pushed separate container images for each service and created individual ECS task definitions.

Finally, I deployed each microservice as a separate ECS service and configured path-based routing on the Application Load Balancer. Requests were routed to the correct microservice based on API paths such as /api/users, /api/threads, and /api/posts. This setup allowed each service to scale and update independently.

## Key Technologies Used

Node.js (Koa framework)

Docker

Amazon ECS (EC2 launch type)

Amazon ECR

Application Load Balancer

AWS CLI

Key Learnings

## Difference between monolithic and microservices architecture

Containerizing applications using Docker

Deploying and managing containers on Amazon ECS

Using Application Load Balancer for path-based routing

Designing scalable and independently deployable services

## Full Guided Documentation - https://www.notion.so/Breaking-a-Monolithic-Node-js-Application-into-Microservices-2e1e8585d3ec80499445e4dc69a30517?source=copy_link
