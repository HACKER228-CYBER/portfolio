<script setup></script>

<template>
  <div class="home">
    <nav>
      <span>Freelance Developer</span>

      <ul>
        <li>Home</li>
        <li>About</li>
        <li>Skills</li>
        <li>Project</li>
        <li>Get in Touch</li>
      </ul>
    </nav>

    <div class="hero">
      <div class="title">
        <h2>
          <span>Hello, I'm Tahiana. </span><span>Fullstack-Developer.</span>
        </h2>
        <span class="description"
          >Build with the
          <span class="highlight">#1 most-used developer tool</span></span
        >
        <div class="actions">
          <button class="contact">Download Docker Desktop</button>
          <button class="download">Learn more about Docker</button>
        </div>
      </div>
    </div>
    <img src="@/assets/img/hero-1.svg" alt="profile picture" />
  </div>
</template>

<style scoped lang="scss">
.home {
  // background: #9a9797;
  position: relative;
  max-height: 100vh;
  overflow: hidden;

  nav {
    display: flex;
    padding: 1.5em 4em;

    span {
      width: 33%;
      color: $color-primary;
    }

    ul {
      display: flex;
      li {
        list-style: none;
        padding-left: 1.5em;
      }
    }
  }

  .hero {
    height: 100vh;
    top: 0;
    display: flex;
    align-items: center;
    width: 100%;
    position: absolute;

    .title {
      display: flex;
      flex-direction: column;
      width: 100%;
      align-items: center;
      margin-bottom: 4em;

      h2 {
        font-size: 3.4em;
        width: 50%;
        text-align: center;
        line-height: 1.2em;
        margin-bottom: 4px;
        color: $color-primary;
      }

      .description {
        margin-bottom: 2em;
        font-weight: $font-weight-small;
        .highlight {
          color: $color-secondary;
        }
      }

      .actions {
        button {
          padding: 0.75em 2em;
          border: none;
          border-radius: 5px;
          font-size: 1.1em;
          font-weight: 600;
          cursor: pointer;
        }

        .contact {
          background: $color-dark-blue;
          color: white;
          margin-right: 2em;
        }
        .download {
          background: transparent;
          color: $color-dark-blue;
          border: 1px solid $color-dark-blue;
        }
      }
    }
  }
  img {
    padding-top: 14em;
    min-width: 100%;
    object-fit: contain;
  }
}
</style>
