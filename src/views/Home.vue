<template>
    <div class="home">
        <h1 v-if="user === 'marielle'">{{ halloWelt }}</h1>
        <h2 v-else>Du bist nicht marielle :(</h2>
        <label>
            <input type="text" v-model="user">
        </label>
        <br>
        <br>
        <button v-on:click="sagWas">
            Sag was!
        </button>
        <br>
        <p v-for="item in schleife" :key="item">
            {{item}}
        </p>

        <div v-bind:class="{ active : isActive }">
            Ich bin ein DIV mit einer reaktiven CSS-Klasse.
        </div>
    </div>
</template>

<script>
  export default {
    name: 'Home',
    data () {
      return {
        ausgabe: 'sali',
        user: 'marielle',
        schleife: [0, 1, 2, 3],
        isActive: false
      }
    },
    computed: {
      // ändert einen gegebenen Wert
      halloWelt () {
        return this.ausgabe + ' ' + this.user
      }
    },
    methods: {
      sagWas () {
        // Bindet nach dem klicken des Buttons die Klasse active mit dem Wert in data (false)
        // this.isActive = true
        this.isActive = !this.isActive
        console.log('Ich sag was!')
      }
    }
  }
</script>
<style lang="scss" scoped>
    .active {
        background-color: yellow;
    }
</style>
