# ⛏️ Minecraft Mob Guesser

A 20-questions-style guessing game for Minecraft mobs. Think of any mob — the game will narrow it down through smart yes/no questions and guess it!

🎮 **[Play it live →](https://banzoxog.github.io/minecraft-gusser/)**

---

## ✨ Features

- **Jumps straight to questions** — no difficulty picker, no setup screen
- **Smart question skipping** — if a question doesn't split the remaining mobs, it's skipped automatically
- **Live mob image + name** shown next to every question (from [minecraft.wiki](https://minecraft.wiki/w/Mob))
- **Progressive narrowing** — the side panel updates in real time showing possible mobs
- **Multiple guesses** — if the first guess is wrong, it tries the next most likely mob
- **Answer history** — see all your yes/no answers as you play
- **Timer** — tracks how fast you identify the mob
- **80+ mobs** from all dimensions: Overworld, Nether, The End

## 🗂️ Structure

```
minecraft-gusser/
└── index.html   ← entire game, single self-contained file
```

No build step. No dependencies. No frameworks. Just HTML + CSS + JS.

## 🚀 Deploy to GitHub Pages

1. Fork or clone this repo
2. Go to **Settings → Pages**
3. Set source to **main branch / root**
4. Your game is live at `https://<username>.github.io/minecraft-gusser/`

## 🧠 How it works

Each mob has ~15 boolean attributes (hostile, passive, undead, flying, aquatic, illager, etc.). The game picks the question that best splits the current pool of possible mobs, skipping any question where all remaining mobs would give the same answer. This ensures every question is always meaningful.

## 📸 Images

Mob images are loaded directly from [minecraft.wiki](https://minecraft.wiki) using their standard image filenames. If an image fails to load, a `?` placeholder is shown instead.

## 🤝 Contributing

Want to add more mobs or improve the question logic? Edit the `MOBS` array and `QUESTIONS` array in `index.html`. Each mob entry looks like:

```js
{ 
  name: "Creeper", 
  img: "Creeper_JE4.png",
  hostile: true, passive: false, neutral: false,
  nether: false, end: false, aquatic: false,
  undead: false, flying: false, boss: false,
  tameable: false, rideable: false, animal: false,
  arthropod: false, illager: false, humanoid: true,
  size: "medium", spawner: true
}
```

## 📄 License

MIT — do whatever you want with it.
