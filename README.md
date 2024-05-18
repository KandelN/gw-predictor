# GW-predictor - Groundwater Prediction Using Machine Learning
GW-predictor is a research project written in Python that aims to predict the groundwater discharge potential at any coordinate specified. At the moment, the project is trained for Kathmandu Valley and ready to use for predicting discharge within Kathmandu. Training and testing of Gaussian Process Model is implemented in jupyter lab interface with the use of python package GPy. Keeping in mind that very few data is used for training the model, it's relatively low accuracy of prediction is not a surprise.

GW-predictor is a result of work for the 'Code for Nepal Datacrunch Hackathon' by team Lithosphere. Members of team Lithosphere include [Nelson Kandel](https://www.linkedin.com/in/nelsonkandel/), [Samriddhi Ghimire](https://www.linkedin.com/in/samriddhi-ghimire-522803215/) and [Prabesh Gyawali](https://www.linkedin.com/in/prabesh-gyawali-9849952a0/). Team Lithosphere succeded to secure the second position in the hackathon.

Gw-predictor is availabe under the MIT license. We'd love to incroporate your changes, so fork us.
## Requirements
GW-predictor uses the following Python packages:
* [jupyter](https://docs.jupyter.org/en/latest/)
* [numpy](https://numpy.org/doc/stable/)
* [pandas](https://pandas.pydata.org/docs/)
* [matplotlib](https://matplotlib.org/stable/index.html)
* [GPy](https://gpy.readthedocs.io/en/deploy/)

## Data Description
A [sample](https://github.com/KandelN/gw-predictor/blob/main/data/DeepTubeWell_Data-SAMPLE.xlsx) of original data file is provided in data folder. Each well have their unique well ids. Multiple row entry for with same well id represent data for multiple depth of the soil layer below ground level. First row entry of each well ids have discharge and other hydraulic properties associated with the specific well. 

## Preprocessing
Following steps are considered for preprocessing process:
1. Read original data file.
2. Extract first row for each unique well ids.
3. Check for no values.
4. Save the required information.

## Model Training
Train test ration = 70% <br>
**RBF Kernal:** <br>
Input Dimensions = 2 (i.e, x, y UTM coordinates) <br>
Lengthscale = 200 <br>
Variance = 5 <br>
**Optimization Algorithm:**
Limited-memory Broyden-Fletcher-Goldfarb-Shanno (L-BFGS)

## Results
**Scatter Plot of Actual Discharge vs Predicted Discharge**<br>
<img src="https://raw.githubusercontent.com/KandelN/gw-predictor/main/images/Qact_Qpre.png" alt="Q_act vs Q_pred" height="500"/>

**1D Cross section of prediction model along x-axis**<br>
<img src="https://raw.githubusercontent.com/KandelN/gw-predictor/main/images/interval.png" alt="Q_act vs Q_pred" height="500"/>

## Data Courtesy
[Kathmandu Upatyaka Khanepani Limited](https://kathmanduwater.org/)
