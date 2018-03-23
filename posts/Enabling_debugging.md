## Enabling Debugging

In nativescript-vue's vue-cli template, debugging is not enabled by default so if there is an error with the code, we get this message `Error: A Frame must be used to navigate to a Page.`

If you don't know better you will think that there is a problem with Frames and then start going down a crazy rabbithole. When in fact it is as simple as turning on a flag to see the real error. 

### Lets enable debugging

#### Step 1
Locate the `src/main.js` file 

#### Step 2 
Around line 9-10 you should see the following line
```js
// Uncommment the following to see NativeScript-Vue output logs
//Vue.config.silent = false;
```
Uncomment the second line so it should look like this 
```js
// Uncommment the following to see NativeScript-Vue output logs
Vue.config.silent = false;
```
Save this file and when the app refreshes you will see the real error in the console
