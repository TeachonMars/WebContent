# ToM JS libraries
Compatible with HTML5, IE11+
Work with Android, iOS and webApp 

## Table of Contents
**[API Activity data](#api-activity-data)**<br>
**[API Environment variables](#api-environment-variables)**<br>
**[API Parameter variables](#api-parameter-variables)**<br>
**[API Utils](#api-utils)**<br>
**[API Home](#api-home)**<br>

##### ToM.version
Get the version of the library

## API Activity data
The data API allow you to retrieve and update session data of a learner

### List of available environment variables
| Name          | Data type     | Description |
| ------------- | ------------- | ----------- |
| `time`        | Integer (>0)  | Time spent on an activity during this session. If not setted or if time = 0, then the application will set it to the time spent in activity since launch |
| `totalTime`   | Integer (>=0) | Total time spent on an activity (sum of all previous sent sessions) |
| `points`      | Integer (>=0) | Number of points earned on an activity during this session |
| `progress`    | Integer (>=0 & <=100) | Progress on an activity |
| `score`       | Integer (>=0 & <=100) | Score on an activity |
| `success`     | Boolean  | Success is set to true if an activity is validated (score > successThreshold) |
| `suspendData` | String   | A string containing data that could be retrieve during another session |
| `location`    | String   | A string representing the current location in a multipage activity |

### Available functions
##### ToM.data.init()
Initialize all the data listed above with previous session values (if they exists) or with default values

##### ToM.data.get(key)
Get data stored for current session

##### ToM.data.set(key, value)
Set data to storage for current session.
If a value is already stored in session, then a set will overwrite the previous value.

##### ToM.data.send()
Send the current session data

***********************************************************************************************
## API Environment variables
### List of available environment variables
| Name                    | Description |
| ----------------------- | ------ |
| `APPLICATION_SERVER_ID` | Application server ID |
| `APPLICATION_VERSION`   | Application version |
| `COACHING_ID`           | Coaching ID |
| `EMAIL`                 | Email for current logged in user |
| `FIRST_NAME`            | First name for current logged in user |
| `LANGUAGE`              | Language setted in the application |
| `LAST_NAME`             | Last name for current logged in user |
| `LEARNER_ID`            | The unique identifier for current logged in user|
| `LOGIN`                 | Login of current logged in user |
| `SEQUENCE_ID`           | Sequence ID |
| `TRAINING_ID`           | Training ID |
| `USER_OS`               | OS on witch the application is running |
| `metadata.CODE_META`    | Display the value of a metadata (CODE_META is case sensitive |

### Available functions
##### ToM.env.getAll()
Retrieve all environment variables

##### ToM.env.get(paramName)
Retreive a specific environment variable

***********************************************************************************************
## API Parameter variables
### Available functions
##### ToM.params.getAll()
Retrieve all parameter variables

##### ToM.params.get(paramName)
Retreive a specific parameter variable

***********************************************************************************************
## API Utils
### Available functions
##### ToM.utils.enableWakeLock()
Enable wakeLock on smartphones

##### ToM.utils.disableWakeLock()
Disable wakeLock on smartphones

##### ToM.utils.isSandbox()
Check if the current training is a test version

##### ToM.utils.close()
Use this function to notify the content to close

***********************************************************************************************
## API Home
#### Category
##### ToM.home.getCategories()
Return a collection of categories
```
[
    {
        id: 'categoryId',
        title: 'categoryTtle',
        parent: 'parentCategoryId' or null if root category
        children: [childCategoryObject1, childCategoryObject2, ...],
        image: 'fullUrl'
    },
    ...
]
```

##### ToM.home.displayCategory('categoryId')
Redirect to the category passed as parameter

##### ToM.home.getCategoriesById([arrayCategoriesId])
Not implemented yet

#### Training
##### ToM.home.getTrainings()
Not implemented yet

##### ToM.home.getTrainingsByIds([arrayTrainingsIds])
Not implemented yet

##### ToM.home.getTrainingsByCategory(category)
Not implemented yet

##### ToM.home.displayTraining(trainingId)
Not implemented yet

#### Communication
##### ToM.home.getFeaturedCommunications()
Not implemented yet

##### ToM.home.displayCommunication(id)
Not implemented yet

#### Profile
##### ToM.home.getProfile()
Not implemented yet

##### Tom.home.displayProfile()
Not implemented yet

#### Other
##### ToM.home.isShakeAndLearnPossible()
Check if shakeAndLearn is available

##### ToM.home.shakeAndLearn()
Launch shakeAndLearn

##### ToM.home.getWelcome()
Not implemented yet

##### ToM.home.enter()
@TODO

##### ToM.home.leave()
@TODO
