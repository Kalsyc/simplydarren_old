<script lang="ts">
  import HeaderComponent from '../../components/HeaderComponent.svelte';
  import FooterComponent from '../../components/FooterComponent.svelte';
  import { metatags } from '@roxi/routify';
  import ProjectCellComponent from '../../components/ProjectCellComponent.svelte';

  metatags.title = 'Simply Darren | Projects';
</script>

<main>
  <HeaderComponent />
  <div class="project-main-div">
    <span class="project-title-div">My Projects</span>
    <div class="projects-completed">
      <span class="completed-title">Completed Projects</span>
      <div class="completed-grid">
        <ProjectCellComponent
          projectType="appdev"
          projectParam="Xpire"
          projectImgPath="/img/projects/xpire-img.png"
          projectTitle="Xpire"
          projectDesc="Expiry Date Tracker Desktop App"
          projectTag="App Dev"
        />
        <ProjectCellComponent
          projectType="uiux"
          projectParam="PetSaver"
          projectImgPath="/img/projects/petsaver-img.jpeg"
          projectTitle="PetSaver"
          projectDesc="Personal Savings App for UX Design Project"
          projectTag="UI/UX Design"
        />
        <ProjectCellComponent
          projectType="vr"
          projectParam="SafeSpace"
          projectImgPath="/img/projects/safespace-img.png"
          projectTitle="SafeSpace"
          projectDesc="VR Mental Health Simulator and Meditation Guide"
          projectTag="Virtual Reality"
        />
        <ProjectCellComponent
          projectType="webdev"
          projectParam="ProjectKampong"
          projectImgPath="/img/projects/kampong-img.png"
          projectTitle="Project Kampong"
          projectDesc="Online Collaborative platform for Social Sector"
          projectTag="Web Dev"
        />
        <ProjectCellComponent
          projectType="webdev"
          projectParam="DigitalKampung"
          projectImgPath="/img/projects/digitalkampung-img.png"
          projectTitle="Digital Kampung"
          projectDesc="Rate, Review and Search Hawkers in Singapore"
          projectTag="Web Dev"
        />
        <ProjectCellComponent
          projectType="gamedev"
          projectParam="CULLinary"
          projectImgPath="/img/projects/cullinary-gif.gif"
          projectTitle="CULLinary"
          projectDesc="Dungeon Crawler and Restaurant Simulator"
          projectTag="Game Dev"
        />
        <ProjectCellComponent
          projectType="gamedev"
          projectParam="CULLinary2"
          projectImgPath="/img/projects/cullinary2-gif.gif"
          projectTitle="CULLinary2"
          projectDesc="Dungeon Crawler and Delivery Simulator"
          projectTag="Game Dev"
        />
        <ProjectCellComponent
          projectType="webdev"
          projectParam="CanMakan"
          projectImgPath="/img/projects/canmakan.jpg"
          projectTitle="CanMakan"
          projectDesc="Dine-in Rules Checker"
          projectTag="Web Dev"
        />
      </div>
    </div>

    <div class="projects-ongoing">
      <span class="ongoing-title">Ongoing Projects</span>
      <div class="completed-grid">
        <ProjectCellComponent
          projectType="webdev"
          projectParam="Yobu"
          projectImgPath="/img/projects/yobu.jpg"
          projectTitle="Yobu"
          projectDesc="Social Gaming Platform - The newest way to connect"
          projectTag="Web Dev"
        />
        <ProjectCellComponent
          projectType="webdev"
          projectParam="SayNoToUILibraries"
          projectImgPath="/img/projects/saynotouilibraries.jpg"
          projectTitle="SayNoToUILibraries"
          projectDesc="UI Component Reference & Storage"
          projectTag="Web Dev"
        />
      </div>
    </div>
  </div>
  <FooterComponent />
</main>

<style>
  .project-main-div {
    display: flex;
    flex-direction: column;
    text-align: center;
    margin: 1em 0;
    min-height: 100vh;
  }

  .completed-grid {
    padding: 1em 0;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
  }

  .completed-title,
  .ongoing-title {
    font-weight: 700;
    font-size: 1.5rem;
    color: #e87121;
    text-decoration: underline;
  }

  .projects-completed,
  .projects-ongoing {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin: 1em 10%;
  }

  .project-title-div {
    color: #e87121;
    font-weight: 700;
    font-size: 2rem;
    font-weight: 500;
    margin: 5px 0;
  }

  @media screen and (max-width: 1400px) {
    .completed-grid {
      grid-template-columns: repeat(2, 1fr);
    }
  }

  @media screen and (max-width: 900px) {
    .completed-grid {
      grid-template-columns: repeat(1, 1fr);
    }
  }
</style>
