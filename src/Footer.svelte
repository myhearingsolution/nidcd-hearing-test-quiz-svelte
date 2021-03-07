<script lang="ts">
  import EmbedModal from "./EmbedModal.svelte";
  import DisclaimerModal from "./DisclaimerModal.svelte";
  import InfoModal from "./InfoModal.svelte";

  let currentModal: "embed" | "disclaimer" | "info" | false = false;
</script>

<div id="widget-logos">
  <img
    alt="National Institute on Deafness and Other Communication Disorders (NIDCD). Part of the National Institutes of Health (NIH), U.S. Department of Health and Human Services (HHS)"
    src="https://www.nidcd.nih.gov/sites/default/files/Widgets/HearingWidget/Images/HHS_NIDCD.png"
    width="225"
    height="640"
  />
</div>
{#if currentModal === "embed"}
  <EmbedModal on:close={() => (currentModal = false)} />
{/if}
{#if currentModal === "disclaimer"}
  <DisclaimerModal on:close={() => (currentModal = false)} />
{/if}
{#if currentModal === "info"}
  <InfoModal on:close={() => (currentModal = false)} />
{/if}
<div id="embed-info-container">
  <p id="footer_links">
    <!-- svelte-ignore a11y-invalid-attribute -->
    <a
      id="embed-link"
      href="#"
      on:click|preventDefault={() => (currentModal = "embed")}
    >
      Share This</a
    >
    <!-- svelte-ignore a11y-invalid-attribute -->
    <a
      id="info-link"
      href="#"
      on:click|preventDefault={() => (currentModal = "info")}
    >
      Info
    </a>
    <!-- svelte-ignore a11y-invalid-attribute -->
    <a
      id="disclaimer-link"
      href="#"
      on:click|preventDefault={() => (currentModal = "disclaimer")}
    >
      Disclaimer
    </a>
    <a
      id="privacy-link"
      href="https://www.nidcd.nih.gov/privacy"
      target="_blank"
    >
      Privacy
    </a>
  </p>
  <p id="widget-html">
    <a href="https://www.nidcd.nih.gov/hearing-test-widget" target="_blank">
      https://nidcd.nih.gov/hearing-test-widget
    </a>
  </p>
</div>
