<template>
  <div class="home">
    <header>
      <nav class="navbar navbar-expand-lg navbar-light bg-info">
        <div class="container">
          <a class="navbar-brand" href="#">
            <img
              src="../assets/header/Logo_mockup.png"
              alt=""
              width="35"
              height="35"
            />
            Bootstrap
          </a>
          <button
            class="navbar-toggler"
            type="button"
            data-bs-toggle="collapse"
            data-bs-target="#navbarNavAltMarkup"
            aria-controls="navbarNavAltMarkup"
            aria-expanded="false"
            aria-label="Toggle navigation"
          >
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
            <div class="navbar-nav">
              <router-link class="nav-link active" to="/">Home</router-link>
              <router-link class="nav-link" to="/about">About</router-link>
            </div>
          </div>
        </div>
      </nav>
    </header>
    <section class="container">
      <p class="title-sub">切版</p>
      <div class="row py-3">
        <div v-for="(value, index) in modelData" :key="index" class="col-3">
          <div class="card">
            <img
              :src="require(`../assets/home-web-small/${value.img}.jpg`)"
              class="card-img-top"
              :alt="value.img"
            />
            <div class="card-body">
              <h5 class="card-title">{{ value.title }}</h5>
              <p class="card-text">{{ value.text }}</p>
              <a href="#" class="btn btn-primary">Go somewhere</a>
            </div>
          </div>
        </div>
      </div>
      <p class="title-sub">外部連結</p>
      <div class="row py-3">
        <div v-for="(value, index) in linkData" :key="index" class="col-3">
          <div class="card">
            <img
              :src="require(`../assets/home-web-small/${value.img}.jpg`)"
              class="card-img-top"
              :alt="value.img"
            />
            <div class="card-body">
              <h5 class="card-title">{{ value.title }}</h5>
              <p class="card-text">{{ value.text }}</p>
              <a :href="value.url" target="_blank" class="btn btn-primary">Go somewhere</a>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>
<style scoped>
.title-sub {
  font-size: 2rem;
  font-weight: bold;
  text-align: left;
  padding: 12px 12px 0 12px;
  margin: 0;
  line-height: 2rem;
}
</style>
<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: "Home",
  data() {
    return {
      modelData: [
        {
          name: "model01",
          title: "風格01",
          img: "model01",
          text: "Some quick example text to build on the card title and make up the bulk of the card's content.",
        },
        {
          name: "model01",
          title: "風格01",
          img: "model01",
          text: "Some quick example text to build on the card title and make up the bulk of the card's content.",
        },
      ],
      linkData: [
        {
          name: "firebase",
          title: "firebase-blog",
          img: "firebase",
          text: "用firebase建立的網站使用vue2，簡單使用firebase功能的聊天室",
          url: "https://chat-firebase-971ee.firebaseapp.com/#/",
        },
        {
          name: "vercel-hexo-blog",
          title: "vercel-hexo-blog",
          img: "blog",
          text: "vercel建立的hexo Blog，應用vercel ci/cd功能能自動同步github更新。",
          url: "https://blog-test-three-alpha.vercel.app/",
        },
      ]
    };
  },
};
</script>
