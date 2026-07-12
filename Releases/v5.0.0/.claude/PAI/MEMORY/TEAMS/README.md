# TEAMS

`TEAMS/` stores configuration and runtime state for predefined agent teams — multi-agent workflows that spin up coordinated sets of subagents for tasks like council debates, parallel research, or red-team analyses. The `Agents` skill manages team definitions and the runtime artifacts those teams produce.

Where individual agent runs are scoped to their slug in `WORK/`, team-level metadata, shared blackboards, and cross-agent context live here so the team can resume cleanly.

Empty in fresh installs. Populates the first time you spin up a team via the `Agents` skill or any workflow that orchestrates multiple agents. Edit by hand only when adjusting team-level config.
