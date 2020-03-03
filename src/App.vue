<template>
  <div id='center'>
    <div id='color-block' v-bind:style="{ backgroundColor: input }"></div>

    <input id='input-field' type='text' autocomplete='off' placeholder='Enter some colors...' v-model='input' />
  </div>
</template>

<script>
export default {
  data() {
    return {
      input: ''
    }
  },

  methods: {
    changeColor: color => {
      const redConditions    = color == 'red'
      const blueConditions   = color == 'blue'
      const yellowConditions = color == 'yellow'
      const greenConditions  = color == 'green'
      const brownConditions  = color == 'brown'
      const orangeConditions = color == 'orange'

      const displayColor = 
          redConditions    ? 'red'
        : blueConditions   ? 'blue'
        : yellowConditions ? 'yellow'
        : greenConditions  ? 'green'
        : brownConditions  ? 'brown'
        : orangeConditions ? 'orange' 
        : ''

      switch(color) {
        case 'red':
          return 'red'
        case 'green':
          return 'green'
        case 'yellow':
          return 'yellow'
      }

      return displayColor
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#color-block {
    display: block;
    height: 10rem;
    width: 10rem;
    border: solid black;
}

#center {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

#input-field {
  margin-top: 1rem;
  height: 2rem;
  width: 10rem;
}
</style>
