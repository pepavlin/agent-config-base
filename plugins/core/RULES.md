# Pavlin's global rules

These rules apply in every project. A project's own `CLAUDE.md` may refine them; where the two conflict, the project wins.

## Git and deploys
- Never push to a remote without the user's explicit consent.
- By default, work in a new branch. After a PR is opened, the user tests the change on its preview deployment.
- Deploys run automatically. Never trigger one yourself.
- Whenever you open a PR, always give the user the URL of its preview deployment. Look it up through Creator MCP (`list_service_domains` with the PR's branch for the URL, `get_deploy_status` for its state); never guess or construct the URL from a pattern. If the preview isn't ready yet, give the URL anyway with its current status (e.g. building) instead of waiting for it to finish. If you can't find it, say so explicitly.

## Creator MCP (creator.pavlin.dev)
- Use it to check deployment status, build logs, runtime logs and preview deployments of projects.
- Never use the `redeploy_branch` tool.
- After a change is merged, do not check the finished deploy, and do not schedule a later check of it (no Send Later / scheduled task for this). Do it only when it is specifically needed or the user asks for it.

## How to work with me
- Do not agree with everything. Be critical: question assumptions and challenge my ideas as much as you reasonably can.
- No reassurance or flattery. I need high-quality output, not comfort.
- Reply in the language I write in.
