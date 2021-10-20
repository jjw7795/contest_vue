<template>
  <header>
    <Logo />
    <div class="nav nav-pills">
      <div v-for="nav in navigations" :key="nav.name" class="gnb">
        <RouterLink
          :to="nav.href"
          active-class="active"
          :class="{ active: isMatch(nav.path) }"
          class="nav-link"
        >
          <img :src="nav.image" :alt="nav.name" />
        </RouterLink>
      </div>
    </div>
  </header>
</template>

<script>
import Logo from "~/components/Logo";
export default {
  components: {
    Logo,
  },
  data() {
    return {
      navigations: [
        {
          name: "공모전 소개",
          href: "/",
          image: "src/assets/menu1.png",
        },
        {
          name: "공모전 요강",
          href: "/pot",
          image: "src/assets/menu2.png",
        },
        {
          name: "작품 접수",
          href: "/apply",
          image: "src/assets/menu3.png",
        },
        {
          name: "접수 확인",
          href: "/check",
          image: "src/assets/menu4.png",
        },
        {
          name: "공지사항",
          href: "/notice",
          image: "src/assets/menu5.png",
        },
        { name: "Q&A", href: "/qua", image: "src/assets/menu6.png" },
      ],
    };
  },
  mounted() {
    console.log(this.nav2);
  },
  methods: {
    isMatch(path) {
      if (!path) return false;
      return path.test(this.$route.fullPath);
    },
  },
  computed: {},
};
</script>

<style lang="scss" scoped>
@import "~/scss/main";
header {
  height: 120px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 1200px;

  margin: 0 auto;
}

.gnb {
  display: flex;
  justify-content: center;
  align-items: center;
}
.gnb li {
  font-size: 20px;
  font-weight: bold;
  margin-right: 30px;
}
.gnb li:last-child {
  margin-right: 0;
}
.gnb li > a {
  display: block;
  padding: 20px 0;
  transition: 1s;
  color: $black;
}
.gnb li:hover > a {
  border-bottom: 1px solid #000;
}
</style>
