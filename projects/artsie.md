# ARTsie

[ARTsie](https://github.com/faheemdehalvi/artsie) is a local Mac workspace, hub and shared MCP gateway around [ArtCraft's creative applications](https://getartcraft.com/apps). ArtCraft's team builds the editors. ARTsie provides the workspace and integration layer around them.

## The workflow it supports

An AI assistant first discovers which applications and tools are installed. It reads the exact schema for the operation, works on a copy of the input and saves a new project or export. The operation's result and the output file both matter when deciding whether the work succeeded.

This makes the integration useful across different creative tasks while retaining each editor's own capabilities and limitations.

## Engineering decisions worth explaining

- Discover native tool schemas before making calls. An operation name alone does not establish its current arguments.
- Keep originals and editable projects. ARTsie separates imported files, projects and exports in its workspace.
- Distinguish headless documents from visible editor windows. A headless operation does not establish that a user's desktop document changed.
- Treat timeouts as uncertain outcomes. Inspect the session or expected file before repeating a mutation.

These behaviours are described in the repository's setup and usage documentation. They illustrate the integration decisions I want to make understandable to someone using AI with creative software.

## Evidence and current limits

The public README was reviewed on 11 November 2026 at [source snapshot 5e16a90](https://github.com/faheemdehalvi/artsie/tree/5e16a9088d30d3f017cde95fe1076480132626a7). It documents thirteen editor integrations, with different support for headless and live operation.

Its verification scripts cover particular workflows, rather than every editor feature or output format. I did not run a new creative-export evaluation for this write-up, and workspace file roots should not be described as an operating-system sandbox.

## A useful next demonstration

Show an original file, import a copy, perform one edit, save an editable project and export a new file. Keep the original unchanged and inspect the result. A repeatable demonstration like that would provide clearer evidence than a list of supported tools.

[Repository](https://github.com/faheemdehalvi/artsie) · [Upstream ArtCraft apps](https://getartcraft.com/apps) · [My writing](https://faheemdehalvi.github.io/)
