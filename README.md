
# Deepminds alphatensor , matrix multiplication to train neural network

DeepMinds #alphatensor discovered matrix multiplication algorithms with lower rank factorization ever known, published last week. Rank determines the complexity of matrix multiplication, as rank corresponds to the number of multiplications which mainly determines the complexity. I was curious how using these factorizations will affect the efficiency of neural networks “itself “as neural network heavily depends on matrix multiplications. 
I tried to modify a neural network from scratch code( https://lnkd.in/gZQMAtbR) , supplanting the matrix multiplication with the new algorithm and tried to see how long it takes to train when juxtaposed against the same network using naive matrix multiplications with O(I*j*k). I took neuron blocks of multiplicative dimension (13*4,13*5) and (13*5,13*5) which were reshaped to (4,5,13,13) and (5,5,13,13). Dimension of (4,5)*(5,5) was already referenced in their blog( https://lnkd.in/gwXmRzci) having the rank of 76. Therefore, theoretically, it would have complexity of O(76*(13^3)) compared to naive one with O(100(4*5*5)*13^3). I tool the u,v,w stadard arithmetic factorizations numpy array from alpha tensor GitHub( https://lnkd.in/g_cHGdGK ran 10 trains with 2 epochs each on the MNIST dataset with 13*4*7 training samples batched into (13*4) sizes to keep into the matrix multiplication dimensionality
The results from 10 trails are shown below.




## Screenshots

![App Screenshot](https://github.com/Ariq154404/Deepmind_alphatensor_matrixmul/blob/main/Screenshot%202022-10-15%20at%204.25.19%20PM.png)


## Acknowledgements

 - [The Independent code]({https://github.com/TheIndependentCode/Neural-Network)
 - [Alphatensor Github]( https://lnkd.in/g_cHGdGK)
 

References:

R1:
@misc{theindependentcode, title={TheIndependentCode/neural-network: Machine Learning Library for educational purpose.}, url={https://github.com/TheIndependentCode/Neural-Network}, journal={GitHub}, author={TheIndependentCode}}



R2:
@Article{AlphaTensor2022,
  author  = {Fawzi, Alhussein and Balog, Matej and Huang, Aja and Hubert, Thomas and Romera-Paredes, Bernardino and Barekatain, Mohammadamin and Novikov, Alexander and Ruiz, Francisco J. R. and Schrittwieser, Julian and Swirszcz, Grzegorz and Silver, David and Hassabis, Demis and Kohli, Pushmeet},
  journal = {Nature},
  title   = {Discovering faster matrix multiplication algorithms with reinforcement learning},
  year    = {2022},
  volume  = {610},
  number  = {7930},
  pages   = {47--53},
  doi     = {10.1038/s41586-022-05172-4}
}
