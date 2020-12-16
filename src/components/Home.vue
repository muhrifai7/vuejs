<template>
  <nav>
    <div v-if="name" id="logo">
      <img src="../assets/icons/app.png" height="40" />
    </div>
    <div v-else id="logo">
      <img v-bind:src="logoImg" alt="Logo" />
    </div>

    <ul class="nav-links">
      <li v-for="list in navLinks" :key="list.key">
        <a v-if="list.dropdown === false" :href="list.link">{{ list.name }}</a>
        <div class="dropdown-link" v-else>
          <a :href="list.link">
            {{ list.name }}
            <span>&#x2193;</span>
          </a>
          <ul class="dropdown-menu">
            <li v-for="item in list.dropdownLinks" :key="item.key">
              <a :href="item.link">{{ item.name }}</a>
            </li>
          </ul>
        </div>
      </li>
    </ul>

    <div v-on:click="openMobileNav()" id="burger">
      <div class="line1"></div>
      <div class="line2"></div>
      <div class="line3"></div>
    </div>
  </nav>

  <section class="banner_container">
    <div class="section_banner">
      <div id="image1">
        <img src="../assets/images/laptop1.jpg" />
        <div class="brand_text-container">
          <p class="text-brand">
            <span class="brand_title">Booked Tools </span>Enable You to create
            interactive advertisement
          </p>
          <br />
          <button id="btn">What is it</button>
        </div>
      </div>
      <div id="image2">
        <img src="../assets/images/laptop2.png" />
      </div>
    </div>
    <div class="form_booked">
      <div>
        <p>Please Log In To Star Using</p>
        <p class="subtitle">Booked Tool</p>
      </div>
      <input v-model="message" class="input_form" placeholder="Email" />
      <input v-model="message" class="input_form" placeholder="Password" />
      <div><button id="btn">What is it</button></div>
    </div>
  </section>

  <!-- discover -->
  <section class="discover_container">
    <img src="../assets/icons/dicover_icon.jpg" height="50" width="50" />
    <p class="brand_title">Discover</p>
    <p class="text-header">Booked Tool</p>
    <div id="discover_image">
      <img src="../assets/images/discover.jpg" height="300" width="450" />
    </div>
    <div class="discover_taps">
      <div class="container_button">
        <p class="discover_button" v-on:click="openTaps('dis_a')">
          Discover A
        </p>
      </div>
      <div class="container_button">
        <p class="discover_button" v-on:click="openTaps('dis_b')">
          Discover B
        </p>
      </div>
      <div class="container_button">
        <p class="discover_button" v-on:click="openTaps('dis_c')">
          Discover C
        </p>
      </div>
      <div class="container_button">
        <p class="discover_button" v-on:click="openTaps('dis_d')">
          Discover D
        </p>
      </div>
    </div>
    <div id="hr"></div>
    <div class="value_taps">
      <div id="dis_a" class="taps_value">
        <p>
          On the other hand, we denounce with righteous indignation and dislike
          men who are so beguiled and demoralized by the charms of pleasure of
          the moment, so blinded by desire, that they cannot foresee the pain
          and trouble that are bound to ensue; and equal blame belongs to those
          who fail in their duty through weakness of will, which is the same as
          saying through shrinking from toil and pain. These cases are perfectly
          simple and easy to distingui
        </p>
      </div>

      <div id="dis_b" class="taps_value" style="display:none">
        <p>
          equal blame belongs to those who fail in their duty through weakness
          of will, which is the same as saying through shrinking from toil and
          pain. These cases are perfectly simple and easy to distingui,On the
          other hand, we denounce with righteous indignation and dislike men who
          are so beguiled and demoralized by the charms of pleasure of the
          moment, so blinded by desire, that they cannot foresee the pain and
          trouble that are bound to ensue; and
        </p>
      </div>

      <div id="dis_c" class="taps_value" style="display:none">
        <p>
          are so beguiled and demoralized by the charms of pleasure of the
          moment, so blinded by desire, that they cannot foresee the pain and
          trouble that are bound to ensue; and equal blame belongs to those who
          fail in tOn the other hand, we denounce with righteous indignation and
          dislike men who
        </p>
      </div>
      <div id="dis_d" class="taps_value" style="display:none">
        <p>
          So blinded by desire, that they cannot foresee the pain and trouble
          that are bound to ensue; and equal blame belongs to those who fail in
          their duty through weakness of will, which is the same as saying
          through shrinking guiled and demoralized by the charms of pleasure of
          the moment, so blinded by desire, that they cannot foresee the pain
          and trouble that are bound to ensue; and equal blame belongs to those
          who fail in their duty through weakness of will, which is the same as
          saying through shrinking from toil and pain. These cases are perfectly
          simple and easy to distingui
        </p>
      </div>
    </div>
  </section>
  <!-- register? -->
  <section class="register">
    <div class="container_search">
      <img
        src="https://img.icons8.com/carbon-copy/2x/image.png"
        height="50"
        width="50"
      />
      <p class="subtitle">Get In Touch</p>
      <p class="text-append">
        Want to get In Touch?We Love to Hear From You,Here you can reach
      </p>

      <input v-model="message" id="search" placeholder="Search" />
    </div>
    <div class="container_form">
      <!-- maps -->
      <div id="maps">
        <h1>Maps</h1>
      </div>
      <!-- forms -->
      <div>
        <form id="form_feed">
          <div>
            <input type="text" class="input_form" value="John" />
            <input type="text" class="input_form" name="lname" value="Doe" />
          </div>
          <input type="text" class="input_form" name="fname" value="John" />
          <input type="text" class="input_form" name="fname" value="John" />
          <button id="send">Send</button>
        </form>
      </div>
    </div>
  </section>
  <footer class="footer-booked">
    <div class="footer-left">
      <p class="footer-links">
        <a href="#">Home</a>

        <a href="#">Discover</a>

        <a href="#">Register</a>

        <a href="#">Search</a>
      </p>
    </div>
  </footer>
</template>

<script>
export default {
  name: "Navbar",
  props: ["name", "logoImg", "navLinks"],
  methods: {
    openMobileNav() {
      const burger = document.getElementById("burger");
      const nav = document.querySelector(".nav-links");
      const navLinks = document.querySelectorAll(".nav-links li");
      nav.classList.toggle("nav-active");
      burger.classList.toggle("toggle");
      navLinks.forEach((link, index) => {
        if (link.style.animation || link.style.webkitAnimation) {
          link.style.animation = "";
          link.style.webkitAnimation = "";
        } else {
          link.style.webkitAnimation = `navLinkFade 0.5s ease forwards ${index /
            7}s`;
          link.style.animation = `navLinkFade 0.5s ease forwards ${index / 7}s`;
        }
      });
    },
    openDropdownNav() {
      const dropdownLink = document.querySelectorAll(".dropdown-link");
      dropdownLink.forEach((dropdown) => {
        dropdown.addEventListener("mouseover", () => {
          dropdown.children[1].style.display = "block";
        });
        dropdown.addEventListener("mouseleave", () => {
          dropdown.children[1].style.display = "none";
        });
      });
    },
    openTaps: function(discover) {
      var i;
      var x = document.getElementsByClassName("taps_value");
      for (i = 0; i < x.length; i++) {
        x[i].style.display = "none";
      }
      document.getElementById(discover).style.display = "block";
    },

    countClicksOnMobileDropdown() {
      const dropdownLink = document.querySelectorAll(".dropdown-link");
      dropdownLink.forEach((dropdown) => {
        let counts = dropdown.clicks || 0;
        dropdown.addEventListener("click", () => {
          counts++;
          if (counts % 2 == 0) {
            window.location.href = dropdown.children[0].getAttribute("href");
          } else {
            event.preventDefault();
            dropdown.children[1].style.display = "block";
            setTimeout(() => {
              dropdown.children[1].style.display = "none";
            }, 5000);
          }
        });
        setTimeout(() => {
          counts = 0;
        }, 8000);
      });
    },
  },
  mounted() {
    this.openDropdownNav();
    if (window.innerWidth < 768) {
      this.countClicksOnMobileDropdown();
    }
  },
};
</script>

<style lang="scss">
.footer-booked .footer-links a {
  display: inline-block;
  line-height: 1.8;
  text-decoration: none;
  color: inherit;
  padding: 10px;
}
</style>
