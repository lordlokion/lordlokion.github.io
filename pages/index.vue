<template>
  <div class="bg-neutral-300 min-h-screen">
    <!-- Navbar -->
    <navbar>
      <div class="flex font-semibold text-3xl p-4 md:p-12"></div>
    </navbar>

    <!-- Content Section -->
    <div class="flex flex-col-reverse md:flex-row">
      <!-- Left Section (2/3 width) -->
      <div class="w-full md:w-2/3 p-4 md:p-12">
        <!-- Content -->
        <Type class="text-4xl md:text-6xl font-bold font-sans mb-4 md:mb-6" />

        <div class="bg-neutral-300 text-black p-4 md:p-8">
          <p class="text-lg md:text-2xl mb-4 md:mb-8">
            <span
              class="font-semibold bg-gradient-to-r from-red-300 via-red-100 to-neutral-300"
              >Full Stack Developer</span
            >
            with a strong foundation in both frontend and backend technologies,
            I specialize in creating robust, scalable, and efficient solutions
            for a diverse range of projects. Let's create something exceptional
            together!
          </p>
        </div>

        <!-- Buttons -->
        <div class="flex flex-wrap">
          <Sbrt textinput="Telegram" link="" />
          <Sbut textinput="Github" link="" />
          <Sbft textinput="LinkedIn" link="" />
        </div>
      </div>

      <!-- Right Section (1/3 width) -->
      <div class="w-full md:w-1/2 p-4 md:p-12">
        <!-- Placeholder Image -->
        <img
          src="../src/img.jpg"
          alt="Placeholder Image"
          class="w-full h-auto rounded-lg"
        />
      </div>
    </div>

    <Timeline />
    <Posts />
  </div>
</template>
