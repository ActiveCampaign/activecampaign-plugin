# Changelog

All notable changes to the ActiveCampaign plugin are documented here.
This project follows [Semantic Versioning](https://semver.org/).

## [0.2.0] — launch preparation

### Added
- **Deals & CRM skill** — create/update deals, build and reorganize pipelines and stages, move deals between stages, bulk-reassign owners, manage deal notes, and model data with custom objects. All writes use a preview → confirm → execute → verify contract.
- **Write capabilities** across Contact Operations and the Data Operations agent, aligned to the production server's actual write tools (contacts, tags, lists, fields, bulk import, deals/CRM, custom objects).
- `LICENSE` (MIT), `CHANGELOG.md`, support contact, and a data-handling note (see README).
- Extracted into a **standalone single-plugin repo** (`amurrey/activecampaign-plugin`) with the plugin promoted to the repo root, in preparation for `claude-community` submission.

### Changed
- Reports (`/campaign-report`, `/weekly-digest`, `/automation-audit`, `/audience-health`, `/deal-pipeline-review`) and the Reporting Analyst skill now comply with the server's no-aggregate rules: they present per-record counts and top-N sorted records instead of computing win rate, completion rate, averages, totals, or conversion. They point to AC's native reporting for true roll-ups.
- Skill `allowed-tools` now pre-approve each skill's **read** tools (smooth UX) while leaving **write** tools to the native permission prompt (safety gate).
- README rewritten to match the real server (60 tools), the actual file layout, the true capability boundaries, and Anthropic-directory distribution.
- Author identity set to ActiveCampaign (official); licensed under MIT.

### Fixed
- Corrected nonexistent tool names `list_pipelines` / `list_stages` to the real `list_deal_pipelines` / `list_deal_stages` across the marketing-planner agent, weekly-digest and deal-pipeline-review commands, and the reporting-analyst skill.
- Removed references to nonexistent config files (`.mcp.production.json`, `.mcp.dev.json`) and an incorrect install path from the README.

## [0.1.0] — initial internal version
- First version: 5 skills, 5 commands, 2 agents, MCP connection via `userConfig` URL.
