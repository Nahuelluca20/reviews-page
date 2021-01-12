<template>
  <section class="px-4 mt-10 bg-whitebg md:px-12 lg:px-8">
    <div class="mx-3 mb-8 md:mx-0 lg:mx-0">
      <h3 class="text-green3 font-roboto font-semibold text-xl my-3">
        Valoraciones del producto
      </h3>
      <p class="text-dark3">
        Aquí puedes consultar las últimas valoraciones que los usuarios han
        hecho sobre este producto.
      </p>
    </div>
    <div class="md:grid md:grid-cols-2 md:gap-4 mb-10 lg:grid lg:grid-cols-3">
      <Review
        v-for="post of posts"
        :key="post[+1]"
        :author="post.author"
        :comment="post.comment"
        :date="post.date"
        :useful_count="post.useful_count"
        :rating="post.rating"
      />
    </div>
  </section>
</template>

<script>
import axios from 'axios'
import Review from '../../components/Review'
export default {
  components: {
    Review,
  },
  data() {
    return {
      posts: [],
    }
  },
  async created() {
    const res = await axios.get('http://localhost:3000/api/valoraciones')
    this.posts = res.data.reviews
  },
}
</script>
