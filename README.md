## Modelling and simulating a real store in a Petri Net

<nav style='font-align:justify'>The main goal of the project is model and simulate, in a Colored Petri Net [1] using CPN Tools [2], a real store (of hearing aids devices, in our case) to find possible cases of business failing (bankrupt, for instance) or finding a more efficient way of increasing profit. To develop the petri net we used CPN Tools version 4.0.1, released in Feb. 2015 and the latest version by the time when the project was made.

This project was made to be graded at the elective course of <a href="http://www.cs.au.dk/~cpnbook/" target="_blank">Petri Nets</a>, lectured by <a href="http://buscatextual.cnpq.br/buscatextual/visualizacv.do?metodo=apresentar&id=K4766554T7" target="_blank">Professor Leandro Dias da Silva</a> and available at <a href='http://www.ufal.edu.br/unidadeacademica/ic/graduacao/ciencia-da-computacao' target='_blank'>Computer Science</a> and <a href='http://www.ufal.edu.br/unidadeacademica/ic/graduacao/engenharia-de-computacao' target='_blank'>Computer Engineering</a> degrees of the <a href="http://www.ic.ufal.br" target="_blank">Institute of Computing</a> at <a href="http://www.ufal.edu.br" target="_blank">UFAL - Federal University of Alagoas</a>.

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

### Explaining the developed Petri Net

#### Hearing aids devices - basic flow

1. The client goes to the doctor, that explains to the client that he needs an hearing aid device and must perform an exam to know the exact specifications of the device that he's going to use;
2. The client does the exam and receives the report that contains the device specifications;
3. The client goes to the store to buy the device, the audiologist check the specifications presented on the report and the store requests to the supplier, that will send as soon as possible the device, respecting the report specifications;
4. When the device arrives at the store, the store audiologist makes an calibration, along with the client, so the device can be the most confortable possible when used by the client in his ears;
5. After that, the client takes the device and the warranty works the same way of the buy flow, with no cust to the client.

#### Batteries - basic flow

1. The client goes to the store to buy batteries for his device;
2. The store checks the batteries needed by the client;
2.1. If the store has a low stock of batteries, then it makes an request to the supplier.

#### Supplier specifications

The supplier has two products, always available:

- Batteries;
- Hearing aids devices.

#### Store specifications

The store has two products:

- Batteries, in stock;
- Hearing aids devices, with sales by demand, i.e., only when a client demands, the store requests to the supplier.

The store has two employees:

- Audiologist;
- Accountant.

The store payes four bills:

- Water;
- Energy;
- Rent;
- Phone and Internet.

#### Table of Values

##### Devices

<table>
	<tr>
		<td>Device</td>
		<td>Value at Store</td>
		<td>Value at Supplier</td>
	</tr>
	<tr>
		<td>Low-end</td>
		<td>1.500$</td>
		<td>750$</td>
	</tr>
	<tr>
		<td>Standard</td>
		<td>4.500$</td>
		<td>2.250$</td>
	</tr>
	<tr>
		<td>High-end</td>
		<td>7.500$</td>
		<td>3.750$</td>
	</tr>
</table>

##### Batteries

<table>
	<tr>
		<td>Battery</td>
		<td>Value at Store</td>
		<td>Value at Supplier</td>
	</tr>
	<tr>
		<td>Regular Battery</td>
		<td>4$</td>
		<td>2$</td>
	</tr>
</table>

##### Employees

<table>
	<tr>
		<td>Employee</td>
		<td>Value</td>
	</tr>
	<tr>
		<td>Audiologist</td>
		<td>50$/report and 50$/calibration</td>
	</tr>
	<tr>
		<td>Accountant</td>
		<td>500$/month</td>
	</tr>
</table>

##### Bills

<table>
	<tr>
		<td>Bill</td>
		<td>Value</td>
	</tr>
	<tr>
		<td>Water</td>
		<td>25$</td>
	</tr>
	<tr>
		<td>Energy</td>
		<td>100$</td>
	</tr>
	<tr>
		<td>Rent</td>
		<td>800$</td>
	</tr>
	<tr>
		<td>Phone/Internet</td>
		<td>250$</td>
	</tr>
</table>

#### Additional informations

- The store has a medium sale of 12 batteries/day;
- The store maintains the batteries stock at a maximum number of 100 batteries, when is downgraded to 40 batteries it makes a new request to the supplier to renew the stock and reaching again 100 batteries;
- We are considering that the store opens only in comercial days, so we have a running month of 22 days;
- The flow always starts from the client;
- In CPN Tools model the bills and employees cust are merged;
- The model isn't considering the 13% tax at the end of the year related to the incoming.

### Credits

<a href="http://www.durvalpereira.com.br" target="_blank">Durval Pereira</a>. Contact me  <a href="mailto:contato@durvalpereira.com.br">here</a><br>
<a href="http://bit.ly/durvallattes" target="_blank">Lattes</a> <a href="https://www.linkedin.com/in/durvalpereira">LinkedIn</a> <a href="http://twitter.com/DurvalPCN">Twitter</a> <a href="http://www.facebook.com/durvalpereiracn">Facebook</a> <a href="http://plus.google.com/+DurvalPereiraCesar">Google+</a>

<a href="#" target="_blank">Bruno dos Anjos</a>

### References

[1] Colored Petri Nets, available at < http://www.cs.au.dk/~cpnbook/ > <br>
[2] CPN Tools, available at < http://cpntools.org/ > <br>