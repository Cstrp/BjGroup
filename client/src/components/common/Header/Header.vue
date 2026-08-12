<script lang="ts">
import { links } from '@/constants/';
import { RouterLink } from '@/enums';
import { useDisplay } from 'vuetify';

export default {
  computed: {
    RouterLink() {
      return RouterLink;
    },
  },
  data: () => {
    const display = useDisplay();
    return {
      links,
      display,
    };
  },
};
</script>

<template>
  <header class="header">
    <div class="header__container">
      <div class="header__items">
        <RouterLink :to="RouterLink.HOME">
          <div class="header__logo">
            <div class="header__title">Group</div>
          </div>
        </RouterLink>
        <ul class="header__menu" v-for="link of links" :key="link.name">
          <li class="header__point">
            <RouterLink class="header__link" :to="link.path">{{ link.name }}</RouterLink>
          </li>
        </ul>
        <v-btn
          v-if="display.mdAndUp"
          :to="RouterLink.CONTACT"
          class="header__button"
          elevation="0"
          style="
            width: 228px;
            height: 60px;
            padding: 16px 42px;
            text-transform: capitalize;
            background: #161719;
            border-radius: 14px;
            justify-content: center;
            align-items: center;
            gap: 10px;
            display: inline-flex;
          "
        >
          <span style="color: white; font-size: 22px; font-family: Poppins, serif; font-weight: 600">
            Contact now
          </span>
        </v-btn>
        <div class="burger">
          <input class="burger__checkbox" type="checkbox" id="check-menu" />
          <label class="burger__label" for="check-menu"></label>
          <div class="burger__line burger__line_1"></div>
          <div class="burger__line burger__line_2"></div>
          <div class="burger__line burger__line_3"></div>
          <div class="burger__line burger__line_4"></div>
          <nav class="burger__main-menu">
            <div class="burger__shell" v-for="link of links" :key="link.name">
              <RouterLink :to="link.path" class="burger__link">{{ link.name }}</RouterLink>
            </div>
          </nav>
        </div>
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped></style>
