<div align="center">

# 🪤 Cowrie Honeypot Lab

**Laboratório prático de Cibersegurança utilizando o Cowrie Honeypot**

Estudo de ataques SSH, força bruta, análise de logs e atividades suspeitas.

<p>
  <img src="https://img.shields.io/badge/Linux-Ubuntu-orange?style=for-the-badge&logo=ubuntu&logoColor=white" alt="Ubuntu">
  <img src="https://img.shields.io/badge/Cowrie-Honeypot-red?style=for-the-badge" alt="Cowrie">
  <img src="https://img.shields.io/badge/SSH-Security-blue?style=for-the-badge&logo=openssh&logoColor=white" alt="SSH">
  <img src="https://img.shields.io/badge/Oracle%20Cloud-Server-F80000?style=for-the-badge&logo=oracle&logoColor=white" alt="Oracle Cloud">
</p>

</div>

---

## 🎯 Sobre o Projeto

Este projeto consiste na criação de um laboratório controlado de Cibersegurança utilizando o **Cowrie Honeypot**. 
O objetivo é simular um serviço SSH vulnerável e observar como sistemas automatizados e agentes maliciosos interagem com o sistema. O laboratório possui finalidade puramente educacional, permitindo estudar técnicas de monitoramento, análise de logs e segurança em servidores Linux.

---

## 🎯 Objetivos

Durante o desenvolvimento do laboratório, serão estudados:

* 🔐 Tentativas de autenticação SSH
* 🔑 Ataques de força bruta
* 💻 Comandos executados nas sessões
* 📋 Análise detalhada de logs
* 🐧 Segurança em servidores Linux
* 📊 Monitoramento de atividades suspeitas
* 🌐 Mapeamento e análise de endereços IP de origem

---

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Utilização |
| :--- | :--- |
| 🐧 **Ubuntu Linux** | Sistema operacional do servidor |
| 🪤 **Cowrie** | Honeypot SSH interativo |
| 🔐 **SSH** | Serviço simulado no laboratório |
| ☁️ **Oracle Cloud** | Hospedagem da infraestrutura do servidor |
| 🐙 **Git / GitHub** | Versionamento e documentação |

---

## 🖥️ Configuração do Servidor

O laboratório é executado em um servidor virtual Ubuntu Linux hospedado na Oracle Cloud.

> **Nota:** As especificações de CPU, Memória RAM, Armazenamento e configurações de rede são documentadas na pasta `docs/` conforme a evolução do ambiente.

---

## 🪤 Instalação e Configuração do Cowrie

O Cowrie será configurado para atuar como um honeypot SSH de média/alta interação. As etapas planejadas e executadas incluem:

1. Instalação de dependências do sistema
2. Configuração do ambiente virtual Python e do Cowrie
3. Ajustes nos arquivos de configuração (`cowrie.cfg`)
4. Redirecionamento de portas e inicialização do serviço
5. Coleta e centralização dos logs

---

## 🔐 Monitoramento e Simulação SSH

Como o SSH é o principal vetor de interação, o laboratório registra:
* Tentativas de login bem e mal-sucedidas
* Combinações de usuários e senhas mais utilizadas (`root`, `admin`, etc.)
* Comandos digitados pelos agentes maliciosos dentro da sessão simulada
* Horários das conexões e IPs de origem

---

## 📊 Análise dos Logs

O Cowrie armazena telemetria detalhada sobre todas as interações. Os principais campos analisados são:

| Informação | Descrição |
| :--- | :--- |
| 🌐 **IP** | Endereço de origem da conexão |
| 📅 **Data/Hora** | Momento exato da tentativa de acesso |
| 👤 **Usuário** | Credencial utilizada na autenticação |
| 🔑 **Autenticação** | Sucesso ou falha no login |
| 💻 **Comandos** | Ações executadas durante a invasão simulada |
| ⚠️ **Atividade** | Comportamentos e padrões considerados maliciosos |

---

## 📸 Evidências dos Testes

> *As evidências, capturas de tela e exemplos reais de ataques capturados serão adicionados na pasta `screenshots/` e `logs/` conforme a evolução do projeto.*

---

## 🚧 Status do Projeto

🟡 **Em desenvolvimento**

- ✅ Criar repositório
- ✅ Definir objetivo do laboratório
- ✅ Definir tecnologias utilizadas
- ✅ Criar documentação inicial (`README.md`)
- ✅ Configurar servidor Ubuntu na Oracle Cloud
- ✅ Instalar e configurar o Cowrie
- ✅ Realizar testes controlados
- ✅ Analisar logs capturados
- ✅ Adicionar evidências e capturas de tela

---

## 📂 Estrutura do Repositório

```text
Cowrie-Honeypot-Lab/
├── [README.md](README.md)
├── [docs/](docs/)
│   └── [configuracao.md](docs/configuracao.md)
├── [screenshots/](screenshots/)
│   └── [cowrie/](screenshots/cowrie/)
└── [logs/](logs/)
    ├── [iocs.txt](logs/iocs.txt)
    └── [cowrie-session-sample.json](logs/cowrie-session-sample.json)
```
## 🔍 Análises de Ataques Capturados

Nesta seção, documento casos reais de interações maliciosas capturadas pelo laboratório.

### 🛡️ Caso: Automação SSH (Botnet em Go)

* 📅 **Data:** 14/08/2026
* 📝 **Resumo:** Captura de um bot automatizado que utilizou credenciais `admin:admin` e tentou realizar download de payloads via SCP/cURL.

| Indicador Técnico | Detalhe da Evidência |
| :--- | :--- |
| 🌐 **IP Origem** | `130.12.180.51` |
| 🤖 **Tipo de Bot** | `SSH-2.0-Go` |
| ⚡ **Ação do Atacante** | Tentativa de deploy de chave privada e execução remota |
| 🎯 **Servidor C2** | `217.60.195.113` |

### 💡 Lições Aprendidas

* 🔒 A importância crítica de evitar o uso de credenciais padrão (`admin:admin`).
* ⚙️ Como agentes maliciosos automatizam o bypass de verificação de chaves SSH (`StrictHostKeyChecking no`).
* 📊 O valor prático de logs detalhados para mapear a infraestrutura de Comando e Controle (C2) de botnets.

> 📌 **Nota:** A documentação técnica completa e as evidências brutas detalhadas estão arquivadas na pasta `/logs` deste repositório.
