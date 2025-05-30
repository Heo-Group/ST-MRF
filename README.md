# ST-MRF
Saturation transfer MR fingerprinting (ST-MRF) for MTC and CEST quantification

The ST-MRF reconstruction architecture was designed to map an MR fingerprint space to a tissue parameter space. The overall framework consisted of a reconstruction network and deep-learning Bloch equation simulator (dBES or deepBS). The input ST-MRF profile was fed to the reconstruction network to estimate the output tissue parameters and then, the following dBES retrospectively synthesized an ST-MRF profile with the tissue estimates for the calculation of a self-consistency loss. The reconstruction network had six fully-connected dense layers. The first five dense layers had 512 neurons with the rectified linear unit activation function, and the last output dense layer had four neurons. The sigmoid function was adopted at the last layer to de-normalize the output values (tissue parameters) with pre-defined ranges. For the dBES network, the output dense layer had 103 hidden neurons corresponding to the length of the ST-MRF profile. The deep-learning framework was trained by minimizing the two loss functions, the L2-norms of difference between the ground-truth tissue parameter and the estimated tissue parameter, and between the ground-truth ST-MRF and the synthesized ST-MRF profile. 
Publication ()

![Image](https://github.com/user-attachments/assets/8f87d3aa-88d2-4b88-a102-e6b266a04218)
