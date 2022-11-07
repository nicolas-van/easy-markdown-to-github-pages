# Week 1

## Requirements Step

Working on the files:
- `cred.js`
- all the other files importing the backendURL 

The backendURL is hardcoded in all of the modues which mack request to the backend server. If in future, we need to change this url, we would have to change this url in all of these modules individually and thus it would be a very time consuming process. What we require to do is make a single point updating method available for this particular task.

https://github.com/AmitPandey-Research/dfs-frontend/issues/1

## Design Step
- Tech stack being used: `Javascript`
- We need to extract this backendURL in a seperate module and then import this module in all the other modules . Doing this would help us to change the url at one point and this can be useful while testing and deploying the webapp seperately by just switching the url. 
- We can also have these two options so that we can dynamically switch between the two.
    - backendURL_developer
    - backendURL_deployment
- In future , this  `cred.js` module can be used to store various kinds of tokens which are commonly used among various modules hence making the design extensible.


## Build Step
- A new module named `cred.js` is created which stored a JSON object with `key:url` holding the backendURL.  
- `const url = 'http://10.4.25.20:3001/';` This piece of coded is commented from all the files.
- `import urls from "../../creds"; const url= urls.url;` This piece of code is added to import the url from    `cred.js`.


- Pull Request: [#3](https://github.com/AmitPandey-Research/dfs-frontend/pull/3)

## Testing Step
- Tested code for all possible conditions for login and signup.

- Test Cases
    - Checking the invalid login credentials
    - Checking that correct login credentials connects to the database properly

![](https://i.imgur.com/qM438ma.png)


![](https://imgur.com/qrAPwWg.png)

Logging in using correct credentials leads to proper connection with database

![](https://imgur.com/I2i31pj.png)
