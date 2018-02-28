# Nativescript-vue and vue-cli!

Well [nativescript-vue](http://nativescript-vue.org) just hit 1.0 in February and it is awesome! 

Just in case you haven't heard about it before, [nativescript-vue](http://nativescript-vue.org) allows you to write truely native mobile apps just as you would a regular [Vue.js](https://vuejs.org) app, the major exception being that instead of writing html templates you write the xml equivalent 

For example instead of:
```html
<template>
	<div>
		<nav>...</nav>
	</div>
</template>
```
You would write:
```html
<template>
	<Page>
		<ActionBar  title="NativeScript-Vue">...</ActionBar>
	</Page>
</template>
```
This means that if you have ever written an app in [Vue.js](https://vuejs.org) you now have the tools to write a native app.

The tooling around it is still being shaped. There are a bunch of community templates floating around with webpack and roundup bundling but there is a new [template](https://github.com/nativescript-vue/vue-cli-template) created by "@lewebsimple" Pascal Martineau that uses the vue-cli version 2.x. 

It allows you to write single file components as .vue files (Single file components allow you to write the template css and scripts in one file). This is awesome because it helps you keep your code base logically separated and helps you stay sane and avoid spaghetti code.

It supports using most plugins that are already available to be used in Nativescript including Firebase 

I'm sure you can't wait to get started so lets install it. I am assuming that you already have your system setup for nativescript development, if not you can follow the [quick setup](https://docs.nativescript.org/start/quick-setup) before trying the steps below:

Installing vue-cli
```sh
$ npm install -g vue-cli
```
Scaffolding the project
```
$ vue init nativescript-vue/vue-cli-template <project-name>
```
Go in to the project folder
```sh
$ cd <project-name>
``` 

Install dependencies
```sh
$ npm install
```

Build the app, load it on the emulator or on a device and enable hot reloading(you don't need to run both commands unless you want to run both emulators)
```sh
$ npm run watch:android
$ npm run watch:ios
```
