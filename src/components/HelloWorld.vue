<template>
  <div class="hello">
    <h1 v-for="item in characters.results" :key="item.id">{{ item.name }}</h1>
  </div>
</template>

<script>
import gql from 'graphql-tag'

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  apollo: {
    characters: gql`
    query getCaracters {
      characters {
        results {
          name
          species
        }
      }
      
      character(id: 5) {
        name
      }
    }
    `,
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
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
