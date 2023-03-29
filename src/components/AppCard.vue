<script>


export default {
    data() { 
        return {

            textButton:'Compra',

            showInfo : false,

        }
    },

    components : {
       
    },

    props : {
        card: Object,
    },

    methods : {
        aggiungiAlCarrello() {
           if (this.textButton== 'Compra') {
            this.textButton = 'Aggiunto (Rimuovi)'
           }  else {
            this.textButton = 'Compra'
           }
        }
    }
}
</script>

<template>
    <!-- contenitore dell'intera card -->
    <div class="card">
        <!-- contenitore dell'immagine  -->
        <div class="container-image-card">
            <!-- immagine della card da visualizzare interpolata tramite vue (:src) -->
            <img class="image-card" v-on:mouseleave="showInfo=false" :class="textButton == 'Aggiunto (Rimuovi)' ? 'border-yellow' : 'border-none'" :src="card.card_images[0].image_url" alt="'image-card' + {{ card.name }}">
            <!-- bottone compra e rimuovi dal carrello -->
            <button @click="aggiungiAlCarrello()" class="bottone-compra" :class="textButton == 'Aggiunto (Rimuovi)' ? 'yellow' : 'blue'">{{ textButton }} </button>
            <button @click="showInfo == false ? showInfo=true : showInfo = false" class="bottone-info">Info</button>
            
            <div v-show="showInfo" class="container-info">
                <div v-show="card.name">
                    <em class="id-info">Name:</em> <strong class="value name"> {{card.name}}</strong>                
                </div>
                <div v-show="card.type">
                    <em class="id-info">Type:</em> <strong class="value type"> {{card.type}}</strong>
                </div>
                <div v-show="card.race">
                    <em class="id-info">Race:</em> <strong class="value race"> {{card.race}}</strong>                
                </div>
                <div v-show="card.frameType">
                    <em class="id-info">Frame type:</em> <strong class="value race"> {{card.frameType}}</strong>                
                </div>
                <div v-show="card.atk">
                    <em class="id-info">Atk:</em> <strong class="value race"> {{card.atk}}</strong>                
                </div>
                <div v-show="card.def">
                    <em class="id-info">Def:</em> <strong class="value race"> {{card.def}}</strong>                
                </div>
                <div v-show="card.level">
                    <em class="id-info">Level:</em> <strong class="value race"> {{card.level}}</strong>                
                </div>
                <div v-show="card.archetype">
                    <em class="id-info">Archetype:</em> <strong class="value race"> {{card.archetype}}</strong>                
                </div>
                <div v-show="card.attribute">
                    <em class="id-info">Attribute:</em> <strong class="value race"> {{card.attribute}}</strong>                
                </div>
                <div v-show="card.card_sets">
                    <hr>
                    <hr>
                    <div>
                        <em class="id-info">Sets:</em> 
                    </div>
                    <div>
                        <p v-for="set in card.card_sets" class="value race"> -{{set.set_name}} </p>               
                    </div>
                </div>
            </div>
        </div>
            
        <div class="info-card">
            <!-- contenitore delle info della card -->
            <!-- contenitore dedicato al nome della carta -->
            <div class="contanier-name-card">
                <!-- qui visualizziamo il nome tramite 'baffi' vue  -->
                <em class="id-info">Name:</em> <strong class="value name"> {{card.name}}</strong>
            </div>
            <!-- contenitore dedicato al tipo di carta -->
            <div class="container-type-card">
                <!-- qui visualizziamo il tipo di carta tramite 'baffi' vue -->
                <em class="id-info">ID card:</em> <strong class="value type"> {{card.id}}</strong>
            </div>
            <!-- contenitore dedicato alla 'race' della carta -->
            <div class="container-race-card">
                <!-- qui visualizziamo la race della carta tramite 'baffi' vue -->
                <em class="id-info">Price:</em> <strong class="value race"> {{card.card_prices[0].ebay_price}} $</strong>
            </div>
        </div>
    </div>
</template>
            
<style scoped lang="scss">
    .card {
        display: flex;
        flex-direction: column;
        
        width: calc(100% / 5 - 20px / 5 * 4);
        
        transition: 2s;

        position: relative;

        &:hover{
            border-radius: 12px;
            background-color: rgb(0, 0, 0);
            scale: 150%;
            z-index: 2;
        }
        .container-image-card {
            position: relative;
            
            img {
                width: 100%;
                transition: 0.050s;
            }

            .bottone-compra {
                position: absolute;
                top: -21px;
                right: -1px;
                
                display: none;

                border-top-left-radius: 12px;
            }

            .bottone-info {
                position: absolute;
                top : -21px;
                left : 0px;

                border-top-right-radius: 12px;
                
                display: none;

                background-color: white;
                color: black;
            }

            .container-info {
                position: absolute;
                top: 0;
                left: 0;

                padding: 15px 20px;
                border-bottom-right-radius: 12px;

                font-size: 10px;



                color: white;
                background-color: rgba(103, 103, 103, 0.863);
            }
        }
        .info-card {
        padding: 5px;
            .id-info {
                font-size: 10px;
            }
            .value {
                font-size: 13px;
            }
        }  
    }

    .card:hover .bottone-compra,
    .card:hover .bottone-info{
        display: block;
    }
            
    .card:not(:hover) .container-info {
        display: none;
    }

    .yellow {
        background-color: rgba(255, 255, 0, 0.835);
        color: red;

    }

    .blue {
        background-color: rgba(0, 0, 255, 0.799);
        color: white;
    }

    .border-yellow {
        box-sizing: border-box;
        border: 3px solid yellow;
    }

    .border-none {
        box-sizing: border-box;
        border: 0px solid yellow;
    }


</style>