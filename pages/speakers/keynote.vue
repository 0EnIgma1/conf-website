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
            Keynote Speakers:
          </div>
          <div class="flex flex-col items-start w-full">
            <MiscPerson
              :news="article"
              v-for="article in articles"
              :key="article.title"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<script setup lang="ts">
const { data: articles } = await useAsyncData("home", () =>
  queryContent("speakers", "keynote").find()
);
useHead({
      title: "Keynote Speakers",
      meta: [
        { hid: "title", name: "title", content: "Keynote Speakers" },
        { hid: "og:title", name: "og:title", content: "Keynote Speakers" },
      ],
    })
</script>

