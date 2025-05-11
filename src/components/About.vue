<script setup lang="ts">
import { AboutData } from "@/data/About/About";
import { ref } from "vue";

const getImageUrl = (imagePath) => require(`${imagePath}`);

const imgUrl = ref("13186262_5152371.svg");
// const imgUrl = ref(
//   "https://media.licdn.com/dms/image/v2/D4D03AQFtizpXbauKcQ/profile-displayphoto-shrink_800_800/profile-displayphoto-shrink_800_800/0/1718471233098?e=1748476800&v=beta&t=buF1ld2f9078h73ItgnChw7rHVZ3AMvs7-jrhpSnG60"
// );

const abouts = ref(AboutData);
</script>

<template>
  <div class="about__wrapper container">
    <div class="about__header">
      <div class="about__title text-primary-gradient">About Me</div>
      <h4 class="">I'm an experienced fullstack JavaScript Developer.</h4>
      <h5>
        Docker helps developers build, share, run, and verify applications
        anywhere — without tedious environment configuration or management.
      </h5>
    </div>

    <div class="about__container">
      <h3>About Me</h3>

      <div class="about__content">
        <div class="left">
          <div class="about__skills" v-for="about in abouts">
            <div class="about__skill_header">
              <img :src="about.svgUrl" alt="" />
              <h4 class="title">{{ about.title }}</h4>
            </div>
            <span class="__desc">{{ about.description }}</span>
          </div>

          <div class="about__project_link">
            <a href="">Project done</a>
          </div>
        </div>
        <div class="right">
          <img src="@/assets/img/13186262_5152371.svg" alt="" />
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.about__wrapper {
  // padding-top: 3em;
  // background: rgba(0, 128, 0, 0.427);
  .about__header {
    text-align: center;
    width: 65%;
    margin: auto;

    .about__title {
      font-size: 1.5em;
      padding-top: 2.5em;
    }

    h4 {
      font-size: 3em;
      color: $color-primary;
      line-height: 1em;
      margin-top: 0.25em;
    }
    h5 {
      font-size: 1em;
      color: $color-primary;
      font-weight: normal;
      margin-top: 1.5em;
      margin-bottom: 3em;
    }
  }

  .about__container {
    h3 {
      font-size: 2.5em;
      color: $color-primary;
    }

    .about__content {
      display: flex;
      flex-direction: row;
      // border: 1px solid grey;
      justify-content: space-between;
      // align-items: start;
      gap: 8em;

      .left {
        // border: 1px solid;
        width: 62%;

        .about__skills {
          margin-top: 1.25em;
          .about__skill_header {
            img {
              width: 4em;
              height: 4em;
            }
            .title {
              color: $color-primary;
              font-weight: 500;
              font-size: 1.25em;
            }
          }
          .__desc {
            font-size: 0.94em;
            color: $color-grey;
          }
        }

        .about__project_link {
          margin-top: 2em;
          span {
            color: $color-secondary;
            font-size: 0.94em;
          }
        }
      }
      .right {
        border: 1px solid $color-grey;
        border-radius: 24px;
        position: relative;
        width: 24em;
        max-height: 23em;
        overflow: hidden;

        img {
          background: blue;
          position: absolute;
          width: 100%;
          height: 100%;
          object-fit: cover;
          top: 40px;
          left: 40px;
        }
      }
    }
  }
}
</style>
