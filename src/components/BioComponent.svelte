<div class="bio-div">
  <img class="about-bio-img" alt="" src="/img/about/about-bio.jpg" />
  <div class="about-bio-text-div">
    <span class="about-bio-text">
      Born in 1997 in Singapore, Darren Sim is currently a Final Year Computer Science Major at the National University of Singapore (NUS). His main
      interests in the world of tech include but not limited to Web Development, Game Design, AR/VR Applications and UI/UX Design. As a passionate
      software developer, Darren <s>wastes</s> spends a lot of his time fiddling around with new projects, in a bid to learn new tools, frameworks and
      languages.
      <br /><br />
      Darren also has a passion for teaching and has been serving as a Teaching Assistant (TA) for various modules in university since his second year.
      He was also the head of a coding/tech interest group in CAPT (a dormitory where he stayed during the first 2 years of college) where he conducted
      workshops for Telegram Bots, Conversation Counter, as well as teaching Python 101.
      <br /><br />
      Outside of his work, Darren is also an enthusiast in music, having been an avid guitar player for almost a decade.
    </span>
  </div>
</div>

<style>
  .bio-div {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: justify;
    -webkit-animation: fadein 2s;
    -moz-animation: fadein 2s;
    -ms-animation: fadein 2s;
    -o-animation: fadein 2s;
    animation: fadein 2s;
  }

  .about-bio-img {
    border-radius: 5%;
    aspect-ratio: 1;
    height: 250px;
    width: 250px;
    object-fit: cover;
  }

  .about-bio-text-div {
    padding: 3em;
    width: 50%;
  }

  .about-bio-text {
    font-weight: 500;
    font-size: 1.1rem;
  }

  @keyframes fadein {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }

  @-moz-keyframes fadein {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }

  @-webkit-keyframes fadein {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }

  @-ms-keyframes fadein {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }

  @-o-keyframes fadein {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }
</style>
