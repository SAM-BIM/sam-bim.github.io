# sam-bim.github.io
SAM-BIM official website

## Evidence assets

Screenshots and diagrams referenced by the homepage live in
[`assets/evidence/`](assets/evidence/README.md). That manifest lists the exact
filenames (E01–E09, V1, D1), their homepage slots and the drop-in procedure.
Placeholder slots render cleanly until the captures exist — never commit dummy
or broken imagery.

## License

Site content (text and imagery) is licensed under [CC-BY-4.0](LICENSE). The SAM software it describes is licensed separately under LGPL-3.0-or-later — see [SAM-BIM/SAM](https://github.com/SAM-BIM/SAM).

## Checks

GitHub Actions validate the site on every push/PR and weekly: HTML validity ([html-validate](.htmlvalidate.json)), link health ([lychee](lychee.toml)), accessibility (pa11y, WCAG2AA), spelling (cspell), Lighthouse budgets, and responsive screenshots. Bot-blocked domains (LinkedIn, ResearchGate) are excluded from link checking.
