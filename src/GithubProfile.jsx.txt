import { useState } from "react";
import { motion } from "framer-motion";

export default function GithubProfile() {
  const [darkMode, setDarkMode] = useState(true);

  const projects = [
    {
      name: "TrendNest",
      description:
        "A sleek, analytics-powered e-commerce platform with wishlist alerts, admin dashboards, and real-time visualizations.",
      tech: ["Flask", "Python", "MySQL", "JavaScript", "CSS"],
      repo: "https://github.com/TiasPal/TrendNest"
    },
    {
      name: "Portfolio Site",
      description:
        "Interactive and aesthetic portfolio built with animations, theme toggles, and smooth transitions.",
      tech: ["React", "TailwindCSS", "Framer Motion"],
      repo: "https://github.com/TiasPal/portfolio"
    }
  ];

  return (
    <div
      className={`min-h-screen ${
        darkMode
          ? "bg-gradient-to-br from-[#0f2027] via-[#203a43] to-[#2c5364] text-white"
          : "bg-gradient-to-br from-[#fdfbfb] to-[#ebedee] text-gray-800"
      } font-sans transition-all duration-500`}
    >
      <div className="max-w-5xl mx-auto px-4 py-20 text-center">
        <button
          onClick={() => setDarkMode(!darkMode)}
          className="absolute top-4 right-4 bg-white dark:bg-black rounded-full p-2 shadow-md hover:scale-105 transition-transform"
        >
          {darkMode ? "🌞" : "🌙"}
        </button>

        <motion.h1
          initial={{ opacity: 0, y: -40 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 0.6 }}
          className="text-5xl md:text-6xl font-bold mb-6 bg-gradient-to-r from-green-400 to-blue-500 bg-clip-text text-transparent"
        >
          Hey, I'm Tias Pal! 🚀
        </motion.h1>

        <motion.p
          initial={{ opacity: 0, y: 20 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ delay: 0.2, duration: 0.6 }}
          className="text-xl md:text-2xl text-gray-300 dark:text-gray-700 mb-8"
        >
          Full-Stack Developer | UI/UX Enthusiast | Lifelong Learner
        </motion.p>

        <motion.div
          className="flex justify-center gap-6 mb-12"
          initial={{ opacity: 0 }}
          animate={{ opacity: 1 }}
          transition={{ delay: 0.4, duration: 0.6 }}
        >
          <a href="mailto:pal.tias2007@gmail.com" target="_blank" className="hover:scale-110 transition-transform">
            <img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" />
          </a>
          <a href="https://www.linkedin.com/in/tias-pal-148890316/" target="_blank" className="hover:scale-110 transition-transform">
            <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" />
          </a>
          <a href="https://x.com/PalTias" target="_blank" className="hover:scale-110 transition-transform">
            <img src="https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white" />
          </a>
          <a href="https://github.com/TiasPal" target="_blank" className="hover:scale-110 transition-transform">
            <img src="https://img.shields.io/badge/GitHub-000000?style=for-the-badge&logo=github&logoColor=white" />
          </a>
        </motion.div>

        <motion.div
          initial={{ opacity: 0, y: 30 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ delay: 0.6, duration: 0.6 }}
        >
          <h2 className="text-2xl font-semibold mb-4">Tech Stack</h2>
          <p className="mb-6">
            <img
              src="https://skillicons.dev/icons?i=python,flask,js,react,html,css,bootstrap,mysql,git,github,vscode,figma&theme=dark"
              alt="Skills"
              className="mx-auto"
            />
          </p>
        </motion.div>

        <motion.div
          initial={{ opacity: 0 }}
          animate={{ opacity: 1 }}
          transition={{ delay: 0.8, duration: 0.6 }}
          className="space-y-12 mt-16"
        >
          <h2 className="text-2xl font-semibold">📊 GitHub Stats</h2>
          <div className="flex flex-col items-center gap-10">
            <img
              src="https://github-readme-stats.vercel.app/api?username=TiasPal&show_icons=true&count_private=true&theme=github_dark&hide_border=true"
              alt="GitHub Stats"
              className="w-full max-w-xl"
            />
            <img
              src="https://github-readme-streak-stats.herokuapp.com/?user=TiasPal&theme=github-dark&hide_border=true"
              alt="GitHub Streak"
              className="w-full max-w-xl"
            />
            <img
              src="https://github-readme-stats.vercel.app/api/top-langs/?username=TiasPal&layout=compact&theme=github_dark&hide_border=true"
              alt="Top Languages"
              className="w-full max-w-xl"
            />
            <img
              src="https://github-readme-activity-graph.vercel.app/graph?username=TiasPal&theme=github-compact&bg_color=0d1117&hide_border=true"
              alt="Contribution Graph"
              className="w-full max-w-4xl"
            />
          </div>
        </motion.div>

        <motion.div
          initial={{ opacity: 0 }}
          animate={{ opacity: 1 }}
          transition={{ delay: 1, duration: 0.6 }}
          className="mt-20"
        >
          <h2 className="text-2xl font-semibold mb-6">🚀 Featured Projects</h2>
          <div className="grid md:grid-cols-2 gap-8">
            {projects.map((project, idx) => (
              <div
                key={idx}
                className="rounded-xl border border-gray-700 bg-black/20 dark:bg-white/10 p-6 shadow-md hover:shadow-xl transition-shadow duration-300"
              >
                <h3 className="text-xl font-bold mb-2 text-green-400">{project.name}</h3>
                <p className="text-sm mb-2 text-gray-300 dark:text-gray-200">{project.description}</p>
                <p className="mb-4 text-sm text-gray-400">
                  <strong className="text-blue-300">Tech:</strong> {project.tech.join(", ")}
                </p>
                <a
                  href={project.repo}
                  target="_blank"
                  className="inline-block text-sm text-blue-400 hover:underline"
                >
                  View Repository →
                </a>
              </div>
            ))}
          </div>
        </motion.div>

        <motion.footer
          initial={{ opacity: 0 }}
          animate={{ opacity: 1 }}
          transition={{ delay: 1.2, duration: 0.6 }}
          className="mt-20 text-center text-gray-400"
        >
          <p>🚀 Thanks for visiting! Let's build something awesome together.</p>
        </motion.footer>
      </div>
    </div>
  );
}

