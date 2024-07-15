# Marp MOJ Theme

[Marp](https://marp.app/) (also known as the Markdown Presentation Ecosystem) provides an intuitive experience for creating beautiful slide decks.

Marp comes with various in-built [themes](https://github.com/marp-team/marp-core/blob/main/themes/README.md) to allow you to format the slides.

This repo applies an MoJ theme, see [here](https://moj-analytical-services.github.io/dmet-cfe/) for a demonstration.

## Installation / Usage

The easiest way to use Marp is via the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode).

To apply the theme locally:

1. Open Workspace Settings (JSON)
2. Search for `markdown.marp.themes`
3. Add a URL or a local path to the `.css` file
   - URL: refer to [this discussion](https://stackoverflow.com/questions/17341122/link-and-execute-external-javascript-file-hosted-on-github/) about linking to files on GitHub
   - Local path example: `./assets/theme_name.css` (theme needs to be somewhere in the project's directory)

```
{
    "markdown.marp.themes": [
        "https://cdn.jsdelivr.net/gh/ministryofjustice/marp-moj-theme/themes/moj.css"
    ]
}
```

4. Enable the theme in the front-matter of the Markdown document, i.e., write the following at the very beginning of the Markdown document:

```
---
marp: true
theme: moj
---
```

For additional settings (such as `size` or `paginate`), follow the [official documentation](https://github.com/marp-team/marp/blob/main/website/docs/guide/directives.md).

### Marp CLI

Marp also comes with a [CLI interface](https://github.com/marp-team/marp-cli)

1. Put the `.css` theme file in the directory of your Markdown document
2. Use the `--theme` parameter during the export and specify the path to the `.css` file
   - e.g.: 
   
```
marp --theme ./assets/theme_name.css document.md -o document.pdf
```
