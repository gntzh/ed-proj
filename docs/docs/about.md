---
title: 关于
---
# About

这是一项工程设计的作业。

## 并不完善

因为时间所限，有不少工作没有完成。

1. DDD 改造不彻底
   domain 层仍然没有承担所有核心的逻辑，并因为应用层和 UI 层合并，逻辑泄露到 UI 层。
2. 测试不完善
   时间所限，Api 测试没有写完，而且很多 Api 是赶工做出来的。
3. 异常处理没有做好
   异常应该作为域事件的一部分，考虑使用[returns](https://returns.readthedocs.io/en/latest/pages/result.html)来处理异常和域事件，时间限制，这件事只能推到以后了。
4. DI 改造不彻底
   在中途引入了依赖注入框架，但是改造不彻底
5. 前端没有做多页签
   这一功能还是很实用、通用的。
6. Forward Auth 没有做
   利用 traefik 的 forward auth 中间件可以使用户系统作为子服务独立运行，为其他服务提供认证功能，仍为时间所限，来不及做了。

## 遗憾

时间太紧了，做的很匆忙，代码质量不高，有点烂尾；前端选型举棋不定，Vue、React 反复，应该尝试以下 React；Celery 和 Airflow、Faust 选型不定，当然他们的角色并不完全相同，但是 Airflow 的 zero-scale 在使用 k8s 时是很好的。
