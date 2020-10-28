---
date: 2020-10-27T00:0:00+00:00
title: Serum Swap
weight: 1
---

[Serum Swap](https://swap.projectserum.com/#/) 是 Serum 上首个 AMM！ 用户可以点击 [Github](https://github.com/project-serum/oyster-swap)查看 AMM 的源代码。

{{% notice tip %}}
点击网址即刻体验 Serum Swap: [https://swap.projectserum.com](https://swap.projectserum.com)
{{% /notice %}}

## Serum Swap 运作规则简介：

Serum Swap 的操作原理类似于常见的 AMM，用户可以加入资产池进行交易。Serum Swap AMM 用的是标准的**x\*y=k 型曲线**。

搭建在 Solana 链上的 AMM Serum Swap 速度惊人！Serum Swap 处理每笔交易、资产池添加或移除，都只需**1 秒**左右！此外，还有超低的 Gas 费，每笔交易仅需约**\$0.00002 美金**。

![serum-swap](/images/articles/serum-swap/swap-form.png?classes=shadow&width=30pc)

## Serum Swap 可以流动性挖矿吗？

当然可以！用户可以自由选择给任意资产池提供流动性并挖矿。

划重点：下个月会**空投 1,000,000 枚 SRM 通证**，作为流动性供应奖励!

**SRM 流动性供应奖励细节：**

- 开始时间：香港时间 2020 年 10 月 28 日凌晨 1 点
- 结束时间：香港时间 2020 年 11 月 25 日凌晨 1 点
- 空投总量：1,000,000 个 SRM
- 空投方式: 随机挑选 20 个时间点空投，每次空投 5 万枚 SRM。
- 空投资产池：每次空投，以下罗列的 10 个资产池，每个资产池会分别收到 5,000 个 SRM 空投：

  - SRM/BTC
  - SRM/ETH
  - SRM/USDT
  - SRM/USDC
  - SRM/SOL
  - SRM/YFI
  - SRM/LINK
  - SRM/SUSHI
  - SRM/FTT
  - SRM/FRONT

{{% notice tip %}}
空投获取方法: 空投的 SRM 会直接进入自动化流动性供应池（AMM Pool），然后分给所有持有 LP 通证的用户。
{{% /notice %}}

{{% notice tip %}}
注意：上述均为指示性计划，如果实际执行中有任何挑战，我们会不惜一切努力，维持原计划的初衷。
{{% /notice %}}

## Serum Swap 的手续费

吃单手续费率是 0.3%，其中：

- 0.25% 会给到流动性提供方（LPs）;

- 0.04%会用于 SRM 的回购与销毁；

- 0.01%会给到前端网页的 Hoster（这一数值可以在网页的源代码中设定）。

吃单手续费率： 0.25%+0.04%+0.01%=0.03%

## 如何创建自己的 Serum Swap 前端网页？

### Serum Swap 前端网页开源代码

你可以点击下方链接查看 Serum Swap 前端的开源代码: [https://github.com/project-serum/oyster-swap](https://github.com/project-serum/oyster-swap). 这里面包含了搭建一个 Serum Swap 前端网页所需要的所有资源。

利用这个开源代码存储库，您可以在本地环境运行创建的前端网页，通过执行下方指令：

```bash
yarn start
```

### 手续费收取

用户如果在您创建的 Serum Swap 前端网页下单，进行了交易，您将能获取部分那些订单产生的手续费。为了获取这些手续费，您需要参考下方示例，修改一下`.env`这个文档：

```bash
# HOST Public Key used for additional swap fees
SWAP_HOST_FEE_ADDRESS=''

# Rewired variables to comply with CRA restrictions
REACT_APP_SWAP_HOST_FEE_ADDRESS=$SWAP_HOST_FEE_ADDRESS
```

为了获取这些手续费，请输在 `.env`文档中输入您的地址。

### 设置您自己的网站域名

`package.json` 文档包含了一个叫`homepage`的字段，需要把它修改为您自己的域名。

### Hosting

Host 一个自己的 Serum 前端网页有很多种方案，您可以选择通过 Github Pages 免费 host 一个前端网页，又或者在自己的服务器上运行这个前端网页。

#### 将网页 host 在 Github Pages 上

是目前最简单的一种开发和 host Serum 前端网页的渠道。您可以使用并运行下述的指令，即可在 Github Pages 上开发出自己的 Serum 前端网页。

```bash
yarn deploy
```

运行上述指令之后，这个前端网页就会 host 在您 Github 程序库的`gh-pages` 分支下面。

#### 将网页 host 在您自己的服务器上

您也可以选择将 Serum 网页 host 在您自己的服务器上，例如使用 Nginx 去运行维护它。可以通过运行下述指令来创造生产构件（production build）：

```bash
yarn build
```

运行指令后，您可以在工作目录（working directory）下面的`build`文件夹中找到这一构件（build）。

## Serum Swap 安全吗？

产品虽已经经过测试，但尚未完成审计。所有使用和资金风险全部由使用人承担。

此外，您使用的网页端报错时，可能不会阐明报错原因。如果对此有任何疑惑，请谨慎评估个人可承受的最大滑点。

{{% notice warning %}}
Serum Swap 虽已经经过测试，但尚未完成审计。所有使用和资金风险全部由使用人承担。
{{% /notice %}}

## 我可以改动前端网页设置吗？

当然可以！这就是去中心化的终极奥义：用户可以把 Serum 当做搭积木，可以对它进行任意组合，对其进行改动调整，甚至通过开源代码自己创建一个 Serum Swap 的前端网页。

感兴趣的话，可以点击访问，参考[Bonfida](http://bonfida.com/dex)和 [CCAI](http://dex.cryptocurrencies.ai)搭建的 Serum Dex 前端网页！

{{% notice tip %}}
Serum Swap 的 UI 使用 [React](https://reactjs.org) 和 [Ant Desing](https://ant.design) UI 程序库。如果想要了解如何定制，请点击他们的[官网](https://ant.design/docs/react/customize-theme)。
{{% /notice %}}

## Serum Swap 的 AMM 是上链的吗？

再一次：当然是的！Serum 本身就是**完全上链并且脱离第三方托管的去中心化生态**！

用户即刻就能使用 Solana 钱包[Sollet.io](https://sollet.io) 或者 [SolFlare](https://solflare.com)连接 Serum Swap，开始交易！

## Serum Swap 是 Serum 唯一的 AMM 吗？

其实之前已经有一个[没有上链的 AMM](https://gitlab.com/OpinionatedGeek/samm)了。
此外，请持续关注 Serum，还有更多的惊喜，比如[资产池计划](https://docs.google.com/document/d/1lmMZRKkxMFOtGOEZOFEKYL7syqv-4QT87F0o55fc35Y/edit)即将上线！
