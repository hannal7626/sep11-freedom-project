# Entry 3
##### 02/06/23
---
## Learn & Build 

Content: <br>
I tried practicing with real-time databases again since that's what I need for my project. Along with [Write data in a firebase real-time database with javascript](https://www.youtube.com/watch?v=VXWmJsv1Vh4) as guidance, I worked on configuration.  After adding the config and attaching firebase, I wanted to save names so I made an `input` for the `namefield` and a `button` for submitting with the code below. <br>
<img src="img/name-html.png"> <br>
Then I wrote js code to make my button interactive when it is clicked and push that information to my project's database. <br>
```js
 var app = initializeApp(firebaseConfig);
            const analytics = getAnalytics(app);
            var firebaseRef = firebase.database().ref('names');
            document.querySelctor('#send').addEventListener('click', ()=>{
                const name = document.getElementById('namefield').value;
                firebaseRef.push('names')
            })
```
This is the page with "Yala" typed as the name:<br>
<img src="img/name-page.png"><br>
And here is the result on the firebase website after clicking submit: <br>
<img src="img/name-database.png"><br>

Authentication: <br>
Following a [video](https://www.youtube.com/watch?v=fgdpvwEWJ9M), I set up the page to get start saving the email and password in firebase's authentication section. This is my page before typing anything in the text inputs:<br>
<img src="img/emailpass-page.png"><br>
Then I write some js to connect my page to the tool firebase and the part I am using. I also create variables to grab a specific part of my page, so that I can use it later for authentication. To make sure that I have no error, I use `console.log` to check the code. <br>

```js
const firebaseApp = firebase.initializeApp({
    apiKey: "AIzaSyAuz_Elb7M2On5C5Ze5TPsD1fgZBu8lTUs",
    authDomain: "hauthentic-95b6e.firebaseapp.com",
    projectId: "hauthentic-95b6e",
    storageBucket: "hauthentic-95b6e.appspot.com",
    messagingSenderId: "738058233345",
    appId: "1:738058233345:web:a60ac0bdbf5f40f5684200",
    measurementId: "G-WTVBW6M09B"
});

const db = firebaseApp.firestore();
const auth = firebaseApp.auth();

var signup = () => {
    const email = document.getElementById('email').value
    const password = document.getElementById('password').value
    // console.log(email, password)

    auth.createUserWithEmailAndPassword(email, password)
    .then((res) => {
        console.log(res.user)
    })
    .catch((err) => {
        console.log(err.code)
        console.log(err.message)
    })
}
```

Then to test the web, type in a test email and password for hello@gmail.com:<br>
<img src="img/emailpass-text.png"><br>
Open the console using inspect to check if the page is running correctly. <br>
<img src="img/emailpass-console.png"><br>
Great! This shows that the data is being transferred to firebase's authentication and if I open the authentication page it should show the new information. 
<img src="img/emailpass-work.png"><br>
Just like above.
From this exercise, I have a deeper understanding of how to initialize firebase, the most important is to always add the config in index.html and include which is being used. 


Engineering Design Process:<br>
This is the EDP of defining, researching, and brainstorming the solution to get used to its syntax. It is important to do so since creating the plan for this project will be soon. In order to be skillful, I have to fully understand how to initialize between firebase and javascript so as to limit errors along my year-long project. 

Skill: <br>
This is how to learn and debug. Problems came up while learning my tool and that was okay because I could debug it with the console's help. This taught to learn how to problem-solve instead of giving up. Though I might have failed to complete it the first time as long as I preserve and continue to research different parts of the tool, I am confident in my skill. 

[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
