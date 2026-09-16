# Hey there! 👋 I'm Tedy Clivel

<div align="center">
  <img src="https://komarev.com/ghpvc/?username=tedyclivel&color=brightgreen" alt="Profile Views"/>
</div>

Welcome to my GitHub profile! I'm a passionate full-stack developer and creative technologist building amazing experiences with modern web and mobile technologies. Here you'll find my projects, contributions, and digital creations.

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

## 🎬 Animated Showcase

<div align="center">
  <canvas id="animationCanvas" width="600" height="300" style="border: 2px solid #00d4ff; border-radius: 8px; margin: 20px 0; background: linear-gradient(135deg, #0a0e27 0%, #1a1f3a 100%); display: block;"></canvas>
</div>

<script>
(function() {
  const canvas = document.getElementById('animationCanvas');
  if (!canvas) return;
  
  const ctx = canvas.getContext('2d');
  let animationId;
  let particles = [];
  let time = 0;

  class Particle {
    constructor(x, y) {
      this.x = x;
      this.y = y;
      this.vx = (Math.random() - 0.5) * 6;
      this.vy = -Math.random() * 3 - 2;
      this.size = Math.random() * 4 + 2;
      this.color = ['#00d4ff', '#00ff88', '#ff006e', '#ffbe0b', '#00d4ff'][Math.floor(Math.random() * 5)];
      this.life = 1;
      this.decay = Math.random() * 0.005 + 0.003;
    }

    update() {
      this.x += this.vx;
      this.y += this.vy;
      this.vy += 0.15;
      this.vx *= 0.99;
      this.life -= this.decay;
    }

    draw(ctx) {
      ctx.fillStyle = this.color;
      ctx.globalAlpha = Math.max(0, this.life);
      ctx.beginPath();
      ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
      ctx.fill();
      ctx.globalAlpha = 1;
    }
  }

  function drawText() {
    ctx.font = 'bold 32px Arial';
    ctx.textAlign = 'center';
    ctx.textBaseline = 'middle';
    
    const gradient = ctx.createLinearGradient(0, 0, canvas.width, 0);
    gradient.addColorStop(0, '#00d4ff');
    gradient.addColorStop(0.5, '#00ff88');
    gradient.addColorStop(1, '#ff006e');
    
    ctx.fillStyle = gradient;
    ctx.fillText('Creative Developer', canvas.width / 2, 80);
    
    ctx.font = '18px Arial';
    ctx.fillStyle = '#00d4ff';
    ctx.fillText('Full-Stack | Mobile | Interactive Experiences', canvas.width / 2, 150);
  }

  function drawLines() {
    ctx.strokeStyle = 'rgba(0, 212, 255, 0.1)';
    ctx.lineWidth = 1;
    for (let i = 0; i < 3; i++) {
      const offset = Math.sin(time * 0.002 + i) * 20;
      ctx.beginPath();
      ctx.moveTo(0, 200 + offset);
      ctx.lineTo(canvas.width, 200 + offset);
      ctx.stroke();
    }
  }

  function animate() {
    time++;
    
    // Fade effect instead of full clear
    ctx.fillStyle = 'rgba(10, 14, 39, 0.2)';
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    // Create particles from multiple points
    if (time % 3 === 0) {
      const points = [
        { x: canvas.width / 4, y: canvas.height * 0.7 },
        { x: canvas.width / 2, y: canvas.height * 0.7 },
        { x: (canvas.width * 3) / 4, y: canvas.height * 0.7 }
      ];
      
      points.forEach(point => {
        if (Math.random() < 0.6) {
          particles.push(new Particle(point.x + (Math.random() - 0.5) * 30, point.y));
        }
      });
    }

    // Update and draw particles
    for (let i = particles.length - 1; i >= 0; i--) {
      particles[i].update();
      particles[i].draw(ctx);
      if (particles[i].life <= 0) {
        particles.splice(i, 1);
      }
    }

    // Draw animated elements
    drawLines();
    drawText();

    animationId = requestAnimationFrame(animate);
  }

  animate();

  // Cleanup on page unload
  window.addEventListener('beforeunload', () => cancelAnimationFrame(animationId));
})();
</script>

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