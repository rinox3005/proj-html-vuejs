<!-- JAVASCRIPT -->
<script>
import TeamMembers from "../components/TeamMembers.vue";
import LiveStreaming from "../components/LiveStreaming.vue";
import TrendingGamesCarousel from "../components/TrendingGamesCarousel.vue";
import ExtremeFeatureComponent from "../components/ExtremeFeatureComponent.vue";
import LatestNewsComponent from "../components/LatestNewsComponent.vue";

export default {
  nome: "AboutPage",
  props: {},
  data() {
    return {
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
  components: {
    TeamMembers,
    LiveStreaming,
    TrendingGamesCarousel,
    ExtremeFeatureComponent,
    LatestNewsComponent,
  },
};
</script>

<!-- HTML -->
<template>
  <section>
    <div class="jumbo">
      <div class="container">
        <div class="content">
          <h1 class="title">About Us</h1>
          <span>
            <router-link :to="home" class="anchor">Home</router-link>
            <i class="fas fa-arrow-right"></i>
            About Us
          </span>
        </div>
      </div>
    </div>
  </section>
  <section class="experience">
    <div class="container py-5">
      <h3 class="pt-5">12 Year Experience</h3>
      <div class="row g-5">
        <div class="col-6 text">
          <h2 class="mb-4">We Are The Best Gaming Company</h2>
          <p>
            Nulla quis lorem ut libero malesuada feugiat. Vivamus magna justo,
            lacinia eget consectetur sed, convallis at tellus. Cras ultricies
            ligula sed magna dictum porta.Praesent sapien massa, convallis a
            pellentesque nec, egestas non nisi praesent sapien massa.
          </p>
          <p>
            Nulla quis lorem ut libero malesuada feugiat. Vivamus magna justo,
            lacinia eget consectetur sed, convallis at tellus. Cras ultricies
            ligula sed magna dictum porta.
          </p>
          <ul>
            <li>
              <div class="icons"><i class="fas fa-check"></i></div>
              <p>Sed porttitor lectus nibh. Proin eget tortor risus.</p>
            </li>
            <li>
              <div class="icons"><i class="fas fa-check"></i></div>
              <p>Praesent sapien massa, convallis a pellentesque nec. risus.</p>
            </li>
            <li>
              <div class="icons"><i class="fas fa-check"></i></div>
              <p>Praesent sapien massa, convallis a pellentesque nec. risus.</p>
            </li>
            <li>
              <div class="icons"><i class="fas fa-check"></i></div>
              <p>Praesent sapien massa, convallis a pellentesque nec. risus.</p>
            </li>
          </ul>
          <div class="mb-4">
            <button class="btn">
              Discover More <i class="fas fa-arrow-right"></i>
            </button>
            <div class="play">
              <a href=""><i class="fas fa-play"></i></a>
            </div>
          </div>
        </div>
        <div class="col-6">
          <div class="image">
            <img src="../../img/wordSection/small3.png" alt="" />
            <div class="play">
              <a href=""><i class="fas fa-play"></i></a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
  <div class="team">
    <TeamMembers />
  </div>
  <div class="live">
    <LiveStreaming />
  </div>
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

  <div class="extrim-feat"><ExtremeFeatureComponent /></div>

  <div class="news"><LatestNewsComponent /></div>
</template>

<!-- STYLE -->
<style lang="scss" scoped>
// import:
@use "../assets/scss/partials/variables" as *;
@use "../assets/scss/partials/extend" as *;

* {
  color: $text-primary;
}

h3 {
  font-size: 20px;
  font-weight: 600;
  color: $text-secondary;
}

h2 {
  font-size: 45px;
  font-weight: 900;
}

section {
  .jumbo {
    position: relative;
    width: 100vw;
    height: 80vh;
    background-image: url("/img/background/breadcump-banner.png");
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;

    &::before {
      position: absolute;
      content: "";
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background: rgba(26, 25, 53, 0.6);
    }
    .container {
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
      width: 100%;
      height: 100%;
      width: 100%;
      z-index: 5;

      .content {
        position: relative;
        top: 20%;
        h1 {
          text-transform: uppercase;
          color: $text-primary;
          font-size: 48px;
          font-weight: 700;
          text-align: center;
        }

        span {
          display: block;
          text-align: center;
          color: $text-primary;
          font-size: 18px;
          font-weight: 500;

          .anchor {
            color: inherit;
            text-decoration: none;
            cursor: pointer;
          }

          .fa-arrow-right {
            margin: 0 10px;
            color: $text-secondary;
          }
        }
      }
    }
  }
}

.experience {
  background-color: $bg-primary;

  .text {
    ul {
      padding-left: 0;

      div.icons {
        width: 25px;
        height: 25px;
        border-radius: 100%;
        border: 1.8px solid $text-secondary;
        display: inline-block;
        text-align: center;

        .fa-check {
          font-size: 15px;
          line-height: 30px;
          color: $text-secondary;
        }
      }

      p {
        display: inline-block;
        margin-left: 10px;
      }
    }

    button.btn {
      @extend %btn;
    }

    div.play {
      @extend %play;
      display: inline-flex;
      margin-left: 10px;
    }
  }

  .image {
    position: relative;
    width: 90%;
    overflow: hidden;
    &::before {
      content: "";
      position: absolute;
      left: 0;
      top: 0;
      right: 0;
      bottom: 0;
      background-color: rgba($bg-primary, 0.5);
    }

    .play {
      position: absolute;
      @extend %play;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);

      a {
        .fa-play {
          color: $text-primary;
        }
      }
    }

    img {
      width: 110%;
      height: auto;
      object-fit: contain;
      object-position: -30px;
    }
  }
}
// component TeamMembers:
.team {
  padding-top: 130px;
  padding-bottom: 100px;
  background-color: $top-menu;
}

// component LiveStreaming:
.live {
  padding-top: 150px;
  padding-bottom: 50px;
  background-image: url(img/background/live-streming-bg.png);
  position: relative;
  &::before {
    position: absolute;
    content: "";
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(26, 25, 53, 0.6);
  }
}

// component TrendingGamesCarousel:
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

// coponent Lates News:
.news {
  background-color: $bg-primary;
  margin: 0 auto;
}
</style>
