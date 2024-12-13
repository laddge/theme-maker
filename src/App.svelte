<script lang="ts">
  import JSON5 from 'json5'
  import { getColors } from 'theme-colors'

  let mainColor = '#FFFFFF'
  let theme = {
    50: '#FFFFFF',
    100: '#FFFFFF',
    200: '#FFFFFF',
    300: '#FFFFFF',
    400: '#FFFFFF',
    500: '#FFFFFF',
    600: '#E6E6E6',
    700: '#999999',
    800: '#737373',
    900: '#4D4D4D',
    950: '#333333',
  }
  $: {
    theme = getColors(mainColor)
  }
</script>

<main>
  <div class="navbar bg-base-100">
    <div class="btn btn-ghost text-xl">Theme Maker</div>
  </div> 
  <div class="max-w-xl mx-auto p-4">
    <label>
      <input type="color" bind:value={mainColor} class="absolute h-0 w-0" />
      <div class="btn btn-ghost w-full" style={`background-color: ${mainColor};`}>
        <span class="invert grayscale contrast-[100]" style={`color: ${mainColor};`}>Pick Color</span>
      </div>
    </label>
    <div class="p-4">
      {#each Object.entries(theme) as [colorId, color]}
        <div class="flex">
          <div class="w-12 flex justify-end items-center mr-3">{colorId}</div>
          <div class="w-full h-12 flex justify-center items-center" style={`background-color: ${color};`}>
            <span class="invert grayscale contrast-[100]" style={`color: ${color};`}>{color}</span>
          </div>
        </div>
      {/each}
    </div>
    <pre>{JSON5.stringify(theme, null, 2)}</pre>
  </div>
</main>
