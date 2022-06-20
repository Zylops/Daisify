<script>
    export let playlist;
</script>

<div class="animate__animated animate__zoomIn card card-compact w-50 bg-base-100 mt-2 image-full h-24">
    <figure><img src="{playlist.cover}" alt="Shoes" /></figure>
    <div class="card-body">
      <h2 class="card-title">{playlist.name}</h2>
    </div>
</div>