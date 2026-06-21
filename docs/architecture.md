# Architecture

A high-level view of how the home lab is put together.

<pre class="mermaid">
graph TD
    Internet([Internet]) --> Router[Router / Firewall]
    Router --> Host["ThinkCentre M920q<br/>Proxmox VE (master node)"]

    subgraph Proxmox["Proxmox VE"]
        Docker["docker-host (VM)<br/>Docker + Portainer"]
    end

    Host --> Proxmox

    subgraph Containers["Portainer-managed containers"]
        Svc1[Services]
    end

    Docker --> Containers

    Router --> NAS["WD My Cloud EX2 Ultra<br/>(NAS — family backups)"]

    subgraph Planned["Planned"]
        Pi["4 × Raspberry Pi 4B (8GB)<br/>k8s cluster for labbing"]
    end

    Router -.-> Planned
</pre>

- **Host:** a Lenovo ThinkCentre M920q running **Proxmox VE** as the master node
  (see [Hardware](hardware.md)).
- **Virtualization:** Proxmox hosts a **docker-host** VM (Ubuntu Server) that runs Docker.
- **Containers:** workloads run as Docker containers, managed through **Portainer**
  (see [Software & Services](services.md)).
- **NAS:** a WD My Cloud EX2 Ultra handles family backups
  (see [Storage & Backups](storage.md)).
- **Planned:** 4 × Raspberry Pi 4B (8 GB) earmarked for a Kubernetes cluster
  (see [Roadmap](roadmap.md)).

The diagram above is rendered with [Mermaid](https://mermaid.js.org/) loaded from a CDN.
