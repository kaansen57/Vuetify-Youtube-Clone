<template>
  <v-bottom-navigation
    value="1"
    horizontal
    fixed
    v-show="searchButton"
    height="60"
  >
    <v-form>
      <v-container>
        <v-text-field
          placeholder="Ara"
          outlined
          dense
          class="float-left col-8 "
        >
        </v-text-field>

        <v-btn
          @click="loadingButton()"
          class="float-left mt-2"
          :loading="loading"
          icon
          small
        >
          <v-icon v-text="'mdi-movie-search'"></v-icon>
        </v-btn>
      </v-container>
    </v-form>
    <v-avatar
      @click="emitSearchButton()"
      role="button"
      class="float-right col-1"
    >
      <v-icon v-text="'mdi-close-circle'"></v-icon>
    </v-avatar>
  </v-bottom-navigation>
</template>

<script>
import { eventBus } from "../main";
export default {
  data: () => ({
    loading: false,
    searchButton: false,
  }),
  methods: {
    emitSearchButton() {
      this.searchButton = false;
      eventBus.$emit("searchButton", this.searchButton);
    },
    loadingButton() {
      this.loading = true;
      setTimeout(() => {
        this.loading = false;
        this.emitSearchButton();
      }, 2000);
    },
  },
  created() {
    eventBus.$on("searchButton", (searchBtnEvent) => {
      this.searchButton = searchBtnEvent;
    });
  },
};
</script>

<style></style>
