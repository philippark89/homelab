# Software & Services

The software stack running on the lab. See [Architecture](architecture.md) for how
these layers connect.

| Layer                | Technology    | Notes                          |
| -------------------- | ------------- | ------------------------------ |
| Hypervisor           | Proxmox VE    | Runs on the ThinkCentre M920q  |
| VM guest OS          | Ubuntu Server | The docker-host VM             |
| Containers           | Docker        | Hosted on the docker-host VM   |
| Container management | Portainer     | Web UI for managing Docker     |
| Monitoring           | _TODO_        |                                |
| Home automation      | _TODO_        |                                |
| Reverse proxy        | _TODO_        |                                |

> The _TODO_ rows are placeholders to be filled in.
