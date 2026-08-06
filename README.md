# New Mathematics for Pollinator Health

Website for the research collaboration on the mathematics of pollinator decline, originating from the 2026 American Institute of Mathematics workshop *Addressing Declining Pollinator Populations Through New Mathematics*.

Built with [Quarto](https://quarto.org/). Published at
<https://yunkang2021.github.io/pollinatormodeling.github.io/>.

## Local development

Install Quarto (<https://quarto.org/docs/get-started/>), then:

```bash
quarto preview      # live-reloading local preview
quarto render       # build the full site into docs/
```

## Deployment

Pushing to `main` triggers `.github/workflows/publish.yml`, which renders the site
and deploys it via GitHub Pages.

**One-time setup in the repository settings:** go to *Settings → Pages* and set
**Source** to **GitHub Actions**. No `gh-pages` branch is needed.

## Repository layout

```
_quarto.yml              site config: navigation, theme, formats
index.qmd                homepage (hero, stats, six priority areas)
research/
  index.qmd              priority research agenda
  foundations.qmd        established mathematical results
  working-groups.qmd     the eight workshop groups + cross-cutting themes
  open-problems.qmd      open questions for students and collaborators
roadmap.qmd              coordinated 12-month plan and deliverables
data.qmd                 datasets, software targets, external resources
publications.qmd         reference list
people.qmd               participants
news.qmd                 updates
contact.qmd              contact and acknowledgements
assets/
  theme.scss             colours, type scale, components
  styles.css             small refinements
  mark.svg, favicon.svg  navbar mark and favicon
references.bib           BibTeX bibliography
```

## Editing guide

**Add a news item.** Open `news.qmd` and add a new `### Month Year — Headline`
section at the top, followed by a short paragraph.

**Add a publication.** Add the entry to `references.bib`, then add a matching
bullet under the relevant heading in `publications.qmd`.

To switch `publications.qmd` to automatic BibTeX rendering instead of a manual
list, replace the body with:

````markdown
::: {#refs}
:::

<!-- cite everything so it appears in the list -->
::: {.hidden}
@perry2015rapid @kang2016disease @messan2017migration @messan2018vitellogenin
@thieme1993persistence @moore2025sterols @gekiere2024lethal @nunes2021soil
:::
````

**Add a person.** Add a row to the table in `people.qmd`.

**Add a research page.** Create `research/your-page.qmd` with a YAML header
containing `title:`, then add it to both the `navbar` menu and the `sidebar`
contents list in `_quarto.yml`.

## Design notes

The three accent colours are not decorative. They encode the bistable structure
at the centre of the science: green for the healthy equilibrium, red for the
extinction equilibrium, amber for the threshold that separates them. The
homepage hero is a schematic of three colony trajectories relative to that
threshold. Keep the accents tied to that meaning rather than using them as
generic brand colours.

Type: Fraunces (display), IBM Plex Sans (body), IBM Plex Mono (labels, data,
eyebrows). All loaded from Google Fonts in `_quarto.yml`.

## Content source

Page content is drawn from the workshop final report
(`AIM_Workshop_Report-Long-v3-GDH-7May2026.docx`). Where the report gives figures
or attributions, they have been carried over directly; the connective prose is
written for a web audience.
