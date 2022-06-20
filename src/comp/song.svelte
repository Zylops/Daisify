<script>
    export let song;
</script>

<div class="bg-base-300 rounded-md w-44 animate__animated animate__zoomIn">
    <img src="{song.cover}" alt="Shoes" class="w-full"/>
    <div class="p-4">
      <h2 class="font-bold">{song.name}</h2>
        <p class="text-gray-400 text-xs">{song.artists.join(', ')}</p>
    </div>
</div>