<template>
    <div class="bot">
        <div class="botInfo">
            <h1>{{robot.name}}</h1>
            <h3>Attack: {{robot.attack}}</h3>
            <h3>Health: {{robot.health}}</h3>
        </div>
        <div>
            <button @click='addBot(robot)'>Select</button>
            <button>Retire</button>
        </div>
    </div>
</template>

<script>
export default {
  props: ['robot', 'addBot']
};
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Orbitron');
.bot {
  font-family: 'Orbitron', sans-serif;
  background-color: #f5f5f5;
  width: 300px;
  height: 300px;
  padding: 20px;
}
.bot h1 {
  padding: 20px;
}
.botInfo {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>