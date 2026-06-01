# hrc - Homelab Research Computing

Ambiente de laboratório focado em computação científica e infraestrutura como código.

## Arquitetura
* **Hypervisor (`pve-01`):** Proxmox VE (Hardware físico - 192.168.1.50).
* **VM de Serviços (`rocky-base`):** Rocky Linux 9 (4GB RAM - 192.168.1.182).
* **Nó de Computação (`thinkpad`):** Bare-metal (Pendente de integração de rede).

## Monitorização e Observabilidade
A stack de monitorização está centralizada na VM de serviços e recolhe métricas a cada 15 segundos:
* **Prometheus:** Servidor de recolha de métricas e gestão de targets.
* **Grafana:** Dashboard de visualização em tempo real (Recursos, rede e armazenamento).
* **Node Exporter:** Agente de métricas do sistema operativo executado nos nós do cluster.

## Automação
* **Ansible:** Gestão de inventário e automação do deployment de agentes.
* **Docker:** Contentorização dos serviços Prometheus e Grafana.
