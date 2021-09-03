<template>
  <div
    :title="plan.done ? 'Done' : 'On-Going'"
    class="
      w-5/6
      mx-auto
      md:w-full
      flex flex-col-reverse
      items-center
      justify-center
      my-12
    "
    :class="index % 2 == 0 ? 'md:flex-row' : 'md:flex-row-reverse'"
  >
    <div
      class="w-full md:w-1/2 py-8 px-6 shadow-2xl border border-warmGray-200"
      :class="plan.done ? 'bg-warmGray-700' : 'bg-white'"
    >
      <h2
        class="font-black text-xl lg:text-2xl tracking-wide"
        :class="plan.done ? 'text-white' : 'text-gray-600'"
      >
        {{ plan.title }}
      </h2>
      <ul class="ml-5 mt-2">
        <li
          v-for="(e, idx) in plan.events"
          :key="idx"
          class="lg:text-lg my-2 list-disc"
          :class="plan.done ? 'text-gray-100' : 'text-gray-900'"
        >
          {{ e }}
        </li>
      </ul>
    </div>

    <div class="w-full md:w-1/2">
      <h3
        class="font-black px-8 text-5xl tracking-wide text-warmGray-700"
        :class="index % 2 == 0 ? 'md:text-left' : 'md:text-right'"
      >
        {{ plan.no }}
      </h3>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    plan: {
      type: Object,
      required: true,
    },
    index: {
      type: Number,
      required: true,
    },
  },
}
</script>
