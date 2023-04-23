<script setup>
import Header from '@/layouts/Header.vue';
import Footer from '@/layouts/Footer.vue';

import Button from '@/components/Button.vue';
import Card from '@/components/Card.vue';
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
            <Button />
          </div>
        </div>
      </div>
      <div class="statistics  body_size body_center">
        <div class="statistics_description">
          <h2>Advanced Statistics</h2>
          <p>Track how your links are performing across the web with our
            advanced statistics dashboard.</p>
        </div>
        <div class="statistics_cards">
          <Card />
          <Card />
          <Card />
        </div>
      </div>
      <div class="started  body_size body_center">
        <h2>Boost your links today</h2>
        <Button />
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
  --size-card: 375px;
  --size-ball: 88px;
}

.layout_main {
  text-align: center;
  overflow-x: hidden;
}

// firt section
.presentation {
  padding-top: 1rem;
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
    display: flex;
    flex-direction: column;
    gap: var(--space-between-card);
  }
}

// third section
.started {
  background: var(--background-tersiary);
  padding-top: var(--started-padding);
  padding-bottom: var(--started-padding);
  gap: 1em;

  h2 {
    color: var(--color-title-light);
  }
}
</style>
