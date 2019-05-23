<template>
    <div class="container">

            <div v-for="note in pianoKeyOrder">
                <app-piano-key @click.native="test($event)" :note="note" :id="id" :color="getColor(note)"></app-piano-key>
            </div>


        <!--
        For loop creating White and Black Keys components

        -->
    </div>
</template>

<script>
    import PianoKey from './PianoKey'

    export default {
        props: {
            id: {
                type: Number,
                required: true
            }
        },

        data() {
            return {
                pianoKeyOrder: ['c','cs','d','ds','e','f','fs','g','gs','a','as','b']
            }
        },
        methods: {
            test(event){
                console.log(event);
            },
            getColor(note){
                const whiteKeys = ['c','d','e','f','g','a','b'];
                const blackKeys = ['cs','ds','fs','gs','as'];
                if(whiteKeys.includes(note)){
                    return 'white';
                }
                else if(blackKeys.includes(note)){
                    return 'black';
                }
                else{
                    return null;
                }
            },
            getNote(note){
                return note+this.id.toString();
            }
        },
        computed: {

        },
        components: {
            'app-piano-key': PianoKey,
        }
    }
</script>

<style>


</style>
