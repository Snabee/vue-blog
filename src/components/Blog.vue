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
          <div v-if="checked">
            <img src="https://lh3.googleusercontent.com/proxy/xKQ1h7XmgKuffM0Vu7Qqdkjdm7w-IJKz70xUdmNAZxpZdLrEL19PpLpmc4Sx38J2loIf_41SPnFRQYSLXy0zzhuhnrWIUw0">
          </div>
          <div v-else>
            <img src="https://pngimage.net/wp-content/uploads/2018/06/hover-icon-png-9.png">
          </div>
          
          
        </v-card-text>

        <v-fade-transition>
          <v-overlay
            v-if="hover"
            absolute
            color="#000000"
          >
            <v-btn @click="check">See more info</v-btn>
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

.text--primary img{
  width: 50px;
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
      checked: false,
  }),

  methods:{
    check: function() {
      this.checked = true;
    }
  },
}

</script>
