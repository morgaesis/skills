# skills 🧰

Agent skills. Drop a folder into your agent's skills directory (`~/.claude/skills/` for Claude Code) and go.

| Skill | Does |
| --- | --- |
| 🎞️ [temporal-browser-observation](temporal-browser-observation/SKILL.md) | Watches a web page over time, because a screenshot taken 40 ms after the click is not a bug report. 🙄 |

![Chart.js polar area chart after clicking Randomize: faded ghosts of the slices from 56 to 988 ms under the settled chart at 1198 ms](temporal-browser-observation/example/motion_trail.png)

The [Chart.js polar area sample](https://www.chartjs.org/docs/latest/samples/other-charts/polar-area.html) after clicking Randomize. Screenshot it at 56 ms and you'll file a bug about the yellow slice. Don't. 🫠
