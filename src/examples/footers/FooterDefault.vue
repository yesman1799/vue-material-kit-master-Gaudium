<template>
  <footer class="footer pt-5 mt-5">
    <div class="container">
      <div class="row">
        <div class="col-md-3 mb-4 ms-auto">
          <div>
            <br />
            <br />
            <h6 class="font-weight-bolder mb-4">{{ i18n.t('footer.companyName') }}</h6>
          </div>
        </div>
        <div
          class="col-md-2 col-sm-6 col-3 mb-4"
          v-for="{ name, items } of menus"
          :key="name"
        >
          <h6 class="text-sm">{{ i18n.t(name) }}</h6>
          <ul class="flex-column ms-n3 nav">
            <li class="nav-item" v-for="item of items" :key="item.name">
              <a class="nav-link" :href="item.href" target="_blank">
                {{ renderTranslatedText(item.name) }}
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

<script setup>
import { defineProps } from 'vue';
import { useI18n } from 'vue-i18n';

const i18n = useI18n();

defineProps({
  brand: {
    type: Object,
    default: () => ({
      name: "Gaudium 2022",
      route: "/",
    }),
  },
  menus: {
    type: Array,
    default: () => [
      {
        name: 'footer.location',
        items: [
          {
            name: 'footer.companyName',
          },
          {
            name: 'footer.address',
          },
          {
            name: 'footer.city',
          },
          { name: 'footer.country' },
        ],
      },
      {
        name: 'footer.contact',
        items: [
          {
            name: 'gaudium2022@seznam.cz',
            href: 'mailto:gaudium2022@seznam.cz',
          },
          {
            name: '+420777857773',
            href: 'tel:+420777857773',
          },
        ],
      },
    ],
  },
});

const renderTranslatedText = (key) => {
  return key.includes('email') || key.includes('phone')
    ? i18n.t(key).replace('{0}', `<span>${i18n.t(key, { value: '' })}</span>`)
    : i18n.t(key);
};
</script>