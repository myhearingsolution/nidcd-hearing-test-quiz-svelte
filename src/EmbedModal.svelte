<script lang="ts">
  import { createEventDispatcher } from 'svelte'

  const dispatch = createEventDispatcher<{ close: undefined }>()
</script>

<div id="embed-modal" class="modal" style="display: block">
  <h3 class="share-header">Share This Widget!</h3>
  <p class="share-header-2">
    Copy the code below and paste it into your website
  </p>
  <!-- FIXME: textarea value -->
  <textarea
    id="embed-code"
    value='<div id="hwcontainer"></div><script src="https://www.nidcd.nih.gov/HWE"></script>'
    on:click={(event) => {
      event.currentTarget.focus()
      event.currentTarget.select
      event.currentTarget.setSelectionRange(0, 9999)
    }}
  />
  <p class="share-text">
    Placement of the NIDCD widget is to be used only as a tool to access NIDCD
    content. The NIDCD widget cannot be edited or appended in any manner. We
    encourage you to use the widget. However, placement of the widget or linking
    to our site does not imply that the NIDCD, the National Institutes of
    Health, or the U.S. Department of Health and Human Service endorse your
    products, services, or ideas.
  </p>
  <p class="share-learn-more">
    Learn more about the
    <a href="https://www.nidcd.nih.gov/health/do-you-need-hearing-test-widget"
      >Hearing Test Widget</a
    >
  </p>
  <div class="return-container">
    <!-- svelte-ignore a11y-invalid-attribute -->
    <a href="#" class="return-link" on:click={() => dispatch('close')}>
      Return
    </a>
  </div>
</div>
