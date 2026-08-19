# elm-mnist
Extreme Learning Machine (ELM)
An ELM is a single-hidden-layer feedforward neural network with one key property that sets it apart from a network trained by backpropagation:

- The weights and biases connecting the INPUT layer to the HIDDEN
  layer are chosen RANDOMLY and then FROZEN -- they are never
  updated during training.
- Only the weights connecting the HIDDEN layer to the OUTPUT layer
  (traditionally called "beta") are learned, and they are learned
  in one shot, in closed form, by solving a linear least-squares
  problem -- no gradient descent, no epochs, no backpropagation.

Because the only “training” step is solving a single linear system, ELMs train extremely fast compared to a conventionally trained network, at the cost of some accuracy/flexibility.

This example: 1. Loads MNIST using scikit-learn’s fetch_openml. 2. Builds a random hidden layer. 3. Solves for the output weights using the NORMAL EQUATION beta = (H^T H)^-1 H^T T instead of the Moore-Penrose pseudo-inverse (np.linalg.pinv), which is the approach most ELM tutorials use.

Run it!  [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/lostrabajadores/ELM-MNIST/HEAD?urlpath=%2Fdoc%2Ftree%2FELM.ipynb)

note: ELM-MNIST requires more memory than the 2 GB that Binder provides. You need to clone the repository to your computer to execute ELM_MNIST. But there is a small version with tiny data that works in Binder and that's the version (ELM) that opens when you click the Binder icon above.