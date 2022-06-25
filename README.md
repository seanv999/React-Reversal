# React.js Reversal
reverse engineering web apps build with the popular React.js library...
# Gaining access to non global methods, functions...

```Js
//Root element, you can narrow down what your search by using child elements of the root
const app = document.getElementById('root');
Object.values(app);
//ya kinda a big flaw with react
```
# Finding Good Paths
kinda just trial and error, just look thru the console till you find what you wanna exploit
# Example
Gimkit uses React so we will use this

open up dev tools and look for elements that look promising 

![image](https://user-images.githubusercontent.com/79374771/175785525-0acd2a12-f3e2-44fc-80e1-ea08b0faf65a.png)

in this instance game-div looks the most valuable...

Lets grab that element and log its values to the console

```js
const entry = document.getElementById('game-div');
Object.values(entry);
```
now look thru the object till you find somethiong useful

![image](https://user-images.githubusercontent.com/79374771/175785722-7a3ceba3-0567-4b16-a493-4456d753b6bd.png)

as you can see i've find some good paths, lets use this to hack our speed




![image](https://user-images.githubusercontent.com/79374771/175785800-9aef0d3e-d3d4-4e8d-955f-5d4a7657576e.png)

We have find our path, right click and copy the path. Now we can call our setMovment function

```js
const entry = document.getElementById('game-div');
//path we found
Object.values(entry)[0].return.child.child.child.pendingProps.value.phaser.mainCharacter.movement.character.physics.setMovementSpeed('900')
```

Thanks for reading make sure to star!
