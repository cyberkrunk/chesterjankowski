---
title: pod-ette
layout: layouts/base.njk
---

# pod-ette

[*pod-ette*](http://ettereview.com/podette) is the companion podcast to [*-ette review*](http://ettereview.com), an online literary magazine of short fiction and prose poetry, which was founded by [Beth Hahn](http://beth-hahn.com) and [Nora Maynard](http://www.noramaynard.com) in 2023. One of the things that makes *-ette* great is that for each work published in the magazine, Beth creates an original artwork to complement the piece—and that artwork is then given to the writer as a thank you.

The idea of a companion podcast was also part of the initial conception, and the brainchild of [Melanie Hoopes](http://www.melaniehoopes.com/), a writer, actor, and podcast producer. My own contribution to the project came in the form of a question: “What if, podcast music—that wasn’t terrible?” Perhaps that overstating things a bit, but I had long noted a big gap between the quality of podcasts and their music. So, I found the notion of doing high-quality bespoke music for each episode quite appealing, and thankfully, Melanie, Beth, and Nora agreed.

## Episode 6

In this episode, the opening and closing themes are once again played with solo piano, but this time, compared to episode 5, a little quicker and a little brighter. Interstitial 1 comes immediately after [Rachel Kowalsky](http://www.rachelkowalskymd.com/)’s story [*Dear Dolores*](https://ettereview.com/fall2025/kowalsky/), which is a very cool story about a dialogue that takes place between an E.R. doctor and her medical note reviewer as a series of messages within the [EPIC](https://en.wikipedia.org/wiki/Epic_Systems) system. I like this story very much, and find more details every time I read it, but I didn’t have a *musical* reaction to it right away. Until one night, just as I was falling asleep, it hit me: “Counterpoint!” The next morning, I wrote the cue, which is a brief two-part dialgoue in which tension between the two voices gives way to consonance and resolution.

Interstitial 2 is a brief “spacer” between the two stories. It serves to lower the tension and transition to the next piece. A descending figure, based on two tetrachords with progressively smaller intervals. The subdominant Ab, in contrast to the Eb of the main theme. The piano sound combined with the echo of its own sustained resonance after the notes are struck.

[Matt Liebel](https://www.mattleibel.com/)’s piece [*How to Buy a Snow Globe*](https://ettereview.com/fall2025/leibel/), I found musically evocative, especially with Melanie’s reading of the piece on the podcast. Shimmering high strings, a “shaking” motive in the piano, giving way to arpeggios that end on the theme’s home chord.

<div id="audio-playlist">
    <span class="playlist-name">pod-ette episode 6 music</span>
    <ul id="playlist-ul"></ul>
        <div id="playlist-buttons">
            <button onclick="playPrevSong()"><<</button>
            <button onclick="playNextSong()">>></button>
        </div>
    <audio id="audio-player" controls></audio>  
</div>

<script eleventy:ignore>
const audioPlayer = document.getElementById('audio-player');

const playlist = {
  track: [
    { src: "/audio/pod-ette-ep-06-open.mp3", title: "Opening theme" },
    { src: "/audio/pod-ette-ep-06-int-1.mp3", title: "Interstitial 1: Dear Dolores" },
    { src: "/audio/pod-ette-ep-06-int-2.mp3", title: "Interstitial 2" },
    { src: "/audio/pod-ette-ep-06-int-3.mp3", title: "Interstitial 3: How to Buy a Snow Globe" },
    { src: "/audio/pod-ette-ep-06-close.mp3", title: "Closing theme" }
  ]
};

// generate the ul from the playlist object
const playlistUl = document.getElementById('playlist-ul');
playlist.track.forEach((track, index) => {
  const listItem = document.createElement('li');
  listItem.textContent = track.title;
  listItem.dataset.index = index; 
  playlistUl.appendChild(listItem);
});

playlistUl.addEventListener('click', (event) => {
  const clickedItem = event.target;
  if (clickedItem.tagName === 'LI') {
  const currentlyPlaying = document.querySelector('.now-playing');
    if (currentlyPlaying) {
        currentlyPlaying.classList.remove('now-playing');
      }
  clickedItem.classList.add('now-playing');
  const index = parseInt(clickedItem.dataset.index, 10);
  loadAndPlaySong(index);
  currentSongIndex = index;
  updateNowPlayingUI();
  }
});

// init the player
let currentSongIndex = 0;
updateNowPlayingUI();
audioPlayer.src = playlist.track[0].src;
audioPlayer.load();

function loadAndPlaySong(index) {
  audioPlayer.src = playlist.track[index].src;
  audioPlayer.load();
  audioPlayer.play();
  updateNowPlayingUI();
}

function playNextSong() {
  // Increment the index, do nothing if at end
  currentSongIndex = (currentSongIndex + 1);
  if (currentSongIndex > playlist.track.length - 1) {
    currentSongIndex = playlist.track.length - 1
  } else {
  loadAndPlaySong(currentSongIndex);
  }
}

function playPrevSong() {
  // Decrement the index, and repeat the first track if at the beginning
  currentSongIndex = (currentSongIndex - 1);
  if (currentSongIndex < 0) {
    currentSongIndex = 0
  }
  loadAndPlaySong(currentSongIndex);
}

// autoplay the track list
audioPlayer.addEventListener('ended', playNextSong);

// highlight the currently playing track
function updateNowPlayingUI() {
  const currentlyPlaying = playlistUl.querySelector('.now-playing');
  if (currentlyPlaying) {
    currentlyPlaying.classList.remove('now-playing');
  }
  const newPlayingItem = playlistUl.querySelector(`[data-index="${currentSongIndex}"]`);
  if (newPlayingItem) {
    newPlayingItem.classList.add('now-playing');
  }
}
</script>

## The full episodes:

[Episode 6—Roulette: Take a Chance on Art](https://open.spotify.com/episode/60GBYE6bYWWQJXf7YgdHLi)

[Episode 5—The Villa of Mysteries](https://open.spotify.com/episode/2VOmR6xnKrBTYbxvOGZanl)

[Episode 4—The Looming (Planchette)](https://open.spotify.com/episode/2mw9OItZNHrOzCXDw9iuT8)

[Episode 3—Cavett(e)'s Wrong](https://open.spotify.com/episode/493eSgFTEweKakkHKa6lky)

[Episode 2—Cassette](https://open.spotify.com/episode/3bfoCAet3HnhRSAMGKMRFR)

[Episode 1—If I Could Remake the World](https://open.spotify.com/episode/1A7AxHgRAkpVIGYWzSRRTs)