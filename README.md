# Vue-img-preview

 This is a minimal image preview implementation that does only one thing; give users feedback by showing image chosen from a file input.

#Installation


## Installation

```
	npm install vue-img-preview
```

## Usage

```
import Vue from 'vue'
import vueImgPreview from './vue-img-preview.vue'

new Vue({
	
	el: '#app',
  	components: {vueImgPreview}

})
```

## Browser Usage

```
<script src="path/to/vue/vue.min.js"></script>
<script src="path/to/dist/vue-img-preview.js"></script>

new Vue({

  	el: '#app',
	components: {vueImgPreview}

})
```

 Then:

```
<vue-img-preview
	input-name= "imageName"
	default-image= "https://placehold.it/350x150"
	bg-color= "#ffffff"
	text-color= "#000000"
></vue-img-preview>
```

Or Just:

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
 

## Dev  build 

``` 
npm run dev
```

## Production build

```
 npm run build
```