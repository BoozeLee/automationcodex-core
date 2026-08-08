# automationcodex-core

Graph-theoretic and MDP-based automation framework for orchestrating complex AI workflows and agent systems.

![Python](https://img.shields.io/badge/Python-3.12-blue?logo=python)
![NetworkX](https://img.shields.io/badge/NetworkX-Graph_Theory-000?logo=python)
![MDP](https://img.shields.io/badge/Markov_Decision_Process-Automation-ffcc00?logo=python)

## Overview

automationcodex-core is a foundational automation framework that combines graph theory and Markov Decision Processes (MDPs) to orchestrate complex AI workflows. It serves as the decision-making backbone for 50+ projects across the Bakery Street ecosystem.

## Key Features

- **Graph-Based Workflow Design**: Model complex processes as directed graphs
- **MDP Task Decomposition**: Break down high-level goals into executable agent tasks
- **State Management**: Persistent workflow state with rollback and retry capabilities
- **Plugin Architecture**: Extensible agent and tool registry
- **Evaluation Metrics**: Built-in benchmarking for workflow convergence and efficiency
- **CLI & SDK**: Both command-line and programmatic interfaces

## Tech Stack

- **Language**: Python 3.12+
- **Graph Processing**: NetworkX, igraph concepts
- **Optimization**: MDP-based policies, reinforcement learning primitives
- **Serialization**: JSON, YAML workflow definitions
- **Async**: asyncio for concurrent task execution
- **Testing**: pytest with integration test suite

## Quick Start

```bash
# Clone the repository
git clone https://github.com/BoozeLee/automationcodex-core.git
cd automationcodex-core

# Install dependencies
pip install -r requirements.txt

# Define a workflow
cat > workflow.yml <<EOF
name: research_pipeline
nodes:
  - id: fetch
    type: fetcher
    config:
      source: arxiv
  - id: analyze
    type: analyzer
    config:
      model: gpt-4
  - id: report
    type: reporter
    config:
      format: markdown
edges:
  - from: fetch
    to: analyze
  - from: analyze
    to: report
EOF

# Execute the workflow
python -m automationcodex run workflow.yml
```

## Architecture

### Core Components
- **Workflow Engine**: Parses and executes graph-based workflows
- **Agent Registry**: Pluggable agent implementations (fetchers, analyzers, reporters)
- **State Manager**: Tracks execution state, handles retries and rollbacks
- **Policy Engine**: MDP-based decision making for task routing
- **Event Bus**: Pub/sub for inter-agent communication

### Workflow Execution Model
1. Parse workflow definition (YAML/JSON)
2. Validate graph topology and dependencies
3. Initialize agent instances from registry
4. Execute nodes in topological order
5. Handle failures with configurable retry policies
6. Emit events for monitoring and observability

## Use Cases

- AI research pipeline orchestration
- Multi-step document processing
- Automated testing and validation workflows
- Data pipeline coordination
- Agent task decomposition and execution

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

MIT — see [LICENSE](LICENSE) for details.

## Contact

**Kiliaan Vanvoorden** — [bakerstreetbandit@zohomail.eu](mailto:bakerstreetbandit@zohomail.eu)
