---

# ****

**Living Lab Fiqueok | Pasta: 04_PROJETOS_META**  
**Documento de Roadmap Tecnológico | Versão 1.0 | Janeiro 2026**

---

## **Contexto e Propósito Estratégico**

Este documento registra a evolução arquitetural do Living Lab Fiqueok, detalhando a transição de um modelo proprietário de Privileged Access Management (PAM) para um ecossistema moderno e auditável baseado em tecnologias Open Source. A arquitetura futura implementa os princípios de Zero Trust Network Access (ZTNA), microsegmentação por VLANs e governança de identidades (IGA) alinhadas às normas ISO 27001 e CIS Controls.[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​[fortinet+2](https://www.fortinet.com/br/resources/cyberglossary/what-is-ztna)

Esta é uma **reserva de conhecimento estratégico** que orientará a implementação completa do lab após a consolidação da infraestrutura básica. O documento serve como memória de longo prazo e guia de retomada para a próxima fase de desenvolvimento do projeto.[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​

---

## **Evolução Tecnológica: Do Proprietário ao Open Source**

## **Arquitetura Legada (BeyondTrust 2023)**

A arquitetura original representada no diagrama BeyondTrust configurava um modelo tradicional de PAM baseado em soluções comerciais centralizadas. Este modelo apresentava limitações técnicas e de governança:[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/images/69453806/18613bf3-d5ae-44bd-88d6-d0c4d16c0fba/BeyondTrust.drawio.jpg?AWSAccessKeyId=ASIA2F3EMEYEQRT3N7NP&Signature=Nb0gwUdM6YWL9orQuqGuuR%2FIerM%3D&x-amz-security-token=IQoJb3JpZ2luX2VjEBoaCXVzLWVhc3QtMSJGMEQCIBtVX203Yq04p5Yzsz9cDRMWif%2BxFbzrdPCn7emu90RyAiAAop6T3oly80raFsECdSebSEPdw%2BkJ9MtynohYR2VOjir8BAjj%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F8BEAEaDDY5OTc1MzMwOTcwNSIMlEwKdgoKN%2F%2FvONfvKtAEme8va2AzgM6JRPG9tz9M1c6Bpai1bpiNwUaeG3veTHMEMCsNGm68vh%2B5Pm29WYXm8iXW3osw%2B8Fgoy%2F85nc4YwfTMO08zIxITZRc5e0CoBHP3ZE%2FiYBGHueZEBcPHJkywiw%2BzSWCi%2BuDtLGu%2BD0%2FLlBI%2F%2BI%2FHwIw2rYLIv9INE%2FFWW9T2MGyU1wJAmRpF2i1FRlbwjwHrhQHAZpBFZzYM0gBJh7ripWBmvMrM9yvZgNtFol2MFnFjnJp88ErkILMYEFNSimvqibutMA%2BCbXCr8Ed7TlXY1b1E%2FPwFJMlXFYRQKL59TG12jdakHYuhBwHg%2BzdFsxnkPiVNtPiKGrr2fXC7Wyb5Yq1AvlGyIMOKOvehTw4RVA8cZ9cEMl6MLVvnydH2uFYV%2F%2FdF6eBXJbRAew2s8fOPLniPJzmNTMarPOekfhKnMEpOviUrW0%2F7UVZnOsEs1nir86QlyK7HUPZW9mkYUf4b%2BoeLuJNUsAN1wwSoep0Dv8g4XaV%2F4Gj%2FfJZ30%2BQmRQoWsszi%2Bw7aBc75Q0%2B4T2JEAydtb%2F%2BdDo%2FyNNeOuDHzUo%2Fnx%2F8dsnXKtE0sZ9lX9ALEQcQxgyrkBPXGcCRKvDv%2BeHultEJVU%2FgqKOYmDv4Top0IG4Ia1%2BaZAQiW1yB7KMdz3%2F%2FI9sanXxokNtqrZxui7lY%2FUd%2B%2BQaoiG2qyWbL%2FGtuwm0uFodz9VDAGLvF%2BRCYrqKDi3TNva2jPxmyjvAoIkkP1bj8WTn%2BtjQLNQdbjauSl6W8UDLcFhWEVllX9lJYNMFOIkU2qN7ZSjDfxsnLBjqZAVWUbdxa%2FAjGUwKJhYSH7fSV3cqXP4fCKF6N5gd7fI2U8kkHF5OEjBXHUS0%2Fx%2Bofr05OYnH2nBzK%2FKt7lxH9LObNFf7E5YE4Y6dp6vfhgbOB1wns%2FFGfyVf3D0VC7QOuziTOe1gNuWQtloUZR%2BhcMgrCsSsE0IPhNFjedzMGr9sbpMVjq7sU%2B99DOibkr4UCxVDhj2WmRPimgg%3D%3D&Expires=1769106142)]​

- **Vendor Lock-in**: Dependência de licenças proprietárias com custos recorrentes e restrições de customização
    
- **Visibilidade Limitada**: Auditoria de sessão restrita às capacidades nativas da plataforma, dificultando a integração com frameworks de conformidade
    
- **Baixa Portabilidade**: Dificuldade de replicação em ambientes HomeLab para fins educacionais e de co-criação
    

## **Stack Moderno Open Source (2026)**

A arquitetura futura adota um stack integralmente Open Source que replica funcionalidades corporativas de PAM e IGA com total rastreabilidade e conformidade:[[ssh](https://www.ssh.com/academy/compliance/how-to-ensure-iso-compliance-with-pam)]​[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​

|**Componente**|**Função**|**Localização**|**Justificativa Técnica**|
|---|---|---|---|
|**midPoint**|IGA Maestro (Identity Governance and Administration)|192.168.68.116 (VLAN 68)|Motor de orquestração de identidades com suporte nativo a RBAC, SoD e auditoria completa [[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​|
|**Teleport Proxy**|Gateway de Acesso Privilegiado|192.168.70.10 (VLAN 70)|Proxy ZTNA com auditoria de sessão SSH/RDP/Kubernetes e certificados de curta duração [[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​[[exabeam](https://www.exabeam.com/explainers/zero-trust/zero-trust-in-2026-principles-technologies-and-best-practices/)]​|
|**Apache Guacamole**|Gateway de Acesso Remoto (RDP/SSH via Browser)|192.168.70.20 (VLAN 70)|Interface web clientless para acesso auditado sem necessidade de clientes VPN [[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​|
|**OrangeHRM**|Identity Source of Truth (HR System)|192.168.68.100 (VLAN 68)|Sistema HR que alimenta midPoint com dados autoritativos de identidades (joiner/mover/leaver) [[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​|
|**HashiCorp Vault**|Gestão de Secrets e Credenciais Dinâmicas|192.168.71.20 (VLAN 71)|Injeção automatizada de credenciais rotacionadas para aplicações via midPoint [[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​|
|**Active Directory**|Diretório de Autenticação Corporativo|192.168.71.10 (VLAN 71)|Target system provisionado automaticamente pelo midPoint via LDAPS (porta 636) [[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​|

**Vantagem de Governança**: Todo o stack é auditável via GitLab (desenvolvimento) e GitHub (produção), implementando o conceito de **Governança-as-Code** onde alterações de configuração são versionadas e revisadas conforme ISO 27001 A.12.1.2 (Change Control).[apono+1](https://www.apono.io/blog/components-for-a-privileged-access-management-audit/)

---

## **Topologia de Rede: Microsegmentação e Isolamento**

## **Arquitetura de VLANs e Zonas de Segurança**

A arquitetura implementa **microsegmentação baseada em VLANs** seguindo os princípios de Defense in Depth e Least Privilege Network Access do CIS Control 12 (Network Infrastructure Management):[[fortinet](https://www.fortinet.com/br/resources/cyberglossary/what-is-ztna)]​[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​

## **VLAN 70 - Access Zone (DMZ de Acesso)**

- **Componentes**: Teleport Proxy (192.168.70.10) | Apache Guacamole (192.168.70.20)
    
- **Função**: Zona desmilitarizada que recebe conexões externas e implementa o primeiro nível de autenticação
    
- **Controles**: Nenhum acesso direto a sistemas internos; todo tráfego é mediado por proxies autenticados[[exabeam](https://www.exabeam.com/explainers/zero-trust/zero-trust-in-2026-principles-technologies-and-best-practices/)]​[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​
    

## **VLAN 68 - IGA & Governance Zone**

- **Componentes**: midPoint (192.168.68.116) | OrangeHRM (192.168.68.100)
    
- **Função**: Zona de orquestração de identidades e governança, isolada de zonas de produção
    
- **Fluxo de Dados**: OrangeHRM sincroniza identidades com midPoint via CSV/API; midPoint provisiona contas em sistemas downstream[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​
    

## **VLAN 71 - Core Infrastructure**

- **Componentes**: Active Directory (192.168.71.10) | HashiCorp Vault (192.168.71.20)
    
- **Função**: Serviços críticos de autenticação e gestão de secrets
    
- **Controles**: Acesso restrito via LDAPS (porta 636) provisionado pelo midPoint; secrets injetados dinamicamente em aplicações[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​
    

## **VLAN 72 - Application Zone**

- **Componentes**: Sistema ERP (192.168.72.50)
    
- **Função**: Zona de aplicações de negócio com acesso auditado
    
- **Acesso**: Conexões RDP/SSH mediadas exclusivamente via Teleport Proxy (porta 3389/22 auditadas)[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​
    

## **Fluxos de Tráfego e Controles de Auditoria**

Conforme especificado no arquivo XML da arquitetura:[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​

1. **Identity Provisioning (LDAPS/636)**: midPoint → Active Directory  
    _Sincronização de contas seguindo políticas RBAC e SoD_
    
2. **Secret Injection**: midPoint → HashiCorp Vault  
    _Injeção de credenciais rotacionadas para aplicações sem armazenamento local_
    
3. **Audited Access (3389/22)**: Teleport Proxy → Sistema ERP  
    _Todas as sessões RDP/SSH são gravadas e indexadas para auditoria conforme ISO 27001 A.9.4.3 (Session Recording)_[ssh+1](https://www.ssh.com/academy/compliance/how-to-ensure-iso-compliance-with-pam)
    
4. **Identity Sync (CSV/API)**: OrangeHRM → midPoint  
    _Alimentação do IGA com dados autoritativos de RH (contratações, movimentações, desligamentos)_
    

---

## **Paradigma Zero Trust Network Access (ZTNA)**

## **Transição de VPN para ZTNA**

A arquitetura futura elimina o modelo tradicional de VPN baseado em rede plana, substituindo-o por acesso baseado em identidade e contexto conforme os princípios ZTNA do NIST SP 800-207:[trevonix+2](https://trevonix.com/blogs/7-pillars-of-zero-trust/)

**Limitações do Modelo VPN Tradicional**:

- **Acesso em Nível de Rede**: Uma vez conectado, o usuário obtém visibilidade de toda a rede interna, violando o Princípio do Privilégio Mínimo[[fortinet](https://www.fortinet.com/br/resources/cyberglossary/what-is-ztna)]​
    
- **Falta de Auditoria Granular**: VPNs registram apenas conexão/desconexão, sem visibilidade sobre comandos executados ou dados acessados[[apono](https://www.apono.io/blog/components-for-a-privileged-access-management-audit/)]​
    
- **Exposição de Portas**: Serviços internos precisam ter portas abertas acessíveis pela VPN, aumentando a superfície de ataque[[netfoundry](https://netfoundry.io/vpns/tailscale-and-wireguard-versus-netfoundry-and-openziti/)]​
    

**Modelo ZTNA Proposto**: A arquitetura implementa ZTNA através de duas tecnologias complementares:[venn+1](https://www.venn.com/learn/zero-trust/ztna/)[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​

## **Teleport como ZTNA Broker**

Teleport atua como gateway que valida identidade, contexto de dispositivo e política de acesso antes de conceder acesso a recursos específicos:[exabeam+1](https://www.exabeam.com/explainers/zero-trust/zero-trust-in-2026-principles-technologies-and-best-practices/)

- **Certificados de Curta Duração**: Substituição de senhas por certificados X.509 com validade de minutos, emitidos após autenticação MFA[[exabeam](https://www.exabeam.com/explainers/zero-trust/zero-trust-in-2026-principles-technologies-and-best-practices/)]​
    
- **Per-Service Access**: Acesso granular a serviços específicos (SSH, RDP, Kubernetes) sem exposição de rede[venn+1](https://www.venn.com/learn/zero-trust/ztna/)
    
- **Session Recording**: Gravação integral de sessões com indexação de comandos executados, atendendo ISO 27001 A.12.4.1 (Event Logging)[ssh+1](https://www.ssh.com/academy/compliance/how-to-ensure-iso-compliance-with-pam)
    

## **Headscale ou OpenZiti para Mesh Networking**

**Contexto Futuro (Fase 2)**: Após consolidação do Teleport, o lab avaliará implementação de mesh networking para eliminar completamente a necessidade de VPN e NAT traversal:[reddit+1](https://www.reddit.com/r/selfhosted/comments/1fnd9iv/just_another_secure_deployment_model_for/)

**Headscale (WireGuard-based)**:

- **Modelo de Confiança**: Identidade em nível de dispositivo (device keys) com ACLs baseadas em tags[[netfoundry](https://netfoundry.io/vpns/tailscale-and-wireguard-versus-netfoundry-and-openziti/)]​
    
- **Caso de Uso**: Conectividade ponto-a-ponto para equipes pequenas com controle via ACLs[reddit+1](https://www.reddit.com/r/selfhosted/comments/1fnd9iv/just_another_secure_deployment_model_for/)
    
- **Limitação**: Identidade "morre" na saída do túnel; microsegmentação por serviço requer proxies adicionais[[netfoundry](https://netfoundry.io/vpns/tailscale-and-wireguard-versus-netfoundry-and-openziti/)]​
    

**OpenZiti (Socket-Level ZTNA)**:

- **Modelo de Confiança**: Identidade em nível de socket/serviço com certificados X.509 por serviço, não por dispositivo[[netfoundry](https://netfoundry.io/vpns/tailscale-and-wireguard-versus-netfoundry-and-openziti/)]​
    
- **Caso de Uso**: Ambientes que exigem revogação granular de serviços individuais sem impactar o host[[netfoundry](https://netfoundry.io/vpns/tailscale-and-wireguard-versus-netfoundry-and-openziti/)]​
    
- **Vantagem**: Serviços não precisam portas abertas (SDKs dialout); política aplicada antes do primeiro byte[[netfoundry](https://netfoundry.io/vpns/tailscale-and-wireguard-versus-netfoundry-and-openziti/)]​
    
- **Alinhamento ao Lab**: Ideal para simulações de ambientes multi-tenant e OT/edge com requisitos rigorosos de auditoria[[netfoundry](https://netfoundry.io/vpns/tailscale-and-wireguard-versus-netfoundry-and-openziti/)]​
    

**Decisão Estratégica**: OpenZiti alinha-se melhor aos objetivos de conformidade do lab por implementar identidade contínua e revogação cirúrgica, mas Headscale pode ser usado como stepping stone devido à menor curva de aprendizado.[reddit+1](https://www.reddit.com/r/selfhosted/comments/1fnd9iv/just_another_secure_deployment_model_for/)

## **Princípios ZTNA Implementados**

Conforme frameworks NIST e ISO 27001:[trevonix+2](https://trevonix.com/blogs/7-pillars-of-zero-trust/)

|**Princípio ZTNA**|**Implementação no Lab**|**Controle Normativo**|
|---|---|---|
|**Verify Explicitly**|MFA obrigatório + validação de device posture antes de cada acesso [fortinet+1](https://www.fortinet.com/br/resources/cyberglossary/what-is-ztna)|ISO 27001 A.9.2.1 (User Registration and De-registration) [[ssh](https://www.ssh.com/academy/compliance/how-to-ensure-iso-compliance-with-pam)]​|
|**Least Privilege Access**|Acesso por serviço via Teleport; sem exposição de rede [venn+1](https://www.venn.com/learn/zero-trust/ztna/)|CIS Control 6.8 (Define and Maintain Role-Based Access Control)|
|**Assume Breach**|Monitoramento contínuo de sessões; logs centralizados; micro-segmentação por VLAN [[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​[[fortinet](https://www.fortinet.com/br/resources/cyberglossary/what-is-ztna)]​|ISO 27001 A.12.4.1 (Event Logging) + A.16.1.7 (Collection of Evidence) [ssh+1](https://www.ssh.com/academy/compliance/how-to-ensure-iso-compliance-with-pam)|
|**Encrypted Tunnels**|TLS/mTLS para todos os fluxos; LDAPS (636) para provisionamento [[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​[[venn](https://www.venn.com/learn/zero-trust/ztna/)]​|ISO 27001 A.10.1.1 (Policy on Cryptographic Controls)|
|**Application-Level Gateways**|Teleport Proxy + Guacamole como brokers; nenhum acesso direto à rede [[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​[[exabeam](https://www.exabeam.com/explainers/zero-trust/zero-trust-in-2026-principles-technologies-and-best-practices/)]​|CIS Control 12.2 (Establish and Maintain a Secure Network Architecture)|

---

## **Justificativa de Governança, Risco e Conformidade (GRC)**

## **Alinhamento com ISO 27001**

A arquitetura implementa controles específicos do Annex A da ISO 27001:2022:[apono+1](https://www.apono.io/blog/components-for-a-privileged-access-management-audit/)

**A.9.1.1 - Access Control Policy**:  
Política de acesso baseada em RBAC orquestrada pelo midPoint, com revisão automatizada de privilégios e segregação de funções (SoD).[[ssh](https://www.ssh.com/academy/compliance/how-to-ensure-iso-compliance-with-pam)]​[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​

**A.9.2.2 - Privileged Access Management**:  
Todos os acessos privilegiados são mediados pelo Teleport Proxy com autenticação MFA, certificados de curta duração e gravação integral de sessão.[apono+1](https://www.apono.io/blog/components-for-a-privileged-access-management-audit/)

**A.9.2.4 - Review of User Access Rights**:  
midPoint implementa workflows de recertificação de acesso com notificações automáticas para gestores e auditoria de não-conformidades.[[ssh](https://www.ssh.com/academy/compliance/how-to-ensure-iso-compliance-with-pam)]​

**A.12.4.1 - Event Logging**:  
Logs centralizados de todas as sessões privilegiadas via Teleport, com retenção de 12 meses e indexação de comandos executados para análise forense.[apono+1](https://www.apono.io/blog/components-for-a-privileged-access-management-audit/)

**A.12.4.3 - Administrator and Operator Logs**:  
Logs de administradores são segregados e protegidos contra adulteração, com envio para SIEM externo (futuro).[[apono](https://www.apono.io/blog/components-for-a-privileged-access-management-audit/)]​

## **Alinhamento com CIS Controls v8**

**CIS Control 6 - Access Control Management**:  
Implementação de privilégio mínimo via midPoint com provisionamento automatizado baseado em funções de negócio definidas no OrangeHRM.[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​

**CIS Control 6.8 - Define and Maintain Role-Based Access Control**:  
Matriz RACI e políticas de acesso versionadas no GitLab, auditadas antes de promoção ao GitHub Brain.[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​

**CIS Control 12 - Network Infrastructure Management**:  
Microsegmentação por VLANs com firewalls virtuais (futuro) e regras de tráfego explícitas documentadas em código (IaC via Terraform/Ansible).[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​

## **Auditoria de Sessão e Visibilidade Total**

**Requisito Crítico de Conformidade**: Demonstrar que todos os acessos privilegiados são rastreáveis, auditáveis e vinculados a identidades reais.[ssh+1](https://www.ssh.com/academy/compliance/how-to-ensure-iso-compliance-with-pam)

**Implementação no Lab**:[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​

1. **Gravação de Sessão**: Teleport grava todas as sessões SSH/RDP em formato reproduzível (sessão pode ser "assistida" como vídeo)
    
2. **Indexação de Comandos**: Comandos digitados são indexados, permitindo busca por ações específicas (ex: "sudo rm", "DROP DATABASE")
    
3. **Metadata de Contexto**: Cada sessão registra: usuário autenticado, dispositivo de origem, horário, duração, recursos acessados
    
4. **Trilha de Auditoria End-to-End**:
    
    - OrangeHRM → midPoint (fonte de verdade de identidades)
        
    - midPoint → Active Directory (provisionamento auditado via LDAPS)
        
    - midPoint → Vault (injeção de secrets com rotação automática)
        
    - Teleport → Aplicações (acesso auditado com gravação de sessão)
        

**Valor para Auditoria**: Em uma auditoria ISO 27001, o lab pode apresentar evidências completas de todo o ciclo de vida de acesso privilegiado, desde a criação de conta até a desativação, incluindo todos os comandos executados.[ssh+1](https://www.ssh.com/academy/compliance/how-to-ensure-iso-compliance-with-pam)

---

## **Roadmap de Implementação**

## **Fase 1 - Fundação (Atual)**

- Consolidar infraestrutura de virtualização Hyper-V conforme Política de Acesso
    
- Estabelecer workflow GitLab → GitHub Brain
    
- Implementar VLAN 71 (Core Infrastructure) com Active Directory básico
    

## **Fase 2 - Governança de Identidades**

- Implementar VLAN 68 (IGA Zone) com midPoint e OrangeHRM
    
- Configurar provisionamento automatizado AD via LDAPS
    
- Estabelecer workflows de joiner/mover/leaver
    

## **Fase 3 - Acesso Privilegiado e ZTNA**

- Implementar VLAN 70 (Access Zone) com Teleport Proxy e Guacamole
    
- Configurar gravação de sessão e auditoria de comandos
    
- Eliminar VPN tradicional em favor de acesso via Teleport
    

## **Fase 4 - Mesh Networking e ZTNA Avançado**

- Avaliar Headscale vs OpenZiti para substituição completa de VPN
    
- Implementar identidade em nível de serviço (OpenZiti) ou dispositivo (Headscale)
    
- Eliminar portas expostas e NAT traversal
    

## **Fase 5 - Secrets Management e Automação**

- Implementar HashiCorp Vault (VLAN 71)
    
- Configurar rotação automática de credenciais via midPoint
    
- Integrar Vault com aplicações via secret injection
    

---

## **Controles de Qualidade e Portabilidade**

## **Princípio HomeLab-First**

Todo colaborador deve replicar a topologia completa em seu HomeLab antes de submeter alterações ao GitLab:[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​

**Requisitos de Replicação**:

- 4 VMs mínimas: AD (VLAN 71), midPoint (VLAN 68), Teleport (VLAN 70), App Test (VLAN 72)
    
- Configuração de VLANs virtuais no Hyper-V
    
- Testes de conectividade entre zonas conforme fluxos especificados no XML[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​
    
- Documentação de evidências de testes (logs de provisionamento, gravações de sessão)
    

**Critérios de Aceitação**:

- Provisionamento automatizado de conta de teste via midPoint → AD funcional
    
- Acesso via Teleport Proxy com gravação de sessão habilitada
    
- Logs de auditoria exportados e indexados
    

---

## **Referências Técnicas e Normativas**

- **ISO/IEC 27001:2022** - Annex A.9 (Access Control), A.12.4 (Logging and Monitoring)[apono+1](https://www.apono.io/blog/components-for-a-privileged-access-management-audit/)
    
- **CIS Controls v8** - Control 6 (Access Control Management), Control 12 (Network Infrastructure)
    
- **NIST SP 800-207** - Zero Trust Architecture[fortinet+1](https://www.fortinet.com/br/resources/cyberglossary/what-is-ztna)
    
- **NIST SP 800-53 Rev. 5** - AC-2 (Account Management), AU-2 (Event Logging)[[ssh](https://www.ssh.com/academy/compliance/how-to-ensure-iso-compliance-with-pam)]​
    
- **Arquitetura XML Living Lab Fiqueok** - Especificação técnica de VLANs, IPs e fluxos[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​
    

---

## **Nota de Memória e Retomada**

**Contexto de Retomada**: Este documento será revisitado após a conclusão da **Fase 1 (Fundação)**, quando a infraestrutura básica de Hyper-V, Active Directory e workflow GitLab/GitHub estiver operacional.

**Próximos Passos na Retomada**:

1. Revisar este documento e validar se a arquitetura ainda atende aos objetivos estratégicos
    
2. Atualizar endereçamento IP e VLANs conforme ajustes de implementação
    
3. Iniciar **Fase 2 (Governança de Identidades)** com instalação de midPoint e OrangeHRM
    
4. Documentar desvios de arquitetura e lições aprendidas na Fase 1
    

**Localização do Documento**: `04_PROJETOS_META/VISAO_FUTURA_ZTNA_IGA.md`

---

**Documento elaborado conforme diretrizes de Governança-as-Code do Living Lab Fiqueok**  
**Última atualização**: 22 de Janeiro de 2026  
**Próxima revisão**: Conclusão da Fase 1 de Infraestrutura