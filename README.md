# <span id="typing-animation"></span>

<div align="center">
  <img src="https://komarev.com/ghpvc/?username=tedyclivel&color=brightgreen" alt="Profile Views"/>
</div>

Welcome to my GitHub profile! I'm a passionate full-stack developer and creative technologist building amazing experiences with modern web and mobile technologies. Here you'll find my projects, contributions, and digital creations.

<style>
  @keyframes typing {
    from { width: 0; }
    to { width: 100%; }
  }
  
  @keyframes blink {
    50% { border-right-color: transparent; }
  }
  
  .typing-text {
    overflow: hidden;
    border-right: 3px solid #00d4ff;
    white-space: nowrap;
    animation: typing 3.5s steps(40, end), blink 0.75s step-end infinite;
    font-size: 32px;
    font-weight: bold;
    color: #00d4ff;
    width: fit-content;
    margin: 0 auto;
    display: inline-block;
  }
</style>

<div align="center" style="margin: 20px 0;">
  <div class="typing-text">Hey there! 👋 I'm Tedy Clivel</div>
</div>

<div align="center">
  
  **Full-Stack Developer | Creative Technologist | Code Artist**
  
</div>

---

## 🎮 Snake Game - Commit Eater

<div align="center" style="background: linear-gradient(135deg, #0a0e27 0%, #1a1f3a 100%); padding: 20px; border-radius: 10px; border: 2px solid #00d4ff; margin: 20px 0;">
  <canvas id="snakeGameCanvas" width="400" height="400" style="border: 2px solid #00ff88; display: block; margin: 0 auto; background: #0a0e27; cursor: pointer;"></canvas>
  <p style="color: #00d4ff; margin-top: 10px; font-size: 12px;">🎯 Arrow Keys to move | Eat all commits 🍔 | Score represents commits consumed!</p>
</div>

<script>
(function() {
  const canvas = document.getElementById('snakeGameCanvas');
  if (!canvas) return;
  
  const ctx = canvas.getContext('2d');
  const gridSize = 20;
  const tileCount = canvas.width / gridSize;
  
  let snake = [{ x: 5, y: 5 }];
  let direction = { x: 1, y: 0 };
  let nextDirection = { x: 1, y: 0 };
  let commits = [];
  let score = 0;
  let gameRunning = true;
  
  // Generate initial commits
  function generateCommit() {
    let x, y, collision;
    do {
      collision = false;
      x = Math.floor(Math.random() * tileCount);
      y = Math.floor(Math.random() * tileCount);
      for (let segment of snake) {
        if (segment.x === x && segment.y === y) {
          collision = true;
          break;
        }
      }
    } while (collision);
    commits.push({ x: x, y: y });
  }
  
  for (let i = 0; i < 5; i++) {
    generateCommit();
  }
  
  document.addEventListener('keydown', (e) => {
    if (e.key === 'ArrowUp' && direction.y === 0) nextDirection = { x: 0, y: -1 };
    if (e.key === 'ArrowDown' && direction.y === 0) nextDirection = { x: 0, y: 1 };
    if (e.key === 'ArrowLeft' && direction.x === 0) nextDirection = { x: -1, y: 0 };
    if (e.key === 'ArrowRight' && direction.x === 0) nextDirection = { x: 1, y: 0 };
  });
  
  function update() {
    direction = nextDirection;
    const head = { x: snake[0].x + direction.x, y: snake[0].y + direction.y };
    
    // Wrap around
    head.x = (head.x + tileCount) % tileCount;
    head.y = (head.y + tileCount) % tileCount;
    
    // Check self collision
    for (let segment of snake) {
      if (head.x === segment.x && head.y === segment.y) {
        gameRunning = false;
      }
    }
    
    snake.unshift(head);
    
    // Check commit collision
    let commitIndex = commits.findIndex(c => c.x === head.x && c.y === head.y);
    if (commitIndex !== -1) {
      commits.splice(commitIndex, 1);
      score++;
      generateCommit();
    } else {
      snake.pop();
    }
  }
  
  function draw() {
    // Clear canvas
    ctx.fillStyle = '#0a0e27';
    ctx.fillRect(0, 0, canvas.width, canvas.height);
    
    // Draw grid
    ctx.strokeStyle = 'rgba(0, 212, 255, 0.1)';
    ctx.lineWidth = 0.5;
    for (let i = 0; i <= tileCount; i++) {
      const pos = i * gridSize;
      ctx.beginPath();
      ctx.moveTo(pos, 0);
      ctx.lineTo(pos, canvas.height);
      ctx.stroke();
      
      ctx.beginPath();
      ctx.moveTo(0, pos);
      ctx.lineTo(canvas.width, pos);
      ctx.stroke();
    }
    
    // Draw commits
    commits.forEach(commit => {
      ctx.fillStyle = '#ffbe0b';
      ctx.fillRect(commit.x * gridSize + 2, commit.y * gridSize + 2, gridSize - 4, gridSize - 4);
      ctx.fillStyle = '#ff006e';
      ctx.font = 'bold 12px Arial';
      ctx.textAlign = 'center';
      ctx.textBaseline = 'middle';
      ctx.fillText('◆', commit.x * gridSize + gridSize / 2, commit.y * gridSize + gridSize / 2);
    });
    
    // Draw snake
    snake.forEach((segment, index) => {
      if (index === 0) {
        ctx.fillStyle = '#00d4ff';
        ctx.shadowColor = 'rgba(0, 212, 255, 0.8)';
        ctx.shadowBlur = 10;
      } else {
        ctx.fillStyle = '#00ff88';
        ctx.shadowColor = 'rgba(0, 255, 136, 0.5)';
        ctx.shadowBlur = 5;
      }
      ctx.fillRect(segment.x * gridSize + 1, segment.y * gridSize + 1, gridSize - 2, gridSize - 2);
      ctx.shadowColor = 'transparent';
    });
    
    // Draw score
    ctx.fillStyle = '#00d4ff';
    ctx.font = 'bold 16px Arial';
    ctx.textAlign = 'right';
    ctx.fillText('Commits: ' + score, canvas.width - 10, 20);
    
    if (!gameRunning) {
      ctx.fillStyle = 'rgba(0, 0, 0, 0.7)';
      ctx.fillRect(0, 0, canvas.width, canvas.height);
      ctx.fillStyle = '#ff006e';
      ctx.font = 'bold 24px Arial';
      ctx.textAlign = 'center';
      ctx.textBaseline = 'middle';
      ctx.fillText('GAME OVER!', canvas.width / 2, canvas.height / 2 - 30);
      ctx.fillStyle = '#00d4ff';
      ctx.font = '16px Arial';
      ctx.fillText('Commits Eaten: ' + score, canvas.width / 2, canvas.height / 2 + 20);
      ctx.fillStyle = '#00ff88';
      ctx.font = '12px Arial';
      ctx.fillText('Refresh to play again', canvas.width / 2, canvas.height / 2 + 50);
    }
  }
  
  function gameLoop() {
    if (gameRunning) {
      update();
    }
    draw();
    setTimeout(gameLoop, 100);
  }
  
  gameLoop();
})();
</script>

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
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" alt="HTML5" width="50" height="50" style="margin: 10px;"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" alt="CSS3" width="50" height="50" style="margin: 10px;"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/tailwindcss/tailwindcss-original.svg" alt="Tailwind CSS" width="50" height="50" style="margin: 10px;"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" alt="JavaScript" width="50" height="50" style="margin: 10px;"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg" alt="TypeScript" width="50" height="50" style="margin: 10px;"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" alt="React" width="50" height="50" style="margin: 10px;"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nextjs/nextjs-original.svg" alt="Next.js" width="50" height="50" style="margin: 10px;"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/angularjs/angularjs-original.svg" alt="Angular" width="50" height="50" style="margin: 10px;"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/flutter/flutter-original.svg" alt="Flutter" width="50" height="50" style="margin: 10px;"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg" alt="PostgreSQL" width="50" height="50" style="margin: 10px;"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" alt="Git" width="50" height="50" style="margin: 10px;"/>
</div>

### Specializations
- **Frontend:** HTML5, CSS3, Tailwind CSS, React.js, Next.js, Angular.js, Three.js (3D Graphics)
- **Mobile:** React Native, Flutter
- **Backend:** Node.js, TypeScript
- **Database:** PostgreSQL
- **Version Control:** Git
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

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=tedyclivel&show_icons=true&theme=dark&bg_color=0d1117&title_color=00d4ff&icon_color=00ff88&border_color=00d4ff&border_radius=10&hide_border=false)

</div>

<div align="center">

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=tedyclivel&layout=compact&theme=dark&bg_color=0d1117&title_color=00d4ff&border_color=00d4ff&border_radius=10&hide_border=false)

</div>

<div align="center">

![GitHub Streak](https://github-readme-streak-stats.herokuapp.com/?user=tedyclivel&theme=dark&background=0d1117&stroke=00d4ff&ring=00ff88&fire=ff006e&currStreakNum=00d4ff&sideNums=00d4ff&currStreakLabel=00ff88&sideLabels=00d4ff&dates=00d4ff)

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
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:tedyclivel1@gmail.com)
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

**📧 Let's build something amazing together!** 🚀

```javascript
console.log("Happy coding! 💻");
```

</div>