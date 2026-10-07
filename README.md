<h1 align="center">📡 Zabbix Monitoring</h1>

<p align="center">
  Monitoramento centralizado com Zabbix 7.0, automação do Agent e importação em massa de hosts via API.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Zabbix-7.0_LTS-D40000?logo=zabbix&logoColor=white" />
  <img src="https://img.shields.io/badge/Rocky_Linux-9-10B981?logo=rockylinux&logoColor=white" />
  <img src="https://img.shields.io/badge/PostgreSQL-16-4169E1?logo=postgresql&logoColor=white" />
  <img src="https://img.shields.io/badge/Shell_Script-Bash-4EAA25?logo=gnubash&logoColor=white" />
  <img src="https://img.shields.io/badge/Nginx-009639?logo=nginx&logoColor=white" />
  <img src="https://github.com/SEU_USUARIO/SEU_REPO/actions/workflows/shellcheck.yml/badge.svg" />
  <img src="https://img.shields.io/badge/license-MIT-blue" />
</p>

---

## 📑 Sumário

- [Sobre o projeto](#-sobre-o-projeto)
- [Stack do ambiente](#-stack-do-ambiente)
- [Arquitetura](#️-arquitetura)
- [Estrutura do repositório](#-estrutura-do-repositório)
- [Instalação do Zabbix Agent](#-instalação-do-zabbix-agent)
- [Importação/Exportação em massa](#-importaçãoexportação-em-massa)
- [Dashboards](#-dashboards)
- [Segurança aplicada](#-segurança-aplicada)
- [Troubleshooting](#-troubleshooting)
- [Entregas](#-entregas)
- [Autor](#-autor)

## 📌 Sobre o projeto

Em ambientes com muitos servidores e estações, cadastrar hosts manualmente é lento, propenso a erro e não escala. Este projeto entrega uma solução de monitoramento **padronizada, segura e reproduzível**:

- 🖥️ Zabbix Server 7.0 standalone, instalado 100% via CLI
- 🤖 Instalação do Agent automatizada por script (Linux e Windows)
- 📦 Exportação/importação em massa de hosts e templates
- 📊 Dashboards para visão operacional em tempo real
- 🔐 Comunicação criptografada com PSK

## 🧱 Stack do ambiente

| Item | Valor |
|------|-------|
| Sistema do servidor | Rocky Linux 9 |
| Banco de dados | PostgreSQL 16 + TimescaleDB |
| Frontend | Nginx + PHP-FPM |
| Coleta | Zabbix Agent 2 (ativo + passivo) |

## 🏗️ Arquitetura

```mermaid
flowchart LR
    subgraph Hosts["🖥️ Hosts monitorados"]
        A1[Agent 2 - Linux]
        A2[Agent 2 - Windows]
