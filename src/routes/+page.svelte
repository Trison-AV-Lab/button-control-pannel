<script>
  import Button from "../button.svelte";
  const actions = [
    { name: "Video Bienvenida", url: "http://localhost:80/welcome" },
    { name: "Video Corporativo", url: "http://localhost:80/corporate" },
    { name: "Porsche Contenido", url: "http://localhost:80/porsche" },
    { name: "VR", url: "http://localhost:80/vr" },
    { name: "Porsche + VR", url: "http://localhost:80/porschevr" },
    { name: "Power ON", url: "http://localhost:80/poweron" },
    { name: "Power OFF", url: "http://localhost:80/poweroff" },
  ];
</script>

{#each actions as action}
  <Button
    title={action.name}
    onClick={() => {
      let frame__to__load = document.getElementById("frame__url__loader");
      if (frame__to__load) {
        frame__to__load.src = `http://localhost:80/${action.url}`;
      }
    }}
  />
{/each}

<iframe id="frame__url__loader" title="" />

<style>
  @import "../styles.css";
</style>
