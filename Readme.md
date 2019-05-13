# ACK
basic example of how to use uber's deep learning tool ludwig.


### Prerequisites
- Python3
- VSCode/ Pycharm as development (IDE)
- Linux machine (Preferred)


### Reference:
to install ludwig follow this video tutorial [link](https://www.youtube.com/watch?v=uSOsos2eKHI)

**NB:** The model that is used in this tutorial may not work and you may find this error:

`ludwig train: error: one of the arguments -md/--model definition -mdef/--model definition file is required`


This [link](https://towardsdatascience.com/introducing-ubers-ludwig-5bd275a73eda) is good and has brief description which is worth reading.

**NB:** 
- The model is added already inside the project.
- Make sure you have Python3 installed on your machine.
- Install ludwig on your machine.


ludwig train \
--data_csv reuters-allcats.csv 
--model_definition "{input_features: [{name: text, type: text, encoder: parallel_cnn, level: word}], output_features: [{name: class, type: category}]}"

**we can train a deep learning model using the following command:**

    ludwig experiment \
      --data_csv reuters-allcats.csv \
      --model_definition_file model_definition.yaml
      
      
      
**After training we can evaluate the predictions of the model using the following command:**

        
      ludwig predict \
      --data_csv reuters-allcats.csv \
      --model_path results/experiment_run_0/model/
      
      
      
**Visualization** 
     
        ludwig visualize \
        --visualization learning_curves \
        --training_statistics results/experiment_run_0/description.json  