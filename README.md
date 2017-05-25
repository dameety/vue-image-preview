# Vue-image-preview

 This is a minimal image preview implementation that does only one thing; give users feedback by showing image chosen from a file input.

#Installation


## Installation

```

```

## Usage

```
import Vue from 'vue'
import vueImagePreview from './vue-image-preview.vue'

new Vue({
	
	el: '#app',
  	components: {vueImagePreview}

})

```

+## Browser Usage

```
<script src="path/to/vue/vue.min.js"></script>
<script src="path/to/dist/vue-image-preview.js"></script>

new Vue({
  el: '#app',
  components: {vueImagePreview}
})

```

 Then:

```
<vue-image-preview
	input-name= "imageName"
	default-image= "https://placehold.it/350x150"
	bg-color= "#ffffff"
	text-color= "#000000"
></vue-image-preview>

```

Or Just:

```
<vue-image-preview></vue-image-preview>

```

## Props

| Name | Default | Type | Decsription |
|------|:--------:|------|-------------|
| input-name | file |String| name of the file input field
| default-image |  |String| an image to display when the component loads before the user cliks the file input
| bg-color | #037B38 |String| background color of the select button
| textColor | #ffffff | String| color of the select text
 
