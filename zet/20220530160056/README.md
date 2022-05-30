# NeuRA implementation in modified ath9k drive 

NeuRA [1] is a Rate Adaptation algorithm that uses neural networks 

* They modified the ath9k Linux kernel module 
* Developed a user space process for predictions

This modified drives writes every received Block ACK into ***"kernel message ring buffer"*** 
This buffer is then read by the NeuRA process.
Neura Keeps an EWMA of the FER of each sampling rate and updates it everytime a new block ACK for that rate is received
Every 1 ms (? how) NeuRA calculates the effective throughput of the sampling rates, and feeds them to the neural network to predict the throughput of each rate

The 3 best rates are then sent to the ath9k driver via ***debubfs*** to be used as the transmission and retry rates

The process is written in C++ for performance reasons.
and the ***frugally-deep library***[2] to performn the predictions in C++. 

[1] https://dl.acm.org/doi/abs/10.1145/3416010.3423217
[2] https://github.com/Dobiasd/frugally-deep

 #phd #link_adaptation #rate_adaptation #implementation #ath9k
