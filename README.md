# DenoisingEncoder-for-Digits
An encoder-decoder that takes noisy images of digits and converts them into clean images of the same by encoding them and then decoding them.

**Dataset**
The images were black and white and of size 28 * 28 representing digits from 0 to 9, and the expected output was a cleaned image of the same size.

**Architecture**

I used a sequence of dense layers here and used elu activation for all  of them except for the last layer. 

I started with a layer with n units after the input layer, and followed it up with a layer of n/2 units, followed by n/4 units. 

These layers represent the encoding part of the model.

The decoding part is the opposite, which follows with a layers of n/2 units, n units and then with a dense layer of the actual input size of 28 X 28 with a sigmoid activation. 

The value of n was decide using hyperparameter tuning using the validation set and having 256 as n gave the best result.

**Results**

This model gave a very good RMSE of 0.0053272075 on the test set.
