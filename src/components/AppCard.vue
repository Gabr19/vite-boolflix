<script>
export default {
    name: 'AppCard',
    prop: {
        movie: Object
    }
};
</script>

<template>


    card
    <div>
      <h3>
        {{ movie.title }}
      </h3>
      <h3>
        {{ movie.original_title }}
      </h3>
      <!-- <img :src="getFlag(movie.original_language)" alt=""> -->
      <h3>
        {{ movie.original_language }}
      </h3>
      <p>
        {{ movie.vote_average }}
      </p>
    </div>

</template>


<style lang="scss" scoped>

</style>