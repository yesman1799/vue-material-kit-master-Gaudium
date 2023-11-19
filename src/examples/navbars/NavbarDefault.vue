<script setup>
import { RouterLink } from "vue-router";
import { ref, watch } from "vue";
import { useWindowsWidth } from "../../assets/js/useWindowsWidth";

// images
import ArrDark from "@/assets/img/down-arrow-dark.svg";
// import downArrow from "@/assets/img/down-arrow.svg";
import DownArrWhite from "@/assets/img/down-arrow-white.svg";

const props = defineProps({
  action: {
    type: Object,
    route: String,
    color: String,
    default: () => ({
      route: "/",
      color: "bg-gradient-success",
      label: "nav.contact"
    })
  },
  transparent: {
    type: Boolean,
    default: false
  },
  light: {
    type: Boolean,
    default: false
  },
  dark: {
    type: Boolean,
    default: false
  },
  sticky: {
    type: Boolean,
    default: false
  },
  darkText: {
    type: Boolean,
    default: false
  }
});

// set arrow  color
function getArrowColor() {
  if (props.transparent && textDark.value) {
    return ArrDark;
  } else if (props.transparent) {
    return DownArrWhite;
  } else {
    return ArrDark;
  }
}

// set text color
const getTextColor = () => {
  let color;
  if (props.transparent && textDark.value) {
    color = "text-dark";
  } else if (props.transparent) {
    color = "text-white";
  } else {
    color = "text-dark";
  }

  return color;
};

// set nav color on mobile && desktop

let textDark = ref(props.darkText);
const { type } = useWindowsWidth();

if (type.value === "mobile") {
  textDark.value = true;
} else if (type.value === "desktop" && textDark.value == false) {
  textDark.value = false;
}

watch(
  () => type.value,
  (newValue) => {
    if (newValue === "mobile") {
      textDark.value = true;
    } else {
      textDark.value = false;
    }
  }
);
</script>
<template>
  <nav
    class="navbar navbar-expand-lg top-0"
    :class="{
      'z-index-3 w-100 shadow-none navbar-transparent position-absolute my-3':
        props.transparent,
      'my-3 blur border-radius-lg z-index-3 py-2 shadow py-2 start-0 end-0 mx-4 position-absolute mt-4':
        props.sticky,
      'navbar-light bg-white py-3': props.light,
      ' navbar-dark bg-gradient-dark z-index-3 py-3': props.dark
    }"
  >
    <div
      :class="
        props.transparent || props.light || props.dark
          ? 'container'
          : 'container-fluid px-0'
      "
    >
      <RouterLink
        class="navbar-brand d-none d-md-block"
        :class="[
          (props.transparent && textDark.value) || !props.transparent
            ? 'text-dark font-weight-bolder ms-sm-3'
            : 'text-white font-weight-bolder ms-sm-3'
        ]"
        :to="{ name: 'presentation' }"
        rel="tooltip"
        title="Designed and Coded by Creative Tim"
        data-placement="bottom"
      >
        Guadium 2022
      </RouterLink>
      <div
        class="collapse navbar-collapse w-100 pt-3 pb-2 py-lg-0"
        id="navigation"
      >
        <ul class="navbar-nav navbar-nav-hover ms-auto">
          <li class="nav-item dropdown dropdown-hover mx-2">
            <a
              role="button"
              class="nav-link ps-2 d-flex cursor-pointer align-items-center"
              :class="getTextColor()"
              id="dropdownMenuPages"
              data-bs-toggle="dropdown"
              aria-expanded="false"
            >
              <i
                class="material-icons opacity-6 me-2 text-md"
                :class="getTextColor()"
                >dashboard</i
              >
              {{ $t('nav.slides') }}
              <img
                :src="getArrowColor()"
                alt="down-arrow"
                class="arrow ms-2 d-lg-block d-none"
              />
              <img
                :src="getArrowColor()"
                alt="down-arrow"
                class="arrow ms-1 d-lg-none d-block ms-auto"
              />
            </a>
            <div
              class="dropdown-menu dropdown-menu-animation ms-n3 dropdown-md p-3 border-radius-xl mt-0 mt-lg-3"
              aria-labelledby="dropdownMenuPages"
            >
              <div class="row d-none d-lg-block">
                <div class="col-12 px-4 py-2">
                  <div class="row">
                    <div class="position-relative">
                      <div
                        class="dropdown-header text-dark font-weight-bolder d-flex align-items-center px-1"
                      >
                        {{ $t('nav.options') }}
                      </div>
                      <RouterLink
                        :to="{ name: 'about' }"
                        class="dropdown-item border-radius-md"
                      >
                        <span>{{ $t('nav.about') }}</span>
                      </RouterLink>
                      <!-- <RouterLink
                        :to="{ name: 'author' }"
                        class="dropdown-item border-radius-md"
                      >
                        <span>Naše produkty</span>
                      </RouterLink> -->
                    </div>
                  </div>
                </div>
              </div>
              <div class="d-lg-none">
                <div
                  class="dropdown-header text-dark font-weight-bolder d-flex align-items-center px-0"
                >
                {{ $t('nav.options')}}
                </div>
                <RouterLink
                  :to="{ name: 'about' }"
                  class="dropdown-item border-radius-md"
                >
                  <span>{{ $t('nav.options') }}</span>
                </RouterLink>
                <RouterLink
                  :to="{ name: 'author' }"
                  class="dropdown-item border-radius-md"
                >
                  <span>Naše produkty</span>
                </RouterLink>
              </div>
            </div>
          </li>
          <!-- <li class="nav-item dropdown dropdown-hover mx-2">
            <a
              role="button"
              class="nav-link ps-2 d-flex cursor-pointer align-items-center"
              :class="getTextColor()"
              id="dropdownMenuBlocks"
              data-bs-toggle="dropdown"
              aria-expanded="false"
            >
              <i
                class="material-icons opacity-6 me-2 text-md"
                :class="getTextColor()"
                >view_day</i
              >
              Produkty
              <img
                :src="getArrowColor()"
                alt="down-arrow"
                class="arrow ms-2 d-lg-block d-none"
              />
              <img
                :src="getArrowColor()"
                alt="down-arrow"
                class="arrow ms-1 d-lg-none d-block ms-auto"
              />
            </a>
            <div
              class="dropdown-menu dropdown-menu-end dropdown-menu-animation dropdown-md dropdown-md-responsive p-3 border-radius-lg mt-0 mt-lg-3"
              aria-labelledby="dropdownMenuBlocks"
            >
              <div class="d-none d-lg-block">
                <ul class="list-group">
                  <li
                    class="nav-item dropdown dropdown-hover dropdown-subitem list-group-item border-0 p-0"
                  >
                    <a
                      class="dropdown-item py-2 ps-3 border-radius-md"
                      href="javascript:;"
                    >
                      <div class="d-flex">
                        <div
                          class="w-100 d-flex align-items-center justify-content-between"
                        >
                          <div>
                            <h6
                              class="dropdown-header text-dark font-weight-bolder d-flex justify-content-cente align-items-center p-0"
                            >
                              Druh(na kuzi)
                            </h6>
                            <span class="text-sm">See all sections</span>
                          </div>
                          <img
                            :src="downArrow"
                            alt="down-arrow"
                            class="arrow"
                          />
                        </div>
                      </div>
                    </a>
                    <div class="dropdown-menu mt-0 py-3 px-2 mt-3">
                      <RouterLink
                        class="dropdown-item ps-3 border-radius-md mb-1"
                        :to="{ name: 'author' }"
                      >
                        Produkt1
                      </RouterLink>
                    </div>
                  </li>
                  <li
                    class="nav-item dropdown dropdown-hover dropdown-subitem list-group-item border-0 p-0"
                  >
                    <a
                      class="dropdown-item py-2 ps-3 border-radius-md"
                      href="javascript:;"
                    >
                      <div class="d-flex">
                        <div
                          class="w-100 d-flex align-items-center justify-content-between"
                        >
                          <div>
                            <h6
                              class="dropdown-header text-dark font-weight-bolder d-flex justify-content-cente align-items-center p-0"
                            >
                              Druh 2
                            </h6>
                            <span class="text-sm">Vidět vše</span>
                          </div>
                          <img
                            :src="downArrow"
                            alt="down-arrow"
                            class="arrow"
                          />
                        </div>
                      </div>
                    </a>
                    <div class="dropdown-menu mt-0 py-3 px-2 mt-3">
                      <RouterLink
                        class="dropdown-item ps-3 border-radius-md mb-1"
                        :to="{ name: 'author' }"
                      >
                        Produkt 2
                      </RouterLink>
                    </div>
                  </li>
                  <li
                    class="nav-item dropdown dropdown-hover dropdown-subitem list-group-item border-0 p-0"
                  >
                    <a
                      class="dropdown-item py-2 ps-3 border-radius-md"
                      href="javascript:;"
                    >
                      <div class="d-flex">
                        <div
                          class="w-100 d-flex align-items-center justify-content-between"
                        >
                          <div>
                            <h6
                              class="dropdown-header text-dark font-weight-bolder d-flex justify-content-cente align-items-center p-0"
                            >
                              Druh
                            </h6>
                            <span class="text-sm">See all input areas</span>
                          </div>
                          <img
                            :src="downArrow"
                            alt="down-arrow"
                            class="arrow"
                          />
                        </div>
                      </div>
                    </a>
                    <div class="dropdown-menu mt-0 py-3 px-2 mt-3">
                      <RouterLink
                        class="dropdown-item ps-3 border-radius-md mb-1"
                        :to="{ name: 'author' }"
                      >
                        Produkt3
                      </RouterLink>
                    </div>
                  </li>
                  <li
                    class="nav-item dropdown dropdown-hover dropdown-subitem list-group-item border-0 p-0"
                  >
                    <a
                      class="dropdown-item py-2 ps-3 border-radius-md"
                      href="javascript:;"
                    >
                      <div class="d-flex">
                        <div
                          class="w-100 d-flex align-items-center justify-content-between"
                        >
                          <div>
                            <h6
                              class="dropdown-header text-dark font-weight-bolder d-flex justify-content-cente align-items-center p-0"
                            >
                              Druh
                            </h6>
                            <span class="text-sm">See all examples</span>
                          </div>
                          <img
                            :src="downArrow"
                            alt="down-arrow"
                            class="arrow"
                          />
                        </div>
                      </div>
                    </a>
                    <div class="dropdown-menu mt-0 py-3 px-2 mt-3">
                      <RouterLink
                        class="dropdown-item ps-3 border-radius-md mb-1"
                        :to="{ name: 'author' }"
                      >
                        Produkt4
                      </RouterLink>
                    </div>
                  </li>
                  <li
                    class="nav-item dropdown dropdown-hover dropdown-subitem list-group-item border-0 p-0"
                  >
                    <a
                      class="dropdown-item py-2 ps-3 border-radius-md"
                      href="javascript:;"
                    >
                      <div class="d-flex">
                        <div
                          class="w-100 d-flex align-items-center justify-content-between"
                        >
                          <div>
                            <h6
                              class="dropdown-header text-dark font-weight-bolder d-flex justify-content-cente align-items-center p-0"
                            >
                              Druh
                            </h6>
                            <span class="text-sm">See all elements</span>
                          </div>
                          <img
                            :src="downArrow"
                            alt="down-arrow"
                            class="arrow"
                          />
                        </div>
                      </div>
                    </a>
                    <div class="dropdown-menu mt-0 py-3 px-2 mt-3">
                      <RouterLink
                        class="dropdown-item ps-3 border-radius-md mb-1"
                        :to="{ name: 'author' }"
                      >
                        Produkt 5
                      </RouterLink>
                    </div>
                  </li>
                </ul>
              </div>
            </div>
          </li> -->
        </ul>
        <ul class="navbar-nav d-lg-block d-none">
          <li class="nav-item">
            <a
              :href="action.route"
              class="btn btn-sm mb-0"
              :class="action.color"
              onclick="smoothToPricing('pricing-soft-ui')"
              >{{ $t('nav.contact') }}</a
            >
          </li>
        </ul>
      </div>
    </div>
  </nav>
  <!-- End Navbar -->
</template>
