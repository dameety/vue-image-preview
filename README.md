# Vue-img-preview

 This is a minimal image preview implementation that does only one thing; give users feedback by showing image chosen from a file input.

## looks like this (without the form)

![demo](https://cloud.githubusercontent.com/assets/10757330/26514483/148ab3b8-426a-11e7-8bd3-e40465e2509e.jpg)


## Installation

```
	npm install vue-img-preview --save
```

## Import

```
import Vue from 'vue'
import {vueImgPreview} from 'vue-img-preview'

Vue.component('vue-img-preview', vueImgPreview)

```

## Browser Usage

```
<script src="path/to/vue/vue.js"></script>
<script src="path/to/dist/vue-img-preview.js"></script>

<script>

  Vue.component('vue-img-preview', vueImgPreview)

  const vm = new Vue({
    ...
  });

</script>

```

## Then:

```
<vue-img-preview

	input-name= "profile_picture"
	default-image= "https://placehold.it/350x150"
	bg-color= "#ffffff"
	text-color= "#000000"
	alt-text="profile picture"
    button-text="Choose image"
    picker-style="regular"

></vue-img-preview>
```

## Or Just:

```
<vue-img-preview></vue-img-preview>

```

## Props

| Name | Default | Type | Decsription |
|------|:--------:|------|-------------|
| input-name | file |String| name of the file input field
| default-image |  |String| an image to display when the component loads before the user clicks the file input
| bg-color | #037B38 |String| background color of the select button
| text-color | #ffffff | String| color of the select text
| alt-text | vue img preview | String| alternative text for the image
| button-text | Choose an image | String| text to show on the button
| picker-style | Regular | String | how the image picker should be displayed. Button-text, text-color & bg-color won't work with this.
