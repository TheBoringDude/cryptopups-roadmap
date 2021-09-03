<template>
  <div
    class="
      w-full
      md:w-4/5
      lg:w-3/5
      bg-white
      py-4
      px-2
      my-12
      lg:my-6
      shadow-2xl
      rounded-xl
      border-warmGray-500
    "
    :class="index % 2 == 0 ? 'mr-auto border-r-8' : 'ml-auto border-l-8'"
  >
    <div class="p-4">
      <h3 class="font-black tracking-wide text-warmGray-700 text-3xl">
        {{ plan.month }} {{ plan.year }}
      </h3>
      <ul class="ml-5 mt-2">
        <li
          v-for="(e, idx) in plan.events"
          :key="idx"
          class="text-lg my-2 list-disc"
        >
          <strong v-if="e.date" class="text-warmGray-700"
            >({{ e.date }})</strong
          >
          {{ e.info }}
        </li>
      </ul>
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
