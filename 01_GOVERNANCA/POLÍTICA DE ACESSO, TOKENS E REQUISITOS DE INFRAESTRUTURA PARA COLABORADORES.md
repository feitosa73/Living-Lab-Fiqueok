---


**Living Lab Fiqueok | Pasta: 01_GOVERNANCA**  
**Documento de Governança Técnica | Versão 1.1 | Janeiro 2026**

---

## **Objetivo e Escopo**

Este documento estabelece os requisitos obrigatórios de infraestrutura, virtualização e gestão de acesso para colaboradores do Living Lab Fiqueok. A política alinha-se aos controles de acesso da **ISO 27001:2022** - especificamente **Annex A.5.15 a A.5.18** (Controles Organizacionais de Acesso) e **Annex A.8.2 a A.8.5** (Controles Tecnológicos de Acesso Privilegiado) - garantindo que o ambiente de experimentação replique práticas corporativas de segurança e conformidade.[isms+4](https://www.isms.online/iso-27001/annex-a-2022/how-to-implement-iso-27001-2022-annex-a-control-5-18-access-rights/)[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/images/69453806/c22adc6b-7cd2-4d45-8f66-fa353d747873/Fiqueok-Arq1.drawio.jpg)]​

O Living Lab opera como ecossistema de co-criação onde colaboradores validam soluções de IAM (Identity and Access Management) e GRC (Governance, Risk and Compliance) em cenários simulados reais. Todo colaborador deve replicar topologias em seu HomeLab antes de submeter alterações ao repositório de desenvolvimento no GitLab, assegurando portabilidade e qualidade técnica das soluções.

---

## **Requisitos de Infraestrutura de Hardware**

## **Especificações Mínimas Obrigatórias**

Todo colaborador deve dispor de estação de trabalho que atenda aos seguintes requisitos técnicos:[[cyfuture](https://cyfuture.cloud/kb/cloud-server/what-is-the-benefit-of-type-1-hypervisors)]​

- **Processador**: CPU multi-core com no mínimo 4 núcleos físicos (8 threads lógicos)
    
- **Memória RAM**: 16GB DDR4 (mínimo obrigatório) | 32GB DDR4 (fortemente recomendado)
    
- **Armazenamento**: SSD NVMe com no mínimo 256GB de espaço livre para VMs
    
- **Sistema Operacional**: Windows 10/11 Pro ou Enterprise (obrigatório para Hyper-V nativo) ou distribuições Linux homologadas
    

## **Justificativa Técnica**

Simulações de IGA (Identity Governance and Administration) exigem execução simultânea de múltiplas máquinas virtuais (Active Directory, servidores de aplicação, bancos de dados e ferramentas de IAM). Configurações com menos de 16GB RAM resultam em degradação de performance e instabilidade de rede virtual, comprometendo a validade dos testes de governança de identidade.[[aws.amazon](https://aws.amazon.com/compare/the-difference-between-type-1-and-type-2-hypervisors/)]​

## **Requisitos de Rede Virtual (Adendo)**

**Compatibilidade com Endereçamento Mestre**: O colaborador deve configurar sua rede interna no Hyper-V para compatibilidade com o endereçamento IP mestre do Living Lab, facilitando a integração futura com componentes compartilhados:[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​

- **Rede Padrão do Lab**: 192.168.68.0/24 (IGA & Governance Zone - VLAN 68)
    
- **Gateway Recomendado**: 192.168.68.1
    
- **Exemplo de Alocação**: midPoint IGA Maestro está configurado no IP 192.168.68.116 no ambiente de referência[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​
    

**Recomendação de Implementação**: Configure switches virtuais internos no Hyper-V com sub-redes estáticas para simular a topologia de VLANs do lab (VLAN 68, 70, 71, 72), permitindo testes de microsegmentação e fluxos de provisionamento de identidades entre zonas.[[ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/69453806/2aab932f-d658-45ba-a77b-fa9bba066a6d/Arquitetura-Futura.xml)]​

---

## **Política de Virtualização e Hipervisores**

## **Hipervisor Primário: Hyper-V (Recomendado)**

O **Microsoft Hyper-V** é definido como hipervisor padrão do Living Lab Fiqueok pelas seguintes razões técnicas e de segurança:[cyfuture+1](https://cyfuture.cloud/kb/cloud-server/what-is-the-benefit-of-type-1-hypervisors)

- **Arquitetura Tipo 1 (Bare-Metal)**: O Hyper-V opera diretamente sobre o hardware físico, sem camada de sistema operacional intermediário, proporcionando maior isolamento entre máquinas virtuais e reduzindo a superfície de ataque[aws.amazon+1](https://aws.amazon.com/compare/the-difference-between-type-1-and-type-2-hypervisors/)
    
- **Padrão Corporativo**: É a tecnologia nativa de virtualização em ambientes Microsoft e Azure, alinhando o lab a práticas de mercado e facilitando transição para infraestruturas corporativas reais[learn.microsoft+1](https://learn.microsoft.com/en-us/windows-server/virtualization/hyper-v/overview)
    
- **Eficiência de Hardware**: Como hipervisor Tipo 1, oferece melhor desempenho de E/S de disco e rede, crítico para simulações de IAM que exigem comunicação intensiva entre VMs[reddit+1](https://www.reddit.com/r/virtualization/comments/xiqd1i/hyper_v_or_virtual_box_which_one_will_perform/)
    
- **Recursos de Segurança Integrados**: Suporta nativamente Secure Boot, BitLocker, e integração com VBS (Virtualization-based Security) do Windows, reforçando a postura de segurança do lab[xda-developers+1](https://www.xda-developers.com/reasons-hyper-v-best-hypervisor-windows/)
    

## **Hipervisor Secundário: VMware Workstation/Player**

VMware Workstation é aceito como alternativa secundária, desde que observados:[[cyfuture](https://cyfuture.cloud/kb/cloud-server/what-is-the-benefit-of-type-1-hypervisors)]​

- Licenciamento adequado para uso educacional/experimental
    
- Possíveis conflitos com recursos de segurança VBS do Windows devem ser avaliados
    
- Maior complexidade de configuração de redes virtuais internas
    

## **Restrição: VirtualBox (Não Recomendado)**

O uso de **Oracle VirtualBox é formalmente desencorajado** para laboratórios de IAM e IGA pelos seguintes motivos técnicos:[reddit+2](https://www.reddit.com/r/virtualization/comments/1doioxh/hyperv_or_virtual_box_for_tiny_home_lab_including/)

- **Instabilidade em Cenários Complexos**: VirtualBox apresenta problemas recorrentes de estabilidade em topologias de múltiplas VMs com redes virtuais internas complexas, típicas de labs de identidade e governança[reddit+1](https://www.reddit.com/r/virtualbox/comments/1kvbycq/virtualbox_better_for_labs_im_trying_to_do_this/)
    
- **Performance de E/S Inferior**: Como hipervisor Tipo 2, adiciona camada de abstração que degrada performance em operações de disco e rede intensivas[[reddit](https://www.reddit.com/r/virtualization/comments/xiqd1i/hyper_v_or_virtual_box_which_one_will_perform/)]​
    
- **Incompatibilidade com Hyper-V**: A coexistência de VirtualBox com Hyper-V habilitado gera conflitos de virtualização aninhada, afetando compatibilidade e estabilidade[[reddit](https://www.reddit.com/r/virtualization/comments/1doioxh/hyperv_or_virtual_box_for_tiny_home_lab_including/)]​
    

**Exceção**: VirtualBox pode ser utilizado apenas para testes pontuais de compatibilidade, mas não como plataforma principal de desenvolvimento.

---

## **Gestão de Acesso e Autenticação**

## **Princípio do Privilégio Mínimo para Tokens (PAT)**

Seguindo as diretrizes da **ISO 27001:2022 Annex A.5.15** (Access Control) e **Annex A.8.2** (Privileged Access Rights), todos os acessos programáticos ao GitHub devem observar o **Princípio do Privilégio Mínimo**:[hightable+3](https://hightable.io/iso-27001-annex-a-8-2-privileged-access-rights/)

- **Escopo Restrito**: Tokens de Acesso Pessoal (PAT) devem ter apenas os escopos mínimos necessários para a função específica[learn.microsoft+2](https://learn.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops)
    
- **Escopos Recomendados para Colaboradores**:
    
    - `repo` (acesso a repositórios privados, se necessário)
        
    - `read:org` (leitura de metadados organizacionais)
        
    - **Proibido**: escopos globais como `admin:org`, `delete_repo`, `workflow` sem justificativa técnica documentada e aprovação formal[iso27001+1](https://iso27001.com/iso-27001-annex-a-8-2-privileged-access-rights/)
        

**Autorização Formal**: Conforme **Annex A.8.2**, a concessão de tokens com escopos elevados deve seguir processo documentado de solicitação e aprovação, com segregação entre solicitante e aprovador.[hightable+1](https://hightable.io/iso-27001-annex-a-8-2-privileged-access-rights/)

## **Autenticação via GitHub CLI (gh)**

A autenticação no GitHub **deve ser realizada exclusivamente via GitHub CLI** (`gh`), evitando exposição de credenciais em arquivos de configuração ou variáveis de ambiente não protegidas:[cli.github+2](https://cli.github.com/manual/gh_auth_login)

**Fluxo de Autenticação Obrigatório**:

bash

`gh auth login --hostname github.com --git-protocol https --web`

**Requisitos de Segurança** (conformidade com **Annex A.5.17** - Authentication Information):[isms+1](https://www.isms.online/iso-27001/annex-a-2022/5-15-access-control-2022/)

- **MFA Ativo**: Autenticação multifator (MFA) é **obrigatória** para todos os colaboradores[hightable+2](https://hightable.io/iso-27001-annex-a-5-15-access-control/)
    
- **Token Storage Seguro**: O GitHub CLI armazena tokens em credential stores do sistema operacional (Windows Credential Manager ou Keychain no macOS), evitando armazenamento em texto plano[[cli.github](https://cli.github.com/manual/gh_auth_login)]​
    
- **Renovação Periódica**: Tokens devem ser renovados a cada 90 dias no máximo, preferencialmente a cada 30 dias, conforme práticas de rotação de credenciais[devblogs.microsoft+2](https://devblogs.microsoft.com/devops/retirement-of-global-personal-access-tokens-in-azure-devops/)
    

## **Configuração do Git com GitHub CLI**

Após autenticação via `gh`, configure o Git para usar as credenciais gerenciadas pelo CLI:[github+1](https://github.com/cli/cli/discussions/4333)

bash

`gh auth setup-git`

Isso configura automaticamente o Git para utilizar o GitHub CLI como credential helper, eliminando prompts de senha e garantindo uso de tokens gerenciados de forma segura.

---

## **Workflow de Colaboração e Replicação de Topologias**

## **Princípio de HomeLab-First**

Todo colaborador deve seguir o workflow de validação em ambiente local antes de submeter código ao repositório central, conforme **Annex A.5.18** (Access Rights) que exige provisionamento e modificação de acesso baseado em autorização formal:[hightable+1](https://hightable.io/iso-27001-annex-a-5-18-access-rights/)

1. **Replicação Local**: Implementar e testar a topologia de IAM/IGA em seu HomeLab pessoal usando Hyper-V
    
2. **Validação de Controles**: Executar testes de acesso, segregação de funções e auditoria de logs conforme CIS Controls
    
3. **Documentação**: Registrar evidências de testes em formato Markdown versionado
    
4. **Submissão ao GitLab**: Após validação local bem-sucedida, submeter alterações via pull request ao repositório de desenvolvimento
    
5. **Revisão e Promoção**: Após aprovação técnica, o artefato é promovido ao repositório oficial no GitHub (Brain)
    

## **Controles de Revisão de Acesso**

Conforme **ISO 27001:2022 Annex A.5.18** (Access Rights Management), os acessos de colaboradores devem ser revisados periodicamente:[isms+2](https://www.isms.online/iso-27001/annex-a/5-15-access-control-2022/)

- **Revisão Trimestral**: Auditoria de tokens ativos e seus escopos
    
- **Remoção Imediata**: Revogação de acesso ao término de participação no projeto (processo de "Leaver")[[hightable](https://hightable.io/iso-27001-annex-a-5-18-access-rights/)]​
    
- **Princípio de Segregação de Funções**: Colaboradores não devem acumular papéis de desenvolvimento e aprovação final no mesmo artefato, conforme **Annex A.8.2**[iso27001+1](https://iso27001.com/iso-27001-annex-a-8-2-privileged-access-rights/)
    

---

## **Controles de Conformidade e Auditoria**

Este documento implementa os seguintes controles normativos da **ISO 27001:2022**:

|**Framework**|**Controle**|**Implementação**|
|---|---|---|
|ISO 27001:2022|**A.5.15** - Access Control|Definição de política de acesso baseada em privilégio mínimo e Need-to-Know [isms+2](https://www.isms.online/iso-27001/annex-a-2022/5-15-access-control-2022/)|
|ISO 27001:2022|**A.5.16** - Identity Management|Gestão de identidades via GitHub CLI com MFA obrigatório [isms+1](https://www.isms.online/iso-27001/annex-a-2022/5-15-access-control-2022/)|
|ISO 27001:2022|**A.5.17** - Authentication Information|Armazenamento seguro de tokens via credential stores do SO [isms+1](https://www.isms.online/iso-27001/annex-a-2022/5-15-access-control-2022/)|
|ISO 27001:2022|**A.5.18** - Access Rights|Provisionamento, revisão e revogação de acessos baseado em autorização formal [isms+2](https://www.isms.online/iso-27001/annex-a-2022/how-to-implement-iso-27001-2022-annex-a-control-5-18-access-rights/)|
|ISO 27001:2022|**A.8.2** - Privileged Access Rights|Escopo restrito de tokens PAT com segregação de aprovador/solicitante [hightable+1](https://hightable.io/iso-27001-annex-a-8-2-privileged-access-rights/)[[youtube](https://www.youtube.com/watch?v=Mf3I6bJPjJ0&vl=es)]​|
|ISO 27001:2022|**A.8.3** - Information Access Restriction|Microsegmentação de redes virtuais por VLANs no HomeLab [[hightable](https://hightable.io/iso-27001-annex-a-8-2-privileged-access-rights/)]​|
|ISO 27001:2022|**A.8.5** - Secure Authentication|MFA obrigatório e rotação periódica de tokens [[hightable](https://hightable.io/iso-27001-annex-a-8-2-privileged-access-rights/)]​|
|CIS Control 6|Access Control Management|Princípio do privilégio mínimo para tokens [[cisecurity](https://www.cisecurity.org/-/media/project/cisecurity/cisecurity/data/media/files/uploads/2020/06/Account-Management-Access-Control-Standard.docx)]​|
|NIST 800-53|AC-2 - Account Management|Segregação de contas administrativas e revisão de acesso [idenhaus+1](https://idenhaus.com/6-best-practices-for-privileged-access-management-what-experts-agree-on/)|

---

## **Matriz de Responsabilidades (RACI)**

|**Atividade**|**Colaborador**|**Arquiteto Lab**|**Auditoria**|
|---|---|---|---|
|Configurar HomeLab|**R**|C|I|
|Configurar rede virtual compatível (192.168.68.0/24)|**R**|C|I|
|Replicar topologia|**R**|C|I|
|Autenticar via gh CLI|**R**|I|A|
|Solicitar token PAT|**R**|A|I|
|Revisar escopos de token|I|**R**|A|
|Auditar acessos|I|C|**R**|

**Legenda**: R=Responsável | A=Aprovador | C=Consultado | I=Informado

---

## **Referências Normativas**

- **ISO/IEC 27001:2022** - Annex A.5.15 a A.5.18 (Organizational Controls - Access Control)[isms+4](https://www.isms.online/iso-27001/annex-a-2022/how-to-implement-iso-27001-2022-annex-a-control-5-18-access-rights/)
    
- **ISO/IEC 27001:2022** - Annex A.8.2 a A.8.5 (Technological Controls - Privileged Access Management)[[youtube](https://www.youtube.com/watch?v=Mf3I6bJPjJ0&vl=es)]​[hightable+1](https://hightable.io/iso-27001-annex-a-8-2-privileged-access-rights/)
    
- **CIS Controls v8** - Control 6 (Access Control Management)[[cisecurity](https://www.cisecurity.org/-/media/project/cisecurity/cisecurity/data/media/files/uploads/2020/06/Account-Management-Access-Control-Standard.docx)]​
    
- **NIST SP 800-53 Rev. 5** - AC-2 (Account Management)[learn.microsoft+1](https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-v2-privileged-access)
    
- **Microsoft Security Benchmark** - PA-1 (Separate and Limit Highly Privileged/Administrative Users)[[learn.microsoft](https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-v2-privileged-access)]​
    

---

## **Histórico de Versões**

|**Versão**|**Data**|**Alterações**|**Autor**|
|---|---|---|---|
|1.0|22/01/2026|Versão inicial do documento|Arquiteta de Documentação|
|1.1|22/01/2026|Atualização de nomenclatura ISO 27001:2022 (A.5.15-A.5.18, A.8.2-A.8.5); Adição de requisitos de rede virtual compatível com endereçamento mestre (192.168.68.0/24)|Arquiteta de Documentação|

---

**Documento elaborado conforme diretrizes de Governança-as-Code do Living Lab Fiqueok**  
**Última atualização**: 22 de Janeiro de 2026  
**Próxima revisão**: Abril de 2026