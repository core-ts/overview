# The core-ts Ecosystem

## Building Blocks for Real Software Products

A software product is more than its business logic.

Behind every feature, there are engineering concerns that developers must solve: storing data, validating input, communicating between services, managing security, handling failures, and integrating with external systems.

These concerns appear repeatedly across different applications, projects, and teams.

core-ts provides a collection of focused TypeScript libraries to address these recurring needs.

Rather than forcing every application into a predefined structure, core-ts gives developers reusable building blocks that can be combined to fit their requirements.

## 1. Database

**Write less data-access code while keeping database operations explicit and maintainable.**

Database operations are fundamental to most software products, but implementing common operations repeatedly can make application code verbose and difficult to maintain.

The core-ts database libraries provide reusable solutions for common data-access patterns, including CRUD operations, search, sorting, batch processing, transactions, and database-specific operations.

The goal is to keep application code focused on the data operations it needs to perform, while reusable libraries handle the underlying implementation.

Benefits:
- Reduce repetitive data-access code.
- Reuse common patterns across application modules.
- Keep database operations organized and easier to understand.
- Support different database technologies through dedicated libraries.

Relevant libraries include `sql-core`, `mysql2-core`, `postgres-kit`, `oracle-core`, `mssql-core`, `cassandra-core`, and `mongodb-kit`.

## 2. Validation

**Handle data validation consistently without scattering repetitive checks throughout your application.**

Applications receive data from many sources: API requests, databases, imported files, messages, and external services.

Without reusable validation patterns, different parts of an application may handle invalid data differently.

The core-ts ecosystem includes validation-related abstractions and components that can be used to establish consistent data-handling patterns.

The objective is to make validation easier to reuse and maintain, while keeping application-specific rules explicit.

Benefits:
- Reduce duplicated validation logic.
- Make data-handling patterns easier to recognize.
- Separate reusable validation mechanisms from business rules.
- Improve consistency across application modules.

*The exact validation capabilities depend on the validation libraries and integrations used by a project.*

## 3. Messaging

**Build distributed applications without repeatedly implementing message-processing infrastructure.**

Modern software products often consist of multiple services that communicate asynchronously.

Message queues and event-driven architectures help services operate independently, but reliable message processing introduces additional engineering concerns: retries, failure handling, transport integration, and health monitoring.

core-ts separates message-processing patterns from the underlying messaging technology where practical.

For example, `message-processing` provides reusable processing abstractions, while transport-specific libraries integrate with messaging systems such as Redis, NATS, Kafka, ActiveMQ, and RabbitMQ.

Benefits:
- Reuse message-processing logic.
- Reduce coupling between processing logic and transport implementations.
- Apply common patterns for retry and failure handling.
- Integrate with different messaging technologies through dedicated adapters.
- Keep messaging infrastructure out of application business logic where practical.

Relevant libraries include `message-processing`, `redis-messaging`, `nats-plus`, `kafka-plus`, `activemq`, and `rabbitmq-transport`.

The result is a more consistent way to build message-driven services without requiring every service to implement its own messaging infrastructure.

## 4. Import & Export

**Simplify data movement between applications, databases, and external systems.**

Data integration is an important part of many software products.

Applications may need to import files, process external data, migrate records, or export large datasets from a database.

These tasks often involve repetitive parsing, transformation, error handling, and data-access logic.

The core-ts ecosystem provides dedicated libraries for data import and export workflows.

`import-service` provides reusable import-processing capabilities, while `export-kit` defines export-related functionality that can be integrated with appropriate database-specific implementations.

Benefits:
- Reuse common data-processing patterns.
- Keep import and export workflows organized.
- Separate general processing logic from database-specific implementations where appropriate.
- Reduce the amount of custom integration code required for recurring data tasks.

Relevant libraries include `import-service`, `export-kit`, `pg-exporter`, and database-specific export integrations.

Import/export is a distinct engineering concern from messaging: it focuses on moving and transforming data, rather than primarily coordinating communication between services.

## 5. Cache

**Improve application responsiveness with reusable caching components.**

Repeatedly retrieving the same data can introduce unnecessary database load and increase response times.

Caching can help, but implementing caching separately in every application module often leads to duplicated code and inconsistent behavior.

core-ts provides reusable cache abstractions and implementations that allow applications to use caching without embedding every caching detail in business logic.

For example, `cache-plus` provides an in-memory cache implementation, while `redis-plus` supports Redis-based caching.

Benefits:
- Reuse common caching interfaces and patterns.
- Choose an appropriate caching implementation for your application.
- Reduce direct coupling between application logic and cache technology.
- Keep caching concerns separate from business rules.

The appropriate cache depends on the application's requirements, including data lifetime, consistency, sharing across processes, and operational constraints.

## 6. Security

**Make common authentication and authorization concerns reusable across applications.**

Security is essential to software products, but authentication and authorization code can easily become scattered across controllers, middleware, and business logic.

The core-ts security libraries provide reusable components for common security responsibilities, including authentication, token handling, and authorization-related operations.

Their modular design allows security functionality to be integrated into applications without requiring a single, all-encompassing framework.

Benefits:
- Reuse common authentication components.
- Separate security mechanisms from business workflows.
- Organize token verification and authorization responsibilities.
- Integrate security capabilities into different application architectures.

Relevant libraries include `authen-service`, `authentication-express`, `express-jsonwebtoken`, `security-express`, `signup-service`, and `password-service`.

Applications remain responsible for configuring these components correctly and implementing the security policies appropriate to their requirements.

## 7. Web

**Build web applications and services with reusable components instead of repeatedly assembling the same infrastructure.**

Web applications and backend services share common engineering needs, but they do not necessarily require the same dependencies or runtime structure.

core-ts provides web-related libraries that can be adopted according to the application being built.

For example, `express-web-kit` provides Express-based web capabilities, while `web-one` supports the ecosystem's Next.js-oriented use cases. `ui-formatter` provides reusable UI-formatting functionality.

The ecosystem also keeps certain concerns, such as logging middleware, in separate libraries so applications can avoid introducing unnecessary dependencies.

Benefits:
- Reuse common web integration components.
- Choose components appropriate to the application architecture.
- Avoid bundling unrelated functionality into every application.
- Keep web concerns separate from business logic where practical.

Relevant libraries include `express-web-kit`, `web-one`, `ui-formatter`, and `middleware-logging`.

## 8. Infrastructure & Shared Engineering Components

**Reduce repetitive engineering work across the entire application.**

Beyond databases and web frameworks, software products require a range of supporting capabilities.

Examples include configuration management, logging, health checks, shared interfaces, and locale-related functionality.

These concerns are easy to underestimate because they are not the primary business features of an application. Nevertheless, they affect how consistently applications are developed, operated, and maintained.

core-ts provides dedicated libraries for these recurring needs.

Benefits:
- Reuse common infrastructure components.
- Establish consistent interfaces between application components and supporting technologies.
- Keep infrastructure responsibilities organized.
- Make shared engineering capabilities easier to adopt across projects.

Relevant libraries include `onecore`, `config-plus`, `logger-core`, `health-service`, `reflect-core`, and `locale-service`.

## How the Ecosystem Fits Together

The real value of core-ts is not any individual library. It is the ability to combine focused libraries into a coherent engineering foundation.

Consider a typical software product:

- The web layer receives requests and returns responses.
- Security components handle authentication and authorization.
- Validation components help verify incoming data.
- Database libraries persist and retrieve application data.
- Cache components reduce repeated data access where appropriate.
- Messaging components support communication between services.
- Import/export components support data integration.
- Infrastructure components provide shared capabilities such as configuration, logging, and health checks.

Each component has a distinct responsibility, but they can work together within the same application.

A small application may need only a few libraries. A larger distributed system may use more of the ecosystem.

**You do not need to adopt everything. Start with the components that solve your problems, then expand when your requirements demand it.**

## One Ecosystem, Many Architectures

core-ts is not intended to prescribe one architecture for every project.

Different software products have different needs.

A small API may use a web library and a database library. A data-intensive application may place greater emphasis on import/export and database processing. A distributed system may combine messaging, health checks, caching, and multiple database integrations.

The same ecosystem can support these different needs because its components are designed around focused responsibilities rather than one mandatory application structure.

The guiding principle is simple:

**Reuse common engineering solutions. Keep application architecture under your control.**