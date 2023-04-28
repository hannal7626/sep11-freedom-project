# MVP 
##### 04/17/23
<!-- Content: write about…
How you have been learning your tool
How you finished your MVP
Evidence: code snippets, screenshots, etc
 -->
### Content:
Perview to what has been completed. I have set up imports for authenication and variables that I need to get the user's sign up information and store that in the aunthenication not firestore yet. That would be one of the last step because having it saved at aunthenication files could work fine. Now I am working on `getRedirectResult()` and `GoogleAuthProvider` to access it's token and created a sign out button. 

[Google Access Token](https://firebase.google.com/docs/auth/web/google-signin): <br>
I want to connect my app to the google token so I would use GoogleProvider.
``` js 
 auth.signInWithPopup(auth, googleProvider)
        .then((result) => {
            // This gives you a Google Access Token. You can use it to access the Google API.
            const credential = GoogleAuthProvider.credentialFromResult(result);
            const token = credential.accessToken;
            // IdP data available using getAdditionalUserInfo(result)
            // ...
 ```
This gives me google access token. 
 <img src=img/ac.png>
Doing gave me an error in console that I wan't sure of so I used my google skill to search up solutions related. In [github dicussions](https://github.com/firebase/firebase-js-sdk/issues/5878), I found out that although I stated where GoogleAuthProvider is being called from with `const googleProvider = new firebase.auth.GoogleAuthProvider();`, I haven't mention where its from. I have to include that in my import like ` import { getAuth, createUserWithEmailAndPassword, the oogleAuthProvider} from 'https://www.gstatic.com/firebasejs/9.20.0/firebase-auth.js'`.


Sign out:<br>
When a user signs in their account, they will have access to their past database but we also want them to be able to sign out and ensured that data is linked to their account only so someone else can't access it. We can use `.addEventListener` to listen to the click and run the signOut() that runs the auth's signOut(). 
``` js
document.querySelector("#signout").addEventListener('onclick', signOut);
        //Sign out
        function signOut(){
            firebase.auth().signOut().then(function() {
                // Sign-out successful.
                alert("You have sign off");
                console.log('User Logged Out!');
                }).catch(function(error) {
                // An error happened.
                console.log(error);
            });

        }
 ```
 <img src=img/so.png>
 And when the Sign Out Button is click, the user is informed that they have sign off. 
 

### Engineering Design Process:
We are in step 4 of the engineering design process, building our app to be relivable and sustainable. 

#### Skills:
I am continuing to work on my debugging and googling skills. To debug errors that show up in the console with google when at the request module googleauthprovider was not found. I searched it up and [github dicussions](https://github.com/firebase/firebase-js-sdk/issues/5878) helped me define that i haven't imported it from the Auth's link. 

### Reflection: 
Our MVP is on the way to completion, I think there's other properties in firebase that I want to try out like the Pop Up and language options. That would be more beyond MVP though. 

[Previous](entry04.md) | [Next](entry06.md)

[Home](../README.md)
