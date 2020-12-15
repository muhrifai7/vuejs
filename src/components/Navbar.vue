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
      // Toggle navigation on mobile
      nav.classList.toggle("nav-active");
      // Burger toggler
      burger.classList.toggle("toggle");
      // Animate navigation links
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

<style>
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-right: 3rem;
  padding-left: 3rem;
  background-color: #f1f2f6;
  min-height: 7vh;
  font-family: "Montserrat", sans-serif;
}
div#logo {
  letter-spacing: 4px;
  color: #fefefe;
  font-weight: 800;
  font-size: 1rem;
}
ul.nav-links {
  display: flex;
  justify-content: space-between;
  /* width: 30%; */
}
ul.nav-links li {
  list-style: none;
}

ul.nav-links a {
  text-decoration: none;
  color: #34495e;
  font-size: 0.9rem;
  font-weight: 500;
  /* display: block; */
  padding-top: 5px;
  padding-bottom: 5px;
  padding-left: 15px;
  padding-right: 15px;
}

ul.nav-links a:hover {
  background-color: #95a5a6;
  border-radius: 10px;
}

li {
  display: inline;
  padding: 20px;
}

#burger {
  display: none;
  cursor: pointer;
}
#burger div {
  width: 30px;
  height: 3px;
  margin: 8px;
  background-color: #fefefe;
  transition: all 0.3s ease-in;
}
ul.dropdown-menu {
  position: absolute;
  top: 8vh;
  background-color: #966d6d;
  min-width: 140px;
  cursor: pointer;
  display: none;
}
ul.dropdown-menu li:first-child {
  margin: 0 0 10px 0;
}
ul.dropdown-menu li {
  margin: 10px 0;
}
ul.dropdown-menu li:last-child {
  margin: 10px 0 0 0;
}
ul.dropdown-menu a {
  line-height: 8vh;
  padding: 5px 15px;
  background-color: #f1d1d1;
  line-height: 50px;
}
/* Tablet */
@media screen and (max-width: 1024px) {
  ul.nav-links {
    width: 50%;
  }
}

/* Mobile */
@media screen and (max-width: 768px) {
  ul.nav-links {
    position: absolute;
    flex-direction: column;
    width: 100%;
    height: 120vh;
    top: 15vh;
    right: 0;
    padding: 100px;
    align-items: center;
    justify-content: flex-start;
    background-color: #cac6c6;
    opacity: 0.8;
    z-index: 10000;
    transform: translateX(100%);
    transition: transform 0.5s ease-in;
  }
  ul.nav-links li {
    opacity: 0;
  }
  ul.nav-links a {
    width: 100%;
  }
  div#burger {
    display: block;
  }
  ul.dropdown-menu {
    position: relative;
    top: 0;
  }

  .form_booked {
    width: 50%;
  }
}
.nav-active {
  transform: translateX(0) !important;
}
@keyframes navLinkFade {
  from {
    opacity: 0;
    transform: translateX(-60px);
  }
  to {
    opacity: 1;
    transform: translateX(0px);
  }
}
.toggle .line1 {
  transform: rotate(-45deg) translate(-9px, 10px);
}
.toggle .line2 {
  opacity: 0;
}
.toggle .line3 {
  transform: rotate(45deg) translate(-5px, -6px);
}

#image1 {
  background: linear-gradient(90deg, white);
  background-attachment: fixed;
  background-size: cover;
  overflow: hidden;
  color: white;
  width: 100%;
  height: auto;
  position: relative;
}

.banner_container {
  background-color: #f1f2f6;
  box-sizing: border-box;
}

#image1 img {
  max-height: 500px;
}

#image2 {
  background-attachment: fixed;
  background-size: cover;
  overflow: hidden;
  color: white;
  padding-bottom: 20px;
  width: 100%;
  height: auto;
  margin-left: -30px;
  position: relative;
}

#image2 img {
  width: 100%;
  max-height: 400px;
  min-height: 400px;
}

.section_banner {
  display: flex;
}

.brand_text-container {
  position: absolute;
  flex-wrap: wrap;
  max-width: 230px;
  padding: 10px;
  top: 50%;
  left: 70%;
  transform: translate(-50%, -50%);
  overflow: hidden;
}

#btn {
  border: none;
  color: white;
  padding: 13px 23px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 12px;
  margin: 1px 2px;
  cursor: pointer;
  background-color: #2980b9;
  border-radius: 10px;
}
.brand_title {
  font-size: 1.6rem;
  color: #020a11;
  font-weight: bold;
}
.text-append {
  margin-bottom: 1.5rem;
  line-height: 15px;
}
.text-brand {
  color: #34495e;
}

.input_form {
  margin: 5px 10px;
  border: none;
  padding: 6px 10px;
  border-radius: 3px;
}

.container_search {
  display: grid;
  place-items: center;
}

#hr {
  background-color: #b9c9d6;
  height: 1px;
  width: 34%;
  margin-bottom: 1.5rem;
}

.text-append #get_intouch {
  font-size: 30px;
}

.text-header {
  font-size: 18px;
}
.form_booked {
  padding: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0 auto;
  flex-wrap: wrap;
  overflow: hidden;
  background-color: #f1f2f6;
}

.subtitle {
  font-size: 20px;
}

.discover_container {
  align-items: center;
  padding: 10px;
  margin-top: 10px;
  margin-bottom: 10px;
  display: flex;
  flex-direction: column;
}

#discover_image {
  background-size: cover;
  overflow: hidden;
  color: white;
  padding-bottom: 20px;
  /* width: 100%; */
  height: auto;
  margin: 10px 0px;
  border-radius: 10px;
}

#discover_image img {
  border-radius: 3%;
}

.discover_taps {
  margin-top: 10px;
  display: flex;
}

.container_button {
  cursor: pointer;
}
.discover_button {
  margin: 10px 17px;
  border: none;
  background-color: none;
}
.container_button :hover {
  color: red;
}

.value_taps {
  display: flex;
  justify-content: center;
}

.taps_value {
  width: 35%;
  overflow: hidden;
}
.register {
  background-color: #e8edf0;
  align-items: center;
  min-height: 400px;
}

#form_feed {
  display: flex;
  flex-direction: column;
}

.container_form {
  display: flex;
  justify-content: center;
  margin-top: 20px;
}

footer {
  position: fixed;
  bottom: 0;
}

.footer-booked {
  background-color: #292c2f;
  box-shadow: 0 1px 1px 0 rgba(0, 0, 0, 0.12);
  box-sizing: border-box;
  width: 100%;
  text-align: right;
  font: bold 16px sans-serif;
}

.footer-booked .footer-links {
  color: #f1f2f6;
  margin: 5px 0 5px;
  padding: 5px;
}

#search {
  padding: 8px 20px;
  margin: 0 10px;
  border: none;
  border-radius: 3px;
}

#maps {
  /* width: 30%; */
  background-color: red;
}

#send {
  width: 120px;
  margin-left: 10px;
  border: none;
  color: white;
  padding: 10px 10px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 12px;
  margin: 1px 10px;
  cursor: pointer;
  background-color: #2980b9;
  border-radius: 10px;
}

.footer-booked .footer-links a {
  display: inline-block;
  line-height: 1.8;
  text-decoration: none;
  color: inherit;
  padding: 10px;
}

body {
  font-family: charter, Georgia, Cambria, "Times New Roman", Times, serif;
}
</style>
