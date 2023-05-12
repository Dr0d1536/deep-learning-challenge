# Overview of the analysis:
    The purpose of this project was to see which applicants would be successfully funded my Alphabet Soup
    
    
# Results:

# Data Processing - 
## What variable(s) are the target(s) for your model?:
    The target was the success of the applications submitted to Alphabet Soup

## What variable(s) are the features(s) for your model?:
    Application, classification, asking amount, organization

## What variable(s) should be removed from the input data because they are neither targets nor features?:
    I dropped the following - 
    application_df= application_df.drop(['SPECIAL_CONSIDERATIONS'],1)
    application_df= application_df.drop(['INCOME_AMT'],1)
    application_df= application_df.drop(['STATUS'],1)
    application_df= application_df.drop(['EIN'],1)
    application_df= application_df.drop(['NAME'],1)

# Compiling, Training, and Evaluating the Model - 
## How many neurons, layers, and activation functions did you select for your neural network model, and why?:
    The following provided me with the most accurate results 
    # First hidden layer
    nn_op.add(tf.keras.layers.Dense(units=hidden_nodes_layer1, input_dim=features, activation="sigmoid"))

   # Second hidden layer
    nn_op.add(tf.keras.layers.Dense(units=hidden_nodes_layer2, input_dim=features, activation="linear"))

   # Third hidden layer
    nn_op.add(tf.keras.layers.Dense(units=hidden_nodes_layer3, input_dim=features, activation="tanh"))

   # Fourth hidden layer
    nn_op.add(tf.keras.layers.Dense(units=hidden_nodes_layer3, input_dim=features, activation="tanh"))

   # Output layer
    nn_op.add(tf.keras.layers.Dense(units=1, activation="sigmoid"))
    
## Were you able to achieve the target model performance?
    No. I used keras tuner I found on-line and used the example code to find the best parameters for the task.  At this point about 74 attempts, 72.73% accurancy was found. For sceience, I still have it running to see how high it will go. 
            Trial 75 Complete [00h 00m 42s]
            val_accuracy: 0.7244315147399902

            Best val_accuracy So Far: 0.7278134226799011
            Total elapsed time: 00h 07m 07s

            Search: Running Trial #76

            |Best Value So Far |Hyperparameter
              |relu              |activation
                |41                |first_units
                |4                 |num_layers
                |26                |units_0
                |11                |units_1
                |1                 |units_2
                |16                |units_3
                |1                 |units_4
                |50                |tuner/epochs
                |17                |tuner/initial_epoch
                |2                 |tuner/bracket
                |2                 |tuner/round

  ## What steps did you take in your attempts to increase model performance?:
    Layers, units, removed colums, and played with different activators. 

# Summary:
    I don't think the information collected for this questions is enough to determine how succesful an applicantion submition would be. Addtion varaibles are needed to be collected.
