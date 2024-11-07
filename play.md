---

<iframe>
<script setup>
import { ref, watch } from 'vue'

// Initialize reactive variables
const rootFontSize = ref(16)

// Function to update root font size
function updateRootFontSize(event) {
  rootFontSize.value = parseInt(event.target.value) || 16
}

// Watch for changes in rootFontSize and apply to <html> element
watch(rootFontSize, (newSize) => {
  document.documentElement.style.fontSize = `${newSize}px`
})
</script>

<style>

  .slidev-layout {
    padding: 20px; 
  }

  #boxInRem {
    width: 8rem;
    height: 8rem;
    background-color: #4A90E2;
    font-size: 1rem;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  #boxInPx {
    width: 128px;
    height: 128px;
    background-color: #E24A4A;
    font-size: 16px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  #fontSize {
    background-color: #fff;
    color: #000;
    text-align: center;
  }
</style>

  <div style="display: flex; flex-direction: column; gap: 20px; align-items: center;">
    
    <div style="margin-bottom: 20px; font-size: 16px;">
      <label for="fontSize">Set Root Font Size (px): </label>
      <input style="width: 50px; " id="fontSize" type="number" :value="rootFontSize" @input="updateRootFontSize" />
    </div>

    <div style="display: flex; gap: 20px; align-items: center;">
      <div id="boxInRem">Box 4x4 rem</div>
      <div id="boxInPx">Box 128x128 px</div>
    </div>

  </div>
</iframe>
