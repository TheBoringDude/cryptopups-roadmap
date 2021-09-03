<template>
  <div>
    <Header />

    <div class="py-20 w-11/12 mx-auto">
      <RoadContainer
        v-for="(pl, index) in plans"
        :key="index"
        :plan="pl"
        :index="index"
      />
    </div>

    <Footer />
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const plans = await $content('roadmap')
      .fetch()
      .catch((err) => {
        console.error(err)
      })

    return {
      plans,
    }
  },

  head() {
    return {
      title: 'Roadmap | World of Cryptopups',
    }
  },
}
</script>
