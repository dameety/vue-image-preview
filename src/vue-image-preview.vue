<template>
	
    <div class="vue-image-preview-container">

        <img class="vue-image-preview" :src=getSetImage v-if="getSetImage">

       	<button id="vue-image-preview-button">
	        <input type="file" accept="image/*" :name=inputName @change="chooseImage">
		    <span>Choose Image</span>
		</button>
    
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
		  	
		},

		data () {
			return {
				setImage: null,
			}   
		},
		
		mounted () {

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
	
	.vue-image-preview-container {
		height: 100%;
		width: 100%;
	}

	.vue-image-preview {
		height: 100%;
		width: 100%;
		margin-bottom: 5px;
	}

	#vue-image-preview-button {
	    margin-top: 5px;
	    position: relative;
	    overflow: hidden;
	    cursor: pointer;
	}

	#vue-image-preview-button input {
	    cursor: pointer;
	    position: absolute;
	    top: 0;
	    bottom: 0;
	    left: 0;
	    right: 0;
	    opacity: 0.001
	}

</style>