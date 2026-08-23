# Relatório de incidente de segurança cibernética

## Parte 1 — Resumo do problema

Os registros do `tcpdump` mostram que o computador tentou consultar o servidor DNS para descobrir o endereço IP de `yummyrecipesforme.com`. A consulta saiu do endereço `192.51.100.15` com destino ao servidor DNS `203.0.113.2`, usando UDP e a porta 53.

O identificador `35084+` mostra que havia sinalizadores associados à consulta, enquanto `A?` indica uma solicitação de registro A — utilizado para associar um domínio a um endereço IPv4.

Em resposta, foram recebidas mensagens ICMP com o erro `udp port 53 unreachable`. Isso indica que a porta 53 do servidor DNS estava inacessível. O mesmo comportamento apareceu em três tentativas registradas. Como o navegador não conseguiu receber o endereço IP do domínio, não pôde prosseguir para o carregamento do site.

## Parte 2 — Análise e possível causa

O incidente foi observado hoje a partir das 13:24:32, quando clientes relataram que o site não carregava e apresentava a mensagem `destination port unreachable`. Durante a investigação, o acesso foi testado novamente com o `tcpdump` em execução. As consultas DNS falharam repetidamente e o ICMP comunicou a indisponibilidade da porta UDP 53.

O problema permanecia em investigação e foi encaminhado aos engenheiros de segurança. Os registros confirmam a falha de acesso ao serviço DNS, mas não comprovam sozinhos a causa raiz.

As próximas verificações devem confirmar se o servidor e o serviço DNS estão funcionando, se a porta 53 foi bloqueada pelo firewall e se existe alguma configuração incorreta no servidor ou na rede. Portanto, as possíveis causas incluem serviço DNS parado, bloqueio da porta ou erro de configuração. Um ataque de negação de serviço também poderia deixar o servidor sem responder, mas seriam necessárias outras evidências para confirmar essa possibilidade.

## Evidências observadas

```text
Origem: 192.51.100.15
Destino DNS: 203.0.113.2
Consulta: UDP para a porta 53
Sinalizadores: 35084+ e A?
Resposta: ICMP — udp port 53 unreachable
Repetições: três tentativas com o mesmo erro
Resultado: falha na resolução do domínio
```

## O que aprendi

Neste exercício, aprendi que o DNS permite ao navegador descobrir o endereço IP de um site, que consultas DNS podem usar UDP na porta 53 e que o ICMP pode comunicar erros de entrega. Também aprendi a identificar sinais básicos em um registro do `tcpdump` e a não tratar uma possibilidade, como um ataque, como fato sem evidências suficientes.
