# ProtocolSmith  smithy]

**An artisan's toolkit for forging custom, stateful network protocols to test infrastructure resilience.**

---

## What is ProtocolSmith?

ProtocolSmith is a programmable network traffic simulator. It allows developers, QA engineers, and SREs to precisely craft and execute complex, realistic network behaviors to validate the robustness of intermediary components like proxies, load balancers, and firewalls.

Like a blacksmith forging a custom tool, ProtocolSmith gives you the power to shape raw network interactions (TCP, UDP, HTTP) into sophisticated test scenarios. These scenarios are defined in a simple, declarative language called **MSP (Manageable Scenario Protocol)**, letting you focus on the desired behavior, not the implementation details.

## Why ProtocolSmith?

The current landscape of testing tools is fragmented. You need one tool for L7 load testing, another for L4 packet crafting, and a third for chaos engineering. ProtocolSmith unifies these capabilities:

* **Forge Any Protocol:** Seamlessly script both low-level TCP/UDP conversations and high-level application protocols like HTTP.
* **Integrate Chaos:** Make network failures a deterministic part of your test scenarios, not a separate, random event.
* **Declarative & Accessible:** Describe complex network choreographies in simple, readable YAML files, making advanced testing accessible to the whole team.
* **Test the Middleman:** Built from the ground up to simulate both client and server endpoints, allowing for precise testing of the components in between.

## Project Status: 🔬 Experimental

This project is in an early, experimental phase. The core concepts are being developed and the API is subject to change.

**Please Note:** This is currently a personal project. I am not providing active support and external contributions are not being accepted at this time.

## Core Concepts

* **`psmith` Executor:** A single, standalone Go binary that can act as a client or a server (`--role client|server`).
* **Scenario (`.yml`)**: A YAML file describing the complete "choreography" of a network interaction for all actors.
* **Instructions:** Atomic actions (`network.send`, `core.delay`, `http.request`) that are the building blocks of a scenario.
* **Flows & Workflows:** Reusable sequences of instructions (`Flows`) that can be orchestrated into complex user journeys (`Workflows`).

## Getting Started

*Detailed installation and usage instructions will be available in the official documentation.*

The basic workflow consists of:

1.  **Writing a Scenario:** Define the peers, instructions, and workflow in a `scenario.yml` file.
2.  **Configuring the Server:** (If needed) Define the listeners and their protocols in a `server-config.yml`.
3.  **Running the Test:** Use the `psmith` CLI to execute the scenario with the desired roles.

```bash
# In one terminal, start the server actor
psmith run my_scenario.yml --role server --config my_server.yml

# In another, start the client actor
psmith run my_scenario.yml --role client
````

## Documentation

For detailed examples, tutorials, and the full MSP specification, please refer to the **official documentation site** (coming soon).

This repository is intended for the source code of the core engine. The documentation and a collection of community-provided scenarios will be hosted in a separate repository.

## Contributing

Thank you for your interest\! As the project is in a highly experimental state, contributions are not being accepted at this time. Please refer to the "Project Status" section for more details.

-----

*Project created and maintained by [Guillaume Pineda / @gpineda-dev](https://github.com/gpineda-dev).*
