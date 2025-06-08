# Sistema de Monitoramento de Qualidade do Ar em Regiões de Risco

## Descrição
Este projeto simula um sistema de monitoramento da qualidade do ar em diferentes regiões do país, distinguindo entre zonas monitoradas (urbanas, com sensores) e zonas não monitoradas (rurais, sem sensores). O objetivo é detectar níveis perigosos de poluentes, classificando o nível de emergência e auxiliando na tomada de decisões.

## Funcionalidades
- Registrar zonas (urbana ou rural) utilizando uma árvore rubro-negra (`TreeSet`), com o nome como chave.
- Adicionar sensores apenas em zonas urbanas, registrando ID, data e valor AQI.
- Gerar relatório de cada zona, exibindo total, média semanal e nível de emergência conforme tabela AQI.
- Classificação automática do nível de emergência com base na média semanal dos sensores.
- Mensagens especiais para zonas sem sensores e para médias críticas (acima de 300).

## Estrutura das Classes
- `Sensor`: representa um sensor de qualidade do ar.
- `Emergencia` (interface): define método para classificação do nível de emergência.
- `Zona` (abstrata): base para zonas rurais e urbanas.
- `ZonaRural`: zona sem sensores, relatório padrão.
- `ZonaUrbana`: zona com sensores, métodos para adicionar sensor, calcular total, média e classificar emergência.

## Como Usar
1. Execute o programa.
2. Utilize o menu para:
   - Registrar zonas (urbana ou rural).
   - Adicionar sensores (apenas zonas urbanas).
   - Imprimir relatório de uma zona pelo nome.
   - Finalizar o programa.

## Exemplo de Saída
```
=== RELATÓRIO DE EMERGÊNCIA AMBIENTAL ===

Zona: São Paulo - Zona Sul
Total semanal: 1740,00
Média semanal: 248,57
Nível de emergência: Alerta Laranja

Zona: Serra do Cipó
>>> Zona sem sensores instalados. Monitoramento indireto via satélite.
```
Se a média semanal for superior a 300:
```
>>> ALERTA EXTREMO: Média crítica ultrapassada!
```

## Observações
- Todos os atributos das classes são privados e inicializados via construtor.
- O sistema segue princípios de orientação a objetos, encapsulamento e separação de responsabilidades.
- Consulte o código para detalhes de implementação e regras de negócio.
