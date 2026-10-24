# Local Ollama skills

The skill source files live in `.dsh/skills`. DeepSeek Harness can discover them from a project root, and `bin/local-skill` loads the same files for local Ollama requests.

```sh
./bin/local-skill list
./bin/local-skill /think "Compare these approaches..."
./bin/local-skill /debug --model deepseek-r1:14b "Diagnose this error..."
./bin/local-skill chat
```

In `chat` mode, enter `/think your question` or another skill slash command. The script uses a model specified by `--model`, `LOCALAI_MODEL`, or `OLLAMA_MODEL`; otherwise it picks the first currently running model from `ollama ps`. Start Ollama and a model first, for example `ollama run gpt-oss:20b`. `--think` requests Ollama thinking output when supported. `OLLAMA_HOST` can override the default local API URL.

Ollama's own interactive `ollama run` prompt does not load custom slash commands. Use this launcher as the chat entry point when you want `/think` and the other skill commands. Chat mode sends requests to the same Ollama server and remembers the conversation for that launcher session.

To invoke the command from anywhere, add this directory to your shell PATH:

```sh
export PATH="/Users/phenzic/Documents/workspace-skills/bin:$PATH"
```

For Harness discovery, open this directory as the project root. Harness scans `.dsh/skills/<name>/SKILL.md`; if your Harness project is elsewhere, copy or symlink its `.dsh/skills` directory into that project. The skill files provide roles but do not create an automatic multi-model pipeline.
