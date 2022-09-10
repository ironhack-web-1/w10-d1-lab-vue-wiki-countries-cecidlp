<template>
  <div class="col-7">
    <div>Detalles de pais</div>
    <div>{{ this.$route.params.id }}</div>
    <div>{{ countryDetails.name }}</div>
  </div>
</template>

<script>
    const countryURL="https://ih-countries-api.herokuapp.com/countries/"
export default {
    data() {
        return {
            countryDetails: {}
        }
        },
    methods: {
        async fetchCountry() {
        const countryParam = this.$route.params
        const res = await fetch(countryURL + countryParam.id)
        const result = await res.json()
        this.countryDetails = result
        
       },

       },
    mounted () {
        try {
            this.fetchCountry()
        } catch(error) {
                console.log(error)
            }
    },
    beforeRouteUpdate () {
        try {
            this.fetchCountry()
        } catch(error) {
                console.log(error)
            }
    },
};
</script>

<style></style>
