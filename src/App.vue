<template>
  <div id="app">
    <div class="bg-white dark:bg-gray-800">
      <div>
        <h2 class="text-3xl font-bold text-gray-800 dark:text-gray-100">Our Pricing</h2>
        <div class="flex justify-evenly aligned-center">
          <p class="mt-4 text-gray-500 dark:text-gray-400">Monthly</p>
          <label for="toggleB" class="flex items-center cursor-pointer">
            <!-- toggle -->
            <div class="relative">
              <!-- input -->
              <input type="checkbox" id="toggleB" @click="change" v-bind:value="def"  class="sr-only" />
              <!-- line -->
              <div class="block bg-gray-600 w-14 h-8 rounded-full"></div>
              <!-- dot -->
              <div class="dot absolute left-1 top-1 bg-white w-6 h-6 rounded-full transition"></div>
            </div>
            <!-- label -->
          </label>
          <p class="mt-4 text-gray-500 dark:text-gray-400">Annually</p>
        </div>
      </div>
      <div class="container px-6 py-8 mx-auto">
        <div
          class="flex flex-col items-center card justify-center space-y-8 lg:-mx-4 lg:flex-row lg:items-stretch lg:space-y-0"
        >
          <div
            class="flex flex-col w-full max-w-sm p-8 space-y-8 text-center bg-white border-2 border-gray-200 rounded-lg lg:mx-4 dark:bg-gray-800 dark:border-gray-700"
          >
            <div class="flex-shrink-0">
              <h2
                class="inline-flex items-center justify-center px-2 font-semibold tracking-tight text-blue-400 uppercase rounded-lg bg-gray-50 dark:bg-gray-700"
              >Basic</h2>
            </div>
            <div class="flex-shrink-0">
              <span
                class="pt-2 text-4xl font-bold text-gray-800 uppercase dark:text-gray-100"
              >{{ packe }}</span>
            </div>
            <ul class="flex-1 space-y-4">
              <li class="text-gray-500 dark:text-gray-400">500 GB Storage</li>
              <li class="text-gray-500 dark:text-gray-400">2 Users Allowed</li>
              <li class="text-gray-500 dark:text-gray-400">Send up to 3 GB</li>
            </ul>

            <button
              class="inline-flex items-center justify-center px-4 py-2 font-semibold text-blue-500 uppercase transition-colors rounded-lg focus:outline-none"
            >Learn More</button>
          </div>

          <div
            class="flex flex-col w-full max-w-sm p-8 space-y-8 text-center bg-white border-2 border-gray-200 rounded-lg lg:mx-4 dark:bg-gray-800 dark:border-gray-700"
          >
            <div class="flex-shrink-0">
              <h2
                class="inline-flex items-center justify-center px-2 font-semibold tracking-tight text-blue-400 uppercase rounded-lg bg-gray-50 dark:bg-gray-700"
              >Professional</h2>
            </div>
            <div class="flex-shrink-0">
              <span
                class="pt-2 text-4xl font-bold text-gray-800 uppercase dark:text-gray-100"
              >{{ professional }}</span>
              <!-- <span class="text-gray-500 dark:text-gray-400">
                            1 TB Storage
              </span>-->
            </div>
            <ul class="flex-1 space-y-4">
              <li class="text-gray-500 dark:text-gray-400">1 TB Storage</li>
              <li class="text-gray-500 dark:text-gray-400">5 Users Allowed</li>
              <li class="text-gray-500 dark:text-gray-400">Send up to 10 GB</li>
              <!-- <li class="text-gray-500 dark:text-gray-400">
                        Learn More
              </li>-->
            </ul>

            <button
              class="inline-flex items-center justify-center px-4 py-2 font-semibold text-blue-500 uppercase transition-colors rounded-lg hover:bg-blue-500 focus:outline-none"
            >Learn More</button>
          </div>

          <div
            class="flex flex-col w-full max-w-sm p-8 space-y-8 text-center bg-white border-2 border-gray-200 rounded-lg lg:mx-4 dark:bg-gray-800 dark:border-gray-700"
          >
            <div class="flex-shrink-0">
              <h2
                class="inline-flex items-center justify-center px-2 font-semibold tracking-tight text-blue-400 uppercase rounded-lg bg-gray-50 dark:bg-gray-700"
              >Master</h2>
            </div>
            <div class="flex-shrink-0">
              <span
                class="pt-2 text-4xl font-bold text-gray-800 uppercase dark:text-gray-100"
              >{{ master }}</span>
              <!-- <span class="text-gray-500 dark:text-gray-400">
                            /month
              </span>-->
            </div>
            <ul class="flex-1 space-y-4">
              <li class="dark:text-gray-400">2 TB Storage</li>
              <li class="dark:text-gray-400">10 Users Allowed</li>
              <li class="dark:text-gray-400">Send up to 20 GB</li>
              <!-- <li class=" dark:text-gray-400">
                            Real-time collaborations
                        </li>
                        <li class="text-gray-500 dark:text-gray-400">
                            24x7 Support
              </li>-->
            </ul>

            <button
              class="inline-flex items-center justify-center px-4 py-2 font-semibold text-blue-500 uppercase transition-color rounded-blue solid rounded-lg hover:bg-blue-700 focus:outline-none"
            >Learn More</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      packe: "$19.99",
      professional: "$24.99",
      master: "$39.99",
      def: false,
    };
  },

  methods: {
    change() {
      this.def = !this.def;
    this.annuel();
    },
    annuel() {
      if (this.def == false) {
        this.packe = "$19.99";
        this.professional = "$24.99";
      this.master = "$39.99";
      }
      else {
        this.packe = "$199.99",
          this.professional = "$249.99",
          this.master = "$399.99"
      }
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
input:checked ~ .dot {
  transform: translateX(100%);
  background-color: blueviolet;
}
</style>
