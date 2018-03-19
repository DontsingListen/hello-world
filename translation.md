## Binance Dexathon
Decentralized Exchange Coding Competition

## 币安十项全能运动
去中心化交易编程竞赛


### Overview
### 总览
Currently, decentralized exchanges are inefficient and difficult to operate for the average user. As a result, they generally have reduced liquidity. Cryptocurrency is evolving at a rapid rate and we must ensure that blockchain technology is able to keep up.

目前，去中心化交易不够高效，并且对普通用户来说存在操作难度。导致它们的交易量日渐减少。但加密货币正以高速发展，所以我们必须确保区块链技术是可以跟上的。

This is an all-hands-on-deck initiative, combining the state-of-the-art technological excellence at Binance and the best of the community to once again push the envelope in blockchain technology.

这是一个结合币安最顶级的技术优势和最好的社区支持，又一次推动区块链技术，呼吁所有人参与的倡议。

In addition to having internal teams working on dex implementation, we will continue our community-driven approach and work closely with our community to build the next generation blockchain.
除了让内部团队开展去中心化交易所的工作，我们将会继续运用社区驱动手段，与社区紧密结合来建设下一代区块链。

To help facilitate this innovation, Binance will host a coding competition with the clear intent of merging the best implementation(s) and/or team(s) into Binance Chain. On top of this, we will also offer a total prize pool equivalent of $1,000,000 USD, paid in BNB. How does winning a million dollar prize, then joining the Binance team, sound to you?
为了帮助促进这项创新，以“为币安链引进最好的技术和/或团队”为清晰目的，币安将会举行一个代码竞赛。在这个基础上，我们还会提供一个总价值$1,000,000美金（通过代币BNB支付）的奖金池。那么赢得一百万美元的奖金，然后加入币安团队，对你来说够吸引力吗？

This paper outlines the high level requirements of what we are looking for, as well as our initial design philosophies for the Binance Chain.
这篇文章列出了我们正在突破的高层面要求，同时也是我们对币安公链的原始设计理念。

### Goal
### 目标

The objective of this project is to solicit prototypes of a decentralized exchange with a focus on speed and capacity, or more precisely, a dex blockchain that is low-latency and high-throughput.
该项目的目标是征集去中心化交易的原型，其特点是：重点关注速度和容量，或者更确切地说，是一个低延迟和高吞吐量的去中心化交易所区块链。

The dex prototype should have the following features:
该去中心化交易所原型应该具有以下特点：

- Sending and receiving of the native coin
- New token creation
- Sending, receiving, freezing, and burning of tokens
- Ability to trade one token with another token (all within the same chain)

- 发送和接收原生货币
- 创建新代币
- 发送、接收、冻结和销毁代币
- 能够进行币币交易（两种代币都在都一个链中）

Bonus feature:
加分点

- Native on-chain ICO
- 原生链上ICO

For performance, we recommend the following design considerations:
对于性能，我们推荐以下的设计原则：

- All features mentioned above built-in natively to the blockchain
- No support for smart contracts, virtual machines or turing complete languages
- If a trade-off is required, always choose speed and simplicity over fancy features.

- 所有以上提到的特征与原生区块链无缝连接
- 不支持智能合约，虚拟机和图灵完备语言
- 如果需要权衡，总是选择快速和简洁而非花俏的功能

### Mining & Consensus
### 挖矿与共识

A blockchain where all native tokens are pre-mined, there will be no mining (all BNB coins will be converted from BNB ERC20 tokens that already exist today). You are free to use any consensus algorithm you like; performance is key.

该区块链的所有原生代币已预先发行，所以不需要挖矿（所有将会转换成BNB货币的ERC20系BNB代币目前已经存在）。你可以使用任何共识算法，但性能是关键。

### Basics
### 基础
Basic features such as block generation and sending/receiving of the native coin should obviously be included. You are also free to use graphs instead of chains, assuming you can make it work reliably.
产生区块和发送/接收原生货币等基础功能明显是需要的。你也可以自由使用图技术而不是链技术，前提是能稳定工作。

### Token Creation
### 产生代币
Native support for new token generation is required. That is, users should be able to create new tokens simply by specifying token parameters, such as symbol, total supply, decimals, etc, without having to write smart contracts. New token generation will cost a fee, payable in the native coin of the blockchain.
对发行新代币的原始支持是必需的。也就是说，不用必须写智能合约，用户可以通过简单的指定符号、最大量、小数点等代币参数来创造新代币。发行新代币需要消耗一定的费用，该费用可通过区块链原生代币来支付。
Tokens can follow a simple structure; fixed supply, all pre-mined, etc. Again, if there is a need for a trade-off between advanced features vs speed and simplicity, the latter wins.
代币可以遵循一些简单的结构，例如指定供应量，全部预先挖出等。在此重申，如果需要在高级功能和速度与简洁之间权衡，总是后者胜出。

### Orders & Trades
### 订单和交易
Users should be able to place orders and trade one token for another directly on the blockchain. These orders should be natively supported by the blockchain and not via smart contracts. Limit GTC orders must be supported, and bonus points may be awarded for limit FOK and IOC, market, and other advanced order types, but keep in mind that speed is of higher priority.
用户可以直接在区块链上进行下订单和交易代币。这些订单不能通过智能合约实现，只能由区块链提供本地支持。必须支持限制GTC订单，有限制FOK和IOC，市值和其它高级的订单类型可能会有额外的加分点，但是请记住速度是最优先级的。
An order should contain:

-  Symbol (trading pair)
-  Side
-  Price
-  Amount
-  Expiry time (in blocks)
-  Owner

一个订单需要包括：

- 符号（交易对）
- 买方或卖方
- 价格
- 数量
- 到期时间（区块高度）
- 所有者

Trading is done via sending orders to the network. As network resources are required to process each order, a fee will apply. The order fee will be dynamically adjust based on how busy the network is, similar to other network fees. Order fees are charged when the orders are submitted to the network.
命令一旦发送到网络，交易马上完成。由于处理每一个订单需要网络资源，相应的需要支付费用。与其他网络交易费用类似，订单费用将会根据网络拥挤程度动态调整。一旦订单提交到网络，订单费用就会被收取。
Orders can be cancelled before they are traded. Each cancellation is also a new message to the network, thus incurring another network fee.
在完成交易之前，订单可以取消。但是每单取消对网络来说也是一个信号，所以将会收取另外一笔网络费用。
If an order matches against another order, a trade event happens. A trade is simply one atomic event involving two token transfers on the network. Again, network transfer fees will apply.
如果一个订单与另外一个订单相匹配，一个交易事件就会触发。在网络上，一笔交易仅仅是包含在此交易中的两个代币之间转移的简单原子级事件。同样的，这也要支付网络传输费用。
A trade should also trigger an execution report. We recommend an execution report structure similar to standard FIX 4.4 or higher protocol.
交易也应该触发一个执行报告。 我们推荐一个类似于标准FIX 4.4或更高协议的执行报告结构。

### Matching Engine
### 撮合引擎
You are free to use on-chain or off-chain matching engines in your design. The main consideration factor should be performance.
你可以在你的设计中自由使用链上或者链外撮合引擎，最主要的考虑因素是性能。

### Nodes
### 结点
Nodes on the blockchain will handle:

-  Sending of the native coin
-  Issuing of tokens
-  Sending/receiving of tokens
-  Placing orders and handling trades

链上的结点应该能够处理：
- 发送原生货币
- 发行代币
- 发送、接收代币
- 挂单和交易

Nodes on the network will be compensated by transfer, order, trading, and other fees. Other fees include token creation, and potentially ICOs at a later date.
网络上的结点可以通过传输、挂单、交易和其他费用得到补偿。其他费用包括发行代币和其后潜在的ICO。
For this competition, nodes running in one OS will suffice, ideally Linux.
在这个环节，结点必须满足在OS系统运行，能在Linux系统运行就更完美啦。

### Wallet
### 钱包
The wallet is the user’s interface to the blockchain. For the purpose of this dexathon, GUI wallets are not required and a command line interface (CLI) will suffice.
钱包是链上用户交互。基于这个竞赛的目的，GUI钱包不是必需的，命令行模式（CLI）就足够了。

### ICO
### 初始代币发行
While not required, a natively supported ICO implementation will definitely earn bonus points.
虽然不是必需的，但一个对ICO功能的本地支持必定是个加分点。

### Implementation
### 实现
We generally like to see new implementations built from scratch, but you may choose to fork existing blockchain implementations and improve upon them. You must ensure you do not violate any copyright or license restrictions.
我们通常比较青睐从头开始构建的新方案，但您可以选择分叉现有区块链实现并对其进行改进。 并必须确保您没有违反任何版权或许可限制。
Considering each trade may involve many orders, you will probably want to avoid (or change) blockchains that only allow you to have one input and one output address. Bitcoin’s many-to-many model may be a better fit here.
考虑到每单交易可能包含很多个订单，你可能会避免（或者改进）只允许有一个输入和一个输出地址的区块链。这种情况下，比特币的多对多模型或许更加适用。

### Prize
### 奖金
As previously mentioned, we will offer a prize pool equivalent to $1,000,000 USD, paid in BNB. In addition, winning team(s) may also be considered for employment.
正如前面提到的，我们将会提供一个总价值$1,000,000美金（通过代币BNB支付）的奖金池。并且，可能会为获胜队伍提供币安的工作机会。

### Schedule
### 进程
All entries must be submitted by June 30th, 2018 23:59 UTC. Any entries submitted after this deadline will be ineligible.
所有参赛作品必须在UTC时间2018年6月30日23:59之前提交。 在截止日期之后提交的任何材料都将视为不符合资格。
You may submit your application now and continually update it until the deadline. After the submission deadline, Binance will take a reasonable amount time to review the submissions.
你可以现在就提交参赛申请，在截止日期前再逐渐补全信息。在提交截止后，币安将会花费足够的时间来检查申请。

### To Apply
### 申请
You must register to participate in this competition. Please send the information below to dexathon@binance.com:
参加比赛之前你必须先注册，请把以下信息发送到dexathon@binance.com

-  Name(s)
-  CV(s) or LinkedIn link(s)
-  Team size
-  Github repo location (can be private during the competition)

- 名字
- 简历或领英链接
- 团队人数
- Github仓库地址（在比赛期间可以是私人的）

### University Teams
### 大学团队
We encourage university teams to participate in our competition, and offer a special grant of $10,000 per qualified team — even if you don’t win.
我们鼓励大学团队参加我们的比赛，并为每个合格的队伍（即使没有赢得比赛）发放特定的10000美金奖金。
To apply for this, please have your favorite professor from your university contact us directly at dexathon@binance.com.
如果想申请，请让大学里您最喜爱的教授通过 dexathon@binance.com直接联系我们。

### Questions
### 疑问
If you have any questions, please feel free to contact us at dexathon@binance.com. You must have already submitted your application before asking detailed questions about the competition.
如果你有任何疑问，请随时通过邮箱dexathon@binance.com联系我们。但是在咨询比赛详细问题之前，你必须已经提交参赛。
Lastly, Binance reserves all rights to adjust the rules of this competition, with or without further notice.
最后，币安保留调整本次比赛规则的权利，恕不另行通知。

原文链接： https://medium.com/binanceexchange/binance-dexathon-845dc0cbfffe
译者： lllds 2018-3-19

