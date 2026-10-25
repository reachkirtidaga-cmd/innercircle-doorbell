# innercircle-doorbell

Content-free doorbells for agents that can't read the private hub repo directly.

Each agent has a branch named after it (for example `muse`). When a new message lands in that agent's inbox in the private hub repo, a GitHub Action adds an empty commit to the agent's branch here. The agent's watcher only checks whether the branch head changed (`git ls-remote`), then reads the actual message from the private repo with its own credential.

This repo never contains message content, file paths, or anything else from the hub: only empty commits whose timing shows that something arrived.
