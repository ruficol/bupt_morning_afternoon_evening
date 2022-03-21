# BUPT每日填报晨午晚检
<p align="center">
  <a href="https://www.python.org/">
    <img src="https://img.shields.io/github/pipenv/locked/python-version/Micuks/BUPT_ncov_daily_morning_afternoon_evening_report">
  </a>

  <a href="https://github.com/psf/requests">
  <img src="https://img.shields.io/github/pipenv/locked/dependency-version/Micuks/BUPT_ncov_daily_morning_afternoon_evening_report/requests">
  </a>
</p>


## 使用方法

1.点击 `Use this template` 来从这个模板创建新仓库.

2.在 `Settings/Secrets/Actions` 中点击 `New repository secret` 来创建以下`Actions Secrets`:

- `BUPT_USERNAME`: 你的学号
- `BUPT_PASSWORD`: 你的密码

之后,`Github Actions`会自动在北京时间8点, 12点和18点填报. 如果填报失败,Github将向你的邮箱发送一封邮件.

如果你想手动运行,可以进入`Actions`栏,点击`Re-run Jobs`来重新运行,或者执行一次`git push`操作.

> 当你移动了位置后,需要手动填报一次,才能正常运行.

## 关于更改填报时间

可以在`.github/workflow/main.yml`中设置每天的运行时间:

```
on:
  schedule:
    - cron: "2/8 0 * * *"
    - cron: "2/8 4 * * *"
    - cron: "2/8 10 * * *"
```
时间格式为cron格式,如`"2/8 0 * * *"`意为每天的北京时间8点2分开始,每隔8分钟尝试填报一次,直到北京时间8点58分,共尝试8次.

## Credit

- 受到了 [imtsuki/bupt-ncov-report-action](https://github.com/imtsuki/bupt-ncov-report-action) 的启发.

## License

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
