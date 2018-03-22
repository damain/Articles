## Installing plugins in the vue-cli template

One of the first things we learn as programmers is "don't re-invent the wheel". If you check the [Nativescript market](https://market.nativescript.org/) you can find a plugin for most of the advanced features that you want to have in your app. But getting those plugins to work in the nativescript-vue vue-cli template (that was a mouthful) is not straightforward, but it is easy if you know how to do it.  

Installing plugins in the official vue-cli template is not done the same way as other nativescript projects. 

Let's look at how we install plugins by installing the plugin [nativescript-star-ratings](https://market.nativescript.org/plugins/nativescript-star-ratings)

### Step 1
Open terminal and go to the root of your project

### Step 2
Instead of installing with `tns plugin add` run the following command
```sh
$ npm install nativescript-star-ratings
```
This installs the plugin at the root of the application in the node_modules folder

### Step 3
```sh
$ npm run clean
```
This clears the dist folder if the project was previously built.

### Step 4
Run your project again
```sh
$ npm run debug:android
```
You can change android to ios if you are using that platform 

### Step 5 
Require and register the plugin inside the scripts tag

```js
import Vue from 'nativescript-vue'

Vue.registerElement('StarRating', ()=> require('nativescript-star-ratings').StarRating)
```
The registerElement function expects the name of the XML element as the first argument, and a function that returns the plugin as its second argument.

### Step 6
Use the plugin. In our template tags we add the following
```xml
<StarRating emptyBorderColor="white" emptyColor="white" filledBorderColor="black" filledColor="red" value="2" max="5"/>
```
### Bonus
If you are using a plugin that does not use XML tags then you can skip steps 5-6 and handle it as follows in the script tags
```js
  const StarRating = require('nativescript-star-rating').StarRating
```
(That was just an example of how add a plugin that does not use tags but Star Ratings needs to output tags)

Two things to note here. Firstly we don't add namespaces in the `StarRatings` tag. And secondly we are also not defining namespaces on the page element. This is because in step 5 we used the "magical" registerElement function and that handles the namespacing automatically for us.

So how does this all work? Well when you run the app in Step 4 it sees that the dist folder was cleaned (in step 3) and regenerates the app, this bundles all the plugins that you added in to the dist folder. If you do not do step 3 then it will not bundle your newly added plugins into the dist folder and they won't be available to you. 

In future versions of this template the plan is to remove step 3. So you will have to check the [documentation for the vue-cli template](https://github.com/nativescript-vue/vue-cli-template) to see when step 3 is no longer nescessary. 
