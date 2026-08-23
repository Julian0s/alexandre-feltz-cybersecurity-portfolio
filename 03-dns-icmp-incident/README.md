# 03 — Análise de tráfego DNS e ICMP

## Visão geral

Este projeto acadêmico documenta a análise de um incidente de rede apresentado no **Google Cybersecurity Professional Certificate**, no Coursera.

O cenário simulava usuários incapazes de acessar o site `yummyrecipesforme.com`. O objetivo foi interpretar registros do `tcpdump`, identificar os protocolos envolvidos e registrar uma hipótese responsável para a causa do incidente.

## Principais conclusões

- O navegador tentou consultar o serviço DNS para descobrir o endereço IP do site.
- A consulta DNS foi enviada usando UDP para a porta 53.
- Mensagens ICMP informaram que a porta UDP 53 estava inacessível.
- Sem uma resposta do DNS, o navegador não conseguiu obter o endereço IP e prosseguir para o site.
- O registro comprova a indisponibilidade da porta, mas não determina sozinho a causa exata.

## Habilidades praticadas

- Leitura básica de registros do `tcpdump`
- Identificação de DNS, UDP, ICMP e porta 53
- Interpretação de tráfego de origem e destino
- Diferenciação entre evidência e hipótese
- Documentação de um incidente de rede

## Relatório

[Leia o relatório do incidente](./incident-report.md).

## Observação

Este é um exercício acadêmico realizado durante minha formação. As conclusões representam meu nível atual de aprendizado e não um incidente profissional real.
