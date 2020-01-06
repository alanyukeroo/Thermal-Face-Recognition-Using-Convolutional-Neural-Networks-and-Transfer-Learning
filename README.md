# Thermal-face-recognition-using-transfer-learning
In this project, I introduce a thermal face recognition method based on convolutional neural networks (CNN's) and transfer learning. To the best of my knowledge, this is the first time that the transfer learning approach is applied in the classification of facial thermograms. With this method, various contributions are achieved:
- Best rank-1 recognition rate (100%) in the classical experimental scenario of the benchmark Terravic Facial IR Database (see below for more details).
- For the first time, the benchmark Terravic Facial IR Database is used to design 3 of the most challenged experimental conditions for a succesful thermal face recognition (see below for more details). These experimental scenarios involve the issue of facial occlusion. In the three experiments, the performance of the method is promising, since the rank-1 recognition rates obtained are above 90%, and the rank-5 recognition rates surpass the 99%.

In order to implement my proposal, I used the VGG16 architecture, which was previously presented in the following research paper: 
https://arxiv.org/pdf/1409.1556.pdf%20http://arxiv.org/abs/1409.1556.pdf. The VGG16 architecture is composed by 19 layers.

The facial thermal images utilized in the present project, come from the Terravic Facial IR Database, a database of the public available OTCBVS Benchmark Dataset Collection that can be found at http://vcipl-okstate.org/pbvs/bench/. The thermograms of the Terravic Facial IR Database contain variations in facial poses (front, left, right) and environment (indoor, outdoor), besides of accessories as glasses and hats. As stated in the OTCBVS Benchmark Dataset Collection, the Terravic Facial IR Database is constituted by the samples from 20 individuals, however, it is only possible to download the samples of 18 individuals, which comprise a total of 22,784 images.

The proposed method is distinguished by the implementation of an strategy of fine-tuning, which involves discarding the last 9 layers of the VGG16 model, thus, only the first 10 layers of the VGG16 architecture are used in this project. Out of these 10 layers, the first 7 layers are set up not to be trained, whereas the last 3 layers are set up to be trained. After these 10 layers, a max-pooling layer is appended, followed by a batch-normalization layer and finally, a softmax classifier is added. Of course, before the softmax layer, the previous features of the CNN are flatten.

As for the classical experimental scenario mentioned above, it 
