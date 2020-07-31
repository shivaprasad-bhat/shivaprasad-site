<template>
  <v-card color="grey darken-3" dark>
    <v-card-text>
      <avatar />
      <div class="text-sm-center mb-4 mt-3">
        <h1>
          Shivaprasad
          <span class="light-blue--text text--lighten-3">Bhat</span>
        </h1>
        <span>
          Former Software Engineer @ Envestnet | Yodlee
          <br />MCA student at MIT, Manipal
        </span>
      </div>

      <!-- Info -->
      <sidebar-section :options="sections.info" />

      <!-- Social Links -->
      <sidebar-section :options="sections.socials" />

      <!-- Skills -->
      <sidebar-section :options="sections.skills">
        <template v-slot:item="{item}">
          <v-chip>
            <v-avatar>
              <v-icon>{{ item.icon }}</v-icon>
            </v-avatar>
            {{ item.text }}
          </v-chip>
        </template>
      </sidebar-section>

      <br />

      <!-- Hobbies -->
      <sidebar-section :options="sections.hobbies">
        <template v-slot:item="{item}">
          <v-chip>
            <v-avatar>
              <v-icon>{{ item.icon }}</v-icon>
            </v-avatar>
            {{ item.text }}
          </v-chip>
        </template>
      </sidebar-section>

      <!-- Languages -->
      <sidebar-section :options="sections.languages">
        <template v-slot:items="{items}">
          <v-container pa-0>
            <v-layout wrap class="text-xs-center">
              <template v-for="(item, i) in items">
                <v-flex :key="i" md3 sm4 xs6>
                  <v-progress-circular
                    rotate="360"
                    size="65"
                    width="2"
                    :value="item.value"
                    color="white"
                    class="ma-2"
                  >{{ item.text }}</v-progress-circular>
                </v-flex>
              </template>
            </v-layout>
          </v-container>
        </template>
      </sidebar-section>
    </v-card-text>
  </v-card>
</template>

<script>
import Avatar from "@/views/dark-template/sidebar/Avatar";
import SidebarSection from "@/views/dark-template/sidebar/Section";

export default {
  name: "Sidebar",
  components: { SidebarSection, Avatar },
  data() {
    return {
      sections: {
        info: {
          title: "INFO",
          items: [
            {
              name: "Email",
              icon: "mdi-email",
              text: "shivaprasad.bhat@learner.manipal.edu",
            },
            {
              name: "Phone",
              icon: "mdi-phone",
              text: "+91 8747068436",
            },
            {
              name: "Website",
              icon: "mdi-web",
              text: "shivaprasad.tech",
            },
            {
              name: "Date of Birth",
              icon: "mdi-cake-variant",
              text: "Saturday, Apr 13, 1996",
            },
          ],
        },
        experience: { title: "Experience" },
        socials: {
          title: "SOCIALS",
          items: [
            {
              icon: "mdi-github-circle",
              text: "github.com/shivaprasad-bhat",
              link: "https://github.com/shivaprasad-bhat",
            },
            {
              icon: "mdi-linkedin-box",
              text: "linkedin.com/in/svbneelmane",
              link: "https://linkedin.com/in/svbneelmane",
            },
            {
              icon: "mdi-twitter",
              text: "twitter.com/svbneelmane",
              link: "https://twitter.com/svbneelmane",
            },
            {
              icon: "mdi-instagram",
              text: "instagram.com/svbneelmane",
              link: "https://instagram.com/svbneelmane",
            },
            {
              icon: "mdi-facebook",
              text: "facebook.com/svbneelmane",
              link: "https://facebook.com/svbneelmane",
            },
          ],
        },
        skills: {
          title: "Skills",
          items: [
            {
              icon: "mdi-language-java",
              text: "Java",
            },
            {
              icon: "mdi-language-cpp",
              text: "C and C ++",
            },
            {
              text: "JavaScript",
              icon: "mdi-language-javascript",
            },
            {
              text: "HTML5",
              icon: "mdi-language-html5",
            },
            {
              text: "CSS3",
              icon: "mdi-language-css3",
            },
            {
              text: "Python Basics",
              icon: "mdi-language-python",
            },
            {
              text: "SQL",
              icon: "mdi-database",
            },
            {
              text: "NoSQL Database",
              icon: "mdi-database",
            },
            {
              text: "PHP",
              icon: "mdi-language-php",
            },
            {
              text: "Vue.js Framework",
              icon: "mdi-vuejs",
            },
            {
              text: "Node.js Framework",
              icon: "mdi-nodejs",
            },
            {
              text: "Shell Scripting",
              icon: "mdi-console",
            },
            {
              text: "Server Management",
              icon: "mdi-linux",
            },
            {
              text: "AWS",
              icon: "mdi-amazon",
            },
            {
              text: "Test Driven Development",
              icon: "mdi-test-tube",
            },
            {
              text: "Git",
              icon: "mdi-git",
            },
            {
              text: "Office Suite",
              icon: "mdi-office",
            },
            {
              text: "IDE Handling",
              icon: "mdi-code-array",
            },
          ],
        },
        hobbies: {
          title: "HOBBIES",
          items: [
            {
              icon: "mdi-blogger",
              text: "Blogging",
            },
            {
              icon: "mdi-grease-pencil",
              text: "Writing Poems",
            },
            {
              icon: "mdi-speaker",
              text: "Debate / Speech",
            },
            {
              icon: "mdi-radio",
              text: "Talk Presentation",
            },
            {
              icon: "mdi-book-open-page-variant",
              text: "Books",
            },
            {
              icon: "mdi-bike",
              text: "Cycling",
            },
            {
              icon: "mdi-teach",
              text: "Teaching",
            },
            {
              icon: "mdi-music",
              text: "Music",
            },
          ],
        },
        certificates: {
          title: "Certificates",
          items: [
            {
              icon: "mdi-certificate",
              text: "Coursera - Python Functions, Files, and Dictionaries",
              source: "http://coursera.org/verify/78MRSL8MXGUB",
            },
            {
              icon: "mdi-certificate",
              text: "Coursera - Python Files, Data Handl",
              source: "http://coursera.org/verify/CML688T4Y4US",
            },
          ],
        },
        languages: {
          title: "LANGUAGES",
          items: [
            {
              text: "English",
              value: 70,
            },
            {
              text: "Kannada",
              value: 90,
            },
          ],
        },
      },
    };
  },
};
</script>

<style scoped>
.sidebar {
  background: #2e2e2e;
}
.social-links {
  color: white;
}
</style>
