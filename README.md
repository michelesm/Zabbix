**Relatório sobre a Ferramenta Zabbix e Passo a Passo de Demonstração**

---

**1. Introdução ao Zabbix**

O Zabbix é uma ferramenta open-source de monitoramento de infraestrutura de TI. Ele é amplamente utilizado para monitorar redes, servidores, serviços em nuvem, máquinas virtuais, dispositivos IoT e até mesmo aplicações. O Zabbix coleta dados em tempo real de uma variedade de dispositivos e sistemas, permitindo uma visão completa da performance, disponibilidade e saúde da infraestrutura. As principais funcionalidades incluem monitoramento de disponibilidade, coleta e exibição de métricas, geração de alertas e relatórios, e integração com outras ferramentas.

**2. Funcionalidades do Zabbix**

- **Monitoramento de dispositivos e serviços:** Rastreia o desempenho e disponibilidade de dispositivos de rede, servidores, VMs e aplicativos.
- **Alertas e notificações:** Notifica em tempo real quando um parâmetro de desempenho ultrapassa um limite, com opções de alerta via e-mail, SMS, webhook etc.
- **Coleta e exibição de métricas:** Permite visualizar dados históricos e tendências.
- **Dashboard e relatórios customizáveis:** Oferece dashboards e relatórios para análises e auditorias.
- **Suporte a integrações:** Pode ser integrado a plataformas como Grafana, ServiceNow, PagerDuty, entre outros.

**3. Instalação Básica do Zabbix**

Para realizar uma instalação simples, você precisará de um servidor (recomendado Ubuntu ou CentOS) para hospedar o Zabbix Server. O Zabbix possui três componentes principais:
- **Zabbix Server**: Gerencia a coleta de dados e armazenamento.
- **Zabbix Agent**: Instalado nos dispositivos a serem monitorados.
- **Interface Web**: Dashboard de visualização e configuração.

**4. Demonstração: Monitoramento de um Servidor Linux com Zabbix**

Abaixo, um passo a passo para configurar o Zabbix para monitorar um servx'idor Linux.

---

### Passo a Passo de Configuração do Zabbix

#### 4.1 Instalação do Zabbix Server
1. **Configuração do ambiente**: O Zabbix requer um servidor com MySQL/MariaDB, Apache/Nginx e PHP.
   
2. **Instalação do Zabbix Server**:
   - No terminal do servidor Linux, adicione o repositório do Zabbix:
     ```bash
     sudo apt update
     sudo apt install -y wget
     wget https://repo.zabbix.com/zabbix/5.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_5.0-1+ubuntu18.04_all.deb
     sudo dpkg -i zabbix-release_5.0-1+ubuntu18.04_all.deb
     sudo apt update
     ```
   - Instale o Zabbix Server e o Frontend:
     ```bash
     sudo apt install zabbix-server-mysql zabbix-frontend-php zabbix-apache-conf zabbix-agent
     ```

3. **Configuração do banco de dados**:
   - Crie um banco de dados para o Zabbix e configure o acesso.
   - Após criar o banco de dados, configure o Zabbix para usá-lo:
     ```bash
     sudo nano /etc/zabbix/zabbix_server.conf
     ```
   - Edite o arquivo e informe as credenciais do banco de dados.

4. **Inicie o Zabbix Server**:
   ```bash
   sudo systemctl start zabbix-server
   sudo systemctl enable zabbix-server
   ```

5. **Configuração do Frontend Web**:
   - Abra o navegador e acesse `http://<IP-do-servidor>/zabbix`.
   - Siga o assistente de instalação e defina as configurações.

#### 4.2 Configuração do Zabbix Agent (no Servidor Monitorado)

Para monitorar um servidor específico, instale o Zabbix Agent nele.
1. **Instale o Zabbix Agent**:
   ```bash
   sudo apt update
   sudo apt install zabbix-agent
   ```

2. **Configure o Zabbix Agent**:
   - Edite o arquivo de configuração:
     ```bash
     sudo nano /etc/zabbix/zabbix_agentd.conf
     ```
   - Configure o servidor e o hostname do agente:
     ```conf
     Server=<IP-do-Zabbix-Server>
     Hostname=<Nome-do-Host>
     ```
   
3. **Inicie o Zabbix Agent**:
   ```bash
   sudo systemctl start zabbix-agent
   sudo systemctl enable zabbix-agent
   ```

4. **Adicionar o Host no Zabbix Server**:
   - No Zabbix Frontend, vá até `Configuration` > `Hosts`.
   - Clique em `Create Host`, preencha o hostname e o endereço IP do agente.
   - Adicione templates de monitoramento, como "Template OS Linux" para coletar métricas de CPU, memória e disco.

#### 4.3 Monitoramento e Dashboards

- Após a configuração do host, o Zabbix começará a coletar métricas do sistema. 
- Você pode criar dashboards personalizados em `Monitoring` > `Dashboards`.
- Configure gráficos e widgets para exibir as métricas de CPU, memória e uso de disco, e veja o histórico de dados em `Monitoring` > `Latest data`.

---

**5. Exemplo Básico de Monitoramento**

Para ilustrar o uso do Zabbix, abaixo está um exemplo básico de monitoramento de CPU e memória:

1. **Monitoramento da CPU**:
   - Vá para `Monitoring` > `Graphs`.
   - Selecione o servidor monitorado.
   - Clique no gráfico da CPU para observar o uso ao longo do tempo.

2. **Alertas de Utilização de Memória**:
   - Em `Configuration` > `Actions`, crie uma ação que envie uma notificação quando a utilização de memória ultrapassar 80%.
   - Defina o destinatário e a mensagem de alerta.

---

**6. Conclusão**

O Zabbix é uma ferramenta completa e versátil para monitoramento de infraestrutura de TI. Ele se destaca pela sua capacidade de coletar e exibir métricas detalhadas, além de ser altamente configurável para atender diferentes necessidades de monitoramento. Através deste guia, cobrimos uma instalação básica e as primeiras etapas para monitorar um servidor Linux. Com o Zabbix, é possível criar um sistema de monitoramento robusto, escalável e adaptado ao ambiente corporativo, facilitando a detecção de problemas e ajudando na prevenção de falhas na infraestrutura de TI.
