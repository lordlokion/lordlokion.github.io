<!-- Timeline.vue -->
<template>
  <section class="dark:bg-neutral-300 dark:text-gray-100">
    <div class="container max-w-5xl px-4 py-12 mx-auto">
      <div class="grid gap-4 mx-4 sm:grid-cols-12">
        <div class="col-span-12 sm:col-span-3">
          <div class="text-center sm:text-left mb-14 before:block before:w-24 before:h-3 before:mb-5 before:rounded-md before:mx-auto sm:before:mx-0 before:dark:bg-gray-400">
            <h3 class="text-3xl font-semibold text-gray-900">My Journey</h3>
            <span class="text-sm font-bold tracking-wider uppercase dark:text-gray-600">2018 - 2023</span>
          </div>
        </div>
        <div class="relative col-span-12 px-4 space-y-6 sm:col-span-9">
          <div class="col-span-12 space-y-12 relative px-4 sm:col-span-8 sm:space-y-8 sm:before:absolute sm:before:top-2 sm:before:bottom-0 sm:before:w-0.5 sm:before:-left-3 before:dark:bg-gray-700">
            <div v-for="(item, index) in timelineData" :key="index" class="flex flex-col sm:relative sm:before:absolute sm:before:top-2 sm:before:w-4 sm:before:h-4 sm:before:rounded-full sm:before:left-[-35px] sm:before:z-[1] before:dark:bg-black">
              <h3 class="text-xl font-semibold text-black tracking-wider">{{ item.title }}</h3>
              <time class="text-xs tracking-wider uppercase dark:text-gray-700">{{ item.date }}</time>
              <p class="mt-3 text-gray-600">{{ item.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      timelineData: [
        {
          title: "First Internship - GeeksforGeeks",
          date: "June 2018",
          description: "Secured a technical content writer internship at GeeksforGeeks, contributing to articles that garnered over 1 million monthly views. Recognized as the 'Best Writer of the Month.'",
        },
        {
          title: "First Job - CoolPlugins",
          date: "January 2020",
          description: "Embarked on my journey as a Vue.js developer at CoolPlugins, gaining hands-on experience in front-end development and Vue.js.",
        },
        {
          title: "Full-Stack Developer - TutorialsPoint",
          date: "August 2021",
          description: "Joined TutorialsPoint as a full-stack developer, honing my skills across the entire development stack. Contributed to the development of various projects.",
        },
        {
          title: "Freelancing Success",
          date: "October 2022",
          description: "Ventured into freelancing, collaborating with multiple clients on diverse projects. Established a team of 4 professionals, successfully completing numerous freelance assignments.",
        },
        {
          title: "Team Manager",
          date: "September 2023",
          description: "Elevated to the role of Team Manager, leading a dynamic team and overseeing successful project deliveries. Skills: Full-Stack Developer, Vue.js, TailwindCSS, Team Management.",
        },
      ],
    };
  },
};
</script>
