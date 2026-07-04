# Security Policy

theBABrain is a markdown-based framework: files an AI agent reads and acts on. There is no server, no database, and no hosted service — so most typical vulnerability classes (auth bypass, SQL injection, CORS misconfiguration) don't apply here.

## Reporting a vulnerability

If you find a security issue, please report it privately by opening a [GitHub security advisory](https://github.com/agabalcerzak/thebabrain/security/advisories/new) rather than a public issue.

## The risk that does apply: instruction injection

theBABrain's skill and template files are instructions an AI agent reads and follows literally. A malicious contribution could embed instructions designed to manipulate that agent — for example, hidden text in a demo file or skill definition telling the agent to exfiltrate data or ignore its rules.

Because of this:
- Review skill/instruction files (anything under `skills/`, and the framework's core `.md` files) carefully before merging, treating them as executable, not just documentation.
- Be cautious with demo or example data submitted by outside contributors — treat unfamiliar content as untrusted input, not as instructions to follow.
