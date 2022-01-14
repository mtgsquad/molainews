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
          <span data-toggle="modal"><a href="/#articles">Articles</a></span>
        </div>
        <div class="nav-right">
          <a
            href="mailto:mahir@molai.dev"
            target="_blank"
            >Email Us</a>
        </div>
  </nav>
  <main class="about">
      <h1 class="title">{{ title }}</h1>
      <h2 class="writer-date">{{ desc }}</h2>
      <h2 class="writer-date">{{ writer }}</h2>
      <h2 class="writer-date">{{ date }}</h2>
      <br />
      <h3>{{ article }}</h3>

  </main>
  <br>
  <main id="reports" class="main">
        <div class="row">
          <div class="col">
            <div
              class="card card-info"
              v-on:click="redirect('/')"
            >
              <p class="card-title">Go back Home</p>
              <div class="card-data">
                <div class="difficulty card-sub">
                  <i class="fas fa-bolt"></i>
                  <p class="data">Click me to go back!</p>
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
  },
  props: [
      "title",
      "date",
      "article",
      "writer",
      "desc"
  ]
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

.main {
  height: 110%;
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

  .main {
    height: 190%;
  }
}

.title {
  color: #ff4473;
}

.writer-date {
  color: #26c3e3;
}
</style>