<template>
    <div class="container-fluid">
        <Banner></Banner>
        <div class="bg-content">
        <div class="container">
            <ul class="list-box">
                <li>
                    <div @click="ethereum" class="box">
                        <div class="before-af"></div>
                        <span>
                            <img src="../assets/img/eth.svg">
                        </span>

                    </div>
                </li>
                <li>
                    <div @click="neo" class="box">
                        <div class="before-af"></div>
                        <span>
                            <img src="../assets/img/neo.svg">
                        </span>

                    </div>
                </li>
                <li>
                    <div @click="bitcoin" class="box">
                        <div class="before-af"></div>
                        <span>
                            <img src="../assets/img/bitcoin.svg">
                        </span>
                    </div>
                </li>
                <li>
                    <div class="box">
                        <div class="before-af"></div>
                        <span>
                            <img src="../assets/img/cybermile.svg">
                        </span>
                    </div>
                </li>
                <li>
                    <div class="box">
                        <div class="before-af"></div>
                        <span>
                            <img src="../assets/img/eos.svg">
                        </span>

                    </div>
                </li>
                <li>
                    <div class="box">
                        <div class="before-af"></div>
                        <span>
                            <img src="../assets/img/tron.svg">
                        </span>

                    </div>
                </li>
            </ul>
        </div>
        </div>
        <Footer></Footer>
    </div>
</template>
<script>
    import Footer from '../components/Footer'
    import Banner from '../components/Banner'
export default {
    name: "Home",
    components: {
        Banner,
        Footer
    },
    data() {
        return {

        }
    },

    methods: {
        ethereum() {
            this.$router.push('/eth')
        },
        neo() {
            this.$router.push('/neo')
        },
        bitcoin() {
            this.$router.push('/btc')
        },

    }
}
</script>
<style scoped>
.container-fluid {
    padding-left: 0px !important;
    padding-right: 0px !important;
    background: #92baec;
}
.bg-content{
    background: #92baec;
}
.list-box {
    list-style-type: none;
    padding-left: 0px;

    margin-bottom: 0px;
    padding-bottom: 50px;
}

.list-box li {
    display: inline-flex;
    width: calc(100% / 3);
    padding: 0px 25px;
    text-align: center;


}

.list-box li:nth-child(3n+1) {
    margin-top: 70px;
}



.list-box li .box {

    position: relative;
    transform: translateX(-50%);
    left: 50%;
}

.list-box li span{
    display: block;
}

.list-box li span img {
    width: 170px;
    border: 1px solid #DDD;
    border-radius: 50%;
    padding: 10px;
}
.list-box li .before-af{
    content: "";
    position: absolute;
    top: -22px;
    left: -22px;
    background: url("../assets/img/imgafter.png");
    background-size: 100%;
    width: calc(100% + 44px);
    height: calc(100% + 44px);
    -webkit-transition: all 3s ease;
    transition: all 3s ease;
    cursor: pointer;


}
.list-box li:nth-child(2n+1) .before-af{
    animation: ducAnimationR-L-R 9s linear infinite;
    -moz-animation: ducAnimationR-L-R 9s linear infinite;
    -webkit-animation: ducAnimationR-L-R 9s linear infinite;
    -o-animation: ducAnimationR-L-R 9s linear infinite;

}
.list-box li:nth-child(2n) .before-af{
    transform: rotate(145deg);
    animation: ducAnimationR-R-L 9s linear infinite;
    -moz-animation: ducAnimationR-R-L 9s linear infinite;
    -webkit-animation: ducAnimationR-R-L 9s linear infinite;
    -o-animation: ducAnimationR-R-L 9s linear infinite;

}

@keyframes ducAnimationR-L-R{
    from{transform:rotate(0deg);}
    to{transform:rotate(360deg);}
}
@keyframes ducAnimationR-R-L{
    from{transform:rotate(145deg);}
    to{transform:rotate(-215deg);}
}
@media screen and (max-width: 767px){
    .list-box{
        margin-top: 30px;
    }
    .list-box li{
        width:100%;
        margin-bottom: 60px;
    }
    .list-box li:nth-child(3n+1){
        margin-top: 0px;
    }
}
</style>