<script lang="ts">
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher<{ close: undefined }>();
</script>

<div id="info-modal" class="modal" style="display: block">
  <h3 class="info-header">Information</h3>
  <div class="info-text">
    <p>
      One in six adults in the U.S. reports trouble hearing. Hearing problems
      can be serious.
    </p>
    <p>
      If you or a loved one shows signs of hearing problems, talk with your
      doctor, an otolaryngologist (an ear, nose, and throat doctor), an
      audiologist, or a hearing instrument specialist.
    </p>
    <p>
      Protect your ears from sounds that are too loud and loud sounds that last
      too long.
    </p>
  </div>
  <div class="learn-date-text">
    <p>
      Learn what you can do at
      <a href="https://www.nidcd.nih.gov/health/hearing"
        >www.nidcd.nih.gov/hearing</a
      >.
    </p>
    <p id="date-text">April 2016</p>
  </div>
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
