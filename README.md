# revis-oSO.FATECSJC
Um breve resumo da aula de Sistema Operacional



# Tipos de sistemas operacionais
 * Sistemas monoprogramáveis / Monotarefa;
 Os primeiros sistemas operacionais, realizavam apenas, uma tarefa por vez, fazendo que todo o potencial existente na maquina era reservado apenas para um processo, tais sistemas receberam o nome de sistemas monoprogramáveis (ou monotarefa)
 
 * Sistemas multiprogramáveis / Multitarefa;
 Aqui já é diferente, ele é uma evolução dos sistemas monoprogramáveis, sendo possível a execução de mais de um processo por vez, e mesmo assim existe o compartilhamento de recursos da maquina.
 
  Podemos citar como exemplo:
  
   Enquanto você está escrevendo em um arquivo de texto, e o sistema está captando todas essas informações, existe outro processo que está armazenando ou copiando arquivos em disco, detalhe: O custo é reduzido em comparação ao antigo monotarefa. Mesmo sendo mais rápido, ele acabou sendo mais complexo.
   
  * Os sistemas multitarefas podem ser divididos em três tipos: 
        * Sistema batch
        * Sistemas de tempo real
        * Sistemas de tempo compartilhado
     
 * Sistemas com múltiplos processadores
 * Sistemas fortemente acoplados
 * Sistemas fracamente acoplados
 * 

# CACHE
* Armazena temporariamente, informações em um processador ou disco, mantendo durante um número maior de tempo em base dos processos mais importantes

# BUFFER
* Armazena arquivos temporariamente do dispositivo em questão
Exemplo: caixa de som, armazena um pouco do áudio pra depois reproduzir 

# SPOOL
* Sistema operacional que decide isso, ele traduz pra linguagem da impressora e deixa o arquivo salvo até a impressão.
Exemplo: Texto no word e manda imprimir, mesmo fechando o word, o arquivo continua na fila pra ser impressa 

# Barramento
* Linha que trafega os 0 e 1 na máquina, conunicando-se com todos os componentes de hardware 
Ex: PCI-E
DDR3 / DDR4 

# Concorrência
* Quando vários processos são utilizados, é dado a prioridade a processos do sistema, mantendo uma concorrência entre os processos de qual deverá continuar em funcionamento


# Kernel
* Definição de kernel: ponte entre aplicativos e o processamento real de dados feito a nível hardware

Windows 10 - monolítico, microkernel (ambos) 
-monolitico
Exemplos monolítico: Windows, Linux, Mac OS X, BSD
Todos os serviços do sistema rodam juntos com a linha de execução principal do kernel, encontra-se na mesma área de memória. Só que existe dependência entre os componentes do sistema. Defeito em um driver pode paralisar um sistema todo. Sólido, não divisível.

# Thread
￼* Dividir um processo em duas ou mais tarefas, sendo executados concorrencialmente. 
Vantagens: desempenho, mais rápidos de criar e destruír, simplifica o modelo de programação.
 Exemplo: jogo é dividido em vários threads, um threads pra rodar os gráficos, outro pra rodar o som, e ambos funcionam de forma simultânea


# Microkernel


# Problema do barbeiro

# Problema dos filósofos

# Semáfaros

# Deadlock

# Sistemas preemptivos

# Sistemas Não-preemptivos

# Starvation


# Algoritimos de escalonamento de processos

* FIFO (First In, Firts Out)
* Shortest job first (SJF)
* Circular (Round Robin):
* Prioridades
* Circular com prioridade
* Multiplas filas
* 


# I/O Bound
Dispositivos, como por exemplo gravar um arquivo no Pen drive o uso do CPU é baixo, e ele fica em espera. Aguardando o momento pra ser utilizado (Processos que irão ficar mais tempo sendo executados.)

# CPU Bound
Usa uma capacidade elevada do processador e ele alterna entre pronto e execução (Processos que irão ficar menos tempo sendo executado, curto prazo de tempo)



# EXERCÍCIOS

# Dê um exemplo que apresente todas as mudanças de estado de um processo, juntamente com o evento associado a cada mudança.

#  Diferencie processos multithreads, subprocessos e processos independentes.

# Qual a relação entre processo e arquitetura microkernel ?

# Justifique com um exemplo a frase "o sinal está para o processo assim como as interrupções e exceções estão para o sistema operacional"


# O que é o núcleo do sistema e quais são suas principais funções?
* É a ponte entre as aplicações e o hardware. Função: gerenciamento de memória, gerenciar recursos do sistema, geranciamento de dispositivos, processos, 
# O que são instruções privilegiadas e não-privilegiadas ? Qual é a relação dessas instruções com os modos de acesso?
* Privilegiadas são instruções que só devem ser executadas pelo sistema operacional, impedindo problemas de segurança e integridade do sistema. Não privilegiadas não oferece risco ao sistema, uma aplicação no modo usuário utiliza de instruções não privilegiadas, 

# Como o kernel do sistema operacional pode ser protegido pelo mecanismo de modos de acesso?
* Pode ser protegido pelo modo usuário, impedindo que aplicativos alterem qualquer informação referente ao sistema a ponto de comprometer seu funcionamento,

# O que é system call? E qual sua importância para a segurança do sistema? Como as system calls são utilizadas por um programa ?
* É um mecanismo programático onde o programa de computador solicita algum serviço do núcleo do sistema operacional sobre o que está sendo executado. incluindo hardware (acessar uma unidade de disco). Uma implementação de mecanismos de proteção ao núcleo. Cada serviço possui um system call, e cada sistema operacional tem seu conjunto de chamadas 

# Pesquise comandos disponíveis em linguagens de controle de sistemas operacionais.
* Windows: cd, rmdir, rename, mkdir, copy, del, dir
 Ubuntu: cd / cp / apt-get install, update, search / ls - lista directorio / shutdown / kill / sudo
 



#Atividades
Estado de processo
-----------------
Número de processo
------------------
Contador do programa
-------------------
Registradores
--------------------
Memória
---------------------
Arquivos
----------------------

Mudanças de contexto - pág 68 fig 2

￼
Salva registradores do Processo A --> carrega registradores do Processo B


# Defina o conceito processo.

Inicialmente é definido como um programa em execução. Abrangendo mais, seria o conjunto de informações para que o sistema operacional implemente a concorrência de programas. É necessário guardar tal informação, para que quando necessário não a falte em um programa interrompidos.

# Por que o conceito de processo é tão importante no projeto de sistemas multiprogramáveis?

Para que seja implementado a concorrência de diversos programas e atendam múltiplos usuários de forma simultânea.


# É possível que um programa execute no contexto de um processo e não execute no contexto de um outro? Por quê?

É possível, já que o determinado processo em execução pode ser interrompido para que seja executado outro processo, nesse meio termo, as informações são salvas em registradores, conhecida como mudança de contexto, sempre variando entre os processos, não demonstrando que algum deles foi de fato interrompido.


# Quais partes compõem um processo? 
 Ele é formado por três partes:
 
 
 # Compartilhar memória pode acarretar em danos sérios, com isso algumas técnicas foram desenvolvidas para evitar danos maiores
 * Exclusão mutua: multiplos processos não podem escrever na mesma região de memória, durante a sessão critica;
 * Sessão critica: É utilizado uma parte de memoria por algum processo
 * Lembrando que existem soluções de software e hardware para solucionar problemas.

 * Algoritimos para a aplicação da exclusão mutua:
   * Primeiro algoritimo:
   * Segundo algoritimo:
   * Terceiro algoritimo:
   * Quarto algoritimo:
   * Dekker:
   * Peterson:

