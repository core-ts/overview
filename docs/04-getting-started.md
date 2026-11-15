# Getting Started

## Start Small. Build as You Grow.

You do not need to adopt the entire core-ts ecosystem to benefit from it.

Start with a specific engineering problem, choose the library that addresses it, and introduce additional components as your application evolves.

### Step 1: Explore the Ecosystem

Choose a starting point based on your application's needs.

| If you want to... | Explore |
|---|---|
| Simplify database operations | `sql-core`, `mysql2-core`, `postgres-kit`, `oracle-core` |
| Build reusable message-processing workflows | `message-processing` |
| Integrate messaging systems | `redis-messaging`, `nats-plus`, `kafka-plus`, `activemq`, `rabbitmq-transport` |
| Process imported data | `import-service` |
| Export database data | `export-kit`, `pg-exporter` |
| Add caching capabilities | `cache-plus`, `redis-plus` |
| Implement authentication and authorization | `authen-service`, `authentication-express`, `express-jsonwebtoken`, `security-express` |
| Build web applications and services | `express-web-kit`, `web-one`, `ui-formatter` |
| Add operational capabilities | `config-plus`, `logger-core`, `health-service` |

Each library has its own responsibilities, dependencies, and documentation. Start with the package most relevant to your requirements.

### Step 2: Install the Library You Need

core-ts libraries are distributed as individual npm packages.

Install the package you want to use:

```bash
npm install sql-core
```

For a PostgreSQL application, for example, you can explore `postgres-kit` alongside `sql-core` to understand how the database integration and shared SQL abstractions work together.

Choose compatible package versions and follow each library's installation instructions.

### Step 3: Explore Practical Examples

The best way to understand the ecosystem is to see how its components work together in an application.

Start with a focused example, understand the responsibilities of each component, and then adapt the patterns to your own requirements.

For example, a modular API might use a web layer, a service layer, a repository layer, and a database integration. Other applications may require message processing, data integration, or distributed-service capabilities instead.

The goal is not to copy a predefined architecture blindly. It is to understand the reusable patterns and apply them where they make sense.

### Step 4: Compose Your Own Solution

Once you are familiar with individual libraries, combine them to build the engineering foundation your application needs.

For example, a backend service might combine:

- A web library for HTTP handling.
- Database libraries for persistence.
- Validation components for incoming data.
- Security libraries for authentication and authorization.
- Logging and health-check libraries for operational support.

A distributed application might add messaging and caching. A data-processing application might focus on import/export and database operations.

Choose the components that provide real value to your application.

**Use what you need. Keep what works. Expand when necessary.**

## Explore the core-ts Repositories

The core-ts ecosystem is organized into individual repositories, allowing you to explore the implementation and documentation of each library.

Start with the [core-ts GitHub organization](https://github.com/core-ts) to discover the available projects.

For a more practical introduction, explore the [modular PostgreSQL sample](https://github.com/typescript-tutorial/postgres-modular-sample), which demonstrates how several core-ts libraries can work together in a modular REST API.

You can also begin with a specific library's README to understand its purpose, installation requirements, API, and examples.

## Build Better Software, One Library at a Time

You do not need a giant framework to benefit from a coherent set of engineering practices.

You need reusable solutions to recurring problems, clear boundaries between responsibilities, and the flexibility to assemble the right solution for your application.

That is what core-ts aims to provide.

**Less repetitive code. Cleaner architecture. Consistent engineering patterns.**

Build your software product with core-ts.