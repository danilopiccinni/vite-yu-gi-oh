<script>


    export default {
        data() {
            return{
                showInfo : false
            } 
        },

        props : {
            card2 : Object,
        }
    }
</script>

<template>

<div v-show="showInfo" class="container-info">
                <div v-show="card2.name">
                    <em class="id-info">Name:</em> <strong class="value name"> {{card2.name}}</strong>                
                </div>
                <div v-show="card2.type">
                    <em class="id-info">Type:</em> <strong class="value type"> {{card2.type}}</strong>
                </div>
                <div v-show="card2.race">
                    <em class="id-info">Race:</em> <strong class="value race"> {{card2.race}}</strong>                
                </div>
                <div v-show="card2.frameType">
                    <em class="id-info">Frame type:</em> <strong class="value race"> {{card2.frameType}}</strong>                
                </div>
                <div v-show="card2.atk">
                    <em class="id-info">Atk:</em> <strong class="value race"> {{card2.atk}}</strong>                
                </div>
                <div v-show="card2.def">
                    <em class="id-info">Def:</em> <strong class="value race"> {{card2.def}}</strong>                
                </div>
                <div v-show="card2.level">
                    <em class="id-info">Level:</em> <strong class="value race"> {{card2.level}}</strong>                
                </div>
                <div v-show="card2.archetype">
                    <em class="id-info">Archetype:</em> <strong class="value race"> {{card2.archetype}}</strong>                
                </div>
                <div v-show="card2.attribute">
                    <em class="id-info">Attribute:</em> <strong class="value race"> {{card2.attribute}}</strong>                
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

</template>