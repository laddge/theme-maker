<script lang="ts">
  let mainColor = '#fff'
</script>

<main>
  <div class="navbar bg-base-100">
    <div class="btn btn-ghost text-xl">Theme Maker</div>
  </div> 
  <div class="max-w-xl mx-auto p-4">
    <label>
      <input type="color" bind:value={mainColor} class="absolute h-0 w-0" />
      <div class="btn btn-ghost w-full" style={`background-color: ${mainColor};`}>
        <span class="mix-blend-difference">Pick Color</span>
      </div>
    </label>
  </div>
</main>
