<template>
  <section>
    <div class="photo"></div>
    <div class="content">
      <p class="text--primary">Hey! I'm Andrew Bondarenko</p>
      <p class="text--secondary">Web developer with knowlange of 
        <a class="tag" href="#stack">PHP</a> 
        <a class="tag" href="#stack">Javascript</a>
        <a class="tag" href="#stack">HTML</a>
        <a class="tag" href="#stack">CSS</a>
        <a class="tag" href="#stack">SASS</a>
        <a class="tag" href="#stack">SCSS</a>
        <a class="tag" href="#stack">Vue</a>
        <a class="tag" href="#stack">jQuery</a>
        <a class="tag" href="#stack">Laravel</a>
        <a class="tag" href="#stack">Git</a>
        <a class="tag" href="#stack">Docker</a>
        <a class="tag" href="#stack">...</a>
      </p>
      <div class="questions">
        <a href="#stack">What is your skills?</a>
        <a href="#faq">Can i see examples of your code?</a>
        <a href="#expirience">What is your expirience?</a>
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
    flex: 1;
    aspect-ratio: 1;

    background-image: url(/src/assets/photo-1.webp);
    background-size: 100%;
    background-position: right 15% top 25%;

    border-radius: 50%;
  }

  .content {

    flex: 2.2;
    
    .text--primary {
      font-size: 3.0rem;
    }

    .text--secondary {
      font-size: 1.2rem;

      .tag {
        background-color: var(--vt-c-soft-transparent);
        color: var(--vt-c-soft-white);
        margin: 0.25rem;
        padding: 0.3rem 1.1rem;
        font-size: 0.85rem;

        border-radius: 0.5rem;
        transition: color 0.5s;

        cursor: pointer;
        display: inline-block;

        &:hover {
          transition: color 0.5s;
          color: var(--color-text);
        }
      }
    }

    .questions {
      margin-top: 2rem;
      display: flex;
      justify-content: space-between;

      a {
        cursor: pointer;
        font-size: 1.32rem;
        color: white;
        
        position: relative;

        &::after {
          content: "";
          background-color: white;
          position: absolute;
          bottom: -2px;
          left: 0;
          height: 2px;
          width: 0;
          transition: 0.3s;
        }

        &:hover,
        &:focus {
          color: white;
        }

        &:hover::after,
        &:focus::after,
        &.active::after {
          background-color: white;
          width: 100%;
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


