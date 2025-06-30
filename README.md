# Farm home controller
# Matriz de Requisitos do Sistema Agrícola Doméstico

| ID | Categoria | Descrição | Prioridade | Método de Verificação |
|----|-----------|-----------|------------|-----------------------|
| R1 | Hardware - Relés | 5 relés para bomba, iluminação, ventilador, aquecedor, fertirrigação. | Alta | Teste funcional: Verificar ativação/desativação de dispositivos. |
| R2 | Hardware - Relés | Cada relé suporta 10A a 250V AC ou 30V DC. | Alta | Teste de carga: Medir corrente/tensão. |
| R3 | Hardware - Relés | Relés controláveis individualmente. | Alta | Teste funcional: Ativar/desativar relés separadamente. |
| R4 | Hardware - Entradas | 10 entradas digitais para sensores (umidade, luz, temperatura, etc.). | Alta | Teste funcional: Verificar leitura de sensores simulados. |
| R5 | Hardware - Entradas | Entradas suportam 3,3V/5V com pull-up/down. | Média | Teste elétrico: Verificar compatibilidade de tensão. |
| R6 | Hardware - Entradas | Entradas com debouncing (hardware/software). | Média | Teste de estabilidade: Simular sinais ruidosos. |
| R7 | Hardware - Microcontrolador | STM32F4 com 16 KB flash, 2 KB RAM, I²C, SPI, UART, 16 GPIOs. | Alta | Revisão de especificação: Confirmar datasheet. |
| R8 | Hardware - Microcontrolador | Operação a 3,3V ou 5V. | Alta | Teste elétrico: Verificar operação na tensão. |
| R9 | Software - Controle | Monitorar 10 entradas digitais continuamente. | Alta | Teste funcional: Verificar resposta às mudanças de entrada. |
| R10 | Software - Controle | Controlar relés com base em entradas (e.g., umidade para bomba). | Alta | Teste funcional: Simular entradas e verificar relés. |
| R11 | Software - Configuração | Configurar limites via UART ou controles físicos. | Média | Teste de interface: Verificar aplicação de limites. |
| R12 | Software - Alertas | Alertas visuais (LEDs) para condições críticas (e.g., nível de água). | Média | Teste funcional: Simular condições e verificar alertas. |
| R13 | Software - Modo Manual | Modo manual via Entrada 10. | Alta | Teste funcional: Verificar controle manual. |
| R14 | Software - Emergência | Desativar saídas em <100 ms via Entrada 7. | Crítica | Teste de desempenho: Medir tempo de resposta. |
| R15 | Software - Persistência | Armazenar configurações em memória não volátil. | Média | Teste de recuperação: Verificar preservação após reinício. |
| R16 | Software - Modularidade | Software modular (entradas, saídas, FSMs, etc.). | Média | Revisão de código: Verificar estrutura modular. |
| R17 | Software - Diagnósticos | Verificar integridade de sensores e relés. | Média | Teste funcional: Simular falhas e verificar diagnósticos. |
| R19 | FSM - Principal | FSM com estados Desligado, Automático, Manual, Emergência. | Alta | Teste funcional: Verificar transições (Entrada 7, 10). |
| R20 | FSM - Irrigação | FSM com estados Parada, Irrigando, Aguardando (Entradas 1, 4, 6, 7). | Alta | Teste funcional: Verificar transições e Relé 1. |
| R21 | FSM - Iluminação | FSM com estados Desligada, Ligada (Entradas 2, 7). | Alta | Teste funcional: Verificar transições e Relé 2. |
| R22 | FSM - Ventilação | FSM com estados Desligado, Ligado (Entradas 5, 7). | Alta | Teste funcional: Verificar transições e Relé 3. |
| R23 | FSM - Temperatura | FSM com estados Desligado, Ligado (Entradas 3, 7). | Alta | Teste funcional: Verificar transições e Relé 4. |
| R24 | FSM - Fertirrigação | FSM com estados Fechada, Aberta (Entradas 4, 7, 9). | Alta | Teste funcional: Verificar transições e Relé 5. |
| R26 | FSM - Persistência | Armazenar estados das FSMs em memória não volátil. | Média | Teste de recuperação: Verificar estados após reinício. |
| R27 | FSM - Sincronização | Atualizar FSMs em ciclos ≤500 ms. | Alta | Teste de desempenho: Medir tempo de ciclo. |
| R28 | Proteções Ambientais | Proteção contra poeira/água (IP54), temperatura (0–50°C), surtos. | Alta | Teste ambiental: Verificar operação em condições. |
| R29 | Proteções Ambientais | Proteção contra sobrecorrente para relés. | Alta | Teste elétrico: Simular sobrecarga. |
| R30 | Carcaça | Carcaça de ABS com montagem, cabos, ventilação, acesso. | Média | Inspeção física: Verificar design. |
| R31 | Carcaça | Dimensões ≤200x150x80 mm. | Média | Medição física: Verificar dimensões. |
| R32 | Não Funcional - Alimentação | Operar com 12V/24V DC, consumo ≤20W. | Alta | Teste elétrico: Medir consumo. |
| R33 | Não Funcional - Confiabilidade | MTBF ≥50.000 horas. | Média | Análise: Calcular MTBF em testes. |
| R34 | Não Funcional - Interface | Interface básica (LEDs/display) para status/alertas. | Média | Teste funcional: Verificar exibição. |
| R35 | Não Funcional - Conformidade | Conformidade com CE, UL ou equivalente. | Alta | Revisão documental: Verificar certificações. |
| R36 | Não Funcional - Desempenho | Processar entradas, saídas, FSMs em ≤500 ms. | Alta | Teste de desempenho: Medir ciclo. |
| R37 | Restrição | Uso interno ou abrigado ao ar livre. | Média | Revisão de design: Verificar adequação. |
| R38 | Restrição | Sem dependência de rede para funções principais. | Alta | Teste funcional: Verificar operação offline. |
| R39 | Restrição | Custo otimizado sem comprometer confiabilidade. | Média | Análise de custo: Revisar componentes. |
| R40 | Premissa | Usuários fornecem sensores/atuadores compatíveis. | Média | Documentação: Verificar instruções. |
| R41 | Premissa | Configuração via UART ou controles físicos. | Média | Teste funcional: Verificar configuração. |
| R42 | Premissa | Sensores fornecem sinais digitais compatíveis. | Alta | Teste funcional: Verificar sinais. |
| R43 | Premissa | Microcontrolador suporta FSMs sequenciais. | Alta | Revisão de especificação: Confirmar capacidade. |

## Notas
- **Prioridade**: Crítica (segurança/funcionalidade essencial), Alta (operações principais), Média (importante, não essencial).
- **Métodos de Verificação**:
  - Teste funcional: Simulação de condições.
  - Teste de desempenho: Medição de tempos.
  - Teste elétrico: Parâmetros elétricos.
  - Revisão de especificação: Análise documental.
  - Inspeção física: Verificação física.
  - Análise de confiabilidade: Testes de longo prazo.
  - Revisão documental: Conformidade com padrões.
- Excluídos R18 e R25 (paralelismo) para alinhar com execução sequencial.
