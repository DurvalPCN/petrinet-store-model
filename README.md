## Modelling and simulating a real store in a Petri Net

<nav style='font-align:justify'>The main goal of the project is model and simulate, in a Colored Petri Net [1] using CPN Tools [2], a real store (of hearing aids devices, in our example) to find possible cases of business failing (bankrupt, for instance) or finding a more efficient way of increasing profit.

This project was made to be graded at the course of <a href="http://www.cs.au.dk/~cpnbook/" target="_blank">Petri Nets</a>, lectured by <a href="http://buscatextual.cnpq.br/buscatextual/visualizacv.do?metodo=apresentar&id=K4766554T7" target="_blank">Professor Leandro Dias</a> in the <a href="http://www.ic.ufal.br" target="_blank">Institute of Computing</a> at <a href="http://www.ufal.edu.br" target="_blank">UFAL - Federal University of Alagoas</a>.

In the source files, you can find:

- `project-v1.0-with-hierarchy.cpn` to load in CPN Tools;
- `sketchs/` a folder containing sketchs made at the begin of the project design;
- `screenshots/` a folder containing screenshots of the petri net.

Feel free to perform a pull request to the project, implementing additional functions or improving some of the existents.<br>

</nav>

### CPN Tools

CPN Tools is a tool for editing, simulating, and analyzing Colored Petri nets.

The tool features incremental syntax checking and code generation, which take place while a net is being constructed. A fast simulator efficiently handles untimed and timed nets. Full and partial state spaces can be generated and analyzed, and a standard state space report contains information, such as boundedness properties and liveness properties.

CPN Tools is available for Windows, Linux and Mac OS X. If you use Linux/Mac OS X, we recommend you to download the latest stable Windows version of CPN Tools and run it using a virtual machine, since to these operating systems there is only an older version of CPN Tools available to download these pand versions are not maintained any longer.

To download CPN Tools, you can click <a href='http://cpntools.org/download' target='_blank'>here</a>.

### Explaining the Petri Net

#### Hearing aids devices flow

(1) O cliente vai ao médico. O médico fala para o paciente que o cliente(C) precisa de uma aparelho auditivo e fala que C precisa fazer um exame para ter as especificações do aparelho. (2) C vai faz o exame e recebe o laudo que contém as especificações do aparelho que C vai usar. (3) C procura a loja para compra o aparelho, o fonodiologo da loja verifica o laudo e a (4) loja faz o pedido para o fornecedor que envia o aparelho seundo a especificações do laudo o mais rápido
possivel. (5) Com o aparelho na loja, o fonodiologo da loja faz uma calibragem junto com C para deixar de forma confortavel aos ouvidos de C, e C leva o aparelho. A garantia funciona como o esquema depois do (3), mas sem custo para o cliente.

#### Batteries flow

(3) C vai a loja comprar pilhas para o aparelho. (5) A loja verifica vendo a pilha para C. (4) se a loja tiver com estoque de pilhas defazado ela faz pedido para fornecedor.

#### Supplier specifications

The supplier has two products, always available:

- Batteries;
- Hearing aids devices.

#### Store specifications

The store has two products:

- Batteries, in stock;
- Hearing aids devices, with sales by demand, i.e., only when a client demands, the store requests to the supplier.

The store has two employers:

- Audiologist;
- Accountant.

The store payes four bills:

- Water;
- Energy;
- Rent;
- Phone and Internet.

#### Table of Values

#### Additional informations

- A Loja tem uma média de venda de 12 pilhas por dia;
- A Loja mantém o estoque de no máximo 100 pilhas, ao chegar em 40 pilhasr no estoque ela fazer um novo pedido de pilhas para renovar o estoque.(com mais 100 pilhas);
- Vamos considerar que a loja abre apenas dias de semanas, logo teremos um mês de 20 dias;
- O movimento se inicia sempre a partir do cliente;
- No modelo no cpntolls os imposto e custo com funcionarios estão todos juntos;
- Não esta se levando em consideração o imposto de 13% no final do ano em cima do faturamento.

### Credits

<a href="http://www.durvalpereira.com.br" target="_blank">Durval Pereira</a>. Contact me  <a href="mailto:contato@durvalpereira.com.br">here</a>.<br>
<a href="http://bit.ly/durvallattes" target="_blank">Lattes</a> <a href="https://www.linkedin.com/in/durvalpereira">LinkedIn</a> <a href="http://twitter.com/DurvalPCN">Twitter</a> <a href="http://www.facebook.com/durvalpereiracn">Facebook</a> <a href="http://plus.google.com/+DurvalPereiraCesar">Google+</a>

<a href="#" target="_blank">Bruno dos Anjos</a>.

### References

[1] Colored Petri Nets, available at < http://www.cs.au.dk/~cpnbook/ > <br>
[2] CPN Tools, available at < http://cpntools.org/ > <br>