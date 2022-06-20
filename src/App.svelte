<script>
  import Song from './comp/song.svelte';
  import MainMenu from './comp/mainMenu.svelte'
  import MenuItem from './comp/menuItem.svelte'
  import PlaylistItem from './comp/PlaylistItem.svelte'
  import UserPill from './comp/UserPill.svelte'
  import Playlist from './comp/Playlist.svelte'
  import Controls from './comp/controls.svelte'
  import CurrentSong from './comp/currentSong.svelte'
  import Volume from './comp/volume.svelte'

  let currentSong = {
    "name": "A very real song",
    "cover": "https://avatars.dicebear.com/api/adventurer-neutral/real.svg",
    "artists": ["very real artist"]
  }

  let playlists = [
    {
      "name": "The Lorem Ipsum Playlist",
      "cover": "https://api.lorem.space/image?w=350&h=300"
    }
  ]

  let songs = [
    {
      "name": "Song",
      'artists': ['Bob', 'Jeff'],
      'cover': 'https://avatars.dicebear.com/api/adventurer-neutral/test.svg'
    },

    {
      "name": "Objectively Better Song",
      'artists': ['John', 'Joe'],
      'cover': 'https://avatars.dicebear.com/api/adventurer-neutral/john.svg'
    },

    {
      "name": "Dont Wanna Get DMCA'd",
      'artists': ['Zylops'],
      'cover': 'https://avatars.dicebear.com/api/adventurer-neutral/Zylops.svg'
    },

    {
      "name": "Gotta Make Up Fake Song Names",
      'artists': ['Zylops'],
      'cover': 'https://avatars.dicebear.com/api/adventurer-neutral/zylops.svg'
    }
  ]
</script>

<body class="bg-gradient-to-b from-indigo-500 to-black ">
    <div class="grid grid-cols-6 h-screen">
        <div class="bg-gray-900 text-white col-span-1 p-4 animate__animated animate__fadeInLeft">
            <MainMenu/>

            <ul class="mt-4 p-2">
              <MenuItem><i class="bi-plus-square-fill mr-2 text-xl"></i> Create Playlist</MenuItem>

              <MenuItem><i class="bi-bookmark-heart-fill mr-2 text-xl"></i> Liked Songs</MenuItem>

              <MenuItem><i class="bi-broadcast-pin mr-2 text-xl"></i> Your Episodes</MenuItem>
                
              <MenuItem><i class="bi-brightness-low-fill mr-2 text-xl"></i> Made For You</MenuItem>
            </ul>

            <div class="divider p-2 m-1 animate__animated animate__zoomIn"></div>

            <ul class="p-2">
              {#each playlists as playlist}
                <PlaylistItem {playlist}/>
              {/each}
            </ul>
        </div>

        <div class="text-white col-span-5 p-4 h-full">
            <UserPill/>

            <h1 class="text-2xl font-bold animate__animated animate__fadeInDown">Good afternoon.</h1>
            <div class="playlists flex gap-2">
                {#each playlists as playlist}
                  <Playlist {playlist}/>
                {/each}
            </div>

            <div class="divider animate__animated animate__zoomIn"></div>

            <h1 class="text-xl p-2 font-bold mt-4 animate__animated animate__fadeInDown">Jump back in:</h1>
            <div class="px-2 flex gap-4">
              {#each songs as song}
                <Song {song}/>
              {/each}
            </div>
        </div>
        </div>

    <div class="player w-full bg-base-300 flex justify-between items-center fixed inset-x-0 bottom-0">
        <CurrentSong {currentSong}/>

        <Controls/>

        <Volume/>
    </div>
  </body>