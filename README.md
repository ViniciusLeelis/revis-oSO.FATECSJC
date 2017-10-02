## ROADMAP - Sistemas operacionais 

ROADMAP para prova de sistemas operacionais

### Leitura do livro - Arquitetura de Sistemas Operacionais 4ª Edição

Fazer a leitura dos seguintes capitulos

Capitulos
* Conceitos básicos;
* Conceitos de hardware e software;
* Concorrência;
* Estrutura do sistema operacional;
* Processos;
* Threads;
* Sincronização e comunicação entre processos;
* Gerência do processador.

### Exercícios

A leitura é importânte, porém para a fixação dos conceitos é necessário fazer todos os exercícios, abaixo vou listar os principais:

* Página 22 e 23 - Exercícios 4, 14, 18, 19 e 20;
* Página 39 - Exercícios 2, 6, 8 e 10;
* Página 62 - Exercícios 1, 2, 4, 5, 6 e 8;
* Página 84 - Exercícios (1, 2, 3), 4, (5, 6), 9;
* Página 84 - Exercícios 10, 11, 13, 14, 15;
* Página 94 - Exercícios 1, 2, 3;
* Página 152 - Exercícios 12 a 18.



### PARTE 1 Conceitos Básicos
* O que é um Sistema Operacional ?
      Sistema Operacional, resumidamente é apenas um conjunto de rotinas executado pelo processador, podemos dizer que é semelhante aos programas dos usuários. Sua principal função é controlar o funcionamento de um computador, gerenciando a utilização e o compartilhamento dos seus diversos recursos, como processadores, memrias e dispositivos de entrada e saída
* Tipos de Sistemas Operacionais
   * **Sistemas Monoprogramáveis / Monotarefa:**
   Foram os primeiros sistemas operacionais. São sistemas que pode-se executar apenas um programa por vez, para que outra aplicação fosse executada, deveria aguardar o término do programa corrente. Processador, memria e periféricos são de total exclusividade a execução de um único programa.
 Sua implantação é extremamente simples, não existindo preocupação no compartilhamento de recursos, tais como memória, processador e dispositivos E/S
         
   * **Sistemas Multiprogramáveis / Multitarefa:**
   Uma evolução dos antigos sistemas monoprogramáveis, aqui é diferente, os recursos computacionais são compartilhados entre aplicações e usuários. Enquanto um simples programa espera para ler ou gravar algo em disco, outros programas estão sendo processados no mesmo intervalo de tempo. O S.O se preocupa em gerenciar o acesso concorrente aos diversos recursos, de maneira ordenada e protegida. Suas vantagens: custo reduzido, redução total de tempo de execução dos programas. Desvantagens: mais complexo a implementação.
 #### Sistemas Multiprogramáveis podem ser divididos em: batch, tempo compartilhado e tempo real.
   
 * **Sistema Batch:**
   Primeiros tipos de sistema operacionais multiprogramáveis. Os programas(jobs) eram submetidos para execução usando          cartões perfurados e armazenados em disco ou fita, sendo guardados para serem processados. Os jobs eram executados,          produzindo uma saída em disco ou fita.
     
   Ele não exige interação do usuário com a aplicação. Entradas e saídas de dados implementadas por memória                    secundária(geralmente arquivos em disco).
   
   Quando bem projetados são eficientes, já que utilizam melhor o processador, só que o tempo de resposta pode ser             longo.
   
> Exemplo de aplicações: envolvendo cálculos numericos, compilações, ordenações, backups e outros que não é necessário        o usuario.
  
  -------------------------------------------------------------
  
 * **Sistemas de tempo compartilhado:**
  Os sistemas de tempo compartilhado, permitem que diversos programas sejam executados em pequenos intervalos definidos       pelo sistema operacional.
     
  Esta forma de trabalho é bastante utilizada pelas aplicações corporativas, por oferecerem tempo de resposta e execução      bons. Neste sistema, o usuário pode interagir com o sistema operacional, utilizando mouse, teclado e vídeo.
  
> Caso o tempo definido para uma aplicação não seja o suficiente, ela volta para a fila e outro processo entra em seu          lugar.
      
--------------------------------------------------------------
 * **Sistema em tempo real:**
  A forma de implementação de sistemas de tempo real, porém com a diferença que o tempo separado para a execução da     aplicação é feito de forma muito rígida, e não é finalizado a qualquer momento, para um possível novo calculo do tempo, como é feito com o tempo compartilhado.
 
 Aqui não existe a divisão do tempo, a aplicação pode levar o tempo que for necessário para rodar a aplicação, e todas as definições do tempo que será gasto, quais recursos serão utilizados, é definido pelo próprio programa que está executando, e  não pelo sistema operacional, assim como ocorre nos demais formatos citados acima.
 
> É um tipo de sistema muito utilizado em aplicações críticas, como usinas nucleares e controle de tráfego aéreo.


--------------------------------------------------------------------
--------------------------------------------------------------------
 ## Sistemas com Múltiplos Processadores
 Sistemas com múltiplos processadores se caracterizam por terem mais de uma UCP (_Unidade de processamento central_) trabalhando em conjunto. Tal sistema possuem algumas caracteristicas importantes:
 
 * _Escalabilidade_: Ampliar a capacidade de processamento, simplesmente adicionando mais processadores, ao invez de alterar toda a arquitetura para a implementação de outro processador;
 
 * _Disponibilidade_: Caso alguma falha ocorra, os outros processadores serão capaz de manter a tarefa ou o processo rodando. Possibilitando maior segurança para aplicações de alto risco;
 
 * _Balanceamento de carga_: Evita a ociosidade entre um processador e outro, distribuindo os processos de forma mais equilibrada;
  
### Tipos de Sistemas com Múltiplos Processadores

 * **Sistemas fortemente acoplados:**
 Basicamente são vários processadores compartilhando uma memória e um sistema operacional, por isso são também conhecidos como multiprocessadores.
Sistemas multiprocessados podem se dividir em:

   * **SMP**: (_Symmetric Multiprocessors_) Possuem tempo de acesso a memória principal uniforme.
   * **NUMA**: (_Non-Uniform Memory Access_) São conjuntos de processadores e memórias principais interconectados. O tempo de acesso a memória se dá pela localização física.
 
 * **Sistemas fracamente acoplados:**
 Também conhecidos como _Multiprocessadores_, possuem seu próprio sistema operacional, gerenciando seus próprios recursos. São independente entre sí.
 
 Estes computadores são conectados entre sí, multas vezes pos cabos de conexão ethernet ou fibra ótica. 
> A maior vantagem de sistemas fracamente acoplados é a escalabilidade, já que pode-se simplesmente conectar mais um computador para almentar o poder de processamento.


-------------------------------------------------------------

# HARDWARE E SOFTWARE

* **Hardware:** É a parte física, na maioria das vezes composta por [transistores](https://pt.wikipedia.org/wiki/Trans%C3%ADstor)
   * Processador:
   É responsável por executar e controlar instruções presentes na memória peincipal, através de operações aritmética (soma, subtração, divisão, multiplicação) e lógicas (comparações lóicas: E, OU, NÃO) e movimentação de dados.
   Um processador é composto de três componentes:
      * Unidade lógica aritmética: Realiza as instruções desejada, como somar, comparar bits entre outras instruções presente na unidade;
      * Unidade de controle: Responsável pela gravação de dados em disco, buscar próximas instruções na memórias, entre outros.
      * Registradores: Armazena resultados entre uma operação e outra.
   * Memória Principal:
   Onde as instruções e variáveis são armazenados enquanto necessárias para o processamento. Uma memória é organizada em celulas e o tamanho máximo é definido pela largura do barramento 2³² em um sistema com barramento de 32 bits.
   
   O endereço que será acessado é dado a partir de um registrador especifico, o MAR (Memory Address Register). Há também o MBR (Memory Buffer Register) que é usado para armazenar dados temporários ou antes de uma transferência para o disco.
   * Memória Secundária:
   Meio para manter o dado armazenado de forma relativamente permanente, atualmente o meio mais utilizado é o HD.
   * Memória Cache:
   Armazena temporariamente, informações em um processador ou disco, mantendo durante um número maior de tempo em base dos processos mais importantes
   * Dispositivos de entrada e saída:
   TODO
   * Barramento:
Linha que trafega os 0 e 1 na máquina, conunicando-se com todos os componentes de hardware 
Ex: PCI-E
DDR3 / DDR4 

### BUFFER
* Armazena arquivos temporariamente do dispositivo em questão
Exemplo: caixa de som, armazena um pouco do áudio pra depois reproduzir 

### SPOOL
* Sistema operacional que decide isso, ele traduz pra linguagem da impressora e deixa o arquivo salvo até a impressão.
Exemplo: Texto no word e manda imprimir, mesmo fechando o word, o arquivo continua na fila pra ser impressa 

 
* **Software:**
Parte do computador em que descreve seu comportamento por meio de 0 e 1s, não podemos ver ou tocar, mas podemos observar seu comportamento por meio dos dispositivos de entrada e saída.
   * Tradutor: Normalmente um programa ou um software é escrito em uma linguagem humanamente legível, o que faz necesário a tradução para 0s e 1s esse processo é denominado compilação ou tradução em português.
   * Interpretador: Processo semelhante ao de compilar, ou traduzir, porém é realizado em tempo de execução. Enquanto o programa executa, o interpretador diz ao computador o que deve ser feito.
   * Linker: É responsável por unir diferentes partes de um programa em um unico programa executável, é utilizado para unir as bibliotecas utilizadas ao programa principal.
   * Loader: É responsável por carregar na memória o programa a ser executado.
   * Depurador: Um utilitário para ajudar o usuário a encontrar erros sintáticos e lógicos no software a ser desenvolvido.
   
# Concorrência
Sistemas multiprogramaveis, diminuem a osciosidade do processador. Quando vários processos são utilizados, é dado a prioridade a processos do sistema, mantendo uma concorrência entre os processos de qual deverá continuar em funcionamento. 

## Interrupções e Exceções
TODO- não prioritário

## Operações de Entrada e Saída


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

