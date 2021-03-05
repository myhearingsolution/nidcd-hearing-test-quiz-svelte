<script lang="ts">
  import { createEventDispatcher } from 'svelte'

  export let imgSrc: string, text: string
  export let number: number, of: number

  const dispatch = createEventDispatcher<{ answer: 'Yes' | 'No' }>()
</script>

<div class="question" id="q{number}">
  <img src={imgSrc} alt="" width="225" height="217" />
  <p class="questionText">{@html text}</p>
  <form class="yn_buttons">
    <label
      class="qolabel"
      for="qo{number}yes"
      on:click={() => dispatch('answer', 'Yes')}>YES</label
    >
    <label
      class="qolabel"
      for="qo{number}no"
      on:click={() => dispatch('answer', 'No')}>NO</label
    >
  </form>
  <p class="questionNumber">Question {number} of {of}</p>
</div>
