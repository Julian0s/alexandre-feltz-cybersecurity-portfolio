# Relatório de incidente de segurança cibernética

## Parte 1 — Resumo do problema

Os registros do `tcpdump` mostram que o computador tentou consultar o servidor DNS para descobrir o endereço IP de `yummyrecipesforme.com`. A consulta foi enviada por UDP para a porta 53, utilizada pelo serviço DNS.

Em resposta, foram recebidas mensagens ICMP com o erro `udp port 53 unreachable`. Isso indica que a porta 53 do servidor DNS estava inacessível. Como o navegador não conseguiu receber o endereço IP do domínio, não pôde prosseguir para o carregamento do site.

## Parte 2 — Análise e possível causa

O incidente foi observado a partir das 13:24, quando usuários relataram que o site não carregava e apresentava a mensagem de porta de destino inacessível. Durante a investigação, as tentativas de consulta DNS falharam repetidamente e o ICMP comunicou a indisponibilidade da porta UDP 53.

O problema permanecia em investigação e foi encaminhado aos engenheiros de segurança. Os registros confirmam a falha de acesso ao serviço DNS, mas não comprovam sozinhos a causa raiz.

As próximas verificações devem confirmar se o serviço DNS está funcionando, se a porta 53 foi bloqueada por um firewall e se existe alguma configuração incorreta no servidor ou na rede. Portanto, as possíveis causas incluem serviço DNS parado, bloqueio da porta ou erro de configuração. Não há evidência suficiente no registro para afirmar que ocorreu um ataque.

## Evidências observadas

```text
Consulta: computador → servidor DNS, usando UDP
Resposta: ICMP — udp port 53 unreachable
Resultado: falha na resolução do domínio
```

## O que aprendi

Neste exercício, aprendi que o DNS permite ao navegador descobrir o endereço IP de um site, que consultas DNS podem usar UDP na porta 53 e que o ICMP pode comunicar erros de entrega. Também aprendi a não tratar uma possibilidade, como um ataque, como fato sem evidências suficientes.
