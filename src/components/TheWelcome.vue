<template>
  <section>
    <div class="photo"></div>
    <div class="content">
      <p class="text--primary">Hey! I'm <b>Andrew Bondarenko</b></p>
      <p class="text--secondary">Web developer with 5+ years of experience
      </p>
      <div class="questions">
        <a href="#stack">My stack</a>
        <a href="#expirience">My expirience</a>
        <a href="#contacts">My contacts</a>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
    
  section {
    display: flex;
    align-items: center;

    min-height: 100vh;

    gap: 5rem;
  }

  .photo {
    display: block;

    width: 30rem;
    flex: 1.5;
    aspect-ratio: 1;

    background-image: url(/src/assets/photo.webp);
    background-size: 100%;
    background-position: right 15% top 25%;

    border-bottom-right-radius: 2rem;
    border-top-left-radius: 2rem;
  }

  .content {

    flex: 2.2;
    
    .text--primary {
      font-size: 3.0rem;
    }

    .text--secondary {
      font-size: 1.2rem;
    }

    .questions {
      margin-top: 2rem;
      display: flex;
      gap: 2rem;

      a {
        cursor: pointer;
        font-size: 1.26rem;
        color: white;

        border: 1px solid white;
        padding: 0.14rem 1.3rem;

        text-align: center;

        box-sizing: border-box;

        &:hover {
          background-color: white;
          color: black;
          border: 1px solid black;
        }
      }
    }
  }
  
  @media (max-width: 600px) {
    section {
      flex-direction: column;
      justify-content: center;

      .photo {
        width: auto;
        width: 40vh;
        max-height: 40vh;
        max-width: 40vh;
      }

      .content {
        flex: 0;

        text-align: center;
      }
    }
  }

</style>


