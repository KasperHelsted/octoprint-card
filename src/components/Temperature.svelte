<svelte:options tag="octoprint-card-temperature" />

<script lang="ts">
  export let actual: { value: string; unit: string };
  export let target: { value: string; unit: string };
  export let label: string;
  export let cssClass: string;
</script>

<div class={`temperature ${cssClass}`}>
  {#if actual}
    <b>
      {actual?.value}{actual?.unit}
      {#if target}
        / {target?.value}{target?.unit}
      {/if}
    </b>
  {:else}
    <b>Unavailable</b>
  {/if}

  {#if label}
    <span>{label}</span>
  {/if}
</div>
