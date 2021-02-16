<template>
<div>
  <carousel>
    <carousel-slide>
      <div style="position:absolute; left:0; right:0; text-align:center; top:50%; color:#FFF; font-size:16px;">Salut les gens</div>
      <img src="https://picsum.photos/630/300?random=1" width="100%">
    </carousel-slide>
    <carousel-slide>
      <div style="position:absolute; left:0; right:0; text-align:center; top:50%; color:#FFF; font-size:16px;">Au revoir les gens</div>
      <img src="https://picsum.photos/630/300?random=2" width="100%">
    </carousel-slide>
  </carousel>
  <br/>
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
