# Workshop - Kubernetes na Google Cloud Plataform

**Autor: Márcio de Oliveira Jales Costa**
**Data: 01/09/2018**
**Duração: 3 horas**

## Objetivo

Introduzir o espectador ao mundo *DevOps*, a nova cultura de operações em TI, e SRE (*Site Reliability Enginerrging*), uma ramificação do *DevOps*.

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
