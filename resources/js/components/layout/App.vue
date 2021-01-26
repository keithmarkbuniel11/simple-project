<template>
    <div>
        <nav class="navbar navbar-expand-lg navbar-dark fixed-top py-3" id="mainNav" style="background: #000">
            <div class="container">
                <router-link :to="{ name: 'home' }" :class="'navbar-brand js-scroll-trigger'">Simple Project</router-link>
                <button class="navbar-toggler navbar-toggler-right" type="button" data-toggle="collapse" data-target="#navbarResponsive" aria-controls="navbarResponsive" aria-expanded="false" aria-label="Toggle navigation"><span class="navbar-toggler-icon"></span></button>
                <div class="collapse navbar-collapse" id="navbarResponsive">
                    <ul class="navbar-nav ml-auto my-2 my-lg-0">
                        <li class="nav-item"><router-link :to="{ name: 'home' }" :class="'nav-link js-scroll-trigger'">Home</router-link></li>
                        <li class="nav-item"><router-link :to="{ name: 'services-create' }" :class="'nav-link js-scroll-trigger'">Services</router-link></li>
                        <li class="nav-item"><router-link :to="{ name: 'portfolio-create' }" :class="'nav-link js-scroll-trigger'">Portfolio</router-link></li>
                    </ul>
                </div>
            </div>
        </nav>
        <div class="container" style="margin-top: 100px;">
            <router-view></router-view>
        </div>
    </div>
</template>
<script>
    export default {}
</script>