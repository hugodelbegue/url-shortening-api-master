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
            <Button text="Get Started" />
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
          <Card img="icon-brand-recognition.svg" title="Brand Recognition" text="Boost your brand recognition with each click. Generic links don’t 
  mean a thing. Branded links help instil confidence in your content." />
          <Card img="icon-detailed-records.svg" title="Detailed Records" text="Gain insights into who is clicking your links. Knowing when and where 
  people engage with your content helps inform better decisions." />
          <Card img="icon-fully-customizable.svg" title="Fully Customizable" text="Improve brand awareness and content discoverability through customizable 
  links, supercharging audience engagement." />
        </div>
      </div>
      <div class="started  body_size body_center">
        <h2>Boost your links today</h2>
        <Button text="Get Started" />
      </div>
    </div>
  </main>
  <Footer />
</template>

<style lang="scss" scoped>
main {
  --space-between-block: 2.5rem;
  --space-title-text: 1em;
  --space-between-card: 6rem;
  --size-img: 400px;
  --junction-padding: 12rem;
  --started-padding: 6.8rem;
  --size-line-through: 10px;
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

  .presentation_img {
    height: var(--size-img);

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

    .text {
      display: flex;
      flex-direction: column;
      gap: var(--space-title-text);
    }
  }
}

// second section
.statistics {
  position: relative;
  background: var(--background-secondary);
  padding-top: var(--junction-padding);
  padding-bottom: var(--space-between-card);
  gap: calc(var(--space-between-block) + 3em);

  .statistics_description {
    display: flex;
    flex-direction: column;
    gap: var(--space-title-text);
  }

  .statistics_cards {
    position: relative;
    display: flex;
    flex-direction: column;
    place-items: center;
    gap: var(--space-between-card);
  }

  .line_through {
    content: "";
    background: var(--color-line-through);
    position: absolute;
    width: 10px;
    height: 100%;
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

  h2 {
    color: var(--color-title-light);
  }
}
</style>
