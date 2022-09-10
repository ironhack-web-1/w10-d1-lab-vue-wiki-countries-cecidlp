<template>
  <div class="row">
    <div class="col-5" style="max-height: 90vh; overflow: scroll">
      <div class="list-group">
        <router-link
          :to="`/details/${country.alpha3Code}`"
          v-for="country in countries"
          :key="country.name.common"
        >
          <a
            class="list-group-item list-group-item-action"
            :href="country.alpha3code"
          >
          <img
            :src="`https://flagpedia.net/data/flags/icon/72x54/${country.alpha2Code.toLowerCase()}.png`"
          />
          <p>{{ country.name.common }}</p>
        </a>
        </router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["countries"],
  computed: {},
};
</script>

<style></style>
