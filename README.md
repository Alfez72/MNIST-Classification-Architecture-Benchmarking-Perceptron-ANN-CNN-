 ## MNIST Classification: Architecture Benchmarking (Perceptron / ANN / CNN)
>
> Comparative implementation of three neural network architectures on MNIST, quantifying how spatial feature extraction impacts classification accuracy independent of parameter count.
>
> ### Results
>
> | Model | Architecture | Test Accuracy |
> |---|---|---|
> | Perceptron | Single dense layer, softmax | 89.18% |
> | ANN | Dense(128) → Dense(64) → Dense(10), ReLU | 96.61% |
> | CNN | Conv2D(32, 3×3) → MaxPooling(2×2) → Dense | **98.76%** |
>
> ### Setup
> 42,000 labeled 28×28 grayscale images, 80/20 train/test split (`train_test_split`, stratified), pixel normalization to [0,1].
>
> ### Analysis
> The accuracy gap between ANN and CNN isolates the effect of preserving spatial structure: the ANN flattens input before any learning occurs, while the CNN's convolutional layers extract local patterns (edges, curves) prior to flattening. Confusion matrix analysis shows CNN misclassifications concentrate on visually ambiguous pairs (4/9, 3/5), indicating the residual error is largely a function of genuine visual similarity rather than model deficiency.
>
> ### Stack
> Python, TensorFlow/Keras, scikit-learn, pandas, matplotlib, seaborn
