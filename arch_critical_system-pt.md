

## Informações do Projeto

|   |   |
|---|---|
|   | Elaborar **diagrama em blocos da arquitetura interna da FPGA** explicitando os tipos de interfaces fisicas com os demais componentes. |
|   | Elaborar uma **tabela para estimativa do numero de I/Os** da FPGA a partir do tipo e do numero de interfaces fisicas. Explicitar padrão da  |interface (3v3, 1v8, etc) e necessidades especiais (corrente, filtros, etc).
|   | Elaborar uma **tabela para estimativa de uso elementos lógicos** da FPGA. |
|   | Elaborar uma **tabela para estimativa de uso de blocos de memória** da FPGA. |



## Propostas de arquitetura
### Boas práticas de desenvolvimento de firmware

|   |   |
|---|---|
|   | Executar **design review** quando o esquematico de hardware estiver disponivel.  |
|   | Prever 2 I/Os 3v3 na FPGA para **interface serial** de desenvolvimento. Hardware deve prever circuito de proteção (resistores) e barra de pinos padrão de interface serial (vcc tx/rx gnd).  |
|   | Prever barra de pinos para **interface JTAG** de programação/desenvolvimento e seleção de modo de programação se houver.  |
|   | Prever **blocos de memoria e elementos lógicos para o SignalTap** (no caso da Altera). A capacidade necessária depende do numero de sinais e de quantas amostras são necessárias para verificar as funcionalidades.  |
|   | Prever **pinos dedicados para expor sinais internos específicos** (podem ser selecionador atraves de um mux) a serem usados na verificação. Exemplo são sinais que não são verificaveis via SignalTap: clock gerados, sinais de controles, etc  |
|   | Prever na arquitetura um **bloco de registradores endereçáves** na FPGA. Estes registradores controlam e monitoram os ourtos blocos do projeto como PID, PWM, ADC, etc. Dependendo da necessidade ele pode ser apenas uma brigde ou de fato implementar os registradores.  |
|   | Prever malha de **monitoramento para controle critico** na FPGA. Pode ser simplesmente o feedback de um sinal que habilita um atenuador até o monitoramento de corrente em uma carga.  |
|   | Prever bloco de **watchdog**  a depender da arquitetura de proteção do sistema. Por exemplo entre MCU e FPGA, FPGA e watchdog discreto, etc.  |
|   | Prever, se disponivel, **outras referencias de clock** para a FPGA com o objetivo de teste de fabrica do clock e se necessário implementar redundância de fonte de clock.  |
|   | Prever, a aquisição de **kits de desenvolvimento para permitir o inicio da implementação** do firmware e gerar imagens de teste que permita a validação da produção de lotes alpha.  |
|   | Prever, a aquisição de **kits de desenvolvimento para permitir a geração de sinais para estimulação e execução de testes durante o  desenvolvimento**. Exemplo de outros kits de desenvolvimento FPGA com entradas/saidas logicas e analogicas.  |
|   | Prever os **recursos necessários ao desenvolvimento** do firmware: licensas de software sintese e programação, cabos de programação, licensa de simulador, etc  |




