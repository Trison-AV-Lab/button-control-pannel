<script>
  import Button from "../button.svelte";
  //on click redirect to url
</script>

{#each [1, 2, 3, 4, 5, 6, 7] as n}
  <Button
    title="Preset {n}"
    onClick={() => {
      let frame__to__load = document.getElementById("frame__url__loader");
      if (frame__to__load) {
        frame__to__load.src = `http://localhost:5173`;
      }
    }}
  />
{/each}

<iframe id="frame__url__loader" title="" />

<style>
  @import "../styles.css";
</style>
