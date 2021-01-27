<template>
    <div class="containerOnToggle">
        <span></span>
        <div id="cssSelector"><!--animatejs-class-->
        <div class="line">
            <div class="square el">
                <div class="littleContainer"><!--little container of card-->
                    <div>
                        <button id="touchButton" :style="btnStyle">{{ btnTitle }}</button>
                    </div>
                    <div class="formBloc"><!--container of form card-->
                        <h3 :style="titleStyle">{{ title }}</h3>
                        <input type="text" placeholder="Nom">
                        <input type="email" placeholder="Email">
                        <input type="text" placeholder="Telephone">
                        <textarea placeholder="Message" name="" id="" cols="5" rows="4"></textarea>
                        <button type="submit" :style="btnSubmitStyle">Envoyez</button>
                    </div>
                </div>
            </div>
        </div>
        </div>
    </div>
</template>
<script>
    export default{
        name: 'touchButton',

        data: function(){
            return{
            }
        },

        props: {
            title: {
                String,
                default: 'Recevez nos notification'
            },
            titleColor: {
                String,
                default: '#000'
            },
            btnTitle: {
                String,
                default: 'clique ici'
            },
            btnBackColor: {
                String,
                default: '#000'
            },
            btnColor: {
                String,
                default: '#fff'
            },
            btnSubmitBackColor: {
                String,
                default: '#000'
            },
            btnSubmitColor: {
                String,
                default: '#fff'
            },
        },

        computed: {
            btnStyle(){
                return{
                    "background-color": this.btnBackColor,
                    "color": this.btnColor,
                }
            },
            titleStyle(){
                return{
                    "color": this.titleColor,
                }
            },
            btnSubmitStyle(){
                return{
                    "background-color": this.btnSubmitBackColor,
                    "color": this.btnSubmitColor,
                }
            }
        },

        mounted(){
            var touchButton = document.querySelector('#touchButton')

        
            touchButton.addEventListener("click",function(){
                var el = document.querySelector('.containerOnToggle span')//span fictif for toggle
                var verif = el.classList.toggle('hidden')
                if(verif){
                    toggleElement();
                }else{
                    toggleElement2();
                }
            },false)

            function toggleElement(){
                var cssSelector = global.anime({
                targets: '#cssSelector .el',
                translateX: -250
                });
                console.log(cssSelector)
            }
            function toggleElement2(){
                var cssSelector = global.anime({
                targets: '#cssSelector .el',
                translateX: 0
                });
                console.log(cssSelector)
            }
        }
    }
</script>
<style scoped>

    .containerOnToggle{
        position: fixed;
        top: 20%;
        right: 0px;
        overflow-x: hidden;
    }
    button#touchButton{
        padding: 15px;
        transform: rotate(-90deg);
        margin-right: -32px;
        font-weight: bold;
        font-size: 15px;
        background-color: #061A79;
        text-transform: uppercase;
        border-top-left-radius: 10px;
        border-top-right-radius: 10px;
        border: none;
        color: #fff;
        cursor: pointer;
        max-width: 129px;
        max-height: 65px;
        overflow: hidden;
    }
    .littleContainer{
        display: flex;
        align-items: center;
        transform: translateX(250px);
    }
    .formBloc{
        border: 1px solid #e2e2e2;
        font-family: sans-serif;
        background-color: #fff;
        border-top-left-radius: 10px;
        border-bottom-left-radius: 10px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        color: #000;
        padding: 10px;
    }
    .formBloc input{
        height: 22px;
        margin-top: 10px;
        border: 1px solid #e2e2e2;
        padding: 11px;
        color: #000;
    }
    .formBloc button{
        padding: 11px;
        margin-top: 5px;
        font-size: 13px;
        font-weight: bold;
        border: none;
        background-color: #1FB3FC;
        color: #fff;

    }
    .formBloc textarea{
        margin-top: 5px;
        padding: 11px;
        border: 1px solid #e2e2e2;
    }
    .formBloc h3{
        max-width: 230px;
        max-height: 65px;
        overflow: hidden;
    }
    .hidden{
        display: none!important;
    }
</style>