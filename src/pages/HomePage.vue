<script>
import Jumbotron from "../components/Jumbotron.vue";
import TrendingGamesCarousel from "../components/TrendingGamesCarousel.vue";
import Experience from "../components/Experience.vue";
import LiveStreaming from "../components/LiveStreaming.vue";
import UpcomingCarousel from "../components/UpcomingCarousel.vue";
import ShopCarousel from "../components/ShopCarousel.vue";
import TeamMembers from "../components/TeamMembers.vue";
import TrendingBattle from "../components/TrendingBattle.vue";
import Features from "../components/Features.vue";
import LatestNewsComponent from "../components/LatestNewsComponent.vue";
export default {
  name: "HomePage",
  components: {
    Jumbotron,
    TrendingGamesCarousel,
    Experience,
    LiveStreaming,
    UpcomingCarousel,
    ShopCarousel,
    TeamMembers,
    TrendingBattle,
    Features,
    LatestNewsComponent,
  },
  data() {
    return {
      jumboImages: ["bg1.png", "bg2.png", "bg3.png"],
      jumboText: [
        "you speak of justice",
        "you speak of justice",
        "we fall. then we rise.",
      ],
      gameTeams: ["1.png", "5.png", "6.png", "3.png"],
      gameTitles: [
        "Assassin's Creed",
        "Call of Duty",
        "Tomb Raider",
        "Mortal Combat X",
      ],
      portfolioImages: [1, 2, 3, 4],
    };
  },
};
</script>

<template>
  <main>
    <Jumbotron :jumboImages="jumboImages" :text="jumboText" />

    <div class="trending-games">
      <div class="container">
        <div class="col-6">
          <h3>Trending Games</h3>
          <h1>Choose Who Is The Best In World!</h1>
        </div>
        <TrendingGamesCarousel
          :teams="gameTeams"
          :titles="gameTitles"
          :images="portfolioImages"
        />
      </div>
    </div>
    <div class="experience">
      <Experience image="/img/ab/ab-three.png" />
    </div>
    <div class="live">
      <LiveStreaming />
    </div>
    <div class="trending">
      <TrendingBattle />
    </div>
    <div class="upcoming">
      <UpcomingCarousel />
    </div>
    <div class="shop"><ShopCarousel /></div>
    <div class="team"><TeamMembers /></div>
    <div class="features"><Features /></div>
    <div class="news"><LatestNewsComponent /></div>
  </main>
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/variables" as *;
.trending-games .col-6 h1 {
  margin-top: 10px;
  font-size: 55px;
  font-weight: 600;
  color: #ffffff;
}
.trending-games .col-6 h3 {
  font-size: 18px;
  font-weight: 600;
  color: #00ac4d;
  position: relative;
  margin-bottom: 10px;
  text-transform: capitalize;
}
.trending-games {
  background-color: $bg-primary;
  padding-top: 100px;
  padding-bottom: 80px;
}

.experience {
  background-color: $bg-tertiary;
}

.live {
  padding-top: 150px;
  padding-bottom: 50px;
  background-image: url(img/background/live-streming-bg.png);
  background-repeat: no-repeat;
  background-size: cover;
  position: relative;

  &::before {
    content: "";
    position: absolute;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    background: rgba(26, 25, 53, 0.603);
    z-index: 1;
  }
}

.upcoming {
  padding-top: 130px;
  padding-bottom: 100px;
  background-image: url(img/background/upcoming.png);
  background-position: center;
  background-size: cover;
  position: relative;
  &::before {
    content: "";
    position: absolute;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    background: rgba(26, 25, 53, 0.603);
    z-index: 1;
  }
}

.shop {
  padding-top: 130px;
  padding-bottom: 100px;
  background-image: url(img/background/shop-bg.png);
  background-position: center;
  background-size: cover;
  position: relative;
  &::before {
    content: "";
    position: absolute;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    background: rgba(26, 25, 53, 0.603);
    z-index: 1;
  }
}
.trending {
  background-color: $bg-primary;
}

.features {
  background-color: $bg-tertiary;
}
.team {
  padding-top: 130px;
  padding-bottom: 100px;
  background-color: $bg-primary;
}

.news {
  background-color: $bg-primary;
  margin: 0 auto;
}

.shop {
  background-color: antiquewhite;
}
</style>
