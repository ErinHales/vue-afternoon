<template>
    <form action="">
      <input type="text" placeholder="Bot Name" v-model='name'>
      <input type="text" placeholder="Attack Value" v-model='attack'>
      <input type="text" placeholder="Health" v-model='health'>
      <div className='buttonContainer'>
        <button @click.prevent='newBot(name, attack, health)'>Submit</button>
        <button @click.prevent='clear'>Clear</button>
      </div>
    </form>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      attack: null,
      health: null
    };
  },
  methods: {
    clear() {
      this.name = '';
      this.attack = null;
      this.health = null;
    }
  },
  props: ['newBot']
};
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Orbitron');
form {
  font-family: 'Orbitron', sans-serif;
  display: flex;
  flex-direction: column;
  width: 300px;
  background-color: white;
  padding: 20px;
  /* margin-top: 100px; */
  margin-left: calc(50% - 150px);
}
input {
  font-family: 'Orbitron', sans-serif;
  font-size: 20px;
  padding-top: 15px;
  padding-bottom: 15px;
  border: none;
  border-bottom: 1px solid lightgray;
}
.buttonContainer {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>