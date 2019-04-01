<template>
    <div class="banner">
        <b-carousel
                id="carousel-fade"
                style="text-shadow: 0px 0px 2px #000"
                fade
                indicators
                img-width="1024"
                img-height="480">
            <b-carousel-slide caption="" img-src="~../assets/img/banner/bg-03.jpg" />
            <b-carousel-slide caption="" img-src="~../assets/img/banner/bg-02.jpg" />
            <b-carousel-slide caption="" img-src="~../assets/img/banner/bg-01.jpg" />
        </b-carousel>
    </div>
</template>

<script>
    export default {
        name: "Banner",
    }

</script>

<style scoped>

</style>