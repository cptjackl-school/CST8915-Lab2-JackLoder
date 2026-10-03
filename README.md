CST8915 Lab 2: Algonquin Pet Store on Azure VM Refactored

**Student Name**: Jack Loder
**Student ID**: 040829366
**Course**: CST8915 Full-stack Cloud-native Development
**Semester**: Fall 2026

---

## 1. Demo Video

🎥 [Watch Demo Video](https://youtu.be/ras5STJrndM)

---

## 2. Reflection

i. I updated the order-service and product-service to load configuration from environment variables using dotenv instead of hard-coding ports and connection details. The order-service now connects to RabbitMQ through the RabbitMQ VM's public IP using an application account and publishes persistent messages to a durable queue. The RabbitMQ instance is treated as an external backing service, so it can be changed independently of the order-service by just changing the configuration files to point at the new backing service.

ii. It is important to use configuration files instead of hardcoding variables in order to prepare for situations where the architecture needs to be rearchitectured or rearranged. For example, If a url or port number needs to be changed in a service it may be referenced in many places throughout the app, if a person needs to go through the code and manually change the variable at each point it is referenced it would take a lot of work and create the possibility for errors.

iii. Separate repositories give each microservice its own codebase, dependency files, history, and release process. This keeps changes to one service from unnecessarily affecting the others and allows each service to be tested, deployed, updated, and scaled independently. If the services are replicated as the site scales then all the instances can be changed by editing one centra code repo.

---

## 3. Links

1.[order-service](https://github.com/cptjackl-school/order-service.git)

2.[product-service](https://github.com/cptjackl-school/product-service.git)

3.[store-front](https://github.com/cptjackl-school/store-front.git)
---