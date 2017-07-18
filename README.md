# ToM webContent
This is a template that show you how to use our webContent library.
It allow you to test all available features without any development

Compatible with HTML5, IE9+

Work with Android, iOS and webApp 

## Table of Contents
**[How to use Tom client JavaScript library in your webContent](#how-to-use-tom-client-javascript-library-in-your-webcontent)**<br>
**[Available environment variables](#available-environment-variables)**<br>
**[API](#api)**<br>

## How to use Tom client JavaScript library in your webContent
* Include the script anywhere in your page
    ```html
    <script type="text/javascript" src="assets/js/ToM-client.min.js"></script>
    ```
    
* Create a function that will call 'ToM.env.get(varName)' method to extract environment variable
    ```js
    function displayEnvVars() {
        
        // This is the list of all varName that are available for environment variable
        var placeholders = [
            "APPLICATION_SERVER_ID",
            "APPLICATION_VERSION",
            "COACHING_ID",
            "EMAIL",
            "FIRST_NAME",
            "LANGUAGE",
            "LAST_NAME",
            "LEARNER_ID",
            "LOGIN",
            "SEQUENCE_ID",
            "TRAINING_ID",
            "USER_OS"];
    
        var divElem = document.getElementById("envVars");
        for (var i = 0; i < placeholders.length; i++) {
            var placeholder = placeholders[i];
            var pElem = document.createElement('p'),
                spanElem = document.createElement('span'),
                text = document.createTextNode(placeholder + " : "),
                id = document.createAttribute("id");
    
            id.value = placeholder;
            spanElem.setAttributeNode(id);
            spanElem.appendChild(document.createTextNode(ToM.env.get(placeholder)));
            pElem.appendChild(text);
            pElem.appendChild(spanElem);
            divElem.appendChild(pElem)
        }
    }
    ```
    
* Bind your function to the onLoad DOM event
    ```js
    window.addEventListener('load', displayEnvVars);
    ```
* There is also parameters available when the webContent is launched from the home page.
Those parameters can be accessed by calling 'ToM.param.get(paramName)'

## Available environment variables
| Name                    | Description                                     |
| ----------------------- | ----------------------------------------------- |
| `APPLICATION_SERVER_ID` | TODO                                            |
| `APPLICATION_VERSION`   | TODO                                            |
| `COACHING_ID`           | TODO                                            |
| `EMAIL`                 | The email for current logged in user            |
| `FIRST_NAME`            | The first name for current logged in user       |
| `LANGUAGE`              | The language setted in the application          |
| `LAST_NAME`             | The last name for current logged in user        |
| `LEARNER_ID`            | The unique identifier for current logged in user|
| `LOGIN`                 | TODO                                            |
| `SEQUENCE_ID`           | TODO                                            |
| `TRAINING_ID`           | TODO                                            |
| `USER_OS`               | TODO                                            |

## API
### ToM.version
Get the version of the library your using

### ToM.env.get(varName)
Get the value of *varName* environment variable (list available [here](#available-environment-variables))

### ToM.params.get(paramName)
Get the value of $paramName$ parameter variable

### ToM.utils.enableWakeLock()
Enable wake lock

### ToM.utils.disableWakeLock()
Disable wake lock

### ToM.utils.close()
Close the webContent


And that's it!