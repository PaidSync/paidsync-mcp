# Contributing to PaidSync

This repo documents the hosted PaidSync MCP service. The MCP server source code is closed, but the docs, examples, and prompt library in this repo are open for contributions.

## What you can contribute

- **New AI client integration example.** A new entry in `examples/` for an MCP-compatible AI client we do not cover yet.
- **New prompt recipe.** A useful prompt for a specific workflow (cross-channel audit, conversion tracking setup, agency reporting). Add to `examples/prompts.md`.
- **Documentation fix.** Typo, outdated info, clearer wording.
- **Comparison row.** If you maintain a competing MCP server for ads and want to be added to the comparison table in the README, open a PR with your data.

## What is out of scope

- Source code for the PaidSync MCP server. The server is a hosted managed service, not open source.
- Pricing or plan changes. Pricing is set by the PaidSync team.
- New tool requests. Use [the PaidSync feedback form](https://paidsync.ai/feedback) instead.

## How to contribute

1. Fork the repo.
2. Create a branch: `git checkout -b add-prompt-pmax-audit`
3. Make your change. Keep edits focused (one PR per topic).
4. Open a PR with:
   - What you added
   - Why it matters
   - A real-world scenario where the example or prompt applies
5. We review weekly. Most PRs merge or get feedback within 7 days.

## Style rules for prompts and docs

- Use plain English. No SaaS jargon ("supercharge", "unleash", "game-changer").
- No em dashes. Use periods, commas, or restructure.
- Specific is better than vague. "Pause ad groups under 1.5x ROAS" beats "optimize underperformers".
- Mention real platforms by name (Google Ads, Meta, LinkedIn, TikTok) not "all your ad platforms".
- Prompts must be paste-ready. Someone should be able to copy your prompt directly into Claude or ChatGPT and run it.

## Code of conduct

Be useful, be specific, be honest. If you maintain a competing MCP server, we welcome you in the comparison table. Disagreements about feature accuracy are resolved with screenshots and live tests, not arguments.

## License

By contributing, you agree your contribution is licensed under MIT (same as this repo).
