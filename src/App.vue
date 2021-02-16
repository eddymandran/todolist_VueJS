<template>
<div>
  <carousel>
    <carousel-slide>
      Salut les gens
      <img src="https://picsum.photos/630/300?random=1">
    </carousel-slide>
    <carousel-slide>
      Au revoir les gens
      <img src="https://picsum.photos/630/300?random=2">
    </carousel-slide>
  </carousel>
  <todos v-model="todos"></todos>
</div>
</template>

<script>
import Todos from './components/Todos'
import Carousel from '@/components/carousel/Carousel'
import CarouselSlide from '@/components/carousel/CarouselSlide'

export default {
  data () {
    return {
      todos: [{
        name: 'Demo',
        completed: true
      }]
    }
  },
  methods: {
    addTodo () {
      this.todos.push({
        name: 'Jean',
        completed: false
      })
    }
  },
  components: {
    Todos,
    Carousel,
    CarouselSlide
  }
}
</script>
