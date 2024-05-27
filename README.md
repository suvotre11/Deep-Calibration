# Deep-Calibration
This repository is solely to hold the code, as jupyter-notebook, for the bachelor thesis "Deep Calibration: Machine Learning for Financial Model Selection".

VERSION:

python 3.12.0


ABOUT:

'Working_Code.ipynb': The provided code entails a comprehensive methodology aimed at estimating model parameters for option pricing through a combination of Monte Carlo simulation and machine learning techniques. Let's break down the code and its functionality into various components:

Importing Libraries: The code begins by importing necessary libraries such as NumPy for numerical computations, Keras for building and training neural networks, and Matplotlib for visualization purposes.

Defining Parameters: Several parameters are defined, including the time discretization N, the initial asset value S0, the strike price for the call option, maturity T, activation function for the neural network, the number of paths used in Monte Carlo simulation R, sizes of training and test data, epochs for training the neural network, risk-free interest rate r_free, and the underlying assumption (either "Heston" or "Black-Scholes").

Payoff Function: The function f(S) calculates the payoff of a call option for different strike prices K. It returns the maximum of the difference between the asset price S and the strike price K for each strike price.

Path Generation Functions: Two functions, path() and path2(), are defined to generate sample paths for the Black-Scholes model and the Heston model, respectively. These functions simulate the evolution of the asset price and volatility over time using Monte Carlo simulation.

Generating Training Data: The code then proceeds to create training data by randomly sampling model parameters and simulating sample paths for the chosen model assumption (either Black-Scholes or Heston). For each sample path, the payoff of the call option is computed, and the mean payoff for each strike price is calculated. These mean payoffs, along with the corresponding model parameters (e.g., volatility), serve as input-output pairs for training the neural network.

Neural Network Architecture: Next, a neural network model is defined using Keras. The model takes the mean payoffs of call options as input and aims to predict the model parameters (e.g., volatility) as output. The architecture consists of several dense layers with a specified number of nodes and activation function.

Training the Neural Network: The defined neural network model is compiled and trained using the training data generated earlier. The model is optimized using the Adam optimizer and trained to minimize the mean squared error between predicted and actual model parameters.

Generating Test Data and Evaluation: Finally, test data is generated using a similar procedure as the training data. The trained neural network is then used to predict model parameters for the test data. The code includes visualization of the scatter plot of true versus predicted model parameters, as well as a histogram of prediction errors.

Overall, the code implements a methodology to estimate model parameters for option pricing using Monte Carlo simulation and machine learning. It generates training and test data, trains a neural network model to predict model parameters from option payoffs, and evaluates the performance of the trained model. This approach offers a data-driven approach to model parameter estimation, potentially enhancing the accuracy and efficiency of option pricing techniques.
