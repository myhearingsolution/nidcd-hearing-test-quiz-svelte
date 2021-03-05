<script lang="ts">
  import IntroPage from './IntroPage.svelte'
  import Footer from './Footer.svelte'
  import Questions from './Questions.svelte'

  let quizStarted = false
</script>

<svelte:head>
  <link
    rel="stylesheet"
    type="text/css"
    href="https://www.nidcd.nih.gov/sites/default/files/Widgets/HearingWidget/HearingWidget.css"
  />
</svelte:head>

<div id="hwcontainer">
  <div id="hearing-widget" class="hearing-widget">
    {#if quizStarted}
      <Questions />
    {:else}
      <IntroPage on:startQuiz={() => (quizStarted = true)} />
    {/if}

    <Footer />
  </div>
</div>
