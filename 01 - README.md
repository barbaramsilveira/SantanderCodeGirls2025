#  Laboratório AWS EC2 — Documentação Técnica

Este repositório foi criado como parte do desafio da DIO com o objetivo de **consolidar conhecimentos sobre EC2** na AWS, **simulando** os principais passos de criação, configuração e gerenciamento de instâncias.

## Tecnologias e Serviços
- Amazon EC2
- AWS Free Tier
- SSH
- Ubuntu Server
- GitHub para documentação

****

# O que é uma instância EC2

O serviço **Amazon Elastic Compute Cloud (EC2)** disponibiliza capacidade computacional escalável na nuvem.  
Ele funciona sob demanda, ou seja, o usuário paga apenas pelo que utilizar.  

Além disso, o EC2 pode ser usado gratuitamente por meio do **Free Tier da AWS**, que oferece **até 750 horas mensais gratuitas** em instâncias elegíveis (como `t2.micro` ou `t3.micro`) durante os **12 primeiros meses** de uso.  
Após exceder esse limite ou terminar o período gratuito, a cobrança passa a ser feita conforme a utilização.

****
# IAM

O **Identity and Access Management (IAM)** é o serviço da AWS responsável por **gerenciar identidades e permissões de acesso**.  
Com ele, é possível controlar **quem pode acessar** determinados recursos e **quais ações** cada usuário ou serviço pode realizar.  

Esse controle é essencial para **garantir a segurança do ambiente em nuvem** e **evitar cobranças indesejadas**, permitindo aplicar o princípio do **menor privilégio** (dar somente as permissões estritamente necessárias).


****

# Tipos de Instâncias EC2

As instâncias da **Amazon EC2** são classificadas por famílias, cada uma otimizada para diferentes tipos de cargas de trabalho.  
Abaixo, um resumo dos principais tipos de instância:

| Família | Categoria                    | Exemplos                  |  Características Principais                                                                 |  Casos de Uso                                   |
|------------|----------------------------------|-------------------------------|------------------------------------------------------------------------------------------------|--------------------------------------------------|
| `t`        | Uso Geral (General Purpose)      | t2.micro, t3.micro            | Equilíbrio entre CPU, memória e rede. Elegíveis ao Free Tier.                                  | Aplicações web, dev/teste, ambientes de estudo   |
| `m`        | Uso Geral Avançado              | m5.large, m6i.large           | Mais poder de processamento para aplicações balanceadas.                                       | Aplicações corporativas, microsserviços         |
| `c`        | Computação Otimizada            | c5.large, c6g.medium          | Alta capacidade de CPU em relação à memória.                                                   | Processamento intensivo, servidores de jogos    |
| `r`        | Memória Otimizada               | r5.large, r6g.large           | Alta quantidade de memória RAM para cargas pesadas.                                           | Bancos de dados, cache em memória, análise      |
| `x`        | Memória Avançada                | x1e.xlarge, x2gd.medium       | Projetadas para grandes bancos de dados e aplicações corporativas robustas.                    | SAP HANA, bancos em larga escala                |
| `i` / `d`  | Armazenamento Otimizado         | i3.large, d2.xlarge           | Altíssimo desempenho de leitura e escrita em disco.                                           | Data lakes, NoSQL, Big Data                     |
| `p`        | GPU para Machine Learning       | p3.2xlarge                    | Otimizadas para treinamento de IA e deep learning.                                            | IA, ML, simulações complexas                    |
| `g`        | GPU para Gráficos               | g4dn.xlarge                   | Voltadas para renderização de gráficos e aplicações 3D.                                       | Renderização, streaming de jogos, design 3D     |
| `inf`      | Aceleração de Inferência ML     | inf1.xlarge                   | Aceleradores otimizados para inferência em Machine Learning.                                  | IA em produção, NLP, visão computacional        |

##  Observações
- As instâncias `t2.micro` e `t3.micro` fazem parte do **Free Tier** da AWS (até 750 horas mensais por 12 meses).
- Os nomes seguem o padrão: `<Família><Geração>.<Tamanho>`  
  Exemplo: `t3.micro` → família `t`, geração `3`, tamanho `micro`.

# Regiões e Zonas de Disponibilidade

Chamamos de **regiões** os locais físicos espalhados pelo mundo onde estão localizados os data centers da AWS.  
Cada região representa uma **localização geográfica distinta**, projetada para garantir **redundância**, **alta disponibilidade** e **segurança** dos serviços.

Dentro de cada região, existem **Zonas de Disponibilidade (Availability Zones)** — que são **conjuntos de data centers independentes**, porém interconectados com baixa latência.  
Essa estrutura permite que aplicações sejam implantadas de forma distribuída, aumentando a **resiliência** e reduzindo riscos de falhas.

*Importante:* Os **valores dos recursos variam** de acordo com a região escolhida. Por isso, é comum utilizar regiões com preços mais baixos ou próximas do público-alvo da aplicação.

## Exemplos de Regiões
| Região                  | Código         | Localização                |
|--------------------------|---------------|----------------------------|
| US East (N. Virginia)    | `us-east-1`   | Estados Unidos 🇺🇸          |
| US West (Oregon)         | `us-west-2`   | Estados Unidos 🇺🇸          |
| South America (São Paulo)| `sa-east-1`   | Brasil 🇧🇷                 |
| Europe (Ireland)        | `eu-west-1`   | Irlanda 🇮🇪                |
| Asia Pacific (Tokyo)     | `ap-northeast-1` | Japão 🇯🇵               |

**Dica:**  
- Para estudos e uso do Free Tier, a região `us-east-1` (N. Virginia) costuma oferecer mais serviços gratuitos e atualizações mais rápidas.  
- Para aplicações em produção, geralmente se escolhe a região **mais próxima do público final** para reduzir a latência.

## Autor(a)
Feito por **Bárbara Martins da Silveira** como parte do desafio de consolidação de estudos sobre EC2 na DIO

***

## Documentação Oficial:

[Gerenciando EC2 instâncias da Amazon](https://docs.aws.amazon.com/pt_br/toolkit-for-visual-studio/latest/user-guide/tkv-ec2-ami.html)
