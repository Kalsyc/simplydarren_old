<script lang="ts">
  import HeaderComponent from '../components/HeaderComponent.svelte';
  import FooterComponent from '../components/FooterComponent.svelte';
  import { metatags } from '@roxi/routify';
  import { onDestroy, onMount } from 'svelte';
  import TimelineComponent from '../components/TimelineComponent.svelte';
  import BioComponent from '../components/BioComponent.svelte';
  import TeachingComponent from '../components/TeachingComponent.svelte';
  import SkillsComponent from '../components/SkillsComponent.svelte';
  import ProjectsComponent from '../components/ProjectsComponent.svelte';
  import ContactComponent from '../components/ContactComponent.svelte';

  metatags.title = 'Simply Darren | About';

  let currentNav: string = 'bio';
  let sectionNodes: NodeListOf<Element>;
  let sectionObserver: IntersectionObserver;

  onMount(() => {
    sectionObserver = new IntersectionObserver(
      (entries: IntersectionObserverEntry[]) => {
        document.querySelectorAll('.about-nav-link').forEach((navLink: Element) => {
          navLink.classList.remove('link-circle-selected');
        });
        const allVisibleSections: IntersectionObserverEntry[] = entries.filter((entry: IntersectionObserverEntry) => entry.isIntersecting);
        if (allVisibleSections.length === 0) {
          return;
        }
        const visibleSection: IntersectionObserverEntry = allVisibleSections[0];
        const targetId: string = visibleSection.target.id;
        if (currentNav != targetId) {
          document.getElementById(currentNav + '-circle').classList.remove('link-circle-selected');
          document.getElementById(currentNav + '-circle-label').classList.remove('about-nav-label-selected');
        }
        currentNav = targetId;
        document.getElementById(currentNav + '-circle').classList.add('link-circle-selected');
        document.getElementById(currentNav + '-circle-label').classList.add('about-nav-label-selected');
      },
      { threshold: 0.5 },
    );
    sectionNodes = document.querySelectorAll('.about-section');
    sectionNodes.forEach((section: Element) => sectionObserver.observe(section));
  });

  onDestroy(() => {
    sectionNodes.forEach((section: Element) => sectionObserver.unobserve(section));
  });
</script>

<main>
  <HeaderComponent />
  <div class="about-main-div">
    <nav class="about-nav">
      <div class="about-nav-item">
        <a href="#bio" class="about-nav-link"><div class="link-circle link-circle-selected" id="bio-circle" /></a>
        <span class="about-nav-label about-nav-label-selected" id="bio-circle-label">Bio</span>
      </div>
      <div class="about-nav-item">
        <a href="#work" class="about-nav-link"><div class="link-circle" id="work-circle" /></a>
        <span class="about-nav-label" id="work-circle-label">Work Experience</span>
      </div>
      <div class="about-nav-item">
        <a href="#teaching" class="about-nav-link"><div class="link-circle" id="teaching-circle" /></a>
        <span class="about-nav-label" id="teaching-circle-label">Teaching Experience</span>
      </div>
      <div class="about-nav-item">
        <a href="#skills" class="about-nav-link"><div class="link-circle" id="skills-circle" /></a>
        <span class="about-nav-label" id="skills-circle-label">Skills</span>
      </div>
      <div class="about-nav-item">
        <a href="#projects" class="about-nav-link"><div class="link-circle" id="projects-circle" /></a>
        <span class="about-nav-label" id="projects-circle-label">Projects</span>
      </div>
      <div class="about-nav-item">
        <a href="#contact" class="about-nav-link"><div class="link-circle" id="contact-circle" /></a>
        <span class="about-nav-label" id="contact-circle-label">Contact Me</span>
      </div>
    </nav>
    <div class="about-main-body">
      <div class="about-section about-bio-div" id="bio" data-label="bio">
        <span class="about-section-title">Bio: Darren Sim</span>
        <BioComponent />
      </div>
      <div class="about-section about-work-div" id="work" data-label="work">
        <span class="about-section-title">Work Experience</span>
        <TimelineComponent />
      </div>
      <div class="about-section about-teaching-div" id="teaching" data-label="teaching">
        <span class="about-section-title">Teaching Experience</span>
        <TeachingComponent />
      </div>
      <div class="about-section about-skills-div" id="skills" data-label="skills">
        <span class="about-section-title">Skills</span>
        <SkillsComponent />
      </div>
      <div class="about-section about-projects-div" id="projects" data-label="projects">
        <span class="about-section-title">Notable Projects</span>
        <ProjectsComponent />
      </div>
      <div class="about-section about-contact-div" id="contact" data-label="contact">
        <span class="about-section-title">Contact Me</span>
        <ContactComponent />
      </div>
    </div>
  </div>
  <FooterComponent />
</main>

<style>
  .about-main-div {
    display: flex;
    flex-direction: column;
    text-align: center;
    min-height: 100vh;
  }

  .about-nav {
    padding: 1.5em;
    position: fixed;
    left: 0;
    top: 50%;
    transform: translateY(-50%);
  }

  .about-nav-label {
    color: #e87121;
    font-weight: 700;
    font-size: 0.9rem;
    opacity: 0.5;
    transition: opacity 0.1s;
  }

  .about-nav-link {
    margin: 0.5em 0.75em 0.5em 0;
    scroll-behavior: smooth;
  }

  .link-circle {
    background-color: #e87121;
    opacity: 0.5;
    border-radius: 50%;
    height: 15px;
    width: 15px;
    transition: transform 0.2s;
  }

  .link-circle-selected {
    opacity: 1;
    background-color: #e87121;
    transform: scale(1.35);
  }

  .about-nav-label-selected {
    opacity: 1;
  }

  .about-nav-link:hover ~ .about-nav-label {
    opacity: 1;
  }

  .about-nav-item {
    display: flex;
    align-items: center;
    margin-bottom: 0.5em;
  }

  .about-section {
    min-height: 100vh;
    padding: 1em 0;
  }

  .about-section-title {
    color: #e87121;
    font-weight: 700;
    font-size: 2.5rem;
    padding: 0.5em 1em;
  }

  .about-bio-div {
    background-color: aliceblue;
  }

  .about-work-div {
    background-color: antiquewhite;
  }

  .about-teaching-div {
    background-color: beige;
  }

  .about-skills-div {
    background-color: cornsilk;
  }

  .about-projects-div {
    background-color: honeydew;
  }

  .about-contact-div {
    background-color: floralwhite;
  }

  @media only screen and (max-width: 600px) {
    .about-nav {
      display: none;
    }
  }
</style>
