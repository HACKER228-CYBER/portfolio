<script setup lang="ts">
import { listProjects } from "@/data/Project/Project";
import { ref } from "vue";

const projects = ref(listProjects);
</script>

<template>
  <div class="container projects__wrapper">
    <div class="project_section__title">
      <h3 class="text-primary-gradient">Current Projects</h3>
    </div>

    <div class="project__container">
      <div class="project__content" v-for="project in projects">
        <div class="left">
          <h4 class="project__title">{{ project.title }}</h4>
          <h5 class="project__desc">
            {{ project.description }}
          </h5>
          <div class="project__language">
            <span class="project__lang" v-for="language in project.languages">{{
              language
            }}</span>
          </div>

          <div class="project__skills">
            <ul>
              <li v-for="skill in project.skills">
                <img
                  src="@/assets/img/badge-check-svgrepo-com.svg"
                  alt="badge-check"
                />
                <span>{{ skill }}</span>
              </li>
            </ul>
          </div>
        </div>

        <div class="right">
          <img
            class="project-picture"
            src="@/assets/img/dashboard.webp"
            alt="project-picture-1"
          />
          <img
            class="project-picture"
            src="@/assets/img/dashboard.webp"
            alt="project-picture-2"
          />
          <img
            class="project-picture"
            src="@/assets/img/dashboard.webp"
            alt="project-picture-3"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.projects__wrapper {
  height: 100vh;
  // background: #0000002a;
  padding-top: 4em;

  .project_section__title {
    font-size: 2em;
    text-align: center;
    // width: 100%;
    margin-bottom: 3em;
  }

  .project__container {
    display: flex;
    flex-direction: column;
    gap: 18em;

    .project__content {
      display: flex;
      position: relative;
      gap: 8em;

      .left {
        width: 50%;
        // border: 1px solid #fff;
        display: flex;
        flex-direction: column;
        gap: 1.5em;

        .project__title {
          color: $color-primary;
          font-size: 2em;
        }
        .project__desc {
          color: $color-grey;
          font-weight: normal;
        }

        .project__language {
          display: flex;
          flex-wrap: wrap;
          gap: 1em;

          .project__lang {
            padding: 0.5em 1.5em;
            font-weight: 500;
            color: $color-secondary;
            background-color: $color-secondary-opacity;
            border-radius: 50px;
            font-size: 0.8em;
          }
        }

        .project__skills {
          ul {
            padding-left: 0.5em;
            // border: 1px solid;
            max-height: 6em;
            display: flex;
            flex-direction: column;
            flex-wrap: wrap;
            color: $color-primary;
            li {
              display: flex;
              align-items: center;
              gap: 0.5em;
              list-style: none;
              font-size: 0.9em;
            }
          }
        }
      }

      .right {
        width: 50%;
        min-height: 100%;
        position: relative;
        // background-color: red !important;
        // border: 1px solid red;

        .project-picture {
          position: absolute;
          width: 80%;
          margin-left: 8em;
          margin-top: 4em;
          -webkit-box-shadow: 0px 4px 13px 2px #000000;
          box-shadow: 0px 4px 13px 2px #000000;

          &:hover {
            // left: $spacing;
            // top: calc($spacing * -1);
            width: 90%;
            cursor: pointer;
            z-index: 1;
          }
        }

        $img-spacing: 4em;

        :nth-child(1) {
          left: $img-spacing;
          top: calc($img-spacing * -1);
          // border: 2px solid red;
        }
        :nth-child(2) {
          // border: 2px solid green;
          // top: $img-spacing;
        }
        :nth-child(3) {
          // border: 2px solid blue;
          left: calc($img-spacing * -1);
          top: calc($img-spacing * 1);
        }
      }
    }
  }
}
</style>
