# Disaster-Response-Pipeline
I applied the data pipeline skills learned to analyze disaster data from Figure Eight to build a model for an API that classifies disaster messages. I built a machine learning pipeline to categorize emergency messages based on the needs communicated by the sender.

### Table of Contents

1. [Instructions](#instructions)
2. [File Descriptions](#files)
3. [Screenshots](#screen)
4. [Licensing, Authors, and Acknowledgements](#licensing)

### Instructions:<a name="instructions"></a>
1. Run the following commands in the project's root directory to set up your database and model

    - To run ETL pipeline that cleans data and stores in database
        `python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db`
    - To run ML pipeline that trains classifier and saves
        `python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl`

2. Run the following command in the app's directory to run your web app.
    `python run.py`

3. Go to http://0.0.0.0:3001/ (or you have to modify your link to somehting like this https://SPACEID-3001.SPACEDOMAIN)

### Screenshots:<a name="screen"></a>

<a id='eg'></a>

Running [this command](#com) **from app directory** will start the web app where users can enter their query, i.e., a request message sent during a natural disaster, e.g. _"Please, we need tents and water. We are in Silo, Thank you!"_.

**_Screenshot 1_**

![master](img/master.jpg)

What the app will do is that it will classify the text message into categories so that appropriate relief agency can be reached out for help.

**_Screenshot 2_**

![results](img/res.jpg)

<a id='run'></a>
### File Descriptions:<a name="files"></a>

`process_data.py`: A ETL Pipeline that 
- loads the `messages` and `categories datasets`
- merges the two datasets
- cleans the data
- stores it in a SQLite database

`train_classifier.py`: A Machine Learning Pipeline that
- loads data from the SQLite database
- splits the dataset into training and test sets
- builds a text processing and machine learning pipeline
- trains and tunes a model using GridSearchCV
- outputs results on the test set
- exports the final model as a pickle file

`run.py`: A Flask Web App that visualizes the results

### Licensing, Authors, Acknowledgements<a name="licensing"></a>

Must give credit to Figure Eight for the data.
