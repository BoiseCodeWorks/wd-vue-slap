<template>
  <div class="hello-world">
    <h1 :class="status()">{{target.name}}</h1>
    <p>{{target.health}}</p>
    <button @click="slap">Slap</button>
    <button @click="punch">Punch</button>
    <button @click="pet">Pet</button>
  </div>
</template>

<script>
  export default {
    name: 'hello-world',
    data() {
      return {
        target: {
          name: "Mister Snibbly",
          health: 100
        },
        attacks: {
          slap: 1,
          punch: 5,
          pet: 10
        }
      }
    },
    methods: {
      status() {
        let className = "green"
        if (this.target.health == 0) {
          className = "red"
        } else if (this.target.health <= 45) {
          className = "orange"
        } else if (this.target.health <= 75) {
          className = "yellow"
        }
        return className
      },
      pet() {
        this.target.health -= this.attacks.pet
        this.checkHealth()
      },
      slap() {
        this.target.health -= this.attacks.slap
        this.checkHealth()
      },
      punch() {
        this.target.
        health -= this.attacks.punch
        this.checkHealth()
      },
      checkHealth() {
        if (this.target.health < 0) {
          this.target.health = 0
        }
      }
    },
    components: {

    }
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .red {
    color: red;
  }

  .orange {
    color: orange;
  }

  .yellow {
    color: yellow;
  }

  .green {
    color: green;
  }

  h1,
  h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }

</style>
