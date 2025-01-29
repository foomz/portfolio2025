<template>
  <div class="min-h-screen bg-gray-200">
    <!-- Navigation with scroll effect -->
    <nav class="bg-white shadow-lg fixed w-full z-10 transition-all duration-300" 
         :class="{ 'py-2': scrolled }" 
         ref="navbar">
      <div class="max-w-7xl mx-auto px-4">
        <div class="flex justify-between h-16">
          <div class="flex items-center space-x-2">
            <img src="https://i.imgur.com/Ap9Seoc.png" alt="Profile" class="h-10 w-10 rounded-full object-cover">
            <h1 class="text-xl font-bold">Portfolio</h1>
          </div>
          <div class="flex items-center space-x-4">
            <a v-for="item in navigation" 
               :key="item.name" 
               :href="item.href" 
               class="text-gray-700 hover:text-blue-600 px-3 py-2 rounded-md text-sm font-medium transition-colors duration-300">
              {{ item.name }}
            </a>
          </div>
        </div>
      </div>
    </nav>

    <main class="pt-16">
      <!-- Hero Section -->
      <section class="relative min-h-screen flex flex-col items-center justify-center bg-gradient-to-r from-blue-600 to-purple-700 py-20">
        <!-- Profile Picture and Title -->
        <div class="text-center text-white mb-16"
             v-motion
             :initial="{ y: 100, opacity: 0 }"
             :enter="{ y: 0, opacity: 1 }"
             :delay="200">
          <div class="flex flex-col items-center">
            <div class="w-48 h-48 rounded-full overflow-hidden border-4 border-white shadow-lg mb-8"
                 v-motion
                 :initial="{ scale: 0, opacity: 0 }"
                 :enter="{ scale: 1, opacity: 1 }"
                 :variants="{ custom: { scale: 1.1 } }"
                 :hovered="{ scale: 1.1 }"
                 transition="{ duration: 800 }">
              <img src="https://i.imgur.com/Vbx10VA.png" alt="Johnray M. De Luna" class="w-full h-full object-cover">
            </div>
            <h1 class="text-4xl md:text-6xl font-bold mb-4">Johnray M. De Luna</h1>
            <p class="text-xl md:text-2xl">Cybersecurity Professional & Full Stack Developer</p>
          </div>
        </div>
        
        <!-- Social Links with Icons -->
        <div class="flex justify-center space-x-6"
             v-motion
             :initial="{ x: -100, opacity: 0 }"
             :enter="{ x: 0, opacity: 1 }"
             :delay="400">
          <a href="mailto:jdeluna@nbi.gov.ph" 
             class="flex items-center space-x-2 hover:text-blue-200 transition-colors">
            <EnvelopeIcon class="h-6 w-6" />
            <span>Email</span>
          </a>
          <a href="https://facebook.com/Foomz.Cuteness" 
             target="_blank" 
             class="flex items-center space-x-2 hover:text-blue-200 transition-colors">
            <svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24">
              <path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/>
            </svg>
            <span>Facebook</span>
          </a>
          <a href="https://github.com/foomz" 
             target="_blank" 
             class="flex items-center space-x-2 hover:text-blue-200 transition-colors">
            <svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24">
              <path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0112 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"/>
            </svg>
            <span>GitHub</span>
          </a>
          <a href="https://linkedin.com/in/johnraydeluna" 
             target="_blank" 
             class="flex items-center space-x-2 hover:text-blue-200 transition-colors">
            <svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24">
              <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
            </svg>
            <span>LinkedIn</span>
          </a>
        </div>
      </section>

      <!-- Experience Section -->
      <section class="py-20 px-4 bg-white" id="experience">
        <h2 class="text-3xl font-bold mb-12 text-center"
            v-motion
            :initial="{ y: 50, opacity: 0 }"
            :visible="{ y: 0, opacity: 1, transition: { duration: 800 } }">
          Work Experience
        </h2>
        <div class="max-w-7xl mx-auto space-y-12">
          <div class="bg-gray-50 p-8 rounded-lg shadow-md"
               v-motion
               :initial="{ scale: 0.8, opacity: 0 }"
               :visible="{ scale: 1, opacity: 1, transition: { duration: 1000 } }">
            <div class="mb-6"
                 v-motion
                 :initial="{ x: -50, opacity: 0 }"
                 :visible="{ x: 0, opacity: 1, transition: { duration: 800, delay: 200 } }">
              <h3 class="text-2xl font-bold text-gray-800 mb-2">NATIONAL BUREAU OF INVESTIGATION</h3>
              <h4 class="text-xl font-semibold text-blue-600">Project Worker</h4>
            </div>

            <div class="space-y-8">
              <div v-for="(position, index) in experience"
                   :key="index"
                   class="transform transition-all duration-500"
                   v-motion
                   :initial="{ x: index % 2 === 0 ? -100 : 100, opacity: 0 }"
                   :visible="{ 
                     x: 0, 
                     opacity: 1, 
                     transition: { 
                       duration: 800, 
                       delay: 300 + (index * 200) 
                     } 
                   }">
                <div class="mb-4 hover:translate-x-2 transition-transform duration-300">
                  <p class="text-gray-700 text-lg mb-1">{{ position.department }}</p>
                  <p class="text-blue-600">{{ position.period }}</p>
                </div>

                <div class="space-y-3">
                  <p v-for="(duty, dutyIndex) in position.duties" 
                     :key="dutyIndex"
                     class="text-gray-700 leading-relaxed pl-4 relative before:content-['•'] before:absolute before:left-0 before:text-blue-600"
                     v-motion
                     :initial="{ y: 20, opacity: 0 }"
                     :visible="{ 
                       y: 0, 
                       opacity: 1, 
                       transition: { 
                         duration: 600, 
                         delay: 400 + (index * 200) + (dutyIndex * 100) 
                       } 
                     }">
                    {{ duty }}
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Skills Section -->
      <section class="py-20 px-4 bg-gray-100" id="skills">
        <div class="max-w-7xl mx-auto">
          <h2 class="text-3xl font-bold mb-12 text-center"
              v-motion
              :initial="{ y: 50, opacity: 0 }"
              :visible="{ y: 0, opacity: 1 }">
            Skills
          </h2>
          <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <div v-for="(category, index) in skills"
                 :key="index"
                 class="bg-white p-6 rounded-lg shadow-md"
                 v-motion
                 :initial="{ y: 50, opacity: 0 }"
                 :visible="{ y: 0, opacity: 1 }"
                 :delay="index * 200">
              <h3 class="text-xl font-bold mb-4">{{ category.title }}</h3>
              <div class="space-y-2">
                <div v-for="(subcategory, subIndex) in category.items" 
                     :key="subIndex"
                     class="mb-3">
                  <h4 v-if="subcategory.title" class="font-semibold text-blue-600 mb-2">
                    {{ subcategory.title }}:
                  </h4>
                  <div class="flex flex-wrap gap-2">
                    <span v-for="skill in subcategory.skills" 
                          :key="skill"
                          class="bg-blue-100 text-blue-800 px-3 py-1 rounded-full text-sm">
                      {{ skill }}
                    </span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Projects Section -->
      <section class="py-20 px-4 bg-white" id="projects">
        <div class="max-w-7xl mx-auto">
          <h2 class="text-3xl font-bold mb-12 text-center"
              v-motion
              :initial="{ y: 50, opacity: 0 }"
              :visible="{ y: 0, opacity: 1 }">
            Projects
          </h2>
          <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <div v-for="(project, index) in projects"
                 :key="project.title"
                 class="bg-gray-50 p-6 rounded-lg shadow-md transform transition-all duration-500 hover:scale-105"
                 v-motion
                 :initial="{ x: index % 2 === 0 ? -100 : 100, opacity: 0 }"
                 :visible="{ x: 0, opacity: 1 }"
                 :delay="index * 200">
              <h3 class="text-xl font-bold mb-2">{{ project.title }}</h3>
              <p class="text-gray-600 mb-4">{{ project.description }}</p>
              <a :href="project.link" 
                 target="_blank"
                 class="text-blue-600 hover:text-blue-800">
                View Project →
              </a>
            </div>
          </div>
        </div>
      </section>
    </main>

    <!-- Footer -->
    <footer class="bg-gray-800 text-white py-8">
      <div class="max-w-7xl mx-auto px-4 text-center">
        <div class="flex justify-center space-x-6 mb-4">
          <a href="mailto:jdeluna@nbi.gov.ph" class="flex items-center space-x-2 hover:text-blue-400 transition-colors">
            <EnvelopeIcon class="h-5 w-5" />
            <span>Email</span>
          </a>
          <a href="https://facebook.com/Foomz.Cuteness" target="_blank" class="flex items-center space-x-2 hover:text-blue-400 transition-colors">
            <svg class="h-5 w-5" fill="currentColor" viewBox="0 0 24 24">
              <path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/>
            </svg>
            <span>Facebook</span>
          </a>
          <a href="https://github.com/foomz" target="_blank" class="flex items-center space-x-2 hover:text-blue-400 transition-colors">
            <svg class="h-5 w-5" fill="currentColor" viewBox="0 0 24 24">
              <path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0112 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"/>
            </svg>
            <span>GitHub</span>
          </a>
          <a href="https://linkedin.com/in/johnraydeluna" target="_blank" class="flex items-center space-x-2 hover:text-blue-400 transition-colors">
            <svg class="h-5 w-5" fill="currentColor" viewBox="0 0 24 24">
              <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
            </svg>
            <span>LinkedIn</span>
          </a>
        </div>
        <p>© 2024 Johnray M. De Luna. All rights reserved.</p>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { EnvelopeIcon } from '@heroicons/vue/24/outline'

const scrolled = ref(false)
const handleScroll = () => {
  scrolled.value = window.scrollY > 50
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})

const navigation = [
  { name: 'Experience', href: '#experience' },
  { name: 'Skills', href: '#skills' },
  { name: 'Projects', href: '#projects' }
]

const experience = [
  {
    department: 'Regional District Offices – Investigative Services',
    period: 'March 2024 – December 2024',
    duties: [
      'Provided administrative support for NBI operations, including data entry, filing, and handling sensitive correspondence.'
    ]
  },
  {
    department: 'Technology Infrastructure Division – Information and Communication Technology Services',
    period: 'October 2022 – February 2024',
    duties: [
      'Monitored and maintained the hardware, software, and network infrastructure of the data center to ensure optimal performance and reliability for NBI Clearance Biometric System.'
    ]
  },
  {
    department: 'Cybercrime Division – Investigative Services',
    period: 'July 2018 – September 2022',
    duties: [
      'Conducted detailed investigations into cybercrime incidents, including data breaches, hacking attempts, and online fraud, while preparing comprehensive reports and documentation of investigative findings for use in legal proceedings.',
      'Identified patterns and trends in cybercrime activities to aid in the development of proactive security measures and stayed updated on the latest cyber threats, attack vectors, and security vulnerabilities.'
    ]
  },
  {
    department: 'Digital Forensics Laboratory – Forensic Investigation Services',
    period: 'March 2018 – June 2018',
    duties: [
      'Utilized advanced forensic tools and techniques to collect, preserve, and analyze digital evidence after operations, which was subsequently used in court hearings.'
    ]
  }
]

const skills = [
  {
    title: 'Web Application Development',
    items: [
      {
        title: 'Core Technologies',
        skills: ['HTML', 'CSS', 'Javascript', 'PHP', 'SQL', 'Python', 'Git', 'Github', 'Responsive Design']
      },
      {
        title: 'Front-end Frameworks',
        skills: ['React.js', 'Vue', 'Next', 'Vite', 'Svelte', 'Tailwind']
      },
      {
        title: 'Back-end Frameworks',
        skills: ['Node.js', 'Django', 'Sqlite', 'Mysql', 'MSSQL Server', 'REST API']
      },
      {
        title: 'DevOps & Tools',
        skills: ['Command Line', 'Basic UI/UX', 'Testing', 'Debug', 'Security Practice', 'CI/CD', 'AWS', 'GCP', 'Linode', 'Containerization']
      }
    ]
  },
  {
    title: 'Cyber Security',
    items: [
      {
        title: 'Core Skills',
        skills: ['Python', 'Bash', 'Networking', 'Web App Security', 'IDS', 'IPS', 'Firewall', 'Linux']
      },
      {
        title: 'Security Testing',
        skills: ['SQLI', 'XSS', 'CSRF', 'LFI', 'WAF', 'API EndPoints', 'VAPT']
      },
      {
        title: 'Security Operations',
        skills: ['Security Tools', 'Analytical Skills', 'Social Engineering', 'OSINT', 'Reconnaissance', 'Malware Analysis']
      },
      {
        title: 'Governance',
        skills: ['Security Policies', 'Forensics', 'Security Audit', 'Risk Management']
      }
    ]
  },
  {
    title: 'Administrative Support',
    items: [
      {
        skills: [
          'Microsoft 365',
          'Word',
          'Excel',
          'PowerPoint',
          'Google Sheet',
          'Troubleshooting',
          'Communication',
          'Data Entry',
          'Office Management',
          'Phone Call'
        ]
      }
    ]
  }
]

const projects = [
  {
    title: 'OCR Document Tracking System',
    description: 'This project helps centralize document management, ensuring consistency and improving decision-making through trend analysis. It enhances efficiency by streamlining data entry and automating calculations, while fostering accountability with audit trails and progress monitoring. The scalable design allows for easy expansion and integration, and a responsive interface improves accessibility. Additionally, OCR technology automates data extraction, reduces errors, and creates searchable digital records, promoting a more efficient, transparent, and data-driven operational environment.',
    link: 'https://invs-ocr-document-tracking.vercel.app'
  },
  {
    title: 'Human Resource Management System',
    description: 'This project is a web application built using React for the frontend and Django for the backend. It provides a login system and various HR-related functionalities such as employee management, attendance tracking, recruiting, onboarding, payroll management, and more.',
    link: 'https://human-resource-management-alpha.vercel.app'
  },
  {
    title: 'Network Web Mapper',
    description: 'A Project for my Portfolio. A Web Based Network Mapper that uses reconnaissance to gather information on ip address and domains made by reactJS and Django.',
    link: 'https://network-web-mapper.vercel.app'
  },
  {
    title: 'Simple Current App',
    description: 'A simple currency converter application built with Svelte and TypeScript. This application fetches real-time exchange rates and allows users to convert amounts between different currencies.',
    link: 'https://foomz.github.io/simple-current-app/'
  }
]
</script>

<style>
html {
  scroll-behavior: smooth;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

@keyframes rotate-360 {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

.hover\:rotate-360:hover {
  animation: rotate-360 1s linear;
}

.transform {
  transition-property: transform;
}

.transition-all {
  transition-property: all;
}

.duration-300 {
  transition-duration: 300ms;
}

.duration-500 {
  transition-duration: 500ms;
}

.hover\:translate-x-2:hover {
  transform: translateX(0.5rem);
}
</style>