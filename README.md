# Az104-dio
Repositório referente ao resumo dos conceitos de administração azure

### AZ-104 | EP 01 | INTRODUÇÃO | Azure Administrator | Treinamento Oficial

*   **Certificação AZ-104**: Este vídeo introduz a série de treinamento para a certificação AZ-104 Azure Administrator. Valéria Batista, uma MCT (Microsoft Certified Trainer), compartilha sua experiência e dicas.
*   **Caminho das Certificações**:
    *   A certificação AZ-900 (Azure Fundamentals) é **recomendada** para entender conceitos básicos de nuvem, mas **não é um pré-requisito obrigatório** para a AZ-104.
    *   A certificação **AZ-104 é um pré-requisito para a AZ-305** (Azure Solutions Architect Expert).
*   **Formato e Dificuldade da Prova**:
    *   A AZ-104 é **consideravelmente mais difícil** que a AZ-900.
    *   Contém entre **40 e 60 perguntas**, incluindo **questões de sim ou não que não podem ser revisadas**.
    *   Inclui **estudos de caso** (geralmente no final da prova, mas pode variar).
    *   O tempo de prova foi **reduzido** para 45 minutos (anteriormente 60 minutos para provas de fundamentos).
    *   Tipos de pergunta incluem múltipla escolha, arrastar e soltar, e estudos de caso.
*   **Estratégia de Estudo**:
    *   É estratégico **focar nos tópicos com maior peso** na prova.
    *   **Gerenciamento de Redes** (20-25%) e **Gerenciamento de Computação** (25-30%) são as áreas com maior peso.
    *   **Gerenciar Identidades e Governança** e **Implementar e Gerenciar Armazenamento** têm peso de 15-20% cada.
    *   **Backup e Monitoramento** têm peso de 10-15%.
*   **Estrutura do Curso**: O curso é dividido em **11 módulos** com capítulos e **laboratórios práticos** (hands-on), que são cruciais para a certificação.

### AZ-104 | EP 02 | Azure Active Directory | Treinamento Oficial

*   **Conceitos do Azure Active Directory (Azure AD)**: Este módulo aborda os recursos, conceitos e gerenciamento de identidades híbridas com o Azure AD.
*   **Azure AD vs. Active Directory Local (On-Premises)**:
    *   **Active Directory Local**: Utiliza protocolos como Kerberos e NTLM, e tem um modelo de "árvore" (com domínios e subdomínios, OUs).
    *   **Azure AD**: Utiliza protocolos nativos de nuvem como **SAML, OAuth, OpenID e WS-Federation**, e tem um modelo **"plano"** (sem OUs tradicionais). É uma solução de identidade baseada em HTTP/HTTPS.
    *   A maioria das empresas utiliza um **modelo híbrido** devido a sistemas legados.
*   **Gestão de Identidades Híbridas**:
    *   Envolve a **sincronização de usuários** do ambiente físico (on-premises) para a nuvem (Azure AD) usando o **Azure AD Connect**.
    *   A sincronização é **unilateral** (do local para a nuvem); apenas a senha pode ser sincronizada de volta.
    *   Novas contas de usuário em um ambiente sincronizado devem ser criadas no **Active Directory local**.
*   **Tipos de Contas e Licenças do Azure AD**:
    *   **Contas Sincronizadas**: Originadas do AD local.
    *   **Contas Nativas da Nuvem**: Criadas diretamente no Azure AD.
    *   **Contas de Convidado**: Para usuários externos.
    *   **Modelos de Licença**: Existem os modelos Free, Microsoft 365 Apps, Premium P1 e Premium P2.
        *   **Premium P2**: Oferece funcionalidades avançadas como **Proteção de Identidade** (detecção de riscos como "viagem impossível", uso de IP anônimo, credenciais vazadas) e **Governança de Identidade** (Privileged Identity Management, Access Reviews). Para atribuir uma licença P2, o **local de uso** do usuário deve estar preenchido.
*   **Gerenciamento de Dispositivos (BYOD)**: O Azure AD permite adicionar dispositivos (registrados ou unidos ao AD) para gerenciamento via **Microsoft Intune**, abrangendo diversos sistemas operacionais.
*   **Redefinição de Senha por Autoatendimento (SSPR)**: Permite que usuários redefinam suas próprias senhas, configurando métodos de autenticação como código web, e-mail ou perguntas de segurança (embora as perguntas de segurança não sejam recomendadas). Pode-se exigir um ou dois métodos.
*   **Nomes de Domínio Personalizados**: É possível adicionar e verificar um domínio personalizado no Azure AD utilizando registros DNS do tipo **TXT ou MX**.
*   **Gerenciamento de Tenants**: Você pode ter múltiplos tenants, mas os usuários e permissões **não são compartilhados automaticamente** entre eles.

### AZ-104 | EP 03 | Usuários e Grupos | Treinamento Oficial

*   **Tipos de Contas de Usuário**:
    *   **Sincronizadas**: Vêm do Active Directory local através da sincronização.
    *   **Nativas da Nuvem**: Criadas diretamente no Azure AD.
    *   **Convidados**: Para acesso de pessoas externas à organização.
*   **Gerenciamento de Contas de Usuário**:
    *   **Exclusão**: Usuários excluídos permanecem no Azure AD por **30 dias** antes de serem permanentemente deletados, e podem ser restaurados dentro desse período.
    *   **Auditoria**: Logs de login e auditoria estão disponíveis para acompanhar as autenticações e atividades dos usuários.
    *   **Operações em Massa (Bulk)**: É possível criar, convidar ou excluir usuários em massa utilizando arquivos CSV, o que é eficiente para grandes volumes de contas.
*   **Gerenciamento de Grupos**:
    *   **Grupos de Segurança**: Usados para permissões, **não possuem expiração**. Podem ter membros dinâmicos.
    *   **Grupos do Microsoft 365**: Podem ser configurados para **expirar automaticamente** (mínimo de 30 dias) e são usados para comunicação e colaboração. **Não permitem a adição de dispositivos**.
*   **Atribuição de Membros a Grupos**:
    *   **Atribuído (Manual)**: Membros são adicionados e removidos manualmente.
    *   **Dinâmico**: Membros são adicionados e removidos automaticamente com base em **regras** (ex: departamento, cidade, título de cargo). A atribuição dinâmica de usuários e dispositivos requer licenças específicas, como o Premium P2.
*   **Atribuição de Licenças**: Licenças podem ser atribuídas a usuários ou grupos. É crucial que o **campo "Local de uso" do usuário esteja preenchido** para atribuir licenças como o Premium P2, caso contrário, ocorrerá um erro.
*   **Unidades Administrativas (UAs)**: Permitem a **delegação descentralizada** do gerenciamento de usuários e grupos a administradores locais em escritórios ou departamentos específicos. Requerem licença Premium P2 para os administradores.

### AZ-104 | EP 04 | Assinaturas e Contas | Treinamento Oficial

*   **Regiões do Azure**:
    *   Coleções de **três ou mais datacenters** com baixa latência, distribuídas globalmente (mais de 60 regiões ativas em mais de 140 países).
    *   São essenciais para **recuperação de desastres** e **residência de dados**.
    *   Serviços globais (como Azure AD) são independentes de região.
    *   A região **Brasil Sul** é a única emparelhada com uma região fora de sua geografia (South Central US), o que significa que a replicação para recuperação de desastres pode ocorrer fora do Brasil.
*   **Assinaturas (Subscriptions) do Azure**:
    *   Uma unidade lógica de serviços do Azure, sempre vinculada a uma conta.
    *   Uma conta pode ter **várias assinaturas** (ex: Dev, Teste, Produção), o que facilita a organização, o controle de custos e a aplicação de políticas.
*   **Formas de Obter uma Assinatura**:
    *   **Enterprise Agreement (EA)**: Contrato direto com a Microsoft, geralmente para grandes empresas, com compromisso monetário inicial e descontos.
    *   **Revendedores/Parceiros**: Empresas autorizadas que intermediam a aquisição de serviços.
    *   **Conta Pessoal Gratuita (Trial)**: Oferece créditos (ex: $200) por 30 dias e acesso limitado por 12 meses, convertendo-se para **Pay-As-You-Go** após a expiração dos créditos.
    *   **Pay-As-You-Go (PAYG)**: Paga-se conforme o uso, sem compromisso inicial.
    *   **Conta de Estudante**: Oferece $100 por 12 meses.
*   **Grupos de Recursos (Resource Groups - RGs)**:
    *   **Agrupamentos lógicos** para recursos do Azure.
    *   **Todos os recursos devem estar associados a um RG** (não podem "voar").
    *   Um RG pode conter recursos de **diferentes regiões**.
    *   **Não podem ser renomeados**.
    *   Recursos podem ser **movidos entre RGs ou assinaturas**.
*   **Limites de Recursos (Cotas)**:
    *   Existem limites padrão para tipos de recursos e regiões.
    *   Se atingir o limite, é necessário **abrir um chamado de suporte com a Microsoft** para solicitar o incremento da cota. Este chamado é **gratuito**.
*   **Hierarquia de Recursos**:
    *   **Management Group (Grupo de Gerenciamento)**: Nível mais alto, acima das assinaturas. Permite aplicar políticas e orçamentos em grande escala.
    *   **Assinaturas > Grupos de Recursos > Recursos**.
*   **Tags**:
    *   Pares de chave-valor para **organização, rastreabilidade e rateio de custos** dos recursos.
    *   **Não são obrigatórias** para a criação de recursos, mas são **essenciais para o gerenciamento** e podem ser exigidas por políticas.
    *   **Tags não são herdadas** pelos recursos de um grupo de recursos.
*   **Gerenciamento de Custos (FinOps)**:
    *   Monitoramento e otimização dos gastos na nuvem.
    *   É possível definir orçamentos e alertas para controlar os gastos.
    *   **Estratégias de Redução de Custos**:
        *   **Reservas**: Oferecem descontos significativos (até 80%) ao comprometer-se com o uso de recursos por 1 ou 3 anos.
        *   **Benefício Híbrido Azure (Azure Hybrid Benefit)**: Reutiliza licenças existentes do Windows Server ou SQL Server no Azure, reduzindo custos.
        *   **Escolha da Região**: Os custos variam entre as regiões.
        *   **Desligar recursos ociosos**.
        *   **Calculadora do Azure**: Ferramenta para estimar custos e fazer previsibilidade.

### AZ-104 | EP 05 | Azure Policy | Treinamento Oficial

*   **Definição do Azure Policy**:
    *   Uma ferramenta para **impor padrões organizacionais e garantir conformidade**.
    *   Difere das GPOs (Group Policy Objects) do ambiente on-premises, pois foca na **padronização e restrição de recursos** (ex: tipos de máquinas permitidos, regiões permitidas, exigência de tags), e não nas ações dos usuários.
*   **Funcionalidades e Casos de Uso**:
    *   Permite definir quais **tipos de recursos ou famílias de máquinas** podem ser criados.
    *   Pode **restringir a criação de recursos a regiões específicas**.
    *   Garante que **todos os recursos tenham tags** obrigatórias.
    *   **Automaticamente aplica regras** em todo o ambiente, garantindo que ninguém crie recursos fora dos padrões definidos, independentemente do nível de acesso do usuário.
*   **Remediação**: Para algumas políticas, a remediação pode **corrigir recursos não-conformes** que já existem no ambiente.
*   **Implementação de Políticas**:
    *   Escolhe-se uma **definição de política** (existente ou personalizada).
    *   Define-se o **escopo** de aplicação (assinatura, grupo de recursos).
    *   As políticas são escritas em **JSON**.
    *   É possível **excluir escopos específicos** da aplicação de uma política (ex: aplicar a uma assinatura inteira, mas excluir um determinado grupo de recursos).
*   **Iniciativas do Azure**:
    *   São um **agrupamento de múltiplas definições de políticas**.
    *   Utilizadas para atender a **requisitos de conformidade mais abrangentes** (ex: regulamentações do setor, padrões de segurança como ISO).
    *   Requerem um planejamento cuidadoso ao serem aplicadas.

### AZ-104 | EP 06 | RBAC | Treinamento Oficial

*   **Controle de Acesso Baseado em Função (RBAC)**:
    *   Gerencia o acesso a **recursos do Azure** (máquinas virtuais, contas de armazenamento, redes virtuais, etc.).
    *   É **diferente das funções do Azure AD**, que gerenciam o acesso a **objetos do Azure AD** (usuários, grupos, aplicativos). Uma pessoa pode ser administradora global no Azure AD e não ter acesso a nenhum recurso do Azure se não tiver uma função RBAC atribuída.
*   **Conceitos do RBAC**:
    *   **Entidade de Segurança (Security Principal)**: Quem está solicitando o acesso (usuário, grupo, entidade de serviço).
    *   **Definição da Função (Role Definition)**: Conjunto de permissões concedidas (ex: Proprietário, Colaborador, Leitor).
    *   **Escopo (Scope)**: Onde as permissões se aplicam (Grupo de Gerenciamento, Assinatura, Grupo de Recursos, Recurso Individual).
*   **Princípio do Mínimo Privilégio**: É crucial conceder apenas as permissões necessárias para evitar riscos de segurança e ações indesejadas.
*   **Principais Funções RBAC (para a prova)**:
    *   **Proprietário (Owner)**: Possui acesso total a todos os recursos e **pode delegar acesso a outros**.
    *   **Colaborador (Contributor)**: Possui acesso total para gerenciar todos os recursos, mas **NÃO pode delegar acesso**.
    *   **Leitor (Reader)**: Pode apenas **visualizar** os recursos, sem modificar ou excluir.
*   **Atribuição de Função**: As funções são atribuídas a entidades de segurança em um escopo específico. As permissões são **herdadas** hierarquicamente (ex: uma função atribuída no nível da assinatura se aplica a todos os grupos de recursos e recursos dentro dela).
*   **Funções Personalizadas**: É possível criar funções RBAC personalizadas além das funções internas existentes.

### AZ-104 | EP 07 | Revisão Módulos 1 e 2 | Treinamento Oficial

*   **Criação de Usuário em Novo Locatário**: Apenas o usuário que criou o novo locatário (tenant) no Azure AD pode criar contas de usuário nele inicialmente.
*   **Grupos do Microsoft 365**: São os únicos grupos que permitem a **exclusão automática** após um período configurado (mínimo de 30 dias).
*   **Migração de Recursos**: Recursos como contas de armazenamento, redes virtuais, máquinas virtuais, discos gerenciados e Key Vaults **podem ser movidos entre assinaturas**.
*   **Atribuição de Licenças Azure AD Premium P2**: É realizada na seção de **Licenças do Azure AD**, atribuindo-as a usuários ou grupos específicos.
*   **Verificação de Domínio Personalizado**: Ao adicionar um nome de domínio personalizado no Azure AD, a verificação requer a criação de um registro DNS do tipo **TXT ou MX** no seu registrador de domínio.
*   **Política do Azure (Interpretação)**: É fundamental saber interpretar uma política que se aplica a uma assinatura inteira, mas **exclui um grupo de recursos específico**. Por exemplo, uma política pode impedir a criação de servidores SQL em qualquer lugar da assinatura, exceto em um grupo de recursos específico (`contosoR1`).
*   **Função RBAC para Delegação**: Apenas a função **Proprietário (Owner)** permite que um usuário atribua funções a outros usuários para um recurso.
*   **Unidades Administrativas (UAs)**: São usadas para **conceder permissões de gerenciamento de usuários a administradores locais** em cada escritório ou localidade, descentralizando a administração.
*   **Função Colaborador (Contributor)**: Permite a capacidade de criar recursos, como aplicativos lógicos.

### AZ-104 | EP 08 | Azure Resource Manager | Treinamento Oficial

*   **Azure Resource Manager (ARM)**:
    *   Atua como uma **camada de gerenciamento consistente** no Azure, recebendo e processando todas as requisições de criação, atualização e exclusão de recursos.
    *   Ele valida a solicitação (permissões, parâmetros) antes de chamar os serviços do Azure para executar a ação.
*   **Terminologia Chave**:
    *   **Recurso (Resource)**: Uma instância única de um serviço (ex: VM, Storage Account, VNet).
    *   **Grupo de Recursos (Resource Group - RG)**: Um contêiner lógico para recursos. **Todos os recursos do Azure devem estar em um RG**.
        *   Um RG pode ter recursos de **diferentes regiões**.
        *   **Não pode ser renomeado**.
    *   **Modelo ARM (ARM Template)**: Um arquivo **JSON** que define a infraestrutura e a configuração de recursos do Azure de forma declarativa.
*   **Bloqueios de Recursos (Resource Locks)**:
    *   Impedem exclusão ou modificação acidental de recursos.
    *   **Delete Lock**: Impede a exclusão do recurso. Se um RG tiver um recurso com Delete Lock, o RG não pode ser excluído.
    *   **Read-Only Lock**: Impede qualquer modificação (ex: iniciar/parar VMs, visualizar chaves de acesso de Storage Accounts).
    *   **Escopo**: Podem ser aplicados no nível da assinatura, grupo de recursos ou recurso individual.
    *   **Herança**: Os bloqueios de recursos são **herdados** pelos recursos de escopos superiores (diferente das tags).
*   **Movimentação de Recursos**:
    *   Recursos podem ser movidos entre **grupos de recursos**, **assinaturas** e, em alguns casos, **regiões**.
    *   **Serviços que NÃO podem ser movidos**: Azure AD Domain Services, ExpressRoute e Site Recovery.
    *   Durante a movimentação, os grupos de recursos de origem e destino ficam **bloqueados** para operações.
    *   Bloqueios aplicados diretamente ao recurso **se movem com ele**. Bloqueios herdados do RG de origem **não são levados** para o RG de destino.
*   **Exclusão de Recursos**:
    *   Excluir um recurso individual remove apenas aquele item.
    *   Excluir um grupo de recursos **remove todos os recursos contidos nele**.

### AZ-104 | EP 09 | Azure Portal e Cloud Shell | Treinamento Oficial

*   **Azure Portal**:
    *   É a interface gráfica baseada na web para gerenciar recursos do Azure.
    *   Oferece **personalização** de aparência (cores, idioma, formato regional) e dashboards (painéis) para organizar a visualização dos recursos.
    *   Exibe **notificações** sobre o status da assinatura e créditos restantes.
    *   É importante **estar atento aos itens em "Preview"** (pré-visualização), pois ainda estão em fase de testes e não são recomendados para ambientes de produção.
*   **Azure Cloud Shell**:
    *   Um **terminal interativo acessível diretamente do Portal do Azure** via navegador.
    *   Suporta dois ambientes de linha de comando: **Bash (Linux) e PowerShell (Windows)**.
    *   Requer uma **conta de armazenamento do Azure (Storage Account)** para persistir arquivos e configurações da sessão.
    *   É **temporário**, e a sessão expira após 20 minutos de inatividade.
    *   Permite o **upload e download de arquivos**, facilitando a interação com scripts e dados.

### AZ-104 | EP 10 | PowerShell e CLI | Treinamento Oficial

*   **Azure PowerShell**:
    *   É o **PowerShell nativo** do Windows, estendido com módulos do Azure para gerenciar recursos.
    *   É **compatível com Windows, Linux e macOS**. (Ponto importante para prova).
    *   Pode ser executado **localmente** na sua máquina, permitindo o gerenciamento do Azure sem a necessidade de abrir o Portal.
    *   Utiliza **Cmdlets** (comandos no formato verbo-substantivo, ex: `Get-AzVM`) e módulos específicos do Azure PowerShell.
    *   Suporta execução de comandos interativos ou scripts prontos.
*   **Azure CLI (Command-Line Interface)**:
    *   Outra ferramenta de linha de comando para gerenciar recursos do Azure.
    *   Também é **compatível com Windows, Linux e macOS**.
    *   Precisa ser **instalado** (não é nativo como o PowerShell no Windows).
    *   A sintaxe dos comandos começa com `az` (ex: `az vm create`), diferindo do PowerShell.
    *   Suporta comandos interativos e scripts.
*   **Comparativo e Uso**:
    *   Ambas as ferramentas (PowerShell e CLI) permitem a **criação, alteração e exclusão de recursos no Azure**.
    *   A escolha entre PowerShell e CLI geralmente depende da **preferência pessoal** do administrador e da familiaridade com a sintaxe de cada um.
    *   O **Cloud Shell** (visto no Módulo 9) oferece uma forma de usar tanto Bash (baseado em Linux, similar ao CLI) quanto PowerShell diretamente no portal, sem a necessidade de instalação local, mas com a limitação de sessão temporária.

### AZ-104 | EP 11 | ARM Template e Bicep | Treinamento Oficial

*   **ARM Templates (Azure Resource Manager Templates)**:
    *   São usados para **implantar infraestrutura como código (IaC)** no Azure, permitindo criar, atualizar e excluir recursos de forma **repetível e consistente**.
    *   São escritos em **JSON** (JavaScript Object Notation). Este é um ponto importante para a prova.
    *   **Vantagens**: Otimizam a criação em larga escala, reduzem erros manuais, aceleram implantações e simplificam a orquestração de recursos.
    *   Podem ser **exportados** a partir de recursos ou grupos de recursos existentes no portal do Azure, o que ajuda na reutilização de código.
    *   Contêm **parâmetros** para valores variáveis (ex: nome da VM, nome de usuário, senha).
*   **Azure Bicep**:
    *   É uma **linguagem específica de domínio (DSL)** criada pela Microsoft para implantação de recursos do Azure.
    *   Oferece uma **sintaxe mais concisa e legível** do que o JSON dos ARM Templates, tornando a codificação mais amigável.
    *   O código Bicep é **transpilado** para JSON ARM Templates antes de ser implantado no Azure.
    *   **Vantagens**: Melhora a legibilidade, simplifica a autoria de modelos e oferece melhor modularidade. É **recomendado para quem está começando** com infraestrutura como código no Azure devido à sua simplicidade.
    *   É **exclusivo do Azure**.
    *   Pode ser desenvolvido no **Visual Studio Code** e implantado via CLI ou diretamente pelo VS Code.
*   **Comparativo**: Tanto ARM Templates quanto Bicep alcançam o mesmo objetivo de implantar recursos no Azure. Bicep é mais moderno e simplificado, resultando em menos linhas de código para as mesmas implantações.

### AZ-104 | EP 12 | Azure Virtual Network | Treinamento Oficial

*   **Componentes da Rede Virtual (VNet)**:
    *   A VNet é o **bloco fundamental** para a rede privada no Azure.
    *   Todos os recursos do Azure (ex: Máquinas Virtuais) devem ser associados a uma VNet e uma Sub-rede.
    *   Uma VNet deve ter **pelo menos uma sub-rede**.
    *   **Comunicação Interna**: Todas as sub-redes e recursos dentro da **MESMA VNet se comunicam por padrão**.
    *   **Network Security Groups (NSGs)**: Podem ser aplicados a sub-redes ou a interfaces de rede (NICs) de VMs para controlar o tráfego. É **recomendado aplicar NSGs no nível da sub-rede** para maior eficiência.
*   **Emparelhamento de VNet (VNet Peering)**:
    *   Conecta duas ou mais VNets para permitir a comunicação entre elas, pois **VNets NÃO se comunicam por padrão**, mesmo que estejam na mesma região.
    *   Pode ser **Regional** (na mesma região) ou **Global** (entre regiões diferentes).
    *   **Sub-redes recém-criadas após o Peering**: Se uma nova sub-rede for criada em uma VNet **DEPOIS** que o emparelhamento já foi estabelecido, essa nova sub-rede **NÃO se comunicará** através do emparelhamento existente.
    *   **Solução para Novas Sub-redes**: A recomendação da Microsoft é **excluir o emparelhamento existente, criar a nova sub-rede, e então recriar o emparelhamento**. Esta é uma questão frequente em provas.
    *   **Resolução de Problemas no Peering**: Se o emparelhamento não estiver funcionando, a recomendação é **excluí-lo e recriá-lo** devido à rapidez do processo.
    *   **Espaços de IP**: VNets emparelhadas **NÃO podem ter espaços de endereço IP sobrepostos**.
*   **Encaminhamento de Gateway (Gateway Transit)**: Permite que VNets conectadas a uma VNet hub (que possui um Gateway VPN para o ambiente on-premises) usem este gateway para se comunicar com as redes on-premises, sem a necessidade de emparelhamento direto entre as VNets spoke.
*   **Boas Práticas de Segurança**: Evitar expor portas RDP/SSH diretamente à internet; usar o Azure Bastion ou VPNs para acesso seguro.

### AZ-104 | EP 13 | IP Address | Treinamento Oficial

*   **Endereçamento IP na Nuvem**:
    *   **IP Privado**: Utilizado para comunicação **interna** dentro das redes virtuais do Azure, não acessível pela internet.
    *   **IP Público**: Utilizado para comunicação com a **internet**, acessível externamente.
*   **Configuração de IPs Públicos**:
    *   **Versões**: IPv4 e IPv6.
    *   **SKUs (Modelos)**:
        *   **Básico (Basic)**: Permite atribuição **Dinâmica** (o IP pode mudar ao realocar o recurso) ou **Estática** (o IP é reservado).
        *   **Standard**: Oferece apenas atribuição **Estática** e pode ser **Regional ou Global**, com recursos adicionais como redundância de zona.
    *   **Preferencia de Roteamento**: Permite escolher se o tráfego será roteado pela **rede da Microsoft** (otimizada para baixa latência) ou pela **Internet** (via rede do provedor de serviços).
    *   **Associação**: IPs públicos podem ser associados a interfaces de rede de **máquinas virtuais**, **balanceadores de carga (Load Balancers)**, **Application Gateways** e **VPN Gateways**.
*   **Azure Bastion**:
    *   Oferece acesso seguro a máquinas virtuais via SSH/RDP **diretamente do portal do Azure através do navegador**, eliminando a necessidade de IPs públicos nas VMs.
    *   É altamente **recomendado para ambientes de produção** por aumentar a segurança.
*   **Planejamento de IP**: É crucial **evitar sobreposição de endereços IP** entre redes on-premises e redes do Azure se houver conectividade entre elas.

### AZ-104 | EP 14 | Azure Firewall | Treinamento Oficial

*   **Azure Firewall (FaaS - Firewall-as-a-Service)**:
    *   É um serviço de firewall gerenciado pelo Azure.
    *   **Não é implementado por padrão**, o usuário escolhe utilizá-lo.
    *   **Alternativas**: É possível usar firewalls de **terceiros** (disponíveis no Marketplace) ou **implementar um firewall em uma VM**.
    *   **Vantagens**: Alta disponibilidade, integração total com o Azure e filtragem de ameaças inteligente.
*   **Tiers do Azure Firewall**:
    *   **Standard**: Oferece filtragem de tráfego na camada 3 e 7 (L3-L7), incluindo IPs e FQDNs, e inteligência de ameaças.
    *   **Premium**: Inclui todas as funcionalidades do Standard, mais **filtragem de URL, categorias web, inspeção TLS e IDPS** (Sistema de Prevenção e Detecção de Intrusões). O modelo Premium é indicado para controle mais granular e proteção avançada contra ameaças. A diferenciação entre Standard e Premium é um tópico comum em exames.
*   **Arquitetura de Implantação**:
    *   Geralmente, o Azure Firewall é implantado em uma **topologia hub-spoke** (estrela).
    *   A VNet "hub" centraliza serviços compartilhados (como o Firewall, VPN Gateway, Azure Bastion) e se conecta à rede on-premises.
    *   As VNets "spoke" (onde estão as cargas de trabalho) se emparelham com o hub, mas não se comunicam diretamente entre si.
    *   O Firewall atua como um **ponto central de controle** para todo o tráfego de entrada e saída.
*   **Regras**: Suporta regras de rede (IP, porta, protocolo) e regras de aplicativo (FQDNs).
*   **Custo**: O Azure Firewall é um serviço pago.

### AZ-104 | EP 15 | Azure DNS | Treinamento Oficial

*   **Domínios Personalizados no Azure AD**:
    *   Permite adicionar e verificar um nome de domínio personalizado (ex: `suaempresa.com`) para substituir o domínio padrão `.onmicrosoft.com` usado no Azure AD.
    *   A **verificação do domínio** exige a criação de um registro DNS do tipo **TXT ou MX** no seu registrador de domínio público. Este é um ponto comum em questões de prova.
*   **Zonas DNS do Azure (Azure DNS Zones)**:
    *   Permitem hospedar seus domínios DNS no Azure.
    *   **Delegação**: Você **não pode comprar domínios diretamente no Azure**. Os domínios devem ser adquiridos em registradores de terceiros (ex: Registro.br, GoDaddy) e, em seguida, **delegados ao Azure DNS** atualizando os nameservers no registrador.
    *   **Registros (Record Sets)**: Suportam tipos de registros DNS comuns (A, CNAME, MX, TXT, SRV, PTR).
    *   As zonas DNS são associadas a um Grupo de Recursos e a uma região.
*   **Zonas DNS Privadas**:
    *   Fornecem resolução de nomes para recursos **dentro das Redes Virtuais** do Azure, sem expô-los à internet.
    *   Útil para aplicações e serviços internos que não precisam de acesso público.
    *   **Recomendação**: **Evitar o uso de domínios `.local`** ou `.corp` no Azure; utilizar extensões de domínio padrão.

### AZ-104 | EP 16 | Revisão Módulos 3 e 4 | Treinamento Oficial

*   **Visualizar Detalhes de Implantação de Recursos**: Para ver quem criou um recurso e quando, deve-se ir ao **Grupo de Recursos** e clicar na opção **"Implantações" (Deployments)**. Essa informação não é encontrada em "Implantação Programática" ou "Scripts de Automação".
*   **Configuração de VM a partir de Template**: Ao implantar uma máquina virtual a partir de um modelo, você pode configurar o **Grupo de Recursos** onde ela será criada.
*   **Efeitos do Bloqueio de Leitura (Read-Only Lock)**: Se um bloqueio de "somente leitura" for aplicado a um recurso ou grupo de recursos, **não será possível parar/ligar uma VM**, **carregar dados** para uma conta de armazenamento, ou **visualizar as chaves de acesso** de uma conta de armazenamento.
*   **Porta para Compartilhamento de Arquivos Azure Files**: Para mapear uma unidade de compartilhamento de arquivos do Azure em um computador Windows 10, a **porta 445** precisa estar aberta.
*   **Interfaces de Rede (NICs) para VMs**: Uma única interface de rede (NIC) pode ter **tanto um IP público quanto um IP privado**. Portanto, para 5 máquinas virtuais, são necessárias apenas **5 interfaces de rede**.
*   **Grupos de Segurança de Rede (NSGs) para Múltiplas VMs**: Se 5 máquinas virtuais estiverem na **mesma sub-rede** e precisarem de **regras de segurança idênticas**, um **único NSG aplicado à sub-rede** é suficiente para configurá-las.
*   **Escopo de Função RBAC Personalizada**: Uma função RBAC personalizada pode ser atribuída no nível da **assinatura** para impedir o gerenciamento de permissões de acesso e permitir visualização, criação, modificação e exclusão de recursos em **TODOS** os grupos de recursos dentro daquela assinatura.

### AZ-104 | EP 17 | Vnet Peering | Treinamento Oficial

*   **VNet Peering (Emparelhamento de Rede)**:
    *   É a forma de **conectar duas ou mais Redes Virtuais (VNets)** no Azure para que os recursos nelas possam se comunicar.
    *   **VNets NÃO se comunicam por padrão**, mesmo que estejam na mesma região.
    *   Pode ser **Regional** (entre VNets na mesma região) ou **Global** (entre VNets em regiões diferentes).
    *   **Restrição de IP**: VNets que serão emparelhadas **NÃO podem ter espaços de endereço IP sobrepostos**.
*   **Comunicação de Sub-redes e Peering**:
    *   **Sub-redes dentro da mesma VNet se comunicam por padrão**.
    *   Se uma **nova sub-rede é criada APÓS o emparelhamento** já estar estabelecido, essa nova sub-rede **NÃO se comunicará automaticamente** através do peering existente.
    *   **Procedimento para novas sub-redes**: A recomendação é **excluir o peering, criar a nova sub-rede e, em seguida, recriar o peering**.
*   **Resolução de Problemas no Peering**: Se o emparelhamento apresentar problemas ou parar de funcionar, a recomendação é **excluí-lo e recriá-lo**, pois é um processo rápido e eficaz.
*   **Conectividade de Trânsito (Gateway Transit)**:
    *   Permite que as VNets "spoke" (secundárias) utilizem o **Gateway VPN** de uma VNet "hub" (central) para se comunicar com o ambiente on-premises, sem que as VNets "spoke" precisem de um gateway próprio.
    *   A **VNet hub** atua como uma ponte, facilitando o acesso ao ambiente on-premises.
*   **Modelos de Comunicação**: O emparelhamento pode ser **bidirecional** (tráfego vai e volta, padrão) ou **unidirecional** (tráfego em apenas uma direção).
*   **Impacto de Indisponibilidade**: Parar e recriar o peering causa um **curto período de indisponibilidade**, o que deve ser considerado para workloads críticos.
