# Theories of Quantum Matter

These are the materials for the Part III course Theories of Quantum Matter at the University of Cambridge

- The `master` branch contains the lecture notes that are published on [my site](https://auste.nl).

- The branch `lecture-notes-<year>` contains the files with annotations made during the lectures in `<year>`. View these with the Markdown viewer of your choice, ideally one that is LaTeX-aware: I recommend [Typora](https://typora.io).

- Feel free to [submit any issues](https://github.com/AustenLamacraft/tqm/issues) with the notes!

## Switching between master (for Hugo site) and lecture notes (for Typora)

1. Markdown files in master have extension `.pdc` so that Hugo uses pandoc as external helper. In lecture note branch change this to `.md`

2. Figures for Hugo follow the format: `{{< figure src="HOM.png" title="Four possible outcomes after the passage of two bosons through a beam splitter." numbered="true" lightbox="true" >}}`. Figures for Typora use standard markdown


## TODOs

- [ ] Better quotation styling so that quotes stand out more

- [ ] Make Typora template in the Academic style, allowing for sidenotes. Look into [Tufte CSS](https://edwardtufte.github.io/tufte-css/)
