<script setup>
defineProps({
  brand: {
    type: Object,
    name: String,
    logo: String,
    route: "",
    default: () => ({
      name: "Gaudium 2022",
      route: "/",
    }),
  },
  menus: {
    type: Array,
    name: String,
    items: {
      type: Array,
      name: String,
      href: String,
    },
    default: () => [
      {
        name: "Kde nás najdete",
        items: [
          {
            name: "Guadium 2022 s.r.o.",
          },
          {
            name: "tř. Budovatelů 2327/106",
          },
          {
            name: "Most",
          },
          { name: "Česká republika" },
        ],
      },
      {
        name: "Kontaktujte nás",
        items: [
          {
            name: "gaudium2022@seznam.cz",
          },
          {
            name: "+420 777 857 773",
          },
        ],
      },
    ],
  },
});
</script>
<template>
  <footer class="footer pt-5 mt-5">
    <div class="container">
      <div class="row">
        <div class="col-md-3 mb-4 ms-auto">
          <div>
            <br />
            <br />
            <h6 class="font-weight-bolder mb-4">{{ brand.name }}</h6>
          </div>
        </div>
        <div
          class="col-md-2 col-sm-6 col-3 mb-4"
          v-for="{ name, items } of menus"
          :key="name"
        >
          <h6 class="text-sm">{{ name }}</h6>
          <ul class="flex-column ms-n3 nav">
            <li class="nav-item" v-for="item of items" :key="item.name">
              <a class="nav-link" :href="item.href" target="_blank">
                {{ item.name }}
              </a>
            </li>
          </ul>
        </div>

        <div class="col-12">
          <div class="text-center">
            <p class="text-dark my-4 text-sm font-weight-normal">
              All rights reserved. Copyright ©
              {{ new Date().getFullYear() }}
              By
              <a href="#" target="_blank">noid1799</a>.
            </p>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>
