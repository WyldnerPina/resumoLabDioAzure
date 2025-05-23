===================== Desafio de Projeto =====================

============== localizando serviços por categoria ==================

portal igual das grandes empresas mas barrado em alguns recursos.

engrenagem, idioma e região 
aparência + exibições de inicialização

menu esquerda → todos os serviços (tudo o q temos em categorias)

computação → 
* infraestrutura como um serviço (IaaS) → aqui podemos montar as máquinas
* plataforma como um serviço (PaaS) 
* Rede → bastião (rede segura pra acesso às máqs - jump server)
* Armazenamento
várias outros recursos para a criação

→ versão prévia = NÃO TEM GARANTIA, se usar microsoft não se responsabilizará

BENEFÍCIOS NUVEM =========================================================
1- alta disponibilidade
SLA = acordo de disponibilidade do serviço, se além recebe crédito 
(↑ disponibilidade = > tempo disponível)

2- Escalabilidade e Elasticidade
Escalabilidade → ajusta recs à demanda (↓ ou ↑)
Elasticiadade → "Black friday" qndo o crescimento é repentino e não permanente
se eu chego em X + um servidor, se diminuir etc (pago o q uso)

3- Confiabilidade, previsibilidade e segurança
Confiabilidade → Sistema q se recupera e continua funcionando (Crio onde quiser, fácil)
Previsibilidade → confiança, desempenho, custo. noção e apoio no sistema 
Segurança → têm ferramentas de segurança (realizada pelo CLIENTE)

4- Governança e gerenciabilidade
Governaça → auditoria, para sinalizar recursos e mitigação. padrões corporativos dentro de ramos específicos = Regras
Gerenciabilidade → facilita gerenciamento de recs. criar pelo portal, linha de comando, etc. Modelo pré-configurado. Vc ajusta (gerencia) do seu jeito

TIPOS DE SERVIÇO DE NUVEM ===============================================
* Responsabilidade compartilhada *
IaaS → Infra como serviço (as a Service)
Tenho mais acesso a configuração. e tenho mais acesso ao final. 
personaliza-se mais. servidor e banco etc. + GESTÃO

PaaS → Plataforma como serviço 
engloba mais. não é só a infra. não mexo mais no sistema operacional
só quero por aplicação. Mais APLICAÇÃO, BD msm

SaaS → Soft como serviço
nível mais acima. teams, por exemplo, tenho acesso ao q pago do serviço.
licença personaliza. App já existe e já sei o q entrega o q vejo é dependente
da licença

* Modelo de responsabilidade compartilhada *
segue a ideia acima, o SaaS é o q vc se preocupa menos e vai subindo
PaaS, IaaS e local
SaaS → vc é reponsável por Dados, contas, dispositivos de acesso, Identidade Infra e diretórios (compartilhado)
PaaS → soma Aplicativos e Rede (compartilhados)
IaaS → soma SO (nada compartilhado)
Local → soma Host, Rede, Datacenter (nada compartilhado)


COMPONENTES DA ARQTT AZURE ==============================================
*****Regiões e zonas de disponibilidade
Regiões disponíveis → qndo criamos dizemos onde vai ficar, faço próximo por
causa do delay. cada lugar um valor diferente e recursos não disponíveis em
todas regiões. 
Datacenters globais, zona de disponibilidade (3 datas se 2 caem o outro fica)
eles se comunicam muito bem.
desaster recovery = cai os três da região.

flexibilidade e escala para ↓ latência. escrever nos três ao mesmo tempo

Alguns dados não podem ir pra fora do Brasil.

Pares de região → é uma região para replicar o q temos na região original e 
precisamos levar para outra. é automática pra alguns serviços.

Regiões soberanas → regiões exclusivas para govs militares etc.



*****Assinaturas e grupos de recs
grupo de recs → forma de organizar as coisas (máq e seus recs).
separar por projeto, máqs etc. Vc decide como organizar.
NÃO MUDA NOME.

Assinaturas → uma assinatura pode ter várias assinaturas, mas a
assinatura responde a uma única conta
pode ter várias para cada grupo de trab: desenvolvimento, teste e produção


COMPUTAÇÃO E REDE =======================================================
• Tipos de computação → serviços:maqs, apps, container, área de trab vitual...
• VMs → Dá pra criar tudo menos mexer no hard (IaaS). lift-n-shift subo maq pra nuvem = tenho
• Conjuntos de dimensionamento → oportunidade para balanceamento de carga automat
• conjuntos de disponibilidade de VM → qndo um Rack (domínio de falha = 3 geralmente)
falha com várias máqs. Em linha = domínio de atualização (Rack vertical) ideal sempre 3
• Área de trab virtual → é uma máq virtual, e ↓ riscos de recs e segurança
• Serviços de containers → maq q tem apenas uma rotina de algo, é leve, pode ser recriado etc
o mais conhecido é o Docker e não precisa de sistema operacional (PaaS)
• Apps de container do azure → balanceia a carga e escala (PaaS)
• AKS (azu kubernetes serv) → serviço de orquestração para containers (gerencia ciclo de vida
dos containers)
• Azure Functions → PaaS, Para executar um trab de acordo com demanda, algo dispara o evento
• Serviços de app → Criar, implantar e dimensionar apps web e APIs rapidamente (.net, java, node, py ou php), PaaS
• Serviços de Rede (VNet) → comunicam as máqs. não tem conexão default.
gataway de VPN tbm. expressRoute (estende redes locais para azure)
• DNS do Azure → resolve os nodes e registra log.



IDENTIDADE ACESSO E SEG =================================================
• ID do Microsft Entra → serviço de gerenciamento de diretório e identidades
autenticação, login único (SSO), gerencia de APPs, negocio para negocio (b2b) etc

• Autenticação e autorização → é o logo, vc entra no local. o q vc pode fazer é autorização
Autorização é o nível de acesso. MFA (autenticação multifatorial), se alguém tem usu e senha
não sig q seja a pessoa (algo q sabe (senha) + algo q possui (cel) + algo q vc é (camera))
B2B autenticação → está fora do azure. empresa para empresa, dir separado.
B2C (costumer consumidores) → autentica usando entidade externa pra cadastras (usar o gmail ex)

• Acesso condicional → baseando em condições pra poder acessar verifica: grupo, IP,
dispositivo, App, detecta risco. com isso pode negar ou permitir.

• Controle de acesso baseado em função RBAC → conforme necessidade. 

• Confiança zero → segurança é pensar sempre o pior cenário. 
e pensar em tudo o q pode acontecer
Mais camadas e menor privilégio pra cada pessoa

• Microsft Defender para nuvem → ferramenta para ver o ambiente, ação e correção para ambiente
e vc pode ativar camadas de proteção.

================================================== ATIVIDADES ======================================
02- máqs vituais 
Valores de SLA (acordo de tempo de inatividade) qnto > = tempo<
Todos os serviços → computação → maqs vituais
+ criar (maq virtual do azure)
Olhar disponibilidade → pode criar zonas de acordo com SLA
IMG01

Qntidade de zonas, até três
IMG02


O armazenamento tbm pode ser feito (mudando onde está o cursor):
IMG03


=========================================================================================================
03- Instância de BD
Ainda na criação de máq virtual é possível visualizar, de acordo com a escolha do SO, o valor mensal
IMG04

Avançar discos (parte de baixo) e vc continua a config
IMG05

Rede → gerenciamento → monitoramento 
Tudo deve ser preenchido para criação 
No menu à esq, há “Banco de Dados SQL”, para criar um BD
+ criar →
IMG06

Precisa fazer um servidor, ou indicar um.
IMG07

Escolhe modelo de redundância
IMG08

Já gerando o valor

=========================================================================================================
04- construindo arquiteturas
Sites para ver arquiteturas:
azure.microsoft.com
datacenters.microsoft.com
Dados sensíveis q não podem sair do Brasil, é preciso fazer um requerimento pra Microsoft para replicar aqui. 
Nosso center fica em são Paulo (sudeste), e replicação no RJ. Se for Sul, replicação é pros EUA
Criando grupo de recs:
IMG09

Menu dir → grupos de recursos
IMG10
sua assinatura já vem de acordo com sua, se tiver mais então escolhe. O resto vc configura
Criar subtítulo para recs, colocar o nome e tals:
IMG11



É criado sem nada dentro
IMG12

Menu à esq → IAM é o controle de acesso!
Todo gerenciamento no menu à esq
Dá pra colocar dentro a rede virtual (vnet)
IMG13
IMG14

=========================================================================================================
05- conf recs e dimensionando máqs
Maqs virtuais → +criar (máq virt do azure, outras já têm pré-config com soluções)
Assinatura → grupo de recs → nome da máq → região → disponibilidade 

*(opções: conj de dimensionamento de máqs virt) = criar novo → descer a pág até contagem de instâcias..
No modo de dimensionamento = atualizar manualmente ou automático
Contagem inicial = 2 e máx 20, é como vem, mas dá pra alterar (para black Friday), consulta padrão = 10, mas dá pra mudar.

Instância spot = vc paga metade, mas se chegar alguém q quer pagar tudo vc sai. Vc é derrubado, vale pra desenvolvimento e teste
NUNCA EM PRODUÇÃO.
SEMPRE deixar marcado “excluir com a vm” na escolha do disco. PRA NÃO PAGAR MAIS

Máq precisa estar na mesma localidade da Rede virtual q vc deseja alocar a máq
SEMPRE DEIXAR: excluir IP público e a NIC qndo máq excluída
Habilitar BACKUP

Na parte de alertas dá pra habilitar alertas, assim q clica abre menu
E por fim, já dá pra colocar uma extensão caso queira, como segurança ex
No final já vem o preço

•	 área de trab virtual → cria img em pool ou em pessoal (qndo tem algo q só ela acessa ou usa)

•	Apps de funções → de acordo com a escolha da linguagem já gera o SO  


