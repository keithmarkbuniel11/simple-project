<template>
    <div>
        <section class="page-section" id="services">
            <div class="container-fluid p-0">
                <h2 class="text-center mt-0">Portfolios</h2>
                <hr class="divider my-4" />
                <div class="row no-gutters">
                    <div class="col-lg-4 col-sm-6" v-for="portfolio in portfolios" :key="portfolio.id">
                        <a class="portfolio-box" :href="portfolio.image_url">
                            <img :src="portfolio.image_url" style="width:250px; height:250px;">
                            <div class="portfolio-box-caption">
                                <h3 class="h4 mb-2">{{ portfolio.title }}</h3>
                            </div>
                        </a>
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
                portfolios: []
            };
        },
 
        created() {
            this.getPortfolios();
        },
 
        methods: {
            getPortfolios() {
                let $this = this;
                axios.get('api/portfolio')
                    .then(response => {
                        $this.portfolios = response.data;
                        console.log(response);
                    })
                    .catch(err => console.log(err));
            }
        }
    };
</script>