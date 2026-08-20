# Internal Security Audit — Botium Toys

## Sobre o projeto

Este projeto apresenta uma auditoria interna de segurança realizada a partir de um cenário fictício da Botium Toys durante meus estudos no Google Cybersecurity Professional Certificate.

O objetivo foi analisar a postura de segurança da organização, revisar controles existentes, identificar lacunas e avaliar práticas de conformidade relacionadas a PCI DSS, GDPR e SOC.

## Escopo

A auditoria considerou o programa de segurança da Botium Toys, incluindo:

- equipamentos e dispositivos de funcionários;
- rede interna;
- sistemas e serviços corporativos;
- banco de dados e armazenamento de informações;
- sistemas de e-commerce e inventário;
- sistemas legados;
- controles físicos da unidade.

O cenário apresentou um nível de risco geral de **8/10**, indicando necessidade de melhorias relevantes na postura de segurança.

## Avaliação dos controles

| Controle | Status | Observação |
|---|---|---|
| Least Privilege | ❌ Não implementado | O acesso aos dados internos é amplo e não está limitado apenas ao necessário para cada função. |
| Disaster Recovery Plan | ❌ Não implementado | Não existe um plano formal de recuperação após incidentes. |
| Password Policy | ✅ Implementado parcialmente | Existe uma política de senhas, mas seus requisitos são fracos. |
| Separation of Duties | ❌ Não implementado | Responsabilidades críticas não estão devidamente separadas. |
| Firewall | ✅ Implementado | O firewall bloqueia tráfego com base em regras de segurança definidas. |
| IDS | ❌ Não implementado | Não há sistema de detecção de intrusões instalado. |
| Backups | ❌ Não implementado | Não existem backups dos dados críticos. |
| Antivirus | ✅ Implementado | O antivírus está instalado e é monitorado regularmente. |
| Monitoramento de sistemas legados | ✅ Implementado parcialmente | Existe monitoramento e manutenção, mas sem cronograma regular e procedimentos claros. |
| Encryption | ❌ Não implementado | Dados sensíveis, incluindo informações de cartão, não são criptografados. |
| Password Management System | ❌ Não implementado | Não existe um sistema centralizado para aplicar os requisitos da política de senhas. |
| Locks | ✅ Implementado | A unidade física possui fechaduras adequadas. |
| CCTV | ✅ Implementado | A empresa possui sistema de vigilância por câmeras atualizado. |
| Fire Detection/Prevention | ✅ Implementado | Existem sistemas funcionais de detecção e prevenção de incêndio. |

## Compliance

### PCI DSS

| Prática | Status |
|---|---|
| Restringir dados de cartão apenas a usuários autorizados | ❌ Não atende |
| Armazenar, processar e transmitir dados de cartão em ambiente seguro | ❌ Não atende |
| Utilizar criptografia nos dados e pontos de transação | ❌ Não atende |
| Adotar políticas seguras de gerenciamento de senhas | ❌ Não atende |

### GDPR

| Prática | Status |
|---|---|
| Manter dados de clientes da União Europeia privados e protegidos | ❌ Não atende adequadamente |
| Notificar clientes da União Europeia em até 72 horas após uma violação | ✅ Atende |
| Classificar e inventariar adequadamente os dados | ❌ Não atende |
| Aplicar políticas e procedimentos de privacidade | ✅ Atende |

### SOC

| Prática | Status |
|---|---|
| Políticas adequadas de acesso de usuários | ❌ Não atende |
| Manter PII/SPII confidenciais e privadas | ❌ Não atende |
| Garantir integridade dos dados | ✅ Atende |
| Garantir disponibilidade dos dados | ✅ Atende |

## Principais riscos identificados

Os pontos de maior preocupação foram:

1. acesso excessivo a dados internos e informações sensíveis;
2. ausência de criptografia em dados de cartão de crédito;
3. inexistência de backups de dados críticos;
4. ausência de plano de recuperação de desastres;
5. ausência de IDS para detecção de possíveis intrusões;
6. política de senhas fraca e sem gerenciamento centralizado;
7. falta de organização formal para manutenção de sistemas legados.

## Recomendações

### 1. Implementar Least Privilege e Separation of Duties

Restringir o acesso dos funcionários apenas aos dados e sistemas necessários para suas funções e dividir responsabilidades críticas entre pessoas diferentes.

### 2. Implementar criptografia

Aplicar criptografia para proteger informações sensíveis, especialmente dados de cartão de crédito, durante armazenamento, processamento e transmissão.

### 3. Criar backups e um plano de recuperação de desastres

Realizar backups regulares dos dados críticos e estabelecer um plano formal para reduzir o impacto de incidentes e facilitar a retomada das operações.

### 4. Implementar um IDS

Adicionar um sistema de detecção de intrusões para melhorar a capacidade de identificar tráfego suspeito e possíveis ataques na rede.

### 5. Fortalecer a gestão de senhas

Aumentar os requisitos mínimos da política de senhas e implementar um sistema centralizado para garantir que essas regras sejam aplicadas de forma consistente.

### 6. Formalizar a manutenção de sistemas legados

Criar um cronograma regular de monitoramento, manutenção e intervenção, além de definir claramente os procedimentos usados nesses sistemas.

## O que aprendi

Esta atividade me ajudou a entender que uma auditoria de segurança não consiste apenas em verificar se um controle existe ou não. É necessário analisar as evidências do ambiente, entender o risco causado pela ausência ou implementação inadequada de cada controle e relacionar essas conclusões às necessidades de segurança e conformidade da organização.

Também ficou mais clara para mim a diferença entre controles preventivos, detectivos, corretivos e físicos, além da relação entre confidencialidade, integridade e disponibilidade dos dados.

## Status

✅ Projeto concluído.
