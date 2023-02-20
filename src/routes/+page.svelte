<script>
  import Button from "../button.svelte";
  const actions = [
    {
      name: "Video Bienvenida",
      url: "http://localhost:80/cgi-bin/welcome.cgi",
    },
    {
      name: "Video Corporativo",
      url: "http://localhost:80/cgi-bin/corporate.cgi",
    },
    {
      name: "Porsche Contenido",
      url: "http://localhost:80/cgi-bin/porsche.cgi",
    },
    { name: "VR", url: "http://localhost:80/cgi-bin/vr.cgi" },
    { name: "Porsche + VR", url: "http://localhost:80/cgi-bin/porschevr.cgi" },
    { name: "Power ON", url: "http://localhost:80/cgi-bin/poweron.cgi" },
    { name: "Power OFF", url: "http://localhost:80/cgi-bin/poweroff.cgi" },
    { name: "Background", url: "http://localhost:80/cgi-bin/background.cgi" },
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
