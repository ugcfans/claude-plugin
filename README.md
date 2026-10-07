# UGC Fans Studio

Turn a website into a launch film from inside your AI assistant. This plugin connects Claude Code, Codex, Cursor, VS Code and Gemini CLI to the UGC Fans Studio server at https://mcp.ugc.fans/studio and adds three skills that tell the assistant how to use it: `launch-film`, `finish-clip` and `credits`.

## What it does

- Photographs a website and makes a short launch film from it, in landscape, vertical or square.
- Makes a film from chosen parts of the page, changes the words on it and exports it as a video.
- Trims, captions, reformats, brands and transcribes footage you already have in your UGC Fans library, and shares finished files by link.

## What it runs and what it sends

- Nothing runs on your machine. The plugin is Markdown and JSON: one remote server entry and three skills. It has no scripts, hooks, commands or local servers, and it installs no packages.
- Each tool call goes over HTTPS to https://mcp.ugc.fans with the arguments the assistant fills in: the website addresses you ask it to capture, text for a film, file paths in your UGC Fans library and the options you choose. UGC Fans fetches and photographs the websites you name.
- Searching the template catalogue works without an account. Everything else asks you to sign in at ugc.fans through the standard OAuth flow. The plugin holds no key, token or password in any file.

## Credits

Everything this plugin does runs on UGC Fans' own compute and spends no credits. Your balance is shown by the account tool, and plans and credits are described at https://ugc.fans/pricing.

## Install

- Claude Code: `claude mcp add --transport http ugcfans-studio https://mcp.ugc.fans/studio`, or the plugin from this repository's own marketplace: `claude plugin marketplace add ugcfans/claude-plugin` then `claude plugin install ugcfans-studio@ugcfans-studio`.
- Codex: `codex mcp add ugcfans-studio --url https://mcp.ugc.fans/studio`, then `codex mcp login ugcfans-studio`.
- Gemini CLI: `gemini extensions install https://github.com/ugcfans/claude-plugin`.
- Other clients: add https://mcp.ugc.fans/studio as a remote Streamable HTTP server.

## License

MIT. See `LICENSE`.

Source: https://github.com/ugcfans/claude-plugin, published from the UGC Fans product tree; a change lands here with the ship that made it.
