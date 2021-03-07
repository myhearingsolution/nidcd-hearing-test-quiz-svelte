<script lang="ts">
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher<{ close: undefined }>();
</script>

<div id="disclaimer-modal" class="modal" style="display: block">
  <h3 class="disclaimer-header">Disclaimer</h3>
  <p class="disclaimer-text">
    The NIDCD does not provide personalized medical advice to individuals about
    their condition or treatment. Your quiz results should not be used as a
    substitute for professional health care. We encourage you to work with
    qualified health providers for answers to your hearing health questions.
  </p>
  <div class="return-container">
    <!-- svelte-ignore a11y-invalid-attribute -->
    <a
      href="#"
      class="return-link"
      on:click|preventDefault={() => dispatch("close")}
    >
      Return
    </a>
  </div>
</div>
