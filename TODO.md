# Open items

This file lists the open maintenance items of this repository. It does not list content work.

- Content work and course review live in the
  [issue tracker](https://github.com/maehr/critical-ai-literacy-for-historians/issues).
- The long-term goals live in the
  [roadmap](https://github.com/maehr/critical-ai-literacy-for-historians#roadmap) in `README.md`.
- The rules for a change live in
  [AGENTS.md](https://github.com/maehr/critical-ai-literacy-for-historians/blob/main/AGENTS.md) and in
  [CONTRIBUTING.md](CONTRIBUTING.md).

## Archiving and citation

The project has no release and no DOI yet. Complete these four steps in order.

1. Connect the repository to [Zenodo](https://zenodo.org/account/settings/github/). See the
   [GitHub guide](https://docs.github.com/en/repositories/archiving-a-github-repository/referencing-and-citing-content).
2. Create a `.zenodo.json` file. Add the creators, the contributors, the keywords, and the two licenses. See
   the [Zenodo documentation](https://developers.zenodo.org/#add-metadata-to-your-github-repository-release).
3. Tag the first release. The tag must match the pattern `v[0-9]*`, because `cliff.toml` looks for that
   pattern.
4. Enable the DOI badge in `README.md`. Remove the HTML comment around the badge, and replace
   `ZENODO_RECORD` with the record number from the Zenodo deposit URL. The repository ID in the badge is
   `1081381221`.

## Metadata to keep current

- `CITATION.cff`: add the DOI and the version after the first release.
- `README.md`: update the citation block after the first release.

## Done

The repository already has these items:

- GitHub security alerts and Dependabot updates
- A ruleset on `main` that requires a pull request
- A lint gate that covers every `.md`, `.yml`, `.json`, and `.qmd` file
- A publish workflow that lints, renders, checks the links, and deploys to GitHub Pages
- A changelog workflow that generates `CHANGELOG.md` and commits it to the pull request branch
