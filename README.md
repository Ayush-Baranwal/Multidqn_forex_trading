# Optimized Forex Trading using Ensemble of Deep Q-Learning Agents                                                                                                          

## Abstract 

Foreign exchange market is a fast paced market influenced by a wide variety of factors, which requires the careful study of data to take an advantageous position. There are many AI based approaches, chief among them being the use of single RL agent based systems trained on a specific time period. We have proposed the use of a Deep Q Learning based algorithm consisting of multiple agents trained(run) on different epochs on the dataset. Different feature extraction techniques like CNN, LSTM and their combinations have been tried to ascertain the better technique for our usecase. Decisions taken on each day are logged during validation and testing. An ensembling technique is used on these decisions to get the final decision and profit. It was observed that the combination of CNN and LSTM layers performed better than when each of the layers where tested in isolation from one another, howoever they result in overfitting. LSTM was found to be better overall and using an agreement threshold of 60% provided best results.

## Authors

- Bagesh Kumar
- Ayush Baranwal
- Aaadharsh Roshan
- Sahil Sharma
- Amritansh Mishra
- O.P. Vyas

# Info 

## Description

#### These files are needed to run the main code:
* **main.py**: the entry point of the application;
* **deepQTrading.py**: used to organize our data in walks and set up the agents;
* **spEnv.py**: the environment used for the agents;
* **mergedDataStructure.py**: the data structure we use to instantiate the multi-resolution feature vector;
* **callback.py**: a module used to log and trace the results.

#### Other tools:
* **ensemble.py**: can be used to generate the threshold ensemble from the main agents;
* **splitEnsemble.py**: can be used to generate the final ensemble for the LONG+SHORT agent (after running ensemble.py).


If you want to adapt the code and use it for more markets, you can use the file **utils/parserWeek.py**, to create a weekly resolution dataset.<br>
On the other hand, the file **utils/plotResults.py** can be used to generate a .pdf containing several plots, useful to get information on the testing phase of the algorithm.


## Requirements
* Python 3
* Tensorflow (1.15): `pip install tensorflow==1.15`
* Keras: `pip install keras`
* Keras-RL: `pip install keras-rl`
* OpenAI Gym: `pip install gym`
* Pandas: `pip install pandas`

## Usage
The code needs three positional parameters to be correctly executed:<br>
`python main.py <numberOfActions> <isOnlyShort> <ensembleFolder>`<br>
<br>

* To run the **FULL** agent you need to run: `python main.py 3 0 ensembleFolder`
* To run the **ONLY LONG** agent you need to run: `python main.py 2 0 ensembleFolder`
* To run the **ONLY SHORT** agent you need to run: `python main.py 2 1 ensembleFolder`

where the paramenter **ensembleFolder** is used to set the name of the folder in which you'll get your results.
