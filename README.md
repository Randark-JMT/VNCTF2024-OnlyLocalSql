# VNCTF2024 - OnlyLocalSql

## 如何运行

```shell
cd ./docker
docker-compose up -d
```

如果遇到启动失败，请检查各个参数是否正确，也可以自行修改 `docker-compose.yml` 文件中的参数

本容器兼容 `CTFd` 平台与 `GZ::CTF` 平台，如有其他需求请自行修改服务启动脚本

## 一些来自出题人急了一整天，最后收获一堆差评的碎碎念

> 这么简单的题目打不下来？
>
> 甚至都有非预期出来了，这题目打不下来
>
> 还荣获差评率第一的 Misc 方向题目
>
> 急死我了，气饱了，晚饭都没吃

这题实质上不难，这里简要给出两种主要思路

1. SSH 转发 + 服务探测 + Mysql 恶意服务器
2. web 源码目录可控

在给出普通用户的完整 SSH 情况下，这道题的开放性可以说拉到满了，只是很多选手没有思考过 Docker 能实现多少效果，以及 SSH 究竟有多少种功能

只给了一个 SSH，不是只意味着盯着 SSH 看，你完全可以将 Docker 容器视作一个正常的 Linux 系统看待，上面可能会有数据库，会有网站，会有其他服务，不要盯着门口不会走进去

不要把 Misc 学成了 Musc，每天沾沾自喜，觉得 Musc 很好玩，自己脑洞大开很牛，不要忘了 Misc 的本质是什么，Misc 说难听一点就是彻底的脑洞大开，不要坐井观天每天都只会盯着考点越来越乱的隐写、编码、套娃，这走下去最终只能走向画地为牢的下场，最终走向大家开着玩笑说的 “学 Misc 以后连工作都找不到”。Misc 本质，就是杂，既是复杂的杂，也是混杂的杂，这次给的是 SSH 去转发 Web 服务，去攻击 PHP 的 pdo_mysql 模块，下一次也可能是其他服务去进行跳跃，不要自己给自己上枷锁

学 CTF 挺好的，但是不要目光只放在 Misc 上，面临流量分析的时候你也要接触一定的 PHP 基础，懂得 Webshell 和 Sql 注入等一般网站攻击常规手段；面对取证分析的时候，你也要接触数据库取证解密方案，也要去了解基本的程序逆向流程，这些说是 Web 和 Reverse 的流程，但是 Misc 本来就是主打一个 Misc，不可能 Misc 手生涯中就盯着隐写、编码、套娃不放，Misc 手的生涯，注定是不断学习，不断扩宽自己视野的过程

那对于打不下来这道题目，看了题目描述也想不出来解法，最后问卷题气不过就给这道题目打差评的，我只能说，在这里送上一份祝福（感谢赵总嘴替）

> 在新的一年里，愿你的代码总是报错，你的工具总是失效。愿你在数据的海洋中迷失方向，找不到任何的漏洞，就像在浩瀚的星空中找不到北斗七星。
>
> 新的一年，愿你的逻辑如同最复杂的迷宫，让你自己也迷失；你的眼光如同最模糊的镜子，看不清任何事物；你的智慧如同枯竭的河流，无法滋养任何生命。愿你在漏洞的海洋中漂流，永远找不到岸。
>
> 在这个充满挑战和机遇的新年，愿你的每一次尝试都以失败告终，每一次研究都无法为网络安全贡献力量。愿你的每一次努力都被忽视，每一次成功都被质疑。
>
> 在新的一年里，愿你的生活如同你的代码一样，充满漏洞，充满瑕疵。愿你的心情如同你的工作一样，充满困惑，充满挫折。愿你的每一天都充满新的问题，新的困扰，新的痛苦。
>
> 新年不快乐，愿你在新的一年里，找不到任何的漏洞，失去所有的成就，体验更多的痛苦！
