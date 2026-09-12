# cybersecurity-lab
Cybersecurity Lab dentro de casa - Fedora Server, Docker e Wazuh

# 🔐 Cybersecurity Lab

Home lab de cibersegurança construído para aprendizado prático em Blue Team, DFIR e AppSec — com foco em entender sistemas de dentro pra fora, não apenas configurar ferramentas.

## 📖 Motivação

Estudo teórico é necessário mas não suficiente. CTFs são ótimos mas falta o controle de um ambiente real. E no trabalho, o acesso é limitado pelo escopo da função.

Esse lab existe para preencher essa lacuna — um ambiente onde é possível quebrar, entender e reconstruir sem restrição.

## 🖥️ Hardware

| Componente | Especificação |
|-----------|---------------|
| Modelo | Dell Inspiron |
| CPU | Intel Core i5 7ª geração |
| RAM | 8GB (expansão planejada) |
| Armazenamento | HD 1TB |

## 🏗️ Arquitetura

┌─────────────────┐         ┌──────────────────────┐
│  Lenovo LOQ      │◄───────►│  Dell Inspiron         │
│  Fedora 44/KDE   │ Tailscale│  Fedora Server        │
│  (Analista)      │         │                        │
└─────────────────┘         │  Docker + Compose      │
                              │  └── Wazuh (Manager,   │
                              │      Indexer,          │
                              │      Dashboard)        │
                              └──────────────────────┘

## ⚙️ Stack

- **SO:** Fedora Server
- **Acesso remoto:** Tailscale (MagicDNS)
- **Orquestração:** Docker + Docker Compose
- **SIEM:** Wazuh 4.14.6
- **Automação:** systemd (boot automático de containers + limpeza periódica)

## 🤔 Decisões técnicas

### Por que Fedora e não Ubuntu?
Ecossistema já em uso no notebook principal, gerenciador de pacotes DNF com resolução de dependências mais robusta, e ausência de Snap.

### Por que Docker e não VMs?
Hardware modesto não comporta múltiplas VMs. Além disso, containers compartilham o kernel do host — o que oferece uma via direta pra estudar Linux internals (processos, namespaces, cgroups). Windows é exceção, roda em VM via VirtualBox por limitação de kernel compartilhado.
,,,
## 📂 Documentação detalhada

- [Setup Docker](docs/docker.md)
- [Setup Tailscale](docs/tailscale.md)
- [Setup Wazuh](docs/wazuh.md)

## 🚧 Status

- [x] Servidor Fedora configurado
- [x] Acesso remoto via Tailscale
- [x] Wazuh (Manager, Indexer, Dashboard)
- [ ] Agentes Linux (containers)
- [ ] Agente Windows (VM)
- [ ] Regras de detecção customizadas

## 📝 Artigos relacionados

- [Home Lab Setup](link-dev-to)
```

O que acha? Quer ajustar alguma seção antes de subir?
