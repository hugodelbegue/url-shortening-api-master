<script setup>
import Header from '@/layouts/Header.vue';
import Footer from '@/layouts/Footer.vue';

import Button from '@/components/Button.vue';
import Card from '@/components/Card.vue';
import Shorten from '@/components/Shorten.vue';
</script>

<template>
  <Header />
  <main>
    <div class="layout_main">
      <div class="presentation body_size body_center">
        <div class="presentation_img">
          <img src="@/assets/images/illustration-working.svg" alt="">
        </div>
        <div class="presentation_description">
          <div class="text">
            <h1>More than just shorter links</h1>
            <p>Build your brand’s recognition and get detailed insights
              on how your links are performing.</p>
          </div>
          <div class="presentation_button">
            <Button text="Get&nbsp;Started" />
          </div>
        </div>
      </div>
      <div class="statistics  body_size body_center">
        <Shorten />
        <div class="statistics_description">
          <h2>Advanced Statistics</h2>
          <p>Track how your links are performing across the web with our
            advanced statistics dashboard.</p>
        </div>
        <div class="statistics_cards">
          <div class="line_through"></div>
          <Card class="one" :img="imgUrl('icon-brand-recognition.svg')" title="Brand Recognition" text="Boost your brand recognition with each click. Generic links don’t 
  mean a thing. Branded links help instil confidence in your content." />
          <Card class="two" :img="imgUrl('icon-detailed-records.svg')" title="Detailed Records" text="Gain insights into who is clicking your links. Knowing when and where 
  people engage with your content helps inform better decisions." />
          <Card class="three" :img="imgUrl('icon-fully-customizable.svg')" title="Fully Customizable" text="Improve brand awareness and content discoverability through customizable 
  links, supercharging audience engagement." />
        </div>
      </div>
      <div class="started  body_size body_center">
        <h2>Boost your links today</h2>
        <Button text="Get&nbsp;Started" />
      </div>
    </div>
  </main>
  <Footer />
</template>

<script>
export default {
  data() {
    return {
      imgUrl(file) {
        return new URL(`./assets/images/${file}`, import.meta.url).href;
      }
    }
  }
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/responsive.scss';

main {
  --space-between-block: 2.5rem;
  --space-title-text: 1em;
  --space-between-card: 6rem;
  --size-img: 400px;
  --junction-padding: 12rem;
  --statistics-padding: calc((var(--junction-padding) / 2) + 4px);
  --started-padding: 6.8rem;
  --size-line-through: 10px;
  --padding-card-bottom: var(--space-between-card);
  --offset: 3rem;

  @media #{$tabletScreen} {
    --started-padding: 3.4rem;
    --statistics-padding: calc((var(--junction-padding) / 2) - 17px);
  }

  @media #{$navDesktop} {
    --space-between-card: 2rem;
    --padding-card-bottom: 10.5rem;
  }
}

.layout_main {
  text-align: center;
  overflow-x: hidden;
}

// firt section
.presentation {
  padding-top: 1.5rem;
  padding-bottom: var(--junction-padding);
  gap: var(--space-between-block);

  @media #{$tabletScreen} {
    padding-top: 3.2rem;
  }

  @media #{$desktopScreen} {
    flex-direction: row-reverse;
    gap: 0;
    padding-top: 5rem;
  }

  .presentation_img {
    height: var(--size-img);

    @media #{$desktopScreen} {
      width: 50%;
    }

    img {
      position: relative;
      left: 7rem;
      height: 100%;
    }
  }

  .presentation_description {
    display: flex;
    flex-direction: column;
    gap: var(--space-between-block);

    @media #{$tabletScreen} {
      max-width: var(--tablet);
    }

    @media #{$desktopScreen} {
      text-align: left;
      max-width: auto;
    }

    .text {
      display: flex;
      flex-direction: column;
      gap: var(--space-title-text);

      @media #{$desktopScreen} {
        gap: 0;
      }
    }
  }
}

// second section
.statistics {
  position: relative;
  background: var(--background-secondary);
  padding-top: var(--statistics-padding);
  padding-bottom: var(--padding-card-bottom);

  @media #{$navDesktop} {
    --space-between-block: 6rem;
  }

  .statistics_description {
    display: flex;
    flex-direction: column;
    gap: var(--space-title-text);
    margin-top: calc(var(--space-between-block) + 3em);

    @media #{$tabletScreen} {
      max-width: 32rem;
    }

  }

  .statistics_cards {
    position: relative;
    display: flex;
    flex-direction: column;
    place-items: center;
    gap: var(--space-between-card);
    margin-top: calc(var(--space-between-block) + 3em);

    @media #{$navDesktop} {
      flex-direction: row;
      text-align: left;

      .one {
        bottom: var(--offset);
      }

      .three {
        top: var(--offset);
      }

      &:deep(.ball_card) {
        --width-ball: 85px;
        left: 30px;
      }
    }
  }

  .line_through {
    content: "";
    background: var(--color-line-through);
    position: absolute;
    width: 10px;
    height: 100%;

    @media #{$navDesktop} {
      width: 100%;
      height: 10px;
    }
  }
}

// third section
.started {
  background-image: url(@/assets/images/bg-boost-mobile.svg);
  background-color: var(--background-tersiary);
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  padding-top: var(--started-padding);
  padding-bottom: var(--started-padding);
  gap: 1em;

  @media #{$tabletScreen} {
    background-image: url(@/assets/images/bg-boost-desktop.svg);
  }

  h2 {
    color: var(--color-title-light);
  }
}
</style>
