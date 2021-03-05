<script lang="ts">
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher<{ startQuiz: undefined }>();
</script>

<div id="intro-page" class="page">
  <div id="start-container">
    <h2>
      <!-- svelte-ignore a11y-invalid-attribute -->
      <a id="img-start-link" href="#" on:click={() => dispatch("startQuiz")}
        ><img
          alt="Do you need a hearing test?"
          src="https://www.nidcd.nih.gov/sites/default/files/Widgets/HearingWidget/Images/title_speech_balloons.png"
          width="225"
          height="217"
        /></a
      >
    </h2>
    <p id="startlink">
      <!-- svelte-ignore a11y-invalid-attribute -->
      <a id="start-link" href="#" on:click={() => dispatch("startQuiz")}
        >Take This Quick Quiz</a
      >
    </p>
    <p id="intro">
      A quiz for adults ages 18 to 64. The results of this quiz do not
      substitute for medical advice. Please see our disclaimer below.
    </p>
  </div>
</div>
