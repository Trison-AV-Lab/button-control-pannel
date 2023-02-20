<script>
  import Button from "../button.svelte";
  const actions = [
    { name: "Video Bienvenida", url: "http://localhost:80/welcome.cgi" },
    { name: "Video Corporativo", url: "http://localhost:80/corporate.cgi" },
    { name: "Porsche Contenido", url: "http://localhost:80/porsche.cgi" },
    { name: "VR", url: "http://localhost:80/vr.cgi" },
    { name: "Porsche + VR", url: "http://localhost:80/porschevr.cgi" },
    { name: "Power ON", url: "http://localhost:80/poweron.cgi" },
    { name: "Power OFF", url: "http://localhost:80/poweroff.cgi" },
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
