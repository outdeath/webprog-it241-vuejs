<template>
  <main class="panel">
    <section class="grid">

      <!-- LEFT COLUMN -->
      <div class="left-col">

        <!-- IMAGE TILE -->
        <div class="box avatar-box">
          <img
            src="https://i.pinimg.com/originals/68/b2/95/68b2950c09fe35541f08c756a4c21e9f.gif"
            alt="avatar"
          />
        </div>

        <!-- LINKS TILE -->
        <div class="box links-box">
          <ul>
            <li><strong><a href="https://instagram.com/9ravesites" target="_blank">instagram</a></strong></li>
            <li><strong><a href="https://x.com/fawnfacts" target="_blank">twitter</a></strong></li>
            <li><strong><a href="https://github.com/outdeath" target="_blank">github</a></strong></li>
            <li><strong><a href="https://open.spotify.com/user/ezyhmnapdzi51b3vj8h9nkrmv" target="_blank">spotify</a></strong></li>
          </ul>
        </div>

        <!-- STAMPS -->
        <div class="box stamps-box">
          <img src="https://pix.crd.co/assets/images/gallery14/c75b76f4.png?v=c10c78ee">
          <img src="https://pix.crd.co/assets/images/gallery14/889c9e75.png?v=c10c78ee">
          <img src="https://pix.crd.co/assets/images/gallery14/f28ab42a.gif?v=c10c78ee">
          <img src="https://supplies.ju.mp/assets/images/gallery01/0383b620.png?v=1c1ba870">
        </div>

      </div>

      <!-- RIGHT COLUMN -->
      <div class="right-col">

        <div class="box intro-box">
          <h3>(o _ o) about me . . .</h3>
          <p>
            hallo!! I'm Charlize Jacee G. Garcia, or you can just call me CJ for short!
            I use he/him pronouns but I also use she/her.
            I'm turning 21 on September, a libra.
            My friends often describe me as shy and introverted.
            <img src="https://sweetie.crd.co/assets/images/gallery05/cdf36e97.gif?v=d780b57c">
            I truly adore seals, deers, and otters!
            You can hear me sometimes ramble about them to my friends.
            I love listening to Joji and Malcolm Todd,
            band wise I find myself listening to Rob Zombie,
            Nine Inch Nails, and Korn.
          </p>
        </div>

        <div class="box interests-box">
          <h3>Education / Achievements</h3>
          <p>
            Graduated in Far Eastern University (FEU) Alabang <br>
            Graduated Gradeschool/Highschool at Statefields School Inc. (SSI) Cavite
          </p>
          <h3>Course</h3>
          <p>Bachelor of Science in Information Technology</p>
          <h3>IT Experience</h3>
          <p>basic html and css, Python, javascript, MySQL, use of Flutter.</p>
        </div>

        <div class="box contact-box">
          <h3>Hobbies & Interests</h3>
          <p>
            I like to draw, play games and play with my toys.
            I also love doomscrolling and napping, no joke!
          </p>
          <h3>Goals In Life / Dream</h3>
          <p>
            I wish to live in a ranch and live comfortably rich
            with 4 cats and a horse.
          </p>
        </div>

      </div>
    </section>
  </main>

  <!-- GALLERY -->
  <section class="panel gallery-panel">
    <h3>Gallery</h3>
    <div class="gallery-wrapper">
      <button class="gallery-btn" @click="scrollGallery(-1)">‹</button>

      <div class="gallery-strip" ref="galleryStrip">
        <img src="https://files.catbox.moe/z51k27.png">
        <img src="https://files.catbox.moe/hp0p3w.png">
        <img src="https://files.catbox.moe/k79avg.png">
        <img src="https://files.catbox.moe/exjk4b.png">
        <img src="https://files.catbox.moe/fyddc4.png">
      </div>

      <button class="gallery-btn" @click="scrollGallery(1)">›</button>
    </div>
  </section>

  <!-- GUESTBOOK -->
  <section class="panel guestbook-panel">
    <h3>Guestbook</h3>

    <form @submit.prevent="submitGuest">
      <input v-model="guestName" placeholder="Name (optional)">
      <textarea v-model="guestMsg" placeholder="Leave a message..." required></textarea>
      <button type="submit">Post</button>
    </form>

    <div id="guestbookEntries">
      <div class="guest-entry" v-for="(entry, i) in entries" :key="i">
        <strong>{{ entry.name }}:</strong> {{ entry.msg }}
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      guestName: "",
      guestMsg: "",
      entries: []
    };
  },
  methods: {
    scrollGallery(dir) {
      this.$refs.galleryStrip.scrollBy({
        left: dir * 160,
        behavior: "smooth"
      });
    },
    submitGuest() {
      this.entries.unshift({
        name: this.guestName || "anon",
        msg: this.guestMsg
      });
      this.guestName = "";
      this.guestMsg = "";
    }
  }
};
</script>

<style>
@import "./css/dot.css";
</style>
