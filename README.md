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

================================================== ATIVIDADES 

02- máqs vituais 
Valores de SLA (acordo de tempo de inatividade) qnto > = tempo<
Todos os serviços → computação → maqs vituais
+ criar (maq virtual do azure)
Olhar disponibilidade → pode criar zonas de acordo com SLA

![img01](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img01.jpg)

Qntidade de zonas, até três

![img02](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img02.jpg)

O armazenamento tbm pode ser feito (mudando onde está o cursor):

![img03](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img03.jpg)

==================================================================================

03- Instância de BD
Ainda na criação de máq virtual é possível visualizar, de acordo com a escolha do SO, o valor mensal

![img04](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img04.jpg)

Avançar discos (parte de baixo) e vc continua a config

![img05](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img05.jpg)

Rede → gerenciamento → monitoramento 
Tudo deve ser preenchido para criação 
No menu à esq, há “Banco de Dados SQL”, para criar um BD
+ criar →

![img06](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img06.jpg)

Precisa fazer um servidor, ou indicar um.

![img07](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img07.jpg)

Escolhe modelo de redundância

![img08](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img08.jpg)

Já gerando o valor

==================================================================================

04- construindo arquiteturas
Sites para ver arquiteturas:
azure.microsoft.com
datacenters.microsoft.com
Dados sensíveis q não podem sair do Brasil, é preciso fazer um requerimento pra Microsoft para replicar aqui. 
Nosso center fica em são Paulo (sudeste), e replicação no RJ. Se for Sul, replicação é pros EUA
Criando grupo de recs:

![img09](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img09.jpg)

Menu dir → grupos de recursos

![img10](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img10.jpg)

sua assinatura já vem de acordo com sua, se tiver mais então escolhe. O resto vc configura
Criar subtítulo para recs, colocar o nome e tals:

![img11](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img11.jpg)


É criado sem nada dentro

![img12](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img12.jpg)

Menu à esq → IAM é o controle de acesso!
Todo gerenciamento no menu à esq
Dá pra colocar dentro a rede virtual (vnet)

![img13](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img13.jpg)

![img14](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img14.jpg)

==================================================================================

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

==================================================================================

06- Análise de sentimentos com language studio
Laguage estúdio → ter conj de ferramentas, para entender frases. Ajuda a classificar um texto. Saber o qnto as pessoas estão felizes. O q as pessoas acham em uma única frase. Conseguimos personalizar com perguntas etc.
Serviço de bot → visado para retorno de dúvidas. É preciso muita base de dado para ele ser bom. E a IA vai trazer as melhores respostas. Vai criar resposta através de palavras chaves. Sempre testar. Ajuda a ajustar os scripts para empresas que trabalham com atendimento por telefonia etc. 

Linguagem coloquial → é a compreensão da IA com nossa linguagem do dia a dia. Formado por Declaração (o que eu quero q faça), Intenção (o q eu quero com isso), entidade (o aparelho q estou comandando) = tudo é uma síntese da fala. Reconhecimento e síntese da fala convertendo texto em fala e vice-versa q podemos usar.
Links úteis: • aka.ms/ai900-speech
	      • aka.ms/ai900-text-analysis
Estúdio de fala:
Speech.microsoft.com
Transcreve arqv de aúdio. Ou contrário.
Vá em config (engrenagem) → + criar novo rec

![img15](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img15.jpg)

Depois volta e vá em conversão de fala em texto em tempo real

![img16](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img16.jpg)

Selecionar o texto e a linguagem

![img17](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img17.jpg)

Como usar e serviços para automatizar etc, pra cada serviço um preço:

![img18](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img18.jpg)

Conhecendo o lenguage studio
Create a resource → AI+ machine learning → language service (vai aparecer à dir nos ícones)

![img19](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img19.jpg)

Config

![img20](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img20.jpg)

Create, vai pro cognitive (outro site)

![img21](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img21.jpg)

Criar um novo

![img22](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img22.jpg)

Tipo classificação de texto

![img23](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img23.jpg)

Analisar sentimentos e opiniões, então coloca-se o texto e é feita a análise 

==================================================================================

07-	Azure Cognitive Search: Utilizando AI Search para indexação e consulta de Dados
Pesquisa cognitiva→ pega os dados e mineira para insights. Com a plat do azure pra isso. Preciso de um mecanismo de pesquisa, uma indexação (uma busca estratégica), e a sintaxe para auxiliar. E IA com treinamento pode fazer isso
No Azure → dados recebidos e processados, IA é enriquecida para entender pesquisa. Entender modelo de negócio e tipo de pesquisa para saber o q fazer.
Deve informar por json.
Enriquecimento da IA → mais dados para a pesquisa, qnto mais melhor. Ter acesso ao máximo possível de info para alimentar IA.
E como vou trabalhar esses dados.
Documentação: aka.ms/ai-900-ia-search

Buscas cognitivas → vá no AI Search

![img24](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img24.jpg)

Create → e no price tier selecionar o tipo.
Review + create. 
E cria um AI servisse

![img25](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img25.jpg)

 (feito acima)

![img26](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img26.jpg)

MARCA o check box abaixo
STORAGE ACOUTS → criar →

![img27](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img27.jpg)

Precisa ser único no storage account name.
Em redundância:
 
Após review e create.
Após criar, tela pronta

![img28](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img28.jpg)

Por padrão tem algumas normal de segurança (em settings → configuration)

![img29](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img29.jpg)

habilitar e salvar

![img30](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img30.jpg)

Dentro do storage → vá em + container →

![img31](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img31.jpg)

Criar
Clica nele e já pode fazer upload de arqvs

![img32](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img32.jpg)

Vá no mecanismo de busca (IA Search) e importa dados

![img33](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img33.jpg)

Aponta onde está os docs e criar pesquisa 

![img34](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img34.jpg)

Com uma revisão:

![img35](https://github.com/WyldnerPina/resumoLabDioAzure/blob/main/img/img35.jpg)

Faço uma tríade para automatizar a IA e trazer resultados de forma rápida e precisa.

==================================================================================

08-	Explorando os Recursos de IA Generativa com Copilot e OpenAI
IA generativa responsável → planejamento das IAs, 4 fases = identificar (possíveis danos para o planejado), medida (dados na saída), mitigar (dificultar o máx o dano, se não funcionar em termo de cód) e operar (como implantar etc)
•	Docs introdução → aka.ms/ai900-bing-copilot
		       aka.ms/ai900-azure-openai
		       aka.ms/ai900-content-filters
copilot.microsoft.com para acessar (é a IA do bing)
•	Microsoft learning → aka.ms/oaiapply
Precisa solicitar para usar no azure. Precisa estar associado a uma organização.


•	 área de trab virtual → cria img em pool ou em pessoal (qndo tem algo q só ela acessa ou usa)

•	Apps de funções → de acordo com a escolha da linguagem já gera o SO  


