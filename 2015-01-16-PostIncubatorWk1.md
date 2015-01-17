## Jan. 12, 2015 Jan. 16, 2015
- Received python code adaptation from Andrew allowing me to choose the number of threads and the number of simuations separately 
- Ran 2 threads and simulations on r3.xlarge (30GB RAM), realized that each sim of mine takes up slightly more than 15GB's of RAM each run, meaning this instance is too small.
- Tried on r3.2xlarge (60GB) RAM, 2 threads/sims (t/s) proceeded OK, on two pieces
- Tried successfully on r3.2xlarge 2 t/s and 8 pieces
- Tried unsuccessfully 14 threads on r3.8xlarge (244GB RAM, 32 virtual cpu's), realized that each thread tries to execute the opening and closing of common R objects (saved to hard drive) during the sim. Andrew suggested I explore the tempfile command in R, which allows for customized naming of these intermediate, temporary files (e.g. it provides the name plus some jibberish unique to that particular thread). After implementing this in my code, it worked like a charm: on 2 pieces, 14 t/s. 
- Tried r3.8xlarge, 8 pieces, 14 t/s, worked no problem. 
- Realized the r3.8xlarge, 64 pieces, 14 t/s, maxes out RAM at some point (after 30 mins), so tried same number of pieces, but 12 t/s





