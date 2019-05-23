<template>
    <div>
        <div class="key " :class="[color, note]" :id="note+id" >
            <p class="disable-select">{{ note }}</p>
        </div>
    </div>
</template>

<script>
    import {clickedBus} from "./../main";

    export default {
        props: {
            color: {
                type: String,
                required: true
            },
            note: {
                type: String,
                required: true
            },
            id: {
                type: Number,
                required: true
            }

        },

        data() {
            return {}
        },
        methods: {
            setClicked() {
                clickedBus.$emit('keyClicked',);

            }
        }
    }
</script>

<style scoped>
    .key {
        border: 1px dashed black;
        border-radius: 5px;
        padding: 10px;
        float: left;
        position: relative;
    }
    .key.black:hover,
    .key.white:hover{
        background-color: lightgreen;
        cursor: pointer;

    }
    .key.white{
        height: 12em;
        width: 3em;
        z-index: 1;
        background-color: white;
    }
    .key.black{
        height: 8em;
        width: 2em;
        margin: 0 0 0 -1em;
        z-index: 2;
        background-color: black;
    }
    p{
        margin-left: auto;
        margin-right: auto;
        text-align: center;
    }
    .b, .e, .g, .d, .a{
        margin: 0 0 0 -1em;
    }
    .disable-select{
        -webkit-touch-callout: none; /* iOS Safari */
        -webkit-user-select: none; /* Safari */
        -khtml-user-select: none; /* Konqueror HTML */
        -moz-user-select: none; /* Firefox */
        -ms-user-select: none; /* Internet Explorer/Edge */
        user-select: none; /* Non-prefixed version, currently
                                  supported by Chrome and Opera */
    }

</style>
