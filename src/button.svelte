<script>
  export let onClick = () => {};
  export let title = "";
</script>

<button class="button" on:click={onClick}>
  {title}
</button>
