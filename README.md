# Critical AI Literacy for Historians

**Developing critical engagement with AI technologies in historical research practice.**

This educational repository provides structured, hands-on exercises for historians to develop **critical AI literacy**, **digital source criticism**, and **scholarly practice** with large language models (LLMs). It aims to help learners understand how AI functions as both a research _tool_ and a _method_, reflect on how it shapes historical interpretation and evidence, and apply rigorous digital source criticism to assess data provenance, representation, and bias.

[![GitHub issues](https://img.shields.io/github/issues/maehr/critical-ai-literacy-for-historians.svg)](https://github.com/maehr/critical-ai-literacy-for-historians/issues)
[![GitHub forks](https://img.shields.io/github/forks/maehr/critical-ai-literacy-for-historians.svg)](https://github.com/maehr/critical-ai-literacy-for-historians/network)
[![GitHub stars](https://img.shields.io/github/stars/maehr/critical-ai-literacy-for-historians.svg)](https://github.com/maehr/critical-ai-literacy-for-historians/stargazers)
[![Code license](https://img.shields.io/github/license/maehr/critical-ai-literacy-for-historians.svg)](https://github.com/maehr/critical-ai-literacy-for-historians/blob/main/LICENSE-AGPL.md)
[![Data license](https://img.shields.io/badge/Data-CC_BY_NC_SA_4.0-green)](https://github.com/maehr/critical-ai-literacy-for-historians/blob/main/LICENSE-CCBYNCSA.md)

<!-- [![DOI](https://zenodo.org/badge/GITHUB_REPO_ID.svg)](https://zenodo.org/badge/latestdoi/ZENODO_RECORD) -->

## Purpose

The materials promote responsible, transparent, and ethically informed use of AI in historical research—emphasizing:

- 📊 **Reproducibility** in research workflows
- 🔒 **Privacy** and ethical data handling
- ©️ **Copyright awareness** and proper attribution
- 🌱 **Sustainability** through minimal computing approaches
- 🤝 **Interdisciplinary collaboration** and critical reflection

By fostering interdisciplinary collaboration and critical reflection on AI as both an analytical instrument and a historical artefact, the repository encourages historians to design transparent, meaningful projects that integrate AI into their research without compromising disciplinary rigor.

## Features

### Multilingual Content

The exercises are available in three languages:

- 🇬🇧 **English** - Full curriculum with detailed exercises
- 🇩🇪 **Deutsch** - Vollständiger Lehrplan mit detaillierten Übungen
- 🇫🇷 **Français** - Programme complet avec exercices détaillés

### Structured Exercises

Each exercise follows a consistent pedagogical framework:

- **Clear learning objectives** - What you will learn
- **Difficulty levels** - Beginner, Intermediate, Advanced
- **Time estimates** - Plan your learning journey
- **Prerequisites** - Know what you need to get started
- **Hands-on activities** - Practice critical engagement with AI
- **Critical reflection prompts** - Deepen your understanding
- **Additional resources** - Expand your knowledge

### FAIR and CARE Principles

This project adheres to:

- **FAIR** principles (Findable, Accessible, Interoperable, Reusable) for educational materials
- **CARE** principles (Collective Benefit, Authority to Control, Responsibility, Ethics) for responsible data governance

## Getting Started

### Explore the Exercises

Visit the live website to explore exercises in your preferred language:

- 🌐 [**View the Website**](https://maehr.github.io/critical-ai-literacy-for-historians/)
- 🇬🇧 [English Exercises](https://maehr.github.io/critical-ai-literacy-for-historians/en/)
- 🇩🇪 [Deutsche Übungen](https://maehr.github.io/critical-ai-literacy-for-historians/de/)
- 🇫🇷 [Exercices en français](https://maehr.github.io/critical-ai-literacy-for-historians/fr/)

### For Contributors: Setup with GitHub Codespaces

1. Fork this repository to your GitHub account.

2. Click the green **`<> Code`** button at the top right of your forked repository.

3. Select the **"Codespaces"** tab and click **"Create codespace on `main`"**.
   GitHub will build a container that includes:
   - ✅ Node.js (via `npm`)
   - ✅ Quarto

4. Once the Codespace is ready, open a terminal and preview the documentation:

   ```bash
   quarto preview
   ```

> **Note:** All dependencies (Node.js, Quarto) are pre-installed in the Codespace.

<details>
<summary>👩‍💻 <strong>Advanced</strong> Local Installation</summary>

#### Prerequisites

- [Node.js](https://nodejs.org/en/download/)
- [Quarto](https://quarto.org/docs/get-started/)

#### Local Setup Steps

```bash
# 1. Install Node.js dependencies
npm install
npm run prepare

# 2. Preview documentation
quarto preview
```

</details>

## For Educators and Contributors

### Adding New Exercises

We welcome contributions of new exercises! Please use our [exercise proposal template](https://github.com/maehr/critical-ai-literacy-for-historians/issues/new?template=exercise_proposal.yml) to suggest new exercises.

### Development Workflow

Check that all files are properly formatted:

```bash
npm run check
```

Format all files with [Prettier](https://prettier.io/):

```bash
npm run format
```

Preview the documentation while editing:

```bash
quarto preview
```

Commit your changes using conventional commits:

```bash
npm run commit
```

## Support

This project is maintained by [@maehr](https://github.com/maehr). Please understand that we can't provide individual support via email. We also believe that help is much more valuable when it's shared publicly, so more people can benefit from it.

| Type                                   | Platforms                                                                                                                            |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| 🚨 **Bug Reports**                     | [GitHub Issue Tracker](https://github.com/maehr/critical-ai-literacy-for-historians/issues)                                          |
| 💡 **New Exercise Proposals**          | [Exercise Proposal Template](https://github.com/maehr/critical-ai-literacy-for-historians/issues/new?template=exercise_proposal.yml) |
| 📚 **Docs Issue**                      | [GitHub Issue Tracker](https://github.com/maehr/critical-ai-literacy-for-historians/issues)                                          |
| 🎁 **Feature Requests**                | [GitHub Issue Tracker](https://github.com/maehr/critical-ai-literacy-for-historians/issues)                                          |
| 🛡 **Report a security vulnerability** | See [SECURITY.md](SECURITY.md)                                                                                                       |
| 💬 **General Questions**               | [GitHub Discussions](https://github.com/maehr/critical-ai-literacy-for-historians/discussions)                                       |

## Roadmap

- [ ] Expand exercises to cover advanced AI topics for historians
- [ ] Add interactive elements and quizzes
- [ ] Build a community of practice for AI-literate historians

## Contributing

We welcome contributions from historians, educators, digital humanists, and anyone interested in critical AI literacy! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

## Authors and Credits

- **Moritz Mähr** - _Project lead and initial development_ - [maehr](https://github.com/maehr)

See also the list of [contributors](https://github.com/maehr/critical-ai-literacy-for-historians/graphs/contributors) who participated in this project.

## License

- **Educational content and exercises**: [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)](LICENSE-CCBYNCSA.md) - You are free to share and adapt the materials for non-commercial purposes with appropriate credit and under the same license
- **Code and technical infrastructure**: [GNU Affero General Public License v3.0 (AGPL-3.0)](LICENSE-AGPL.md) - Any modifications must be made available under the same license

## Citation

If you use these materials in your teaching or research, please cite:

```bibtex
@misc{maehr2024critical,
  author = {Mähr, Moritz},
  title = {Critical AI Literacy for Historians},
  year = {2024},
  publisher = {GitHub},
  url = {https://github.com/maehr/critical-ai-literacy-for-historians}
}
```
