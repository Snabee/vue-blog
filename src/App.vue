<template>
  <v-app>
    
    <v-content>
    
    <ul class="navbar">
      <li v-for="url in urls" :key="url.id"><a :href="url.url"> <img :src="url.src" :alt="url.alt"> {{ url.content }}</a></li>
    </ul>

    <v-parallax
    height=650
    dark
    src="https://i.imgur.com/Gwyb20o.jpg"
  >

    <v-row
      align="center"
      justify="center"
    >
      <v-col class="text-center" cols="12">
        <h1 class="display-1 font-weight-thin mb-4">Vuetify.js</h1>
        <h4 class="subheading">Build your application today!</h4>
      </v-col>
    </v-row>
  </v-parallax>

  <!-- <div class="buttons">
    <div class="shuffle" v-on:click="shuffle">Shuffle</div>
  </div> -->

  <div class="my-2">
    <v-btn large color="primary">Primary</v-btn>
  </div>

  <div v-if="Math.random() > 0.5">
  Maintenant vous me voyez
</div>


  <div class="feed">
    <Blog v-for="post in posts" :key="post.id" :title="post.title" :description="post.description" :image="post.image"></Blog>
  </div>


  </v-content>
  </v-app>
</template>

<script>

  import Blog from './components/Blog';

  export default {
    name: 'App',
    components: {
      Blog,
    },
    
    data: function(){
      return {
        posts: [
          { title: "Citron", description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.", image: "https://image.freepik.com/free-vector/lemon-lime-liquid-splash-neon-sign_1262-21353.jpg" },
          { title: "Banane", description: "Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est eligendi optio cumque nihil impedit quo minus id quod maxime placeat facere possimus, omnis voluptas assumenda est, omnis dolor repellendus. Temporibus autem quibusdam et aut officiis debitis aut rerum necessitatibus saepe eveniet ut et voluptates repudiandae sint et molestiae non recusandae.", image: "https://cdn.shopify.com/s/files/1/0023/8469/1252/products/Photo_2018-11-26_3_56_59_PM_2000x.jpg?v=1543288458" },
          { title: "Ananas", description: "At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident, similique sunt in culpa qui officia deserunt mollitia animi, id est laborum et dolorum fuga.", image: "https://cdn.shopify.com/s/files/1/1340/5961/products/brite-lite-tribe-new-neon-pineapple-6914074280041_1200x.jpg?v=1565238118" },
          { title: "Pasteque", description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.", image: "https://images-na.ssl-images-amazon.com/images/I/71mcW03bxYL._SL1500_.jpg" },
          { title: "Fraise", description: "Itaque earum rerum hic tenetur a sapiente delectus, ut aut reiciendis voluptatibus maiores alias consequatur aut perferendis doloribus asperiores repellat.", image: "https://cdn.shopify.com/s/files/1/1638/1487/products/enseigne-neon-sign-fraise-strawberry_696x.jpg?v=1571438890" },
          { title: "Raisin", description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.", image: "https://i.pinimg.com/originals/51/41/f4/5141f4f37de3607f99b99da54eb8794a.jpg" },
          { title: "Cerise", description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.", image: "https://media.istockphoto.com/vectors/cherry-neon-sign-vector-id1133669544?k=6&m=1133669544&s=170667a&w=0&h=5xoPIrNYk_t4eyrfTobIaKWNzSFYzhlJmVfEDtOVQQY=" },
        ],

        urls: [
            { url: "#", content: "Lorem"},
            { url: "#", content: "Lorem" },
            { url: "#", content: "", src: "https://cdn.freebiesupply.com/logos/large/2x/lorem-lorem-logo-png-transparent.png", alt: "logo"},
            { url: "#", content: "Lorem" },
            { url: "#", content: "Lorem" },
          ]
      
      }
    },

    };
    

</script>


<style>

.v-content{
  width: 100%;
  background-color: #15151A;
}

.navbar{
  position: absolute;
  z-index: 999;
  width: 100vw;
  background-image: linear-gradient(to bottom, #000000, transparent);
}

.navbar img{
  max-width: 200px;
}

.v-content ul{
  list-style: none;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 150px;
}

.v-content li{
    width: 200px;
    text-align: center;
    text-decoration: none;
}

ul a{
  color: white !important;
  text-decoration: none;
  font-size: 28px;
  font-weight: lighter;
}

ul a:visited{
  color: white;
  text-decoration: none;
}

ul a:hover{
  color: rgba(255, 255, 255, 0.687);
}

.shuffle{
  width: 300px;
  height: 100px;
  background-color: red;
  margin: 0 auto;
  margin-top: 50px;
  margin-bottom: 50px;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
}

.feed{
    height: auto;
    padding-bottom: 10vh;
    width: 100%;
    background-image: linear-gradient(to bottom, #15151a, #1c1d2c, #22253e, #272e52, #2c3766);
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(3, 1fr);
    grid-column-gap: 0px;
    grid-row-gap: 0px;
}

</style>