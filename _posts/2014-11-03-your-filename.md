---
published: false
---

## Oct. 21,23,28,30
- Developed STATA code to extract full sample from airline dataset
- Tested full sample on EC2 instance r3.2xlarge (memory-optimzed, 61GB RAM)
- Simulation consumed full 61GB RAM and failed
- Andrew diagnosed that my input matrices were dense, and that I could save RAM by making them sparse
- Searched for R packages that would run desired statistical estimation techniques using sparse matrices as inputs
- Found diverse packages capable of computing desired estimation techniques using sparse matrices as inputs 
- (In process) Revising R code to utilize these packages







