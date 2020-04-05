<template>
  <v-card
    color="grey lighten-4"
    light
  >
    <v-card-text>
      <content-section title="About">
        <v-layoyt>
          <v-flex>
            <strong align="justify">Shivaprasad Bhat, a young and energetic software developer is from remote village called Muroor of Uttara Kannada district, Karnataka. After completing his early education in his home town, Kumata, he moved to SDM College Mangalore to pursue his bachelor degree in Computer Application. After securing graduation degree with appreciable grade, he started his profession as an associate software engineer at Envestnet Yodlee and worked there for 2 years. At present he is pursuing his Masters in Computer Application at MIT, Manipal. Mr Shivaprasad Bhat is a motivated and skilled software developer with excellent leadership and managerial qualities. Moreover he is flexible to adopt himself to any challenging environment and passionate to take new roles and responsibilities.</strong>
          </v-flex>
        </v-layoyt>
      </content-section>
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
    </v-card-text>
  </v-card>
</template>

<script>
import ContentSection from '@/views/dark-template/content/Section'
export default {
  name      : 'MainContent',
  components: { ContentSection },
  data      : () => ({
    abc: [
      {
        a:
          'Shivaprasad Bhat, a young and energetic software developer is from remote village called Muroor of Uttara Kannada district. After completing his early education in his home town, Kumata moved to SDM College Mangalore to pursue his bachelor degree in Computer Application. After securing graduation degree with appreciable grade, he started his profession as an associate software engineer at Envestnet Yodlee and worked there for 2 years. At present he is pursuing his Masters in Computer Application at MIT, Manipal. Mr Shivaprasad Bhat is a motivated and skilled software developer with excellent leadership and managerial qualities. Moreover he is flexible to adopt himself to any challenging environment and passionate to take new roles and responsibilities.',
      },
    ],
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
        source: 'coursera.org/verify/78MRSL8MXGUB',
      },
      {
        icon  : 'mdi-certificate',
        text  : 'Coursera - Python Files, Data Handl',
        source: 'coursera.org/verify/CML688T4Y4US',
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
.justify-center {
  text-align: justify;
  text-justify: inter-word;
}
</style>
