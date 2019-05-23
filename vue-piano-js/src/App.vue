<template>
  <div>
    <app-piano-board></app-piano-board>

  </div>
</template>

<script>
  import PianoBoard from './components/PianoBoard';

  export default {
  data () {
    return {
      keyColor: 'white'
    }
  },
  methods: {
    isClicked(){
      this.$emit('isClicked', 'black');
    }
  },
  components: {
    'app-piano-board': PianoBoard
  }
}
</script>

<style>

</style>
