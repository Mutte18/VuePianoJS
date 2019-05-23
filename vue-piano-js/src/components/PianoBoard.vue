<template>
    <div class="container alignDiv">
        <div class="row">
                <div class="col-sm-3" v-for="id in octaveNumber">
                    <app-piano-octave :id="getOctaveId(id)"></app-piano-octave>
                </div>
            </div>

        <!--
        For loop creating White and Black Keys components

        -->
    </div>
</template>

<script>
    import PianoOctave from './PianoOctave'
    export default {
        props: {},

        data() {
            return {
                pianoKeyOrder: ['c','cs','d','ds','e','f','fs','g','gs','a','as','b'],
                octaveNumber: 3
            }
        },
        methods: {
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
            getOctaveId(id){
                return id-2;
            }
        },
        computed: {

        },
        components: {
            'app-piano-octave': PianoOctave,
        }
    }
</script>

<style scoped>
.alignDiv{
    margin-left: 150px;
    margin-top: 100px;
}

</style>
