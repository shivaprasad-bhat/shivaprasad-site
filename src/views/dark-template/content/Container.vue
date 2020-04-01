<template>
  <v-card
    color="grey lighten-4"
    light
  >
    <v-card-text>
      <content-section title="Experience">
        <h3>Software Engineer | Envestenet Yodle</h3>
        <h5>(03-Jul-2017 to 12-Jul-2019)</h5>
        <span>
          <strong>Teams</strong>: Wellness Engineering, Automation COE
        </span>
        <br>
        <span>
          <strong>Technologies Worked On</strong>: Java, XML, Selenium, HTML5, CSS3, Oracle SQL
        </span>
        <br>
        <span>
          <strong>Projects Worked</strong>: PFM3.0, AIFincheck, Cobranding Tool
        </span>
        <br>
        <span>
          <strong>Tools Known</strong>: Perforce, Git, VersionOne, Bugzilla, Jenkins
        </span>
        <br>
        <span>
          <strong>IDEs Experienced</strong>: IntelliJ based IDEs, Eclipse, VSCode
        </span>
      </content-section>
      <content-section
        v-if="projects"
        title="Projects"
      >
        <v-layout
          v-for="(project, i) in projects"
          :key="i"
        >
          <v-flex
            md1
            xs3
          >
            <v-icon right>
              {{ project.icon }}
            </v-icon>
          </v-flex>
          <v-flex
            md11
            xs9
          >
            <p>
              <strong>{{ project.text }}</strong>
              <br>
              <span>{{ project.source }}</span>
            </p>
          </v-flex>
        </v-layout>
      </content-section>
      <content-section
        v-if="educations"
        title="Education"
      >
        <v-layout
          v-for="(education, i) in educations"
          :key="i"
        >
          <v-flex md4>
            {{ education.from }} - {{ education.to }}
          </v-flex>
          <v-flex md8>
            <strong v-if="education.title">{{ education.title }}</strong>
            <div v-if="education.location">
              <i>{{ education.location }}</i>
            </div>
            <div v-if="education.description">
              {{ education.description }}
            </div>
          </v-flex>
        </v-layout>
      </content-section>
      <content-section
        v-if="certificates"
        title="Certificates"
      >
        <v-layout
          v-for="(certificate, i) in certificates"
          :key="i"
        >
          <v-flex
            md1
            xs3
          >
            <v-icon right>
              {{ certificate.icon }}
            </v-icon>
          </v-flex>
          <v-flex
            md11
            xs9
          >
            <p>
              <strong>{{ certificate.text }}</strong>
              <br>
              <span>{{ certificate.source }}</span>
            </p>
          </v-flex>
        </v-layout>
      </content-section>
      <content-section
        v-if="prouds"
        title="Achievements"
      >
        <v-layout
          v-for="(proud, i) in prouds"
          :key="i"
        >
          <v-flex
            md1
            xs3
          >
            <v-icon right>
              {{ proud.icon }}
            </v-icon>
          </v-flex>
          <v-flex
            md11
            xs9
          >
            <p>
              <strong>{{ proud.text }}</strong>
              <br>
              <small>{{ proud.source }}</small>
            </p>
          </v-flex>
        </v-layout>
      </content-section>

      <content-section
        v-if="skills"
        id="to-timeline"
        title="Skills"
      >
        <template slot="actions">
          (% are relative not absolute)
        </template>
        <v-layout wrap>
          <template v-for="(skill, i) in skills">
            <v-flex
              v-if="skill.divider"
              :key="i"
              md12
              xs12
              mb-4
            />
            <v-flex
              v-else
              :key="i"
              md6
              xs12
            >
              <div class="mr-2 ml-2">
                <div class="align-center">
                  <v-icon small>
                    {{ skill.icon }}
                  </v-icon>
                  {{ skill.title }}
                </div>
                <v-progress-linear
                  class="progress"
                  color="secondary"
                  height="3"
                  :value="skill.value"
                />
              </div>
            </v-flex>
          </template>
        </v-layout>
      </content-section>
    </v-card-text>
  </v-card>
</template>

<script>
import ContentSection from '@/views/dark-template/content/Section'
export default {
  name      : 'MainContent',
  components: { ContentSection },
  data      : () => ({
    prouds: [
      {
        icon: 'mdi-account-multiple',
        text:
          'Awarded as Best Outgoing Student 2017, by SDM College of Business Management, Mangaluru',
        source: '(For academic excellece and contribution to Sygma 2016)',
      },
      {
        icon: 'mdi-account-multiple',
        text:
          'Served as CEO of Sygma 2016, a State level IT Fest for UG Students',
        source: '(Organised by SDMCBM, Mangaluru)',
      },
      {
        icon: 'mdi-account-multiple',
        text:
          'Won several awards in various IT fests organized for UG Students.',
        source: '(Also participated in various technical/non-technical events.)',
      },
    ],
    projects: [
      {
        icon  : 'mdi-git',
        text  : 'PFM 3.0 (2017 – 2019)',
        source:
          'PFM is one of the products developed by Envestnet® | Yodlee®. With Personal Financial Management (PFM) tools and user-friendly FinApps, customers can view all of their financial accounts in one place, manage expenses, set a budget, save for personal goals, view investments, calculate net worth, and improve their overall financial wellness.',
      },
      {
        icon  : 'mdi-git',
        text  : 'ILIB - Library Management Application',
        source:
          'iLib is an online library management application developed for SDM College, Mangaluru, and is submitted to Mangalore University as final semester project',
      },
    ],
    certificates: [
      {
        icon  : 'mdi-certificate',
        text  : 'Coursera - Python Functions, Files, and Dictionaries',
        source: 'http://coursera.org/verify/78MRSL8MXGUB',
      },
      {
        icon  : 'mdi-certificate',
        text  : 'Coursera - Python Files, Data Handl',
        source: 'http://coursera.org/verify/CML688T4Y4US',
      },
    ],
    educations: [
      {
        from       : '2019',
        to         : 'Present',
        title      : "Master's degree, Computer Applications",
        location   : 'Manipal Academy of Higher Education, Manipal',
        description: '(10 CGPA, 1st Semester)',
      },
      {
        from       : '2014',
        to         : '2017',
        title      : "Bachelor's degree, Computer Applications",
        location   : 'Mangalore University',
        description: '(8.8 CGPA)',
      },
    ],
    skills: [
      {
        title: 'Object Oriented Programming with Java',
        icon : 'mdi-language-java',
        value: 95,
      },
      {
        title: 'C++ / C Programming',
        icon : 'mdi-language-cpp',
        value: 90,
      },
      {
        title: 'JavaScript',
        icon : 'mdi-language-javascript',
        value: 80,
      },
      {
        title: 'HTML5',
        icon : 'mdi-language-html5',
        value: 88,
      },
      {
        title: 'CSS3',
        icon : 'mdi-language-css3',
        value: 80,
      },
      {
        title: 'Python',
        icon : 'mdi-language-python',
        value: 60,
      },
      {
        title: 'SQL',
        icon : 'mdi-database',
        value: 70,
      },
      {
        title: 'NoSQL Database',
        icon : 'mdi-database',
        value: 60,
      },
      {
        title: 'Vue.js Framework',
        icon : 'mdi-vuejs',
        value: 80,
      },
      {
        title: 'Node.js Framework',
        icon : 'mdi-nodejs',
        value: 30,
      },
      {
        title: 'PHP',
        icon : 'mdi-language-php',
        value: 50,
      },
      {
        title: 'Linux Shell Scripting',
        icon : 'mdi-console',
        value: 40,
      },
      { divider: true },
      {
        title: 'Server Management',
        icon : 'mdi-linux',
        value: 70,
      },
      {
        title: 'AWS',
        icon : 'mdi-amazon',
        value: 80,
      },
      {
        title: 'Test Driven Development',
        icon : 'mdi-test-tube',
        value: 75,
      },
      {
        title: 'Git',
        icon : 'mdi-git',
        value: 70,
      },
      {
        title: 'Jenkins',
        icon : 'mdi-settings',
        value: 70,
      },
      {
        title: 'MS Office Suite',
        icon : 'mdi-office',
        value: 85,
      },
      {
        title: 'VSCode, IntelliJ, Eclipse',
        icon : 'mdi-code-array',
        value: 85,
      },

      { divider: true },
    ],
  }),
}
</script>

<style scoped>
.title {
  border-bottom: 2px #bfbfbf solid;
  line-height: 1.5 !important;
}
.progress {
  margin-top: 0.1rem;
}
</style>
