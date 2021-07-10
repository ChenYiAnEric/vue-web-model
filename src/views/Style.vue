<template>
  <div class="style" :class="'model' + styleId">
    <header>
      <nav
        class="navbar navbar-expand-lg bg-header"
        :class="styleData['model' + styleId].navbar"
      >
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
              <router-link class="nav-link" to="/">Home</router-link>
              <router-link class="nav-link" to="/about">About</router-link>
              <router-link
                v-for="(value, index) in modelData"
                :key="index"
                class="nav-link"
                :class="value.id === $route.params.styleId ? 'active' : ''"
                :to="'/style/' + value.id"
                >Style{{ value.id }}</router-link
              >
            </div>
          </div>
        </div>
      </nav>
    </header>
    <main class="flex-shrink-0">
      <div class="container">
        <div class="banner">
          <img
            :src="
              require('../assets/banner/' +
                styleData['model' + styleId].Folder +
                '/' +
                styleData['model' + styleId].bannerName +
                '.jpg')
            "
            class="card-img-top"
            :alt="styleData['model' + styleId].bannerName"
          />
        </div>
        <div class="select01 border-bottom">
          <div class="col col-lg-9">
            <div class="subtittle">內容一</div>
            <div class="subContent pe-lg-4">
              Lorem Ipsum is simply dummy text of the printing and typesetting
              industry. Lorem Ipsum has been the industry's standard dummy text
              ever since the 1500s, when an unknown printer took a galley of
              type and scrambled it to make a type specimen book. It has
              survived not only five centuries, but also the leap into
              electronic typesetting, remaining essentially unchanged. It was
              popularised in the 1960s with the release of Letraset sheets
              containing Lorem Ipsum passages, and more recently with desktop
              publishing software like Aldus PageMaker including versions of
              Lorem Ipsum.
            </div>
          </div>
          <div class="col col-lg-3">
            <img
              :src="
                require('../assets/room/' +
                  styleData['model' + styleId].Folder +
                  '/' +
                  styleData['model' + styleId].roomName1 +
                  '.jpg')
              "
              class="card-img-top"
              :alt="styleData['model' + styleId].roomName1"
            />
          </div>
        </div>
        <div class="select02">
          <div class="col col-lg-3">
            <img
              :src="
                require('../assets/room/' +
                  styleData['model' + styleId].Folder +
                  '/' +
                  styleData['model' + styleId].roomName2 +
                  '.jpg')
              "
              class="card-img-top"
              :alt="styleData['model' + styleId].roomName2"
            />
          </div>
          <div class="col col-lg-9 contentWrap">
            <div class="subtittle">內容二</div>
            <div class="subContent">
              Lorem Ipsum is simply dummy text of the printing and typesetting
              industry. Lorem Ipsum has been the industry's standard dummy text
              ever since the 1500s, when an unknown printer took a galley of
              type and scrambled it to make a type specimen book. It has
              survived not only five centuries, but also the leap into
              electronic typesetting, remaining essentially unchanged. It was
              popularised in the 1960s with the release of Letraset sheets
              containing Lorem Ipsum passages, and more recently with desktop
              publishing software like Aldus PageMaker including versions of
              Lorem Ipsum.
            </div>
          </div>
        </div>
      </div>
    </main>
    <FooterCommon />
  </div>
</template>
<style scoped lang="scss">
@import "../assets/scss/style.scss";
</style>
<script>
import jsonStyle from "../style/model.json";
import footer from "../components/footer.vue";
export default {
  name: "Style",
  data() {
    return {
      modelData: [
        {
          id: "01",
          name: "model01",
          title: "綠色風格",
        },
        {
          id: "02",
          name: "model02",
          title: "粉紅風格",
        },
      ],
      styleData: jsonStyle,
    };
  },
  components: {
    FooterCommon: footer,
  },
  computed: {
    styleId() {
      return this.$route.params.styleId;
    },
  },
};
</script>
