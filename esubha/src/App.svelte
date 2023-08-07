<script>
  let clicks = 0; // click counter
  let displayclicks = 0;
  let tasbih = [
    "Subhan Allah سُبْحَانَ ٱللَّٰهِ",
    "Alhamd-u-Lilah ٱلْحَمْدُ لِلَّٰهِ‎",
    "Allah-u-Akbar ٱللَّٰهُ أَكْبَرُ"
  ]
  let displayTasbih = tasbih[0];

  function tasbihType() {
    if (clicks <= 33) {
      displayTasbih = tasbih[0];
    } else if (clicks > 33 && clicks <= 66) {
      displayTasbih = tasbih[1];
      displayclicks = 0;
    } else if (clicks > 66 && clicks <= 99) {
      displayTasbih = tasbih[2];
      displayclicks = 0;
    }
  }

  function increment() {
    clicks += 1; // increases click count by 1
    displayclicks += 1;
    tasbihType(); // Call tasbihType function after incrementing clicks
  }

  function reset() {
    clicks = 0;
    displayclicks = 0;
    displayTasbih = tasbih[0]; // Reset displayTasbih to the initial phrase
  }
</script>

<h1 class="text-center text-3xl font-bold font-mono m-5 mb-20">
  <!-- Title -->
  Tasbih Counter
</h1>

<div class="text-center text-3xl font-bold font-mono m-5 mb-20">
  <!-- Subha Screen -->
  <p class="border- border-2 p-9 pr-1 pl-1 rounded-xl ">{displayTasbih}</p>
</div>

<div class="flex flex-col items-center justify-center">
  <!-- Buttons -->
  <button class="btn bg-teal-500 p-20 m-5 rounded-xl block hover:bg-teal-400 font-mono mt-10" on:click={increment}>
    Button clicked {clicks} times 
  </button>
  <button class="btn bg-red-500 p-1 m-2 rounded-md block hover:bg-red-400 font-mono" on:click={reset}>
    Reset counter
  </button>
</div>
