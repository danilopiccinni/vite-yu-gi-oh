<script>
import { store } from '../store';

export default {
    data() { 
        return {
            store,
        }
    },

    props : {
        card: Object,
    }
}
</script>

<template>
    <!-- contenitore dell'intera card -->
    <div class="card">
        <!-- contenitore dell'immagine  -->
        <div class="container-image-card">
            <!-- immagine della card da visualizzare interpolata tramite vue (:src) -->
            <img class="image-card" :src="card.card_images[0].image_url" alt="'image-card' + {{ card.name }}">
        </div>

        <!-- contenitore delle info della card -->
        <div class="info-card">
            <!-- contenitore dedicato al nome della carta -->
            <div class="contanier-name-card">
                <!-- qui visualizziamo il nome tramite 'baffi' vue  -->
                <em class="id-info">Name:</em> <strong class="value name"> {{card.name}}</strong>
            </div>
            <!-- contenitore dedicato al tipo di carta -->
            <div class="container-type-card">
                <!-- qui visualizziamo il tipo di carta tramite 'baffi' vue -->
                <em class="id-info">Type:</em> <strong class="value type"> {{card.type}}</strong>
            </div>
            <!-- contenitore dedicato alla 'race' della carta -->
            <div class="container-race-card">
                <!-- qui visualizziamo la race della carta tramite 'baffi' vue -->
                <em class="id-info">Race:</em> <strong class="value race"> {{card.race}}</strong>
            </div>
        </div>
    </div>

</template>

<style scoped lang="scss">


    .card {
        display: flex;
        flex-direction: column;
        
        width: calc(100% / 5 - 20px / 5 * 4);
        
        transition: 1s;

        &:hover {
            border-radius: 12px;
            background-color: rgb(0, 0, 0);
            scale: 150%;
            z-index: 1;
        }
        img {
            width: 100%;
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


</style>