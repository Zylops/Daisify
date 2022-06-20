<script>
    export let currentSong;
</script>

<div class="flex">
    <img src="{currentSong.cover}" alt="" class="w-16 mx-2">

    <div class="currentSong m-2">
        <h1 class="text-white font-semibold">{currentSong.name}</h1>
        <p class="text-xs">{currentSong.artists.join(', ')}</p>
    </div>
</div>