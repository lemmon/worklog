# worklog

Preview `WORKLOG_<id>.csv` files in the browser and export them to PDF. One dependency-free PHP file.

## CSV

```csv
date,hours,budget,task_description
2026-10-21,1.00,framework,"Intro call: form email problem, maintenance"
```

- `budget` is optional. Empty or `default` means no budget.
- A log with one budget names it next to the title. A log with mixed budgets labels each row and adds subtotals.

## Use

Run from a project root. CSV files are found in `.` or `./docs`.

```sh
worklog                        # preview in the browser
worklog --lang=sk              # Slovak labels, decimal comma
worklog pdf 2026-10            # WORKLOG_2026-10.pdf in the current directory
worklog pdf 2026-10 --out="$HOME/Desktop"
```

PDF export uses headless Google Chrome. Set `WORKLOG_CHROME` to use another Chromium executable.

## Install

```sh
composer global config repositories.worklog path ~/Sites/worklog
composer global require lemmon/worklog:@dev
```
