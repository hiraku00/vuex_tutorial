<template>
  <div class="home">
    <!-- <h1>{{ $store.state.counter }}</h1>
    <h2>{{ cartItemsCount }}</h2> -->
    <h1>vuex helper</h1>
    <p>{{ message }}</p>
    <p>{{ counter }}</p>
    <p>{{ cartItems }}</p>
    <p>{{ cartItemsCount }}</p>
    <button @click="increment(1)">mutation increment</button>
    <button @click="asyncIncrement(1)">action increment</button>
  </div>
</template>

<script>
import { mapState, mapMutations, mapGetters, mapActions } from 'vuex'
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
  },
  computed: {
    ...mapState({
      message: 'message',
      counter: 'counter',
      cartItems: 'cartItems',
    }),
    ...mapGetters([
      'cartItemsCount'
    ])
  },
  methods: {
    ...mapMutations([
      'increment'
    ]),
    ...mapActions({
      asyncIncrement: 'increment'
    })
    // increment() {
    //   this.$store.dispatch('increment', 10);
    // }
  }
}
</script>
