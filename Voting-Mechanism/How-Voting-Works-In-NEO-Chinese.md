# 在NEO网络中投票是如何工作的

由于NEO计划在2019年及以后 [加速权力下放](https://neo.org/blog/details/4125)，NEO网络上将有一些任何持有NEO的人都可以参加的投票周期。该文件汇集了如果NEO持有者想要参加投票应该了解的相关信息。

## 你有多少票？

任何持有NEO的节点都可以投票给无限数量的候选人。投票数对应于账户中持有的NEO数量。如果在投票周期期间NEO余额发生变化，候选人的投票将同时更新以反映余额的变化。

例如，如果一个帐户中有100个NEO，并且该帐户投票给3个候选人，那么每个候选人获得100票。如果在投票后，账户中的NEO被花费了，候选人的投票数将同时减少到当前的NEO余额。

## 如何选择共识节点？

投票结束后，NEO网络将以如下方法实时计算共识节点：

	* 首先，候选节点按其收到的投票数排序。

	* 然后网络计算* N *，这是排序列表中有多少顶级候选者被选为共识节点：
	
	
	1. 按大小对每个帐户投票的候选人数进行排序。例如C1，C2，…，Cn

>        注意：由于每个账户都可以投票给无限数量的候选人，因此每个账户投票的候选人数（Cn）几乎肯定是不同的。

	2. 删除阵列的前25％和最后25％。

	3. 计算剩余50％数据的加权平均值，然后将其确定为要选择的共识节点数N。

>        加权平均值取决于每个账户中持有的NEO。这意味着，在计算要选择的共识节点数时，持有更多NEO的帐户会比平均值贡献更多。

	* 一旦N被确定，拥有最高票数的前N个候选者成为共识节点。


**TL; DR** ：NEO网络通过计算每个账户投票的候选人数的中间50％的加权平均值来确定要选择多少个共识节点。

## 如何投票

在投票之前，您需要知道有哪些候选人和每位候选人的信息;所有这些都可以在NEO [共识节点页面](https://neo.org/consensus)上找到。该页面显示了在NEO区块链上注册的所有候选节点，并且候选人可以自己编辑其相应节点上的信息，例如_Website_ ，_Organization Summary_ 等。

<img src="https://raw.githubusercontent.com/taomo-eo/docs/master/Becoming_Consensus_Node/img/consensusSited1a-EN.png" width="755">

_图片：页面上的共识节点列表。_

一旦找到了您希望投票的候选人，请记下他们的_公钥_，因为在投票期间需要它们。

目前，唯一的投票方式是通过[NEO-GUI](http://docs.neo.org/en-us/node/gui/install.html)。

> 对于初次使用的用户，由于同步区块链需要相当长的时间，因此建议您使用[离线同步包](https://docs.neo.org/en-us/network/syncblocks.html)。您可以从您当前的NEO钱包中导出您的WIF /私钥，然后按照[本指南](https://github.com/neo-project/neo#import-your-wallet-to-the-pc-client)将钱包导入GUI。

	1. 在NEO-GUI中，打开钱包账户进行投票。

	2. 右键单击帐户 - >“投票”。

	3. 在Candidates字段中，输入要投票的候选人的_公钥_（在共识节点页面上可以找到）。您可以输入由换行符分隔的多个公钥。请注意，每行不能包含空格，如下图所示：

<img src="https://raw.githubusercontent.com/taomo-eo/docs/master/Becoming_Consensus_Node/img/votemulti-EN.png" width="725">
   
  _示例：给三名候选人每人100000000票_。

4.如果显示出交易ID消息，则表示您已成功投票。同样，您可以在[共识节点页面](https://neo.org/consensus)上查看每位候选人的投票数。

### 更多信息

该报告主要基于文档[如何成为NEO共识节点](https://neo-ngd.github.io/reference/How-To-Become-NEO-Consensus-Node.html)。文档本身更倾向于共识节点候选者，但可以在那里找到有关NEO共识节点选择过程的更多信息。
