<template>

    <div class="vue-img-preview-container">

        <img class="vue-img-preview" :src=getSetImage :alt=altText v-if="getSetImage">

       	<button id="vue-img-preview-button" :style="[buttonStyle]" v-if="pickerStyle !== 'regular'">
	        <input type="file" accept="image/*" :name=inputName @change="chooseImage">
		    <span>{{ buttonText }}</span>
		</button>

		<div class="form-group" v-if="pickerStyle === 'regular'">
	        <input type="file" accept="image/*" class="form-control" :name=inputName @change="chooseImage">
        </div>

    </div>

</template>

<script>
	export default {

		props: {

			defaultImage: {
		  		type: String,
		    	default: "",
		  	},

		  	inputName: {
		  		type: String,
		  		default: "file",
		  	},

		  	bgColor: {
		  		type: String,
		  		default: "#037B38"
		  	},

		  	textColor: {
		  		type: String,
		  		default: "#ffffff"
		  	},

		  	altText: {
		  		type: String,
		  		default: "vue img preview"
		  	},

		  	buttonText: {
		  		type: String,
		  		default: "Choose an image"
		  	},

		  	pickerStyle: {
		  		type: String,
		  		default: "regular"
		  	}

		},

		data () {
			return {
				setImage: null,
				buttonStyle: {
					backgroundColor: this.bgColor,
					color: this.textColor,
				}
			}
		},

		computed: {

			getSetImage () {
				return this.setImage !== null ? this.setImage : this.defaultImage
			},

		},

	    methods: {

	        chooseImage (e) {

	        	let files = e.target.files;

	        	if(files.length === 0) {
	        		this.setImage = null
	        		return
	        	}

	        	let reader = new FileReader();
	        	reader.onload = (e) => {
                    this.setImage = e.target.result;
                }

                reader.readAsDataURL(files[0]);

	        },

	    },

	}
</script>

<style>

	@import url(https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.0.0-alpha.6/css/bootstrap.min.css);

	/**
	 * the container div for
	 * the whole plugin template
	 */
	.vue-img-preview-container {
		height: 100%;
		width: 100%;
	}

	/**
	 * the class target the
	 * preview image
	 */
	.vue-img-preview {
		height: 100%;
		width: 100%;
		margin-bottom: 5px;
	}

	#vue-img-preview-button {
	    margin-top: 5px;
	    position: relative;
	    overflow: hidden;

	}

	#vue-img-preview-button input {
		width: 100%;
	    cursor: pointer;
	    position: absolute;
	    top: 0;
	    bottom: 0;
	    left: 0;
	    right: 0;
	    opacity: 0.001
	}

	/**
	 * the normal file picker input
	 * setting border and color
	 */
	#vue-img-preview-regular {

		border-style: solid;
		border-color: #cccccc;
		border-width: 1px;

	}

	/**
	 * the normal file picker input
	 * setting the margins
	 */
	#vue-img-preview-regular input {

		margin-top: 10px;
		margin-bottom: 10px;
		margin-left: 10px;

	}

</style>