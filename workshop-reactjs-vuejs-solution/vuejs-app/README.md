# Tesla Battery Range Calculator in Vue !!!

Hey guys, tonight you'll have to build this app:

![Bookstore gif](https://cdn-images-1.medium.com/max/2000/1*8hlNoLDBy5XWZct5tAtPoA.png)

Using either react or vuejs, choose your weapon ⚔

### Clone or downlaod
```bash
git clone https://github.com/petereijgermans11/workshop-reactjs-vuejs.git

### If you'd rather use VueJS

- goto this folder in the terminal: 

cd workshop-reactjs-vuejs
cd ./vuejs-app

### Getting started

- `yarn` To install all the dependencies for this workshop. If you don't have yarn installed, install it via `npm i yarn`
- `yarn start` To start the website locally.
- Navigate to [http://localhost:8080/](http://localhost:8080/) To see the website running, full of bugs :)

### First things first

We've left a few bugs in the website, that you'll have to fix in order to understand the basic concepts of Vue.js

The main.js file is the entry point of the site, it is here that your first component is mounted and rendered.

### App.vue

This is the first component mounted by Vue.
This component consist of the tesla-battery.component. This is the container component.
The tesla-battery.component: Provides data and actions to presentational components.

# Happy coding ! ;-)
```

# TO DO
Please: fix all the bugs before building new features
And download the Vue Devtools extension for a better development experience:
https://github.com/vuejs/vue-devtools


# ERROR 1
```bash

Property or method "wheels" is not defined on the instance but referenced during render. Make sure that this property is reactive, either in the data option, or for class-based components, by initializing the property. See: https://vuejs.org/v2/guide/reactivity.html#Declaring-Reactive-Properties.

found in

---> <TeslaBattery> at src/tesla-battery/tesla-battery.component.vue
       <App> at src/App.vue
         <Root>

See line 'tesla-battery.component':

         '<tesla-wheels v-model="wheels" />'

```

# ERROR 2
```bash

Property or method "model" is not defined on the instance but referenced during render. Make sure that this property is reactive, either in the data option, or for class-based components, by initializing the property. See: https://vuejs.org/v2/guide/reactivity.html#Declaring-Reactive-Properties.

found in:

---> <TeslaStats> at src/tesla-battery/components/tesla-stats.component.vue

see 'tesla-stats.component':

<li v-for="stat in stats" :key="model">
       
```

# ERROR 3
```bash

Missing required prop: "value"

found in

---> <TeslaCounter> at src/tesla-battery/components/tesla-counter.component.vue
       <TeslaBattery> at src/tesla-battery/tesla-battery.component.vue
         <App> at src/App.vue
           <Root>


See line 'tesla-battery.component' (HINT: 'v-model' directive is missing):

<tesla-counter title="Outside Temperature" unit="°" :step="10" :min="-10" :max="40" />

```       

# ERROR 4
```bash

Invalid prop: type check failed for prop "value". Expected String, got Boolean.

found in

---> <TeslaClimate> at src/tesla-battery/components/tesla-climate.component.vue
       <TeslaBattery> at src/tesla-battery/tesla-battery.component.vue
         <App> at src/App.vue
           <Root>

See 'tesla-climate.component'

```

# ERROR 5
```bash

Invalid prop: type check failed for prop "onClick". Expected String, got Function.

found in

---> <TeslaClimate> at src/tesla-battery/components/tesla-climate.component.vue
       <TeslaBattery> at src/tesla-battery/tesla-battery.component.vue
         <App> at src/App.vue
           <Root>

See 'tesla-climate.component'


```

# ERROR 6
```bash

When you click on the 'Speed button', then you get the following error:

Uncaught ReferenceError: increment is not defined
    at HTMLButtonElement.onclick ((index):17)


 See 'tesla-counter.component':

<button tabindex="-1" type="button" onclick="increment" :disabled="value === max"></button>
<button tabindex="-1" type="button" onclick="decrement" :disabled="value === min"></button>
```



# ERROR 7
```bash

The 'stats()' function in the 'tesla-battery.component' does change when the user input changes (wheelzise – climate – speed - temparature).

Extra info:
tesla-battery.component stats()-function is for calculating the maximum battery range per model. 
This range is based on the user input (wheelzise – climate – speed - temparature)

This is the JSON-format what the stats()-function should return per model:

[
  {"model":"60","miles":267},
  {"model":"60D","miles":271},
  {"model":"75","miles":323},
  {"model":"75D","miles":332},
  {"model":"90D","miles":365},
  {"model":"P100D","miles":409}
]

```  

# Exercise 1
```bash

Make the climate button work.
It is always on. 

 ```

# Exercise 2
```bash

Decrement speed/temparature does not work (in the tesla-counter.component).

Fix the decrement function:

 decrement() {
   ...<FIXME>...
 }

 ```


# Exercise 3
```bash

Create the 'tesla-header.component' for showing the tesla 'logo'.
Define 'greeting' as input property!

HINT: See the slides for the solution.

 ``` 

 # Exercise 4
 ```bash
 
Create the 'tesla-car.component' for showing the tesla-car.
Define 'wheels' and 'speed' as input properties!

Move this code from the TeslaBattery.js to the TeslaCar.js and place it in the '<template>-section':

   <div class="tesla-car">
        <div class="tesla-wheels">
            <div :class="`tesla-wheel tesla-wheel--front tesla-wheel--${tesla.wheels}--${tesla.speed}`"></div>
            <div :class="`tesla-wheel tesla-wheel--rear tesla-wheel--${tesla.wheels}--${tesla.speed}`"></div>
        </div>
    </div>

Finally import the 'tesla-car.component' in the 'tesla-battery.component' (alias: TeslaCar)
And define the TeslaCar in the 'components-section' of the 'tesla-battery.component'.

 ``` 

# Exercise 5
```bash

Write a custom 'filter' with the name 'km', to translate Miles to km (in the tesla-stats.component)

  filters: {
    ...<FIXME>...
  }
``` 

# Exercise 6
```bash

The 'Arrow down' does not work when the focus is on it (in the tesla-counter.component).

   onKeyUp(event) {
      ...<FIXME>...
   }

```

# Exercise 7
```bash

Add the Vue component to add a snowfall on your page.

    https://github.com/P3trur0/vue-niege

And change the background color, so you can see the snow (tesla-style.css)
Or change the properties of this component.

```

# Final Exercise:

Too easy for you? Use Vuex to manage the state of your app :)
