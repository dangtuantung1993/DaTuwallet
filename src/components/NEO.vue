<template>
    <div class="container-fluid" id="NEO">
        <div class="logo">
            <img src="../assets/img/neo.svg">
        </div>
        <div class="row">
            <div class="col-lg-12" >

            </div>
        </div>
        <div class="form-group" style="text-align: center">
            <p v-if="!listname.length">
                <textarea class="form-control"
                          style="margin:50px auto;width:50%;"
                          rows="5"
                          v-model="wallets_input"
                          name="your_list_wallets"
                          placeholder="Nhap dia chi vi" autofocus
                          v-validate="'required'"
                          :class="{'form-control': true,
                                     'border-danger': errors.has('your_list_wallets')}">
                </textarea>
                <span v-show="errors.has('your_list_wallets')" class="text-danger">
                                                    {{ errors.first('your_list_wallets') }}
                </span>
            </p>
        </div>
        <button v-if="!listname.length"
                type="button"
                class="btn btn-success text-uppercase"
                @click="send"
                v-on:click="isshow = false">send
        </button>



    </div>
</template>

<script>
    import {listneo} from '../APIs/neoscanAPI';


    export default {
        name: "NEO",
        components:{

        },

        props: {},
        data: function () {
            return {
                isshow2:false,
                isshow: true,
                wallets_input: '',
                neos: null,
                balances: {},
                list_wallets: [],
                name:{ wal: 'Wallet'},
                listname:[],
                error:[]
            }

        },

        methods: {
            wait: function(ms) {
                return new Promise(r => setTimeout(r, ms))
            },
            async send() {
                this.checkForm()
                if (this.errors.length > 0){
                    return
                }
                let result = await this.$validator.validateAll()
                if (!result) {
                    return
                }

                let list_wallets = await this.wallets_input.split('\n')
                for(var i = 0; i < list_wallets.length;i++){
                    await this.getDataFromAPI(`${list_wallets[i]}`)
                    await this.wait(5000)
                }

            },
            checkForm() {
                this.error = []
                if (!this.wallets_input) {
                    this.error.push("Ban can nhap danh sach dia chi vi")
                }
            },
            getDataFromAPI: async function (your_wallet) {
                let neo = await listneo(your_wallet)
                this.neos = neo
                this.balances = neo.balance

            },

        },
    }

</script>
<style scoped>
    .logo {
        width: 70%;
        padding:20px 25px;
        text-align: center;
        display: block;
        margin: 0 auto;
    }



    .table-hover thead tr,.table-hover thead:hover tr{
        background-image:linear-gradient(to right, #0d76d0 , #04235d)!important;
    }
    .table-hover thead th{
        color:#fff;
        text-align: center;
        border-right:1px solid #ccc;
    }
    .table-hover th{
        text-align: center;
    }
    .table-hover td,.table-hover th{
        border-right:1px solid #ccc;
    }
    .table-hover tr:nth-child(even){
        background: #dcdbff;
    }
    .table-hover  tr:hover{
        background: #a6b6f3!important;
    }
    tr {
        width: max-content;
    }

    .container-fluid {
        text-align: center;
    }
    .btn-success {
        width: 50%;
    }

</style>