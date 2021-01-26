<template>
    <div>
        <section class="page-section" id="services">
            <div class="container">
                <h2 class="text-center mt-0">Portfolios</h2>
                <hr class="divider my-4" />
                <div class="row">
                    <div class="col-lg-3 col-md-6 text-center" v-for="service in services" :key="service.id" >
                        <div class="mt-5">
                            <i class="text-primary mb-4 fa-5x" :class="service.icon"></i>
                            <h3 class="h4 mb-2">{{ service.title }}</h3>
                            <p class="text-muted mb-0">{{ service.details }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>
</template>
<script>

import axios from 'axios';

    export default {
        data() {
            return {
                services: []
            };
        },
 
        created() {
            this.getServices();
        },
 
        methods: {
            getServices() {
                let $this = this;
                axios.get('api/services')
                    .then(response => {
                        $this.services = response.data;
                        console.log(response);
                    })
                    .catch(err => console.log(err));
            }
        }
    };
</script>