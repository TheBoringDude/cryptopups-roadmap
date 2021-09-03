<template>
  <div>
    <Header />

    <div class="py-20 w-11/12 mx-auto timeline">
      <RoadContainer
        v-for="(pl, index) in plans.plans"
        :key="index"
        :plan="pl"
        :index="index"
      />
    </div>

    <Footer />
  </div>
</template>

<script>
const title = 'Roadmap'
const description =
  "Follow World of Cryptopups's plans, goals, and solutions for the future. To the moon!"
const image = 'https://roadmap.worldofcryptopups.cf/featured-white.png'

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
    // https://nuxtjs.org/examples/seo-twitter-og
    return {
      title,
      meta: [
        {
          hid: 'twitter:title',
          name: 'twitter:title',
          content: title,
        },
        {
          hid: 'twitter:description',
          name: 'twitter:description',
          content: description,
        },
        {
          hid: 'twitter:image',
          name: 'twitter:image',
          content: image,
        },
        {
          hid: 'twitter:image:alt',
          name: 'twitter:image:alt',
          content: title,
        },
        {
          hid: 'og:title',
          property: 'og:title',
          content: title,
        },
        {
          hid: 'og:description',
          property: 'og:description',
          content: description,
        },
        {
          hid: 'og:image',
          property: 'og:image',
          content: image,
        },
        {
          hid: 'og:image:secure_url',
          property: 'og:image:secure_url',
          content: image,
        },
        {
          hid: 'og:image:alt',
          property: 'og:image:alt',
          content: title,
        },
      ],
    }
  },
}
</script>
