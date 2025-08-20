<!-- File: computing_technology/software_engineering/software_architectural_patterns.md -->

# Software Architectural Patterns

## 1. Overview

Software architectural patterns provide reusable solutions to common design problems in software systems. They guide the organization of components, the flow of data, and the interaction between modules, while also addressing non-functional requirements like scalability, maintainability, and performance.

Choosing an architectural pattern requires considering the **context** of the project, including system constraints, team expertise, and the forces acting on the solution. Not all patterns are suitable for all situations; evaluation of fit is essential.

## 2. Model-View-Controller (MVC) Pattern

The **MVC pattern** separates an application into three primary components:

* **Model:** Manages the application’s data, logic, and business rules.
* **View:** Handles the presentation layer and user interface.
* **Controller:** Manages user input, interacts with the Model, and updates the View.

This separation facilitates modularity, easier maintenance, and independent evolution of components. MVC is **distinct** from the Layers pattern, as it focuses on the interaction between components rather than strictly hierarchical layering.

## 3. Layers Pattern

The **Layers pattern** organizes a system into horizontal layers, each responsible for a specific set of services. Typically, higher layers rely on the services provided by lower layers, and communication is usually restricted to adjacent layers.

Key points:

* Promotes separation of concerns.
* Supports independent development and testing of layers.
* Facilitates substitution or modification of lower layers without affecting higher layers.

## 4. Broker Pattern

The **Broker pattern** is designed for **distributed systems** where components are decoupled. It introduces a mediator component—the **broker**—that handles communication between clients and servers.

Advantages:

* Clients are unaware of server locations or implementations.
* Simplifies system scalability and fault tolerance.
* Enhances flexibility by decoupling service consumers from service providers.

### Summary

| Pattern | Primary Purpose               | Key Components             | Notes                                          |
| ------- | ----------------------------- | -------------------------- | ---------------------------------------------- |
| MVC     | Separation of concerns        | Model, View, Controller    | Interaction-focused; not a Layer adaptation    |
| Layers  | Structured layering           | Multiple horizontal layers | Services flow from lower to higher layers      |
| Broker  | Distributed systems mediation | Broker, Clients, Servers   | Decouples components and manages communication |

---
