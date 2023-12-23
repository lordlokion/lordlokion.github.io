<template>
  <div>
    <a :href="link">
      <div class="container mx-auto px-4">
        <div class="-mx-4 flex flex-wrap items-end">
          <div class="w-full px-4 xl:w-2/3">
            <div class="mx-auto max-w-2xl mt-8 xl:mr-0">
              <a class="group relative inline-block h-14 w-full rounded bg-white sm:w-44 md:w-56 lg:w-64" href="https://dev.to/lordlokion">
                <div class="absolute left-0 top-0 h-full w-full -translate-x-1 -translate-y-1 transform transition duration-300 group-hover:translate-x-0 group-hover:translate-y-0">
                  <div class="flex h-full w-full items-center justify-center rounded border-2 border-white bg-black">
                    <span class="text-base md:text-lg lg:text-xl font-semibold font-mono uppercase text-white">{{textinput}}</span>
                  </div>
                </div>
              </a>
            </div>
          </div>
        </div>
        <div></div>
      </div>
    </a>
  </div>
</template>

<script>
export default {
  name: "Sbut",
  props: {
    textinput: {
      type: String,
      required: true,
    },
    link: {
      type: String,
      required: true,
    },
  },
};
</script>
