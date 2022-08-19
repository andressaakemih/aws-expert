# AWS Expert

* Assunto: AWS
* Criado: March 14, 2022 11:54 AM
* Documentação: https://docs.aws.amazon.com/index.html
* Finalizado: No
* Materiais: https://school.linuxtips.io/courses/enrolled/1703523
* Plataforma: LinuxTips

# AWS Expert

## Day 01

### What is Cloud?

*A ideia de Cloud Computing é poder rodar os “nossos” serviços, os “meus” produtos em algum lugar que eu consiga fornecer isso para alguém, que eu consiga escalar, trazer uma certa elasticidade* 

*Existem algumas caracteristicas que pode considerar um Cloud Computing* 

*Marco “Criação” → 2006, quando a Amazon lançou o produto de máquina virtual que você poderia subir serviços e pagar por hora*

### Characteristics and Advantages

- *Agility → Para ser considerada Cloud Computing a agilidade é uma das primeiras  caracteristicas*
    
    *Os times de desenvolvimento sempre tiveram ferramentas para isso, de Operações “nunca pensaram” ou “nunca tiveram” que entregar coisas de maneira ágil*
    
    - *Time Dev: Sempre tiveram ferramentas para entregar projetos de maneira ágil*
    - *Time Operação e Infraestrutura: Começaram a trabalhar com agilidade após o Cloud, não tem que ficar lidando com a infraestrutura física, Data Center*
- *Maintenance → Data Center é caro, precisa de manutenção e mais funcionários para conseguir manter esse ambiente funcionando*
- *Reliability →  Aumenta a confiabilidade porque é um serviço que tem especialistas cuidadando desse ambiente*
- *Security → Tem muitas ferramentas e recusos de segurança na AWS*
- *Performance → O cloud é pago por demanda, se você precisar de performance você pagará por isso*
- *Scability → Se a aplicação for projetada para ser rodado no Cloud, tem essa possibilidade de escalar o serviço sob demanda. Ex: Black friday. Se eu tive um pico de acesso, eu escalo 1 servidor para 2*
- *Cost and Elasticity → Possibilidade de gerenciar o custo sob demanda, depende de como será utilizado, tem a redução de custo mas precisa usar da maneira correta. Elasticidade: Não é infinito, alguns recursos serão limitados, ter planejamento é essencial, caso precise de um recurso ou produto pode ser que não tenha disponível.*

**NIST (The National Institute of Standards and Technology)**

- *On demand self-service*
- *Broad network access*
- *Resource pooling*
- *Rapial elasticity*
- *Measure service*

### **Service models**

- *IaaS (Infraestrutura como serviço) → Se não tenho uma infraestruta instalada, então utilizo esse serviço (mais utilizado)*
- *PaaS (Plataforma como serviço) → Quero rodar meu produto sem precisar me preocupar com o que está por trás (pouco utilizado)*
- *FaaS (Função como serviço) → Por ex. Um serviço de envio de e-mail (pouco utilizado)*

### **Deployment models**

- *Private Cloud → É o Cloud que é seu, não é compartilhado com outras empresas. Ex: Se você tem um VMWare e fornece VMs para outras pessoas*
- *Public Cloud → Qualquer um pode usar e ter acesso aquela plataforma*
- *Hybrid Cloud → Utiliza o Cloud private e public. Ex: Tenho serviços utilizando esses dois tipos de cloud*
- *Multicloud* → Pode rodar todos os seus serviços em todos os clouds. Ex: Se um player falir você tem o outro para continuar rodando*
- *Community → Empresas se reunem e constroem um cloud comunitário*

## Day 02

### Foundation

### Root Accounts, part 1

*É necessário planejar a melhor forma para começar a utilizar o Cloud*

*A maioria dos problemas estão relacionados a base (o básico)*

*Ex: Configuração da conta, de rede*

![Root accounts aws](https://github.com/andressaakemih/aws-expert/blob/main/img/Untitled.png)

### Root Accounts, part 2

*Root Account características:*

- *É uma conta que você gerencia as outras,  primeira (principal) conta adicionada, a partir dessa conta você cria outras, organização, o ideal é não utilizar essa conta*
- *Basicamente é a conta que serve para você inciar a criação de novas contas, cobrança de serviços*
- *Organização (Não ficar numa única view)*
- *Segurança (Se for “hackeado” a conta que tem tudo, é um problema)*
- *Na prática não é utilizada para subir recursos, é uma boa prática não utilizar a root account para fazer deploy*

*Dica: Se você vai deployar serviços, rodar coisas em PRD, terá outras contas (não é obrigatório), é uma boa prática*

→ *Tem custo criar outras contas? Não*

*→ Tem custo se estiver rodando algum serviço*

### Organizational Unit (OU)

→ *Unidade de organização das suas contas, não só para organizar visualmente, mas também para gerenciamento*

→ *Posso aplicar regras específicas para aquela Unidade organizacional. Ex: OU Dev → Máquinas com um tipo de configuração*

→ *É uma forma de você categorizar suas contas*

→ *Pode aplicar regra para uma conta específica*

→ *É uma boa prática*

*→ Zonas de disponibilidade (Ex: Uma máquina em SP custa mais que em outra região)*

→ *Unidade organizacional por empresas*

### AWS Accounts

- *Sub accounts → São contas criadas abaixo da “root account” utilizadas, com a finalizade de rodar serviços*
- *Caracteristicas de root account → nome, e-mail único*
- *Não usar o e-mail de um funcionario, usa o e-mail do time que vai cuidar disso. Ex: de finaceiro@...*
- *Precisar ler os e-mails*
- *Criar um e-mail válido*
- *Identity → Gerenciador de identidade para cada conta, permissões*
- *Resources → Serviços*    ****

### **AWS Support Center, Service Limits**

*Usar as recomendações passadas pela Amazon*

*Health events → Informações passadas, ex: uma anomalia da conta, algum problema*

*Create case (tem que ser feito em contato em inglês)* 

*Account and biling support: problema relacionado a conta*

*Service limit increase: a sua conta vem com recursos limitados, então se for necessário é para solicitar serviços, por ex: EC2 instances, justificar (software e hardware limits)*

*Technical support: para algum problema técnico (não pode ser com o básico, tem que ter outros planos)*

### **AWS SCP - Service Control Policies, part 1**

*Polices IAM*

*Service Control Polices*

### Lessons

1. *Em uma Organization com 10 AWS Accounts, quantas Root Accounts existem?*
    
    *R. 10*
    
2. *Qual a finalidade de uma OU na AWS?*
    
    *R. Organizar visualmente AWS Accounts e nas regras de segurança dos serviços*
    
3. *Uma Service Control Policy, pode ser aplicada em quais objetos?*
    
    *R. OU e Accounts*
    
4. *O que melhor defini os custos de criação de AWS Accounts?*
    
    *R. Não existe custo*
    
5. *Quantas horas por mês pode ser utilizado o serviço de maquinas virtuais da AWS de forma gratuita?*
    
    *R. 750 horas*
    
6. *Um cliente, quer migrar seu data center para a nuvem e continuar usando os serviços de VMs que hoje ele tem local. Qual modelo de Cloud é mais apropriado para ele?*
    
    *R. IaaS - Infrastructure as a Service*
    
7. *Qual dessas afirmações esta correta:*
    
    *R. Cloud Computing ajuda na “adoção” de DevOps*
    
8. *Qual a diferença entre Master Account de Root Account?*
    
    *R. Master Account é a primeira conta criada na AWS e Root Account é o usuário dono de uma AWS Account.*
    

### Exercício

```
Quando terminar de responder as perguntas acima, faça este exercício.

Scenario 1: Crie uma outra conta na AWS, acessando sua conta principal no menu My Organization, através da segunda opção Create account.
Scenario 2: Agora, crie uma outra conta usando a opção Invite account. Para isso, você precisar criar essa conta antes.
No total do dia, você precisa ter 3 contas criadas na AWS, na seguinte estrutura:

Organizaçõa das contas:

Master Account/Payer Account
    1 OU: Dev
      Dev Account
    1 OU: Prod
      Prod Account

Na conta de Dev, os usuarios não devem conseguir criar RDS
Na conta de Prod, os usuarios não devem conseguir criar S3

Simule o uso dessas SCP em cada conta, usando outros browsers para poder logar
em multiplas contas ao mesmotempo.
Ex.: Chrome para logar na Master Account, Firefox para logar na conta Dev com o Root(email da conta) e
Modo incongnito do firefox ou do Chrome para logar na conta de Prod com o Root(email da conta).

Obs: Use SCP para definir essas regra, e attach em cada conta sua respectiva SCP.
Execute o exercicio, grave um video da sua tela e envie o resultado no grupo do Telegram, me marque lá(Mateus Prado)
Imagina que você quer que alguem pegue esse material e consiga fazer sozinho, como se você estivesse fazendo um tutorial, how-to para a comunidade! Como você gostaria que fosse esse material? Pense como se fosse você procurando isso no Google :)

Troque informações no grupo do Telegram, tire dúvidas, compartilhe idéias com os colegas do grupo.

Boa sorte

Mateus
```

### Links

- *AWS Landing Zone: [https://aws.amazon.com/solutions/aws-landing-zone/](https://aws.amazon.com/solutions/aws-landing-zone/)*
- *AWS Organizations: [https://aws.amazon.com/organizations/](https://aws.amazon.com/organizations/)*
- *AWS Account: [https://aws.amazon.com/account/](https://aws.amazon.com/account/)*
- *AWS SCP: [https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scp.html](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scp.html)*
- *Example Service Control Policies: [https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_example-scps.html](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_example-scps.html)*
- *AWS Calculator: [https://calculator.s3.amazonaws.com/index.html](https://calculator.s3.amazonaws.com/index.html)*

## Day 03

### AWS Well-Architected - Intro

*A AWS criou um framework Well-Architected “bem arquitetado”, de melhoras práticas*

*Ele virou um produto*

*É um documento que tem questionario com diversos pilares (performance, segurança, etc...)*

*Aplicar o que tem no Well-Architected*

*No fim ele mostra um relatório mostrando o que é “critico”*

### What is the AWS Well-Architected Framework?

*É um framework, nele contém:*

*Pilars → Questionários, documentos de determinados assuntos* 

*Design principles → Seus principios vão ser baseados com design. Aprende, mede e e melhora. É um ciclo*

*Questions →  É um questionário que ajuda a dar um norte sobre suas boas práticas, nos diversos assuntos, tem relatório*

### Vantagens de aplicar o Well-Architected

*Speed → Velocidade em deployar e contruir coisas dentro da AWS (usa o* Well-Architected, é de graça!)

*Mitigate risks → Tem risco de usar o cloud, então não é “eliminar” o risco, o* Well-Architected *mostra qual o risco alto ou baixo, aparece no relatório*

*Make informed decisions → Por ex: estar documentado o que foi aplicado*

*Use AWS best practices → Usar as melhoras práticas do AWS*

*Learn → Aprende*

*Measure → Mede*

*Improve → Melhora*

### **Today's Lesson**

```
**Se você já usa AWS, escolha uma aplicação, um serviço específico e tente rodar o Well-Architected nele. Não publique os resultados, use isso dentro da empresa.
Leia cada paper do Well-Architected que está na doc(veja em Links) e entenda mais degtalhes de cada Pilar do framework

Execute na sua conta pessoal da AWS o Well-Architected, criando um workload inicial para medir a qualidade de cada pilar na sua conta inicial.
Vá durante o treinamento, criando milestones, e vendo a evolução da sua conta.
No final do treinamento, vamos rever cada pilar juntos.**
```

### **Links**

- *AWS Well-Architected Tool - [https://aws.amazon.com/well-architected-tool/](https://aws.amazon.com/well-architected-tool/)*
- *AWS Well-Architected Doc - [https://aws.amazon.com/architecture/well-architected/](https://aws.amazon.com/architecture/well-architected/)*
- *The 5 Pillars of the AWS Well-Architected Framework - [https://aws.amazon.com/blogs/apn/the-5-pillars-of-the-aws-well-architected-framework/](https://aws.amazon.com/blogs/apn/the-5-pillars-of-the-aws-well-architected-framework/)*

## Day 04

### Security, Identity e Compliance IAM

*Responsável pela gestão dos usuários*

*Permissão dos usuários que realmente utilizam os serviços*

*Gestão de identidade da sua Organização, usuários*

*Cross Roles → Não precisa sair da conta para fazer outro procedimento*

*Não é recomendável utilizar a root account*

*Questão de segurança*

### IAM Dashboard

*ARN → Amazon Resource Name*

*Tudo que é criado na Amazon tem um ID*

### Groups & Users

*Groups → Categorizar usuários, separar para conseguir colocar permissão para o grupo de usuário, ex: DEV*

*Users → Não usar “nome do usuário” que não dê para identificar a pessoa*

*Add user > Select AWS access type*

*Programmatic access: Ex. Infra como código*

T*o criando uma aplicação e vou precisar algum recurso da AWS, pra isso será necessário conectar com um usuário*

*Usuário de serviço*

*Dica:* *colocar o nome do serviço como usuário para conseguir identificar*

*AWS Manegement Console access: Para pessoas “comuns”, tem acesso ao Console*

*Tags: consegue fazer filtros depois*

*Switch role: posso “saltar” de um tipo de conta para outra, por ex. dev para prod, sem precisar fazer logout (assume role)*

### Roles e Polices

*Roles → Começar a agrupar dentro de uma role várias politicas.* 

*Ex. especifica para grupo de dev, com permissões especificas, posso criar essas roles para incluir as polices.* 

- *Serviços que precisam de permissões, parecido com o Programmatic access, tem o modo mais seguro e recomendada pela AWS*

- *Não é porque está dentro da AWS que tem permissão para fazer tudo*

*- Usar para outras AWS account, ex. usar recursos de outra conta*

*- Quando um recurso pode falar com outro e que permissões ele tem*

*Polices → Tem polices gerenciadas pela AWS e também pode ser criada*

*Permissão de grupo é diferente de permissão de usuário*

*Dentro de uma police tem:*

*- Qual serviços se aplica*

*- O que ela pode fazer, nível de acesso (criar, ler e deletar)*

- *Condição especifica, por ex. por região SP*

*Polices versions: até 5 versões (arquivo JSON)*

### Today’s Lesson

```
Crie um user com Administrator Acess, adicione ele em grupo de Administrators. Ative MFA Virtual ou Físico para este usuário. 
Não utilize mais o usuário Root(email da conta) desta Account. Use uma senha de 64 caracteres no mínimo, e utilize um gerenciador de senhas. 
Ex.: 1Password, LastPass. Se você já tem uma conta que usa durante muito tempo, altere a senha da sua e ative MFA na Root Account. 
Instale o aws-cli, o utilitário linha de comando da AWS: [https://aws.amazon.com/cli/](https://aws.amazon.com/cli/) 
Crie um usuario do tipo Programmatic Access no IAM e attach a policy ReadOnlyAccess Apos instalar o aws-cli, 
configure ele usando: $ aws configure Doc em [https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html#cli-quick-configuration](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html#cli-quick-configuration)
```

## Day 05

*Usar um conta especifica para gerenciamento de identidade*

### Cross account roles

### Assume roles

### Create polices

### Error on create policy

### Identity providers

### Account settings

### Credentials report and overview