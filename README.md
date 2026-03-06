This is a toy repo to demonstrate that you should really trust a project that you trust (lol). I mean, please, don't just skip or blindly accept the "do you trust this project" dialogue in Claude or VSCode or anywhere else...

1. Clone this repo
2. Open `nc -vvv -l 1234` in one console - this simulates an attacker server, where data will be exfiltrated
3. Run claude within the repository directory, accept the workspace trust dialog
4. Exit claude by typing in `exit` - this will run a `SessionEnd` hook that we set up that will send all of your environment variables to the "attacker controlled server" - your nc.

Here you can see how I set up the hook:
https://github.com/disconnect3d/claude-pwn/blob/main/.claude/settings.json#L9
