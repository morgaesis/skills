# skills 🧰

Agent skills. Drop a folder into your agent's skills directory (`~/.claude/skills/` for Claude Code) and go.

| Skill | Does |
| --- | --- |
| 🎞️ [temporal-browser-observation](temporal-browser-observation/SKILL.md) | Watches a web page over time, because a screenshot taken 40 ms after the click is not a bug report. 🙄 |

![Chart.js bar chart after clicking Randomize: bars float mid-animation at 92 to 1021 ms and settle at 1226 ms](temporal-browser-observation/example/motion_trail.png)

The [Chart.js bar sample](https://www.chartjs.org/docs/latest/samples/bar/vertical.html) after clicking Randomize. At 92 ms it looks broken. It isn't. It's just not done yet. 🫠
