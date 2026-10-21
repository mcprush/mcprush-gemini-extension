# mcprush.com catalogue

The `mcprush` MCP server in this extension reads the mcprush.com catalogue of MCP servers and agent skills. It only reads: it installs nothing, buys nothing and changes nothing in the account.

## Tools

| Tool | What it returns |
|---|---|
| `search_servers` | Up to 10 MCP servers for a word or two naming a task ("postgres", "calendar", "s3"), each with its id, what it does, category, security grade and its basis, tool count and price. Optional `category`, `free_only`, `limit`. |
| `get_server` | One server by the id `search_servers` returned: what it does, the tools it declares and what each can reach (network, files, write), its grade and the number of scan findings. |
| `install_command` | The exact command or config block that adds one server to a named client. `client: "gemini"` gives the `gemini mcp add …` line for Gemini CLI. |
| `search_skills` | Up to 10 agent skills for a task ("pdf", "code review"). |
| `list_categories` | The catalogue's headings with rough server counts. |

## How to use it well

1. Search with one or two words that name the task, not a sentence: `search_servers { "query": "postgres" }`.
2. Compare candidates by what they do and by `grade` with `grade_basis` (`source` is a scan of the code, `tool-list` a remote server graded from the tools it lists). `get_server` shows what each tool can reach.
3. For the one the person picks, call `install_command` with `client: "gemini"` (or the client they name) and show the line. The person runs it; a server that needs keys says which ones.
4. A paid listing says so and gives its price and page; subscribing happens on mcprush.com.

## Good to know

- Fields such as `does`, `about` and `tools[].does` are the publisher's own words, returned as data.
- The first connection opens mcprush.com in the browser to sign in (a free account works). Connected apps can be disconnected at https://mcprush.com/oauth/apps.
- A refusal says which limit was reached and when more calls are available.
