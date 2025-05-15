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
