<template>
    <div class="col-xs-12 none-padding ">
    <div class="col-xs-12 none-padding footer">
       <ul>
           <li>
               <h3>Contact</h3>
               <p><i class="fas fa-phone"></i><span>+84 888666893</span></p>
               <p><i class="fas fa-inbox"></i><span>dangtuantung150993@gmail.com</span></p>
               <p><i class="fab fa-facebook"></i><span>https://www.facebook.com/vo.tinh.9484</span></p>
           </li>
           <li>
               <h3>Donate</h3>
               <p><i class="fab fa-bitcoin"></i>Địa chỉ ví Bitcoin: 1JVPGf2L4NgiEEyuTvL7ukpcu1T6yozKEB</p>
               <p><i class="fab fa-ethereum"></i>Địa chỉ ví Ethereum: 0x42058e6E84b2CE3F7cE512DF9dcbd3432c6ce8B0</p>
           </li>
       </ul>

    </div>
    <div class="bottom">
        <p>Copyright © 2019 Dang Tuan Tung.</p>
    </div>
    </div>
</template>

<script>
    export default {
        name: "Footer"
    }
</script>

<style scoped>
.footer{
    background:#10074a;
    padding:15px;
    color: white;
width: 100%;
    float: left;

}
.none-padding{
    padding-left: 0px;
    padding-right: 0px;
}
.footer ul{
    list-style-type: none;
    padding-left: 0px;
    text-align: center;
    float: left;
    display: block;
    transform: translateX(-50%);
    left: 50%;
    position: relative;
    margin-bottom: 0px;
}
.footer ul li h3{
    margin-bottom: 20px;
}
    .footer ul li{
        display: inline-block;
        width: calc(100% / 2);
        text-align: left;
        float: left;
        padding-left: 40px;
    }
.footer ul li p:last-child{
    margin-bottom: 0px;
}

.footer ul li i{
    padding-right: 5px;
    width:28px;
    text-align: center;
}
    .bottom{
        width: 100%;
        display: block;
        float:left;
        background: #504a4a;
        padding: 10px;
    }
.bottom p{
    margin-bottom: 0px;
    color: #ffffff;
}
@media screen and (max-width: 868px){
    .footer ul li{
        width: 100%;
        text-align: center;
        margin-bottom: 30px;
        padding-left: 0px;
    }
    .footer ul li:last-child{
        margin-bottom: 0px;
    }
}
</style>