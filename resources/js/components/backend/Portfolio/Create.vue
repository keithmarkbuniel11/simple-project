<template>
    <div>
        <div class="form-group row">
            <label for="email" class="col-md-4 col-form-label text-md-right fa-3x">Portfolio</label>
        </div>

        <div class="form-group row">
            <label for="email" class="col-md-4 col-form-label text-md-right">Image Url</label>
            <div class="col-md-6">
                <input id="email" type="text" class="form-control " autofocus v-model="form.image_url">
            </div>
        </div>

        <div class="form-group row">
            <label for="email" class="col-md-4 col-form-label text-md-right">Title</label>
            <div class="col-md-6">
                <input id="email" type="text" class="form-control"  v-model="form.title">
            </div>
        </div>

        <div class="form-group row mb-0">
            <div class="col-md-8 offset-md-4">
                <button type="submit" class="btn btn-primary" @click="submit">
                    Create
                </button>
            </div>
        </div>
    </div>
</template>
<script>

import axios from 'axios'
export default {
    data(){
        return{
            form: {
                image_url: null,
                title: null,
            }
        }
    },
    methods: {
        submit(){
            
            axios.post('/api/portfolio',this.form) 
            .then(function (response) {

                console.log('working');
                console.log(response);
            })
            .catch(function (error) {
                 console.log('working error');
                console.log(error);
            });
        }
    }
}
</script>