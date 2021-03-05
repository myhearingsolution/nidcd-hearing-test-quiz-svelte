<script lang="ts">
  import { createEventDispatcher } from 'svelte'

  export let yesAnswerCount: number

  const dispatch = createEventDispatcher<{ resetQuiz: undefined }>()

  $: needsHearingTest = yesAnswerCount > 2
</script>

<div class="results" id="results">
  <p class="result-header">Congratulations on completing the quiz!</p>
  <div class="result-text-1">
    {#if needsHearingTest}
      <p class="second-result">
        Your results suggest that you<br />may need a hearing test.
      </p>
    {:else}
      <p class="first-result">
        Your results suggest that you don't need a hearing test at this time.
      </p>
    {/if}
  </div>
  <div class="result-text-2">
    {#if needsHearingTest}
      <p class="second-result">
        You answered "YES" to 3 or more of these questions.
      </p>
    {:else}
      <p class="first-result">You answered "YES" to fewer than 3 questions.</p>
    {/if}
  </div>
  <div class="result-text-3">
    {#if needsHearingTest}
      <div class="second-result">
        <p>
          Talk with your doctor or another hearing health provider about having
          your hearing checked.
        </p>
        <p>
          Avoid more hearing loss. Protect your ears from sounds that are too
          loud and loud sounds that last too long.
        </p>
      </div>
    {:else}
      <p class="first-result">
        To help prevent hearing loss, protect your ears from sounds that are too
        loud and loud sounds that last too long. If you notice signs of hearing
        loss, talk with your doctor or another hearing health provider.
      </p>
    {/if}
    <p class="result-additional-text-1">
      Learn more at
      <a href="https://www.nidcd.nih.gov/hearing" target="_blank"
        >www.nidcd.nih.gov/hearing</a
      >
    </p>
    <p class="result-additional-text-2">
      Test questions adapted from<br /><cite
        >The Hearing Handicap Inventory for Adults [HHIA]</cite
      >.
    </p>
    <div class="result-links">
      <!-- svelte-ignore a11y-invalid-attribute -->
      <a id="play-again" href="#" on:click={() => dispatch('resetQuiz')}
        >Retake Quiz</a
      ><a
        id="learn-more"
        href="https://www.nidcd.nih.gov/hearing"
        target="_blank">Learn More</a
      >
    </div>
  </div>
</div>
