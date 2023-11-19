<!-- LanguageSwitcher.vue -->
<template>
  <div class="language-switcher">
    <img :src="currentFlag" :alt="currentLocale" @click="toggleDropdown" />
    <ul v-if="isDropdownVisible" class="language-dropdown">
      <li
        v-for="(flag, locale) in flags"
        :key="locale"
        @click="changeLanguage(locale)"
      >
        <img :src="flag" :alt="locale" />
      </li>
    </ul>
  </div>
</template>

<script>
import enFlag from "@/assets/img/flags/en.png";
import csFlag from "@/assets/img/flags/cz.png";
import uaFlag from "@/assets/img/flags/ua.png";

export default {
  data() {
    return {
      isDropdownVisible: false,
      flags: {
        en: enFlag,
        cs: csFlag,
        ua: uaFlag,
        // Add more flags as needed
      },
    };
  },
  computed: {
    currentLocale() {
      return this.$i18n.locale;
    },
    currentFlag() {
      return this.flags[this.currentLocale];
    },
  },
  methods: {
    toggleDropdown() {
      this.isDropdownVisible = !this.isDropdownVisible;
    },
    changeLanguage(locale) {
      this.$i18n.locale = locale;
      this.isDropdownVisible = false;
    },
  },
};
</script>

<style scoped>
.language-switcher {
  position: relative;
  cursor: pointer;
}

.language-dropdown {
  list-style: none;
  padding: 0;
  margin: 0;
  position: absolute;
  top: 100%;
  left: 0;
  background-color: #fff;
  border: 1px solid #ccc;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  z-index: 10;
}

.language-dropdown li {
  padding: 8px;
  cursor: pointer;
}

.language-dropdown img {
  max-width: 25px;
  margin-right: 8px;
}
.language-switcher img {
    max-width: 30px;
    left: 0;
    right: 0;
  }
</style>
