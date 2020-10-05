# rflo-learning

In this minimal example, three algorithms are implemented for training recurrent neural networks (RNNs) to produce a continuous one-dimensional output. The code is has been written to be as clear and self-contained as possible.

- The first algorithm is random feedback local online (RFLO) learning. Motivated by neurobiology, this is a quasi-gradient-based online learning rule for minimizing a loss function in an RNN using only local information to update synaptic weights. This means that the update to a particular synaptic weight depends only on the pre- and postsynaptic activities, as well as a random projection of the error signal. This is contrary to gradient-based learning rules (such as the other two presented here), in which weight updates are nonlocal, depending on all of the activities and weights in the RNN. Please see the paper cited below for details.
- The second algorithm is backpropagation through time (BPTT). This is the standard algorithm for training RNNs, and it is useful to include here in order to (i) compare the performance with RFLO learning and (ii) provide a minimal, self-contained implementation of BPTT to anyone who might want it.
- The third algorithm is real time recurrent learning (RTRL; Williams and Zipser, 1989). As explained in the paper cited below, this algorithm is equivalent to BPTT (at least when weight updates are made at the end of each trial rather than online at each timestep). Unlike BPTT, though, the algorithm runs forward in time rather than backward. RTRL is seldom used in practical applications because it is much more computationally expensive than BPTT or RFLO (again, see the paper below for details).

The code may be reused and adapted, in which case please cite the following paper:

"Local online learning in recurrent networks with random feedback" 
James M. Murray
eLife 8:e43299 (2019)
