<h2>👋 Hey, I'm Baran Ejder!</h2>
<ul>
  <li>📍 I'm 18, currently living in Istanbul, Türkiye.</li>
  <li>🕒 I'm learning Python and exploring AI, machine learning, and app development.</li>
  <li>💻 I enjoy creating small projects and experimenting with software in my free time. Currently, I'm working on AI and software development projects, focusing on practical, real-world applications. Interested in SAAS and app ideas.</li>
</ul>
<hr>
<p>
  <img height="20px" src="https://img.shields.io/badge/ejderrx@gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white"></img>
  <img src="https://komarev.com/ghpvc/?username=baranejder&color=grey&style=flat-square"></img>
</p>


name: Generate Snake

on:
  schedule:
    - cron: "0 */12 * * *"  # Runs every 12 hours
  workflow_dispatch:

permissions:
  contents: write

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4
      
      - uses: Platane/snk@v3
        id: snake-gif
        with:
          github_user_name: baranejder  # Replace with your GitHub username
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
            dist/github-contribution-grid-snake.gif
      
      - uses: crazy-max/ghaction-github-pages@v4
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

