<script lang="ts">
  export let entry;
  export let options;
  export let modelColumn;
  export let labelColumn;
  export let dataColumn;
  export let idColumn;
</script>

<div class="box" style:background-color="white">
  <img
    src={entry[dataColumn]}
    style:max-width="200px"
    loading="lazy"
    alt="Image thumbnail for instance {entry[idColumn]}"
  />
  <br />
  <div class="text">
    <span class="label">label: </span>
    <span class="value">{entry[labelColumn]}</span>
  </div>
  {#if modelColumn && entry[modelColumn]}
    <div class="text">
      <span class="label">output: </span>
      <span class="value">{entry[modelColumn]} </span>
    </div>
  {/if}
</div>

<style>
  .label {
    margin-right: 5px;
    font-size: 10px;
    color: rgba(0, 0, 0, 0.5);
    font-variant: small-caps;
  }
  .text {
    display: flex;
    flex-direction: row;
  }
  .value {
    font-size: 10px;
  }
  .box {
    width: min-content;
    padding: 5px;
    border: 0.5px solid rgb(224, 224, 224);
  }
</style>
