<template>
  <div class="p-8">
    <div class="text-lg">
      <div
        class="
          flex
          md:flex-row md:space-x-12
          flex-col
          items-stretch
          md:justify-between
          justify-start
        "
      >
        <div class="py-2 w-full">
          <div
            class="
              p-2
              text-gray-700
              dark:text-white
              font-semibold
              border-gray-400 border-b-2
            "
          >
            Important Dates:
          </div>
          <div class="flex flex-col items-start w-full">
            <MiscArticle :news="article" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<!--<script>
export default {
  head() {
    return {
      title: "Important Dates",
      meta: [
        {
          hid: "title",
          name: "title",
          content: "Important Dates",
        },
        {
          hid: "og:title",
          name: "og:title",
          content: "Important Dates",
        },
      ],
    };
  },
  async asyncData({ $content }) {
    const article = await $content("dates").fetch();
    return {
      article,
    };
  },
};
</script>-->

<script setup lang="ts">
const { data: article} = await useAsyncData("home", () =>
  queryContent("dates").findOne()
);
useHead({
      title: "Important Dates",
      meta: [
        {
          hid: "title",
          name: "title",
          content: "Important Dates",
        },
        {
          hid: "og:title",
          name: "og:title",
          content: "Important Dates",
        },
      ],
    })
</script>
