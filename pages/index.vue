<template>
<div class="container">
  <nav class="nav">
        <div class="nav-left">
          <div class="logo">
            <a href="/">
              <span class="molai">Molai</span
              ><span class="function">News</span></a
            >
          </div>
        </div>
        <div class="nav-middle">
          <span data-toggle="modal"><a href="#articles">Articles</a></span>
        </div>
        <div class="nav-right">
          <a
            href="mailto:mahir@molai.dev"
            target="_blank"
            >Email Us</a>
        </div>
  </nav>
  <main class="about">
    <img class="av small" src="/logo.png" alt="Logo">
    <h1 class="pname">Molai News</h1>
    <h1 class="name">Molai News</h1>
    <p class="description">Making your voice heard.</p>
  </main>
  <br>
  <main id="articles" class="main">
        <h1>Articles</h1>
        <div class="row">
          <div class="col">
            <div
              class="card card-info"
              v-on:click="redirect('/articles/1')"
            >
              <p class="card-title">Thoughts on Israel</p>
              <div class="card-data">
                <div class="difficulty card-sub">
                  <i class="fas fa-bolt"></i>
                  <p class="data">Mahir Molai</p>
                </div>
              </div>
            </div> 
          </div>
        </div>
  </main>
</div>
</template>

<script>
export default {
  methods: {
    redirect: function (link) {
      if(!link === String) return console.log('Not a string...');

      if(link.startsWith("/")) {
        const redirect = window.location.hostname + link;

        const r = redirect.slice(window.location.hostname.length);

        location = r;

      } else location = link;
    },
    r: function (link) {
      if(!link === String) return console.log('Dumbass thats not a string');

      const l = 'https://' + link;
      location = l;
    }
  }
}
</script>

<style>
@import url("https://cdn.molai.dev/theme.css");

.container {
  height: 100vh;
}

.big {
  font-size: 72px;
}

span > a{
  margin: 25px;
}

main {
  height: 55%;
}

.small {
  border-radius: 50%;
  width: 17%;
  height: auto;
}

.about {
  position: relative;
}

.av {
  position: absolute;
  top: 50%;
  left: 9%;
  transform: translate(-50%, -50%);
}

.name {
  position: absolute;
  top: 43%;
  left: 28%;
  transform: translate(-50%, -50%);
}

.description {
  position: absolute;
  top: 57%;
  left: 33.3%;
  transform: translate(-50%, -50%);
  font-size: 23px;
}

.pname {
  position: absolute;
  display: none;
  transform: translate(-50%, -50%);
}

@media only screen and (max-width: 600px) {
  h1 {
    font-size: 24px;
  }
  p {
    font-size: 10px;
  }

  .name {
    display: none;
  }

  .description {
    display: none;
  }

  .av {
    width: 35%;
    height: auto;
    left: 50%;
    top: 45%;
  }

  .pname {
    display: block;
    top: 75.75%;
    left: 50.9%;
    font-size: 34px;
    white-space: nowrap;
  }
}
</style>