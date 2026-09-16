# Hey there! 👋 I'm Tedy Clivel

<div align="center">
  <img src="https://komarev.com/ghpvc/?username=tedyclivel&color=brightgreen" alt="Profile Views"/>
</div>

Welcome to my GitHub profile! I'm a passionate full-stack developer and creative technologist building amazing experiences with modern web and mobile technologies. Here you'll find my projects, contributions, and digital creations.

---

## 🎬 Animated Showcase

<div align="center">
  <svg width="100%" height="400" viewBox="0 0 600 300" xmlns="http://www.w3.org/2000/svg" style="background: linear-gradient(135deg, #0a0e27 0%, #1a1f3a 100%); border: 2px solid #00d4ff; border-radius: 8px;">
    <defs>
      <style>
        @keyframes float-up {
          0% {
            opacity: 1;
            transform: translateY(0px);
          }
          100% {
            opacity: 0;
            transform: translateY(-200px);
          }
        }
        
        @keyframes pulse {
          0%, 100% {
            opacity: 0.6;
          }
          50% {
            opacity: 1;
          }
        }
        
        @keyframes float-wave {
          0%, 100% {
            transform: translateY(0px);
          }
          50% {
            transform: translateY(-15px);
          }
        }
        
        @keyframes glow {
          0%, 100% {
            filter: drop-shadow(0 0 5px rgba(0, 212, 255, 0.5));
          }
          50% {
            filter: drop-shadow(0 0 15px rgba(0, 255, 136, 0.8));
          }
        }
        
        @keyframes rotate {
          from {
            transform: rotate(0deg);
          }
          to {
            transform: rotate(360deg);
          }
        }
        
        .particle {
          animation: float-up 3s ease-in infinite;
        }
        
        .text-title {
          font-size: 32px;
          font-weight: bold;
          fill: url(#titleGradient);
          text-anchor: middle;
          animation: pulse 2s ease-in-out infinite;
        }
        
        .text-subtitle {
          font-size: 16px;
          fill: #00d4ff;
          text-anchor: middle;
          opacity: 0.9;
        }
        
        .line-animate {
          stroke: rgba(0, 212, 255, 0.3);
          stroke-width: 2;
          animation: pulse 2s ease-in-out infinite;
        }
        
        .icon-tech {
          animation: float-wave 3s ease-in-out infinite;
        }
        
        .spark {
          animation: glow 2s ease-in-out infinite;
        }
      </style>
      
      <linearGradient id="titleGradient" x1="0%" y1="0%" x2="100%" y2="0%">
        <stop offset="0%" style="stop-color:#00d4ff;stop-opacity:1" />
        <stop offset="50%" style="stop-color:#00ff88;stop-opacity:1" />
        <stop offset="100%" style="stop-color:#ff006e;stop-opacity:1" />
      </linearGradient>
    </defs>
    
    <!-- Animated Lines Background -->
    <line x1="0" y1="80" x2="600" y2="80" class="line-animate" style="animation-delay: 0s;"/>
    <line x1="0" y1="220" x2="600" y2="220" class="line-animate" style="animation-delay: 0.3s;"/>
    <line x1="0" y1="150" x2="600" y2="150" class="line-animate" style="animation-delay: 0.6s;"/>
    
    <!-- Main Text -->
    <text x="300" y="70" class="text-title">Creative Developer</text>
    <text x="300" y="120" class="text-subtitle">Full-Stack | Mobile | Interactive Experiences</text>
    
    <!-- Animated Particles -->
    <!-- Column 1 -->
    <circle cx="100" cy="250" r="4" fill="#00d4ff" class="particle" style="animation-delay: 0s;"/>
    <circle cx="110" cy="250" r="3" fill="#00ff88" class="particle" style="animation-delay: 0.5s;"/>
    <circle cx="90" cy="250" r="3.5" fill="#ff006e" class="particle" style="animation-delay: 1s;"/>
    
    <!-- Column 2 -->
    <circle cx="300" cy="250" r="4" fill="#ffbe0b" class="particle" style="animation-delay: 0.2s;"/>
    <circle cx="310" cy="250" r="3" fill="#00d4ff" class="particle" style="animation-delay: 0.7s;"/>
    <circle cx="290" cy="250" r="3.5" fill="#00ff88" class="particle" style="animation-delay: 1.2s;"/>
    
    <!-- Column 3 -->
    <circle cx="500" cy="250" r="4" fill="#ff006e" class="particle" style="animation-delay: 0.3s;"/>
    <circle cx="510" cy="250" r="3" fill="#ffbe0b" class="particle" style="animation-delay: 0.8s;"/>
    <circle cx="490" cy="250" r="3.5" fill="#00d4ff" class="particle" style="animation-delay: 1.3s;"/>
    
    <!-- Glowing Accents -->
    <circle cx="50" cy="150" r="6" fill="none" stroke="#00d4ff" stroke-width="2" class="spark"/>
    <circle cx="550" cy="150" r="6" fill="none" stroke="#00ff88" stroke-width="2" class="spark" style="animation-delay: 0.5s;"/>
    
    <!-- Tech Icons Floating -->
    <g class="icon-tech" style="animation-delay: 0s;">
      <rect x="150" y="30" width="30" height="30" fill="rgba(0, 212, 255, 0.2)" rx="5"/>
      <text x="165" y="52" font-size="20" fill="#00d4ff" text-anchor="middle">◆</text>
    </g>
    
    <g class="icon-tech" style="animation-delay: 0.3s;">
      <rect x="280" y="30" width="30" height="30" fill="rgba(0, 255, 136, 0.2)" rx="5"/>
      <text x="295" y="52" font-size="20" fill="#00ff88" text-anchor="middle">⚛</text>
    </g>
    
    <g class="icon-tech" style="animation-delay: 0.6s;">
      <rect x="410" y="30" width="30" height="30" fill="rgba(255, 0, 110, 0.2)" rx="5"/>
      <text x="425" y="52" font-size="20" fill="#ff006e" text-anchor="middle">◈</text>
    </g>
  </svg>
</div>

---

## 🚀 About Me

I'm a developer obsessed with creating elegant, performant solutions and pushing the boundaries of what's possible with code. I love crafting beautiful user experiences, exploring cutting-edge technologies, and collaborating with talented teams.

```javascript
const aboutMe = {
  passion: "Building amazing digital experiences 💻",
  expertise: "Full-Stack Development & Creative Coding",
  currentlyExploring: "Advanced animations & 3D web experiences",
  funFact: "I turn code into art! ✨"
};
```

---

## 💡 What I Do

- 🎨 **Frontend Development** – Crafting beautiful, responsive UIs with modern frameworks
- 📱 **Mobile Development** – Building cross-platform apps with Flutter & React Native
- 🌐 **Full-Stack Solutions** – End-to-end development with databases and APIs
- ✨ **Creative Coding** – Interactive animations and 3D web experiences
- 🚀 **Performance Optimization** – Building fast, scalable applications

---

## 🛠️ Tech Stack

### Languages & Core Technologies
<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" alt="JavaScript" width="50" height="50" style="margin: 10px;"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg" alt="TypeScript" width="50" height="50" style="margin: 10px;"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" alt="React" width="50" height="50" style="margin: 10px;"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nextjs/nextjs-original.svg" alt="Next.js" width="50" height="50" style="margin: 10px;"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/angularjs/angularjs-original.svg" alt="Angular" width="50" height="50" style="margin: 10px;"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/flutter/flutter-original.svg" alt="Flutter" width="50" height="50" style="margin: 10px;"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg" alt="PostgreSQL" width="50" height="50" style="margin: 10px;"/>
</div>

### Specializations
- **Frontend:** React.js, Next.js, Angular.js, Three.js (3D Graphics)
- **Mobile:** React Native, Flutter
- **Backend:** Node.js, TypeScript
- **Database:** PostgreSQL
- **Creative:** Three.js, WebGL, Canvas animations

---

## ✨ Featured Work

### 🌍 My Portfolio
Check out my projects and creative work:
👉 **[portfolio.tedyclivel1.workers.dev](https://portfolio.tedyclivel1.workers.dev/)**

### 💼 Professional Profile
Connect with me on LinkedIn:
👉 **[linkedin.com/in/tedy-clivel-fokou-temfack](https://www.linkedin.com/in/tedy-clivel-fokou-temfack-2474ba331)**

---

## 📊 GitHub Statistics

<div align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=tedyclivel&show_icons=true&theme=dark&bg_color=0a0e27&title_color=00d4ff&icon_color=00ff88" alt="GitHub Stats" />
</div>

<div align="center">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=tedyclivel&layout=compact&theme=dark&bg_color=0a0e27&title_color=00d4ff" alt="Top Languages" />
</div>

---

## 🌟 Current Focus

<div align="center">

🚀 Building next-generation web experiences with **Next.js** & **React**

📱 Creating seamless mobile apps with **Flutter** & **React Native**

✨ Exploring advanced **3D graphics** with **Three.js**

🎨 Crafting beautiful animations and interactive experiences

</div>

---

## 🤝 Let's Connect

<div align="center">

**Connect with me across platforms:**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/tedy-clivel-fokou-temfack-2474ba331)
[![Portfolio](https://img.shields.io/badge/Portfolio-00d4ff?style=for-the-badge&logo=firefox&logoColor=white)](https://portfolio.tedyclivel1.workers.dev/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/tedyclivel)

</div>

---

## 💬 Fun Facts

- 🎨 **Creative Coder** – I believe code is art and art is code
- 🌍 **Global Developer** – Building projects that reach across borders
- ⚡ **Performance Enthusiast** – Always optimizing for speed and efficiency
- 🚀 **Lifelong Learner** – Constantly exploring new technologies and frameworks
- 🎮 **Interactive Experiences** – Passionate about creating engaging digital experiences

---

<div align="center">

### ✨ Thanks for visiting my profile! ✨

Feel free to explore my repositories, check out my portfolio, and don't hesitate to reach out for collaborations or opportunities!

**Let's build something amazing together!** 🚀

```javascript
console.log("Happy coding! 💻");
```

</div>