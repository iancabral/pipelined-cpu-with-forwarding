# pipelined-cpu-with-forwarding
Pipelined CPU that used forwarding to resolve data hazards and improve throughput performance. 

This pipeline was programmed using a MIPS architecture consisting of 5 stages:
1. IF: Instruction fetch from memory
2. ID: Insturction decode and register read
3. EX: Execute operation or calculate address
4. MEM: Access memory operand
5. WB: Write result back to register

Pipelining improves performance by increasing instruction throughput and allowing for multiple instructions to be executed in parallel.

<img width="600" alt="pipelining example" src="https://github.com/iancabral/pipelined-cpu-with-forwarding/blob/master/images/pipelining.JPG">

However, pipelining is also subject to hazards. In the case of data hazards, a current instruction depends on the result of a previous instruction before it can be executed. Therefore, it must wait for the previous instruction to complete its data read/write cycle before it can access the result and execute. To get around this limitation, forwarding can be used to forward the result onto the next instruction before even writting the result back to memory.

<img width="500" alt="hazards" src="https://github.com/iancabral/pipelined-cpu-with-forwarding/blob/master/images/forwarding.JPG">

The full implementation can be seen below, consisting of pipeline registers, hazard detection, and the 5 MIPS stages.

<img width="800" alt="implementation" src="https://github.com/iancabral/pipelined-cpu-with-forwarding/blob/master/images/implementation.jpg">

# Acknowledgements
This project was completed in collaboration with Ahmed Rahmati and Sohail Rashid.