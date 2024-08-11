# Prompt
Comandos do Prompt(cmd)
## Sobre Rede
Uso: set global [[rss=]disabled|enabled|default]

             [[autotuninglevel=]
                disabled|highlyrestricted|restricted|normal|experimental]
                
             [[congestionprovider=]none|ctcp|default]
             
             [[ecncapability=]disabled|enabled|default]
             
             [[timestamps=]disabled|enabled|default]
             
             [[initialrto=]<300-3000>]
             
             [[rsc=]disabled|enabled|default]
             
             [[nonsackrttresiliency=]disabled|enabled|default]
             
             [[maxsynretransmissions=]<2-8>]
             
             [[fastopen=]disabled|enabled|default]
             
             [[fastopenfallback=]disabled|enabled|default]
             
             [[hystart=]disabled|enabled|default]
             
             [[prr=]disabled|enabled|default]
             
             [[pacingprofile=]off|initialwindow|slowstart|always|default]

Parâmetros:

    Marca           Valor
    rss             - Um dos seguintes valores:
                      disabled: Desabilita o escalonamento no lado do receptor.
                      enabled : Habilita o escalonamento no lado do receptor.
                      default : Restaura o estado de escalonamento do lado do receptor
                          para o padrão do sistema.
                          
    autotuninglevel - Um dos seguintes valores:
                      disabled: Corrige a janela de recepção para seu valor
                          padrão.
                          
                      highlyrestricted: Permite que a janela de recepção cresça além
                          do valor padrão, mas o faz de forma
                          bem conservadora.
                      restricted: Permite que a janela de recepção cresça além
                          do seu valor padrão, mas limita tal
                          crescimento em alguns cenários.
                      normal: Permite que a janela de recepção cresça para
                          acomodar quase todos os cenários.
                      experimental: Permite que a janela de recepção cresça
                          para acomodar cenários extremos.
                          
    congestionprovider - Esse parâmetro foi preterido. Use
                         netsh int tcp set supplemental em vez disso.
                         
    ecncapability   - Habilita/desabilita a Funcionalidade ECN.
                      default : Restaura o estado do sistema para o padrão.
                      
    timestamps      - Habilita/desabilita carimbo de data/hora RFC 1323.
                      default: Restaura o estado do sistema para o padrão.
                      
    initialrto      - Conecta o tempo de retransmissão (SYN) (em ms). default: 3000.
    
    rsc             - Habilita/desabilita o limite de união do segmento de recepção.
                      default: Restaura o estado do sistema para o padrão.
                      
    nonsackrttresiliency - Habilita/desabilita a resiliência rtt para clientes não
                      SACK. default: desabilitada.
                      
    maxsynretransmissions - Conecta as tentativas de repetição usando pacotes SYN.
                      default: 2.
                      
    fastopen        - Habilita/desabilita TCP Fast Open.
                      default: Restaura o estado do sistema para o padrão.
                      
    fastopenfallback - Habilita/desabilita o fallback de TCP Fast Open.
                      default: Restaura o estado do sistema para o padrão.
                      
    hystart         - Habilita/desabilita o algoritmo de início lento de HyStart.
                      default: Restaura o estado do sistema para o padrão.
                      
    prr             - Habilita/desabilita o algoritmo de Redução de Taxa Proporcional.
                      default: Restaura o estado do sistema para o padrão.
                      
    pacingprofile   - Define os períodos durante os quais a análise está habilitada.
                      Um dos seguintes valores:
                      off: Nunca analisa.
                      initialwindow: Analisa a janela de congestionamento inicial.
                      slowstart: Analisa somente durante o início lento.
                      always: Sempre analisa.
                      default: off.


Comentários: Define os parâmetros TCP que afetam todas as conexões.


## Exemplo:

       set global rss=enabled autotuninglevel=normal
