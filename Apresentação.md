# Workshop - Kubernetes na Google Cloud Plataform

**Autor: Márcio de Oliveira Jales Costa**

**Data:**

**Duração: 3 horas**

**E-mail: marcio.dojcosta@gmail.com**

## Palestrante

Márcio Jales, ex-aluno da UFRN, formado em 2017.1, em seu primeiro (tecnicamente, segundo) emprego no cargo de Site Reliability Engineer, na AppProva, Belo Horizonte.

#### A empresa

**AppProva** é uma companhia que conta com mais de 250 colaboradores, em franca expansão. Foi adquirida pela **Somos Educação** no ano passado que, por sua vez, foi adquirida pela **Kroton educacional**, maior empresa privada no mundo no ramo de educação.

Suas soluções partem desde o ensino básico ao ensino superior, com plataformas digitais de preparação para o ENEM, OAB, ENADE, dentre outros, além de soluções integradas (digital + material pedagógico).

## Motivação

Em um passado não tão distante, equipes de operações de TI e de desenvolvimento eram "adversárias". Enquanto a primeira queria um sistemas altamente estável, com poucas mudanças que, inerentemente, trazem riscos, a segunda queria entregar novas funcionalidades o mais frequente possível. Além disso, testes e novas *releases* ocorriam apenas no final de ciclo de desenvolvimento. Assim, havia pouco *feedback* sobre a aplicação e a quantidade de funcionalidades tornavam sua implantação complexa (alto "débito técnico"). Com essa cultura, analistas e engenheiros de TI constantemente tinham seus trabalhos resumidos a "apagar incêndios".

Tudo começou a mudar quando vários movimentos culminaram na "convergência do DevOps", nos quais destacam-se o **manifesto Agile** e o **movimento Lean**, trazendo conceitos da industria como "fluxo de valor" (*value stream*). Assim, testes e validação ocorrem **simultaneamente** ao processo criativo de desenvolvimento de software, e não mais apenas no final. No novo paradigma, desenvolvedores fazem pequenas entregas, várias vezes ao dia, e todas chegam em produção rapidamente. Isto torna mais fácil a depuração de um eventual problema, já que pouco código foi escrito, e, assim, *feedbacks* constantes, além dos clientes experimentarem novas funcionalidades frequentemente.

Tudo isso levou aos conceitos e ferramentas muito comuns em desenvolvimento web, como **Integração/Entrega Contínua (CI/CD)**, **Conteiners**, **Microservices**, **Infraestrutura como código (IaC)** etc.

No âmbito da administração de sistemas, *Site Reliability Engineering* é o principal subconjunto do DevOps. Esta filosofia mudou o foco do adminstrador do tradicional para a engenharia de software. A função que antes se concentrava em uma série de tarefas repetitivas e manuais, mudou seu foco para uma automatização intrínseca. Some-se a isto a *Cloud Computing* e obtem-se o novo administrador de sistemas.

**Kubernetes** é fruto desta nova maneira de pensar. Com base em anos de experiência no Google em administração de infraestruturas complexas altamente escalável, criou-se um ferramente que permite que uma aplicação web seja escalada, atualizada e renovada automataticamente, sem *downtime*.


## Objetivo

Introduzir o espectador ao mundo *DevOps*, a nova cultura de operações em TI, e SRE (*Site Reliability Engineering*), uma ramificação do *DevOps*.

Após, apresentar uma das mais importantes ferramentas atuais na provisão de aplicação web com alta disponibilidade, o **Kubernetes**, utilizando o ambiente *cloud* da **Google Cloud Plataform** (GCP).

Nível abordado será, no geral, introdutório, porém rapidamente chegando a *insights* mais avançados.

## Sumário

- Parte 1 (30 min):
  - Apresentação do palestrante;
  - Motivação;
  - A cultura DevOps e SRE;
- Parte 2 (30 min):
  - O que são containers (Docker);
  - O que é o Kubernetes;
  - Porquê Kubernetes na GCP;
  - Conceitos essenciais do Kubernetes;
  - Arquitetura do Kubernetes;
- Parte 3 - Hands-on (2 horas):
  - Meu primeiro *Deployment*:
    - Criando *Pods*;
    - *Pods* controlados por um *ReplicaSet*;
    - *ReplicaSet* controlado por um *Deployment*;
    - *DaemonSet*;
  - *Labels* e *Annotations*;
  - *Jobs*, aplicações que executam até o término;
  - Acessando minha aplicação:
    - *Service Discovery* com *Services*:
      - Tráfego interno com *ClusterIP*;
      - Tráfego externo com *NodePort*;
      - Mais robustes com *LoadBalancer*;
    - Exposição e roteamento com *ingress*;
      - GCE L7;
      - Traefik;
  - Configuração com *ConfigMaps* e *Secrets*

## Passos preliminares

Todas as demonstrações serão feitas no **Google Cloud Plataform**. Lá, utilizaremos o **Kubernetes Engine**, a solução de Kubernetes integrada do Google.

Como a proposta do curso é uma abordagem *hands-on*, aconselha-se fortemente que essa conta seja aberta. O Google derá US$ 300 gratuitamente para utilizar na plataforma durante 12 meses, portanto não incorrerá nenhum gasto a vocês.

O ambiente mais comum em demonstrações do Kubernetes é o **Minikube** um *cluster* local, com apenas um nó, geralmente utilizado para fins de desenvolvimento e teste local. Porém, achei mais interessante basear-se em uma solução corporativa e robusta, para que você tenha um contato com o que se utiliza no mercado.

É importante que sua conta esteja feita no dia do curso, pois isto **não será feito** lá. Apenas as configurações e ajustes necessários nela que serão demonstrados.

**Qualquer dúvida, não hesite em entrar em contato pelo e-mail no topo do documento**

## Leituras preliminares

Esta leitura não é obrigatória. Porém, algumas tópicos interessantes para um melhor entendimento não serão abordados, como **containers com Docker**. Além disso, sempre é bom chegar com algum conhecimento preliminar, pois facilitará a assimilação durante o workshop.

1. Kubernetes: Up and Running. Kelsey Hightower, Joe Beda, Brendan Burns, 2017. Capítulos 1 e 2
2. Docker Overview. Disponível em https://docs.docker.com/engine/docker-overview/.
3. A Beginner-Friendly Introduction to Containers, VMs and Docker. Disponível em https://medium.freecodecamp.org/a-beginner-friendly-introduction-to-containers-vms-and-docker-79a9e3e119b
4.  Site Reliability Engineering. Editado por by Betsy Beyer, Chris Jones, Jennifer Petoff e Niall Richard Murphy, 2016. Parte 1, capítulos 1 e 2. Disponível em https://landing.google.com/sre/book.html
