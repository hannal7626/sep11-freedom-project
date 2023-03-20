# Entry 4
##### 03/11/23

## MVP

Content: <br>
Mid-Februaryuary, I switched my idea from my budgeting system to working with Yala and David on a pet finder app. We had discussed how we would split the work and included that in our MVP [file](https://docs.google.com/document/d/1IOgOBQIXL0xnpZYDINYj7pjE6Xca6grdK6rAzGLUkfc/edit?usp=sharing) and [wireframe](). In our own time, individually we practiced our tool and worked towards the steps indicated on our MVP sheet. 
Progress: 
I set up the `HTML` page for grabbing information so that Iand David can use firebase to store that data. While Yala adds a map to later locate the coordinates of the pet.

<img src="img/fp-nav.png"><br>
<!-- <img src="img/fp-main.png"><br> -->
<img src="img/fp-pg.png"><br>
<img src="img/fp-map.png"><br>
Below is the code used to store the pet information temporarily so we can later switch to firebase. 

``` js
// Set pet name
            document.getElementById('name').addEventListener("keyup",function(event){
                document.getElementById('petname').innerHTML = event.target.value;
            });

            //Set locations
            document.getElementById('button').addEventListener("click",function(event){
                document.getElementById('coordlong').addEventListener("change",function(event){
                    document.getElementById('locationlong').innerHTML = event.target.value;
                });
            });
            document.getElementById('button').addEventListener("click",function(event){
                document.getElementById('coordlat').addEventListener("change",function(event){
                    document.getElementById('locationlat').innerHTML = event.target.value;
                });
            });

```
As for firebase, I have gotten the initialization in and a ongoing problem occurred with the initialization of the realtime database. 

Engineering Design Process:
This is the EDP of creation. We have planned and started building the MVP page of our prototype. Also, the part to test and debug. 

Skill: 
This is how to learn and debug. Problems came up while learning my tool and that was okay because I could debug it with the console's help. This also taught me patience, it is important to take my time with each line of code and not rush through. Working in a group meant that communication is a norm, it is important to let my partners know when I am having trouble in case of code overlaps and errors and to prevent misconnection. 

[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)