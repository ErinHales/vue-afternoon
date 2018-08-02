<template>
    <div>
        <div class="battleContainer">
            <h3>Bot #1: {{battlingBots[0] ? battlingBots[0].name : 'Select a bot below'}}</h3>
            <h3>Bot #2: {{battlingBots[1] ? battlingBots[1].name : 'Select a bot below'}}</h3>
            <div>
                <button @click='battle'>Battle</button>
                <button @click='clearBots'>Clear</button>
            </div>
        </div>
        <hr>
        <div class='displayBots'>
            <bot v-for='(robot, i) in bots' :key='i' :robot='robot' :addBot='addBot' />
        </div>
    </div>
</template>

<script>
import bot from './bot';
export default {
  data() {
    return {
      battlingBots: []
    };
  },
  props: ['bots'],
  components: {
    bot: bot
  },
  methods: {
    addBot(robot) {
      this.battlingBots.push(robot);
    },
    clearBots() {
      this.battlingBots = [];
    },
    battle() {
      let bot1 = this.battlingBots[0];
      let bot2 = this.battlingBots[1];
      if (this.battlingBots[1]) {
        if (bot1.health + bot1.attack > bot2.health + bot2.attack) {
          alert(`${bot1.name} won!`);
        } else if (bot1.health + bot1.attack < bot2.health + bot2.attack) {
          alert(`${bot2.name} won!`);
        } else {
          alert(`${bot1.name} and ${bot2.name} tied!`);
        }
        this.battlingBots = [];
      }
    }
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Orbitron');
h3 {
  font-family: 'Orbitron', sans-serif;
}
.battleContainer {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: -80px;
}
.displayBots {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  margin-top: 50px;
}
</style>