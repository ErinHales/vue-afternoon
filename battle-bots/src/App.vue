<template>
  <div>
    <div class='navBar'>
      <button class='navButton' @click="create">Create</button>
      <h1>Battle Bots</h1>
      <button class='navButton' @click="battle">Collection</button>
    </div>
    <div class='body'>
      <create v-if="creating" :newBot="newBot"/>
      <collection v-else :bots="bots" />
    </div>
  </div>
</template>

<script>
import Create from './components/create';
import Collection from './components/collection';
export default {
  data() {
    return {
      creating: true,
      bots: []
    };
  },
  methods: {
    newBot(name, attack, health) {
      if (name && attack && health) {
        this.bots.push({ name, attack, health });
        alert('Battle Bot successfully created!');
      }
    },
    create() {
      this.creating = true;
    },
    battle() {
      this.creating = false;
    }
  },
  components: {
    create: Create,
    collection: Collection
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Orbitron');
.navBar {
  display: flex;
  justify-content: space-around;
  background-color: #093969;
  color: white;
  height: 100px;
}
.navBar h1 {
  font-family: 'Orbitron', sans-serif;
}
.navButton {
  background-color: transparent;
  border: none;
  color: white;
}
.body {
  background-color: #61da97;
  height: calc(100vh - 100px);
  padding-top: 100px;
}
button {
  font-family: 'Orbitron', sans-serif;
  border-radius: 0px;
  padding: 10px;
  background-color: #f5f5f5;
  font-size: 15px;
  margin: 10px;
  width: 120px;
}
</style>
