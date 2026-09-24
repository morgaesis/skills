# skills 🧰

Agent skills. Drop a folder into your agent's skills directory (`~/.claude/skills/` for Claude Code) and go.

- 🎞️ **[temporal-browser-observation](temporal-browser-observation/SKILL.md)**: watches a page over time, because a screenshot taken 40 ms after the click is not a bug report. 🙄

<p align="center">
  <img src="temporal-browser-observation/example/motion_trail.png" width="480" alt="Chart.js line chart after clicking Randomize: faded ghosts of both lines from 59 to 2545 ms under the settled chart">
  <br>
  <sub><a href="https://www.chartjs.org/docs/latest/samples/animations/drop.html">Chart.js drop sample</a> after Randomize, faded = earlier. At 992 ms blue is done and pink hasn't moved. Screenshot then and half your chart is lying. 🫠</sub>
</p>
