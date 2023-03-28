<template>
  <main class="about">
    <div class="about__hero">
      <img
        class="about__hero-photo"
        src="../assets/profile-picture.jpg"
        :alt="name"
      />

      <div class="about__hero-intro">
        <p class="about__hero-text flex flex-jc-c flex-gap-sm">
          <span>Hello there</span>
          <img
            class="about__hero-icon"
            src="../assets/wave.svg"
            alt="greetings"
          />
        </p>
        <p class="about__hero-text">
          My name is <span class="about__text-highlight">{{ name }}</span
          >, and I'm a <span class="about__text-highlight">{{ title }}</span
          >.
        </p>
      </div>
    </div>

    <div class="about__section about__section--about">
      <h2 class="about__heading">About Me</h2>
      <ul class="about__content">
        <li v-for="(item, i) in bio" :key="i" v-html="item"></li>
      </ul>
    </div>

    <div class="about__section about__section--skills">
      <h2 class="about__heading">Skills</h2>
      <ul class="about__content flex flex-wrap">
        <li v-for="(skill, i) in skills" :key="i">{{ skill }}</li>
      </ul>
    </div>

    <div class="about__section">
      <h2 class="about__heading">Acknowledgement</h2>
      <div class="about__content">
        <p>
          “I'm SO grateful that I'm surrounded by a wonderful family &amp;
          friends who are a BIG reason for making the best of me, and always
          inspiring me and pushing me to amazing heights. A big shout-out to my
          people, AND to all the great teachers who taught me and helped me grow
          and glow. I can't thank you enough folks!”
        </p>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  name: "About",
  data() {
    return {
      name: "Mohamed Edris",
      title: "JavaScript Developer",
      bio: [
        "I'm a Nubian guy who lives in Alexandria, and graduated from its faculty of Science - class of 2020, CS department.",
        "While my studies, I've worked in many places, and participated in many student activities that helped me improve my soft skills.",
        "I'm a detail-oriented person that loves building minimal and clean websites/web apps that are pleasing to the eyes. I also built a startup before (with a wonderful team) so I know how important the website should be modern, clean-coded, user-friendly, and accessible for everyone.",
      ],
      skills: [
        "JavaScript",
        "HTML",
        "CSS",
        "React.js",
        "Vue.js",
        "SASS",
        "Node.js",
        "Express.js",
        "Ejs",
        "MongoDB / Mongoose",
        "SQL / MySQL",
        "TailwindCSS / Bootstrap",
        "jQuery",
        "Git / GitHub",
      ],
    };
  },
};
</script>
