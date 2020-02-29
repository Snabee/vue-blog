<template>
  
  <v-hover>
    <template v-slot:default="{ hover }">
      <v-card
        class="mx-auto"
        max-width="400"
      >
        <v-img
          class="white--text align-end"
          height="200px"
          :src="image"
        >
          <v-card-title>{{ title }}</v-card-title>
        </v-img>

        <v-card-text class="text--primary">
          <div>{{ description }}</div>
        </v-card-text>

        <v-fade-transition>
          <v-overlay
            v-if="hover"
            absolute
            color="#000000"
          >
            <v-btn>See more info</v-btn>
          </v-overlay>
        </v-fade-transition>
      </v-card>
    </template>
  </v-hover>

</template>

<style>
.v-card{
    margin-top: 50px;
    background-color: #F8F8FF !important;
    transition: transform 1s;
}


</style>

<script>
export default {
  name: 'Blog',
  props: {
    title:String,
    description:String,
    image:String,
  },

  data: () => ({
      overlay: false,
    }),
}

</script>
