----------------------------------------------------
----------------------------------------------------
当使用次要的PDP上下文激活过程时，在消息中不应包含‘选择模式’，'IMSI','MSISDN','端用户地址‘。。。
----------------------------------------------------
3/25 14:38
	在9053上更新双teid_u的版本，重启时间14：20
	14:20
15	14:35	40W用户.
40	15:00	128W	增速	3w/min
90	15:50	278W		3w/min
60	16:20	362W
150	16:50	454W
180	17:20	530W


15:50 9052	1440
	15:50
30	16:20	106W
60	16:51	212W
240	19:51	720W
	21:06	912W
	22:55-23:23	增速趋于7000以下

20:30 9053重新换se，360=3h
23:23 9052换se	360	3000以下

3/26	9053	13:30 720	0cf34599d52d10ae3540398d5589f913
----------------------------------------------------
3/24 21:50;
	9052 double_teid
	9053 ip_idx
----------------------------------------------------
ssh root@182.245.126.78 -p 9053
-----------------------------------------------------
 192.168.1.53 sw
					4056(1,4)	4057(1,0)
vlan add member 1 4056 25 0
vlan add member 1 4057 25 0
vlan remove member 1 4056 10 
vlan remove member 1 4057 22
vlan add member 1 4056 10 1
vlan add member 1 4057 10 1
pvid set 1 25 4032 1 1 
vlan add 1 4032
vlan add member 1 4032 10 1 

   192.168.1.52 sw

vlan add member 1 4057 10 1 
vlan remove member 1 4057 22
pvid set 1 25 4032 1 1 
vlan add 1 4032
vlan add member 1 4032 10 1 
vlan add member 1 4056 25 0
vlan add member 1 4057 25 0
------------------------------------------------------


19:28 3/24	FPA下降有些快。
sgsn_nodes = 24186, update_nodes = 7545
ggsn_nodes = 5736995,ip_nodes = 5737408


交谈中请勿轻信汇款、中奖信息、陌生电话，勿使用外挂软件。
陈小阳(251779677)  16:00:52
我终于上来了

182.245.126.78：15001
182.245.126.78：15002
吴海波(1191107987)  16:01:45
你把你的规则贴进来
16:02:48  吴海波邀请了慕年鹏加入讨论组
陈小阳(251779677)  16:04:00
=============================================================1.1.0.51
vlan add 1 4032
vlan add member 1 4032 25 1
vlan add member 1 4032 10 1
vlan add member 1 4032 22 1

vlan add 1 4033
vlan add member 1 4033 25 1
vlan add member 1 4033 10 1
vlan add member 1 4033 22 1


pcltest -d 1 -i 4 -v 4032 -M 2123 -p 1 -r 1 
pcltest -d 1 -i 4 -v 4032 -N 2123 -p 2 -r 2
pcltest -d 1 -i 0 -v 4033 -M 2123 -p 3 -r 3
pcltest -d 1 -i 0 -v 4033 -N 2123 -p 4 -r 4



vlan add 1 4034
vlan add member 1 4034 10 1 
vlan add member 1 4034 22 1  


=======================================================1.1.0.50
# vlan remove member 0 4032 27 
# # vlan remove member 0 4033 27 
# # vlan remove member 0 4033 1 
# # vlan remove member 0 4034 27 
# # vlan remove member 0 4034 2 
# # vlan add member 0 4034 0 0
#
#
# pvid set 1 25 4034 1 1
# vlan add 1 4034
# vlan add member 1 4034 10 1 
# vlan add member 1 4034 22 1  
# # vlan add member 1 4034 16 1
#
# vlan add 1 4032
# vlan add member 1 4032 25 1
# vlan add member 1 4032 10 1
# vlan add member 1 4032 22 1
#
# vlan add 1 4033
# vlan add member 1 4033 25 1
# vlan add member 1 4033 10 1
# vlan add member 1 4033 22 1
#
# pcltest -d 1 -i 4 -v 4032 -M 2123 -p 1 -r 1 
# pcltest -d 1 -i 4 -v 4032 -N 2123 -p 2 -r 2
# pcltest -d 1 -i 0 -v 4033 -M 2123 -p 3 -r 3
# pcltest -d 1 -i 0 -v 4033 -N 2123 -p 4 -r 4
#
# 加#的是配置后，注释掉的，
# 罗尔夫(80244085)  16:05:59
# ip port ssh不上
# 陈小阳(251779677)  16:06:07
# 现在再试试
# 182.245.126.78端口为：15001   
# 182.245.126.78端口为：15002
# 罗尔夫(80244085)  16:08:15
# 谁你连上吗？
# 吴海波(1191107987)  16:08:45
# 我都ping不通
# 设置防火墙了么
# 陈小阳(251779677)  16:09:45
# 恩，需要通过绿盟的防火墙
# 还在调，再等一会儿
# 陈小阳(251779677)  16:14:22
# 谁要远程？只能先远程协助了
# 罗尔夫(80244085)  16:18:20
# 不能ssh了
# 陈小阳(251779677)  16:18:39
# 好像绿盟的设备有问题
# 吴海波(1191107987)  16:18:56
# 果然不可靠啊
# 哎，他要是OEM咱们的估计就没问题了
# 陈小阳(251779677)  16:19:23
# 美亚的研发工程师好像也在远程调试，所以也不能重启防火墙
# 罗尔夫(80244085)  16:19:58
# 他们怎么远程登陆得？
# 陈小阳(251779677)  16:20:13
# 同样的规则，他们就可以，我们就不可以
# 罗尔夫(80244085)  16:20:23
# 应该还是映射端口出来得吧
# 靠，没天理
# 陈小阳(251779677)  16:20:32
# 恩
# 我远程协助吧
# 登陆到我的电脑，然后再跳转
# 吴海波(1191107987)  16:23:50
# 学毅，你登陆上去了么
# 罗尔夫(80244085)  16:24:08
# 还没有
# 吴海波(1191107987)  16:24:30
# 哦，你先看吧，我是想上去看一下交换芯片的配置
# 因为PCL 广播的这个东西在实验室没有做过测试
# 陈小阳(251779677)  16:24:54
# 那我远程学毅了
# 罗尔夫(80244085)  16:25:03
# 好
# 陈小阳(251779677)  16:26:04
# 学毅没收到我的远程协助吗
# 罗尔夫(80244085)  16:26:27
# 没有啊
# 陈小阳(251779677)  16:26:21
#
#
# 吴海波(1191107987)  16:27:00
# 估计是网速问题
# 陈小阳(251779677)  16:27:35
# 我管了重新申请远程，有吗
# 关
# 罗尔夫(80244085)  16:28:49
# 清孟先上去看一下，有多少用户同时在线？fpa空间够不够
# 我还在找问题
# 孙清孟(361841482)  16:29:15
# 嗯
# 那海波先下了吧
# 吴海波(1191107987)  16:30:19
# 能查看多少用户在线？这个功能灰常不错哦
# 很有用哦
# 吴海波(1191107987)  16:33:50
# 小阳，能不能写个脚本，每分钟读一次这个数据，保存下来，这个数据会有一定的参考意义
# 罗尔夫(80244085)  16:33:55
# MAC QQ上没有找到远程协助
# 等等
# 吴海波(1191107987)  16:34:40
# 难道MAC上没有这个功能？可能是苹果系统的原因哦，用虚拟机呢、
# 孙清孟(361841482)  16:34:52
# 我断开。
# 陈小阳(251779677)  16:34:51
# 我重新更改一下管理口ip，看看能不能完成端口映射
# 恩，
# 孙清孟(361841482)  16:36:32
# 临时节点有：3734
# 学习到的用户：147 8232
# FAP5剩下：651 5074
# 陈小阳(251779677)  16:36:45
# 182.245.126.78端口为：9052   
# 182.245.126.78端口为：9053
#
# 罗尔夫(80244085)  16:36:51
# tim得fpa呢
# 陈小阳(251779677)  16:36:52
# 现在好像可以了吧
# 罗尔夫(80244085)  16:37:04
# 试一下
# 孙清孟(361841482)  16:37:09
# 忘记读了
# 罗尔夫(80244085)  16:37:40
# 可以了，密码？
# 陈小阳(251779677)  16:37:41
# 管理口的ip是临时加的，注意不要重启
# juson
# 陈小阳(251779677)  16:40:52
# 状态对吗
# 罗尔夫(80244085)  16:49:37
# 里面得两条规则是要配置得吗？
# 我看到CPU输出报文没有负载均衡
# 流量不是很大，可以考虑用一个板卡试一下，简化拓扑
# 陈小阳(251779677)  16:52:46
# 关于我们设备的打标签比例显示，美亚的周成祖好像比较关心这个，刘学毅有空的时候，能不能跟他沟通一下详细的细节问题
# 陈小阳(251779677)  16:55:49
# 没有负载均衡？我刚刚统计了一遍速率，38个业务接口基本上都在90Mbps~100Mbps之间
# 罗尔夫(80244085)  17:00:47
# 嗯，我跟周沟通一下，目前因为在实验室找之前发现得问题，还没来得及理会这个事
# 罗尔夫(80244085)  17:01:58
# 你告诉他现在我们上面可以读即时得在线用户数
# 陈小阳(251779677)  17:02:30
# 罗尔夫(80244085)  17:05:34
# 一个万兆大概150万，差不多一起600万左右用户同时在线
# 陈小阳(251779677)  17:06:36
# 不是这么算吧，信令报文是广播到所有56CPU的
# 吴海波(1191107987)  17:07:04
# 学毅，这个是怎么看的，你跟我说下，我写个脚本，然后把这些信息都循环读一下，做一个24小时的数据图出来，这个非常有用
# 罗尔夫(80244085)  17:08:36
# 清孟说吧
# 吴海波(1191107987)  17:09:36
# 这样吧，清梦，等下我找你，你给我说一下吧，QQ里边不好说
# 孙清孟(361841482)  17:09:43
#
# MCDebug(config-zxmdu-cn56a)# gtp_imsi show all
#
# sgsn_nodes = 3761, ggsn_nodes = 1368248, ip_nodes = 1368286
# 嗯，好的，这个得手动看。不过跟csr寄存器的差不多，可以用脚本记录那个值。
# 罗尔夫(80244085)  17:10:49
# 现在一个板卡得两个CPU是136W，另一个是163和156W
# 吴海波(1191107987)  17:11:28
# 信息量还是比较大的
# 罗尔夫(80244085)  17:12:33
# 如果能保证原始一条链路得上下行在一个CPU上处理就是最好得了
# 吴海波(1191107987)  17:13:25
# 呵呵，那帮人肯定懒得去弄这些，分光汇聚后肯定搞不清楚
# 罗尔夫(80244085)  17:21:42
# 奇怪报文都是从一个万兆发往Switch
# ？
# 是哪个ip地址的万兆
# 需要我这里查一下线路吗
# 吴海波(1191107987)  17:25:49
# 没有负载均衡？
# 陈小阳(251779677)  17:25:59
# 我先去吃饭，有时给我电话
# 有事
# 罗尔夫(80244085)  17:26:17
# 跟线路没有关系
# 好
# 罗尔夫(80244085)  17:44:53
# 小阳，你回来得时候试一下把四个万兆的数据往一个CPU发
# 陈小阳(251779677)  17:58:06
# 回来了
# 我现在就给设备下电重启，然后重新配置
# 还有人在设备上吗？
# 罗尔夫(80244085)  18:01:04
# 我没有
# 孙清孟(361841482)  18:01:13
# 没在
# 陈小阳(251779677)  18:01:26
# 那我下电了
# 熊猫的熊(19550252)  18:06:21
# 现在标签率多少了
# 陈小阳(251779677)  18:14:13
# 刘学毅，我已经把所有的数据都导到 端口为9052板卡的56A上了
# 罗尔夫(80244085)  18:14:39
# 好，我先上去看一下
# 陈小阳(251779677)  18:14:47
# 恩
# 罗尔夫(80244085)  18:16:37
# 一共3G
# cpu出口没有负载均衡，我先看一下
# 罗尔夫(80244085)  18:20:30
# 一共就一百万用户在线
# 陈小阳(251779677)  18:36:52
# 现在有一百四十多万了
# 孙清孟(361841482)  18:37:28
#  会越来越多。
#  罗尔夫(80244085)  18:37:44
#  对，我在看负载均衡，很奇怪，一会我给你发一个版本，你升级看一下
#  陈小阳(251779677)  18:37:49
#  好
#  罗尔夫(80244085)  18:57:12
#  小阳，一会收一下邮件，我给你发了
#  罗尔夫(80244085)  18:59:09
#  已经发出去了，你把现场的板卡升一下吧
#  好
#  陈小阳(251779677)  19:08:53
#  升级一台先试看一下？
#  吴海波(1191107987)  19:11:16
#  升级】、
#  果断升级
#  陈小阳(251779677)  19:11:31
#  哈哈
#  熊猫的熊(19550252)  19:17:19
#
#
#  陈小阳(251779677)  19:18:31
#  设备起来了，9052
#  罗尔夫(80244085)  19:20:53
#  好，我先看一下
#  罗尔夫(80244085)  19:22:29
#  初始化没有成功
#  现场是4G内存是吧？
#
#  陈小阳(251779677)  19:23:17
#  对
#  罗尔夫(80244085)  19:24:14
#  刚才我看错了
#  罗尔夫(80244085)  19:26:59
#  奇怪，同样的版本我实验室可以自动负载均衡，为什么在现场的就不能呢？
#  陈小阳(251779677)  19:28:02
#  是因为我没有重启设备的时候，万兆口还有数据吗
#  是因为我重启设备的时候，万兆口还有数据吗
#
#  罗尔夫(80244085)  19:28:52
#  应该不是，我想想
#  陈小阳(251779677)  19:30:24
#  怎么看是否自动负载均衡，我把万兆数据口拔掉，再重启一下试试
#  罗尔夫(80244085)  19:31:15
#  看switch与cpu之间的口stat 0 27 和stat 1 10
#  k靠，我看错了，是报文只从8110下来的，
#  我又把tx rx看反了
#  陈小阳(251779677)  19:32:30
#
#  呵呵，差不多
#  陈小阳(251779677)  19:35:11
#  我把9053端口的设备重启一下，刚刚升级了，没有重启过设备，可以吗
#  陈小阳(251779677)  19:38:51
#  不回我，那我重启了
#  罗尔夫(80244085)  19:40:29
#  不好意思，这个版本编译有问题
#  陈小阳(251779677)  19:41:05
#  哦，没事，重新编译一个就行
#  估计美亚那个兄弟累着了，不想带机房了，一会儿得撤了
#  陈小阳(251779677)  19:43:08
#  多久能编好
#  吴海波(1191107987)  19:43:17
#  在你撤的时候一定要弄一个能用的版本挂上去
#  我这边远程采集一些数据
#  罗尔夫(80244085)  19:44:27
#  你要是急着走，就先恢复到之前清孟给你的吧，我编出来得先试一下
#  这个版本看不出东西
#  陈小阳(251779677)  19:45:36
#  不是可以远程升级吗
#  管理口的线，不拔
#  罗尔夫(80244085)  19:46:18
#  嗯，别拔
#  陈小阳(251779677)  19:46:30
#  好
#  吴海波(1191107987)  19:48:53
#  确保可以远程登录
#  罗尔夫(80244085)  19:49:08
#  对
#  陈小阳(251779677)  19:49:08
#  我走之前会跟你们说一声，等有肯定答复后，再走
#  陈小阳(251779677)  19:52:32
#  升级好了，我全部重启一下
#  罗尔夫(80244085)  19:52:47
#  hao
#  还是用一个CPU就行
#  陈小阳(251779677)  19:53:07
#  好
#  吴海波(1191107987)  19:54:17
#  对
#  陈小阳(251779677)  20:01:28
#  我配置好了
#  等正常登陆吗
#  远程
#  我试一下
#  地址变了么
#  陈小阳(251779677)  20:02:06
#  没变
#  陈小阳(251779677)  20:03:32
#  行吗
#  吴海波(1191107987)  20:03:49
#  好像进不去
#  陈小阳(251779677)  20:04:43
#  端口 9052、9053
#  罗尔夫(80244085)  20:04:54
#  我能进去
#  吴海波(1191107987)  20:05:19
#  9052么
#  陈小阳(251779677)  20:05:22
#  恩
#  吴海波(1191107987)  20:05:30
#  我怎么进不去啊
#  罗尔夫(80244085)  20:05:35
#  dui
#  陈小阳(251779677)  20:05:46
#  哈哈，人品
#  吴海波(1191107987)  20:06:23
#
#  进去了，填错了
#  陈小阳(251779677)  20:06:48
#  呵呵
#  那我闪人了，
#  吴海波(1191107987)  20:06:55
#  把9052给填写在用户名了
#  陈小阳(251779677)  20:07:12
#  美亚的人都把所有东西收拾好了，等着我闪人呢
#  吴海波(1191107987)  20:07:19
#  好
#  陈小阳(251779677)  20:07:24
#  下了
# 
# 
-----------------------------------------------------------------------------
Auto-merging libexec/zxmx.mk
Auto-merging sse/zxmd_mproc.c
Merge made by recursive.
 Makefile                   |    8 +-
 cli/netgate                |    2 +-
 include/executive-config.h |    3 +
 libexec/Makefile.build     |    6 +-
 libexec/acl/zxmx_acl_hfa.c |  124 ++++++++++++---------
 libexec/acl/zxmx_acl_hfa.h |   20 +++-
 libexec/acl/zxmx_hfa.c     |   73 +++++++++----
 libexec/acl/zxmx_hfa.h     |    6 +-
 libexec/acl/zxmx_hfa_api.h |  269 ++++++++++++++++++++++++++++++++++++++++++++
 libexec/eprm/zxmx_if.c     |    6 -
 libexec/zxmx.mk            |    4 +-
 libexec/zxmx_debug.c       |    6 +
 libexec/zxmx_debug.h       |   15 ++-
 libexec/zxmx_utils.h       |    6 +-
 mduapi/src/mduapi_hfa.c    |   11 +--
 sdk/OCTEON-SDK             |    2 +-
 sse/Makefile               |    7 +-
 sse/zxmd_mproc.c           |   22 +---
 18 files changed, 453 insertions(+), 137 deletions(-)
 create mode 100644 libexec/acl/zxmx_hfa_api.h
-----------------------------------------------------------------------------
Updating 8c92259..61d03e3
Fast-forward
 Config.in                         |   45 +
 cli/netgate                       |    2 +-
 libexec/Kbuild                    |   12 +
 libexec/acl/Kbuild                |   16 +
 libexec/acl/hfa/zxmx_acl_hfa.c    |  338 +++++
 libexec/acl/hfa/zxmx_acl_hfa.h    |  163 ++
 libexec/acl/hfa/zxmx_hfa.c        |  163 ++
 libexec/acl/hfa/zxmx_hfa.h        |   25 +
 libexec/acl/rfc/zxmx_acl.c        | 1106 ++++++++++++++
 libexec/acl/rfc/zxmx_acl.h        |  363 +++++
 libexec/acl/rfc/zxmx_aclex.c      | 1229 +++++++++++++++
 libexec/acl/rfc/zxmx_aclex.h      |  353 +++++
 libexec/acl/rfc/zxmx_acsm2.c      | 3002 +++++++++++++++++++++++++++++++++++++
 libexec/acl/rfc/zxmx_acsm2.h      |  180 +++
 libexec/acl/rfc/zxmx_dheap.c      |  826 ++++++++++
 libexec/acl/rfc/zxmx_dheap.h      |   62 +
 libexec/dpim/3gpp/zxmx_3gpp.h     |    2 -
 libexec/zxmx.mk                   |    2 +-
 libexec/zxmx_pcie.h               |  159 ++-
 mduapi/src/Makefile               |   17 +-
 mduapi/src/mduapi_acl.c           | 1577 +++++++++++++++++++
 mduapi/src/mduapi_acl.h           |  378 +++++
 mduapi/src/mduapi_aclex.c         | 1282 ++++++++++++++++
 mduapi/src/mduapi_aclex.h         |  304 ++++
 mduapi/src/mduapi_pcie.c          | 1261 ++++++++++++++++
 mduapi/src/mduapi_pcie.h          |   61 +
 mduapi/src/mduapi_rfc.c           |  233 +++
 mduapi/src/mduapi_rfc.h           |   23 +
 sdk/OCTEON-SDK                    |    2 +-
 sse/build_data_eth_acsmtest512.sh |  112 --
 sse/build_data_pos.sh             |   56 -
 sse/build_data_vlan.sh            |   57 -
 sse/zxmd_init.c                   |   26 +
 sse/zxmd_main.c                   |    2 +
 sse/zxmd_mproc.c                  |  220 +++-
 35 files changed, 13422 insertions(+), 237 deletions(-)
 create mode 100644 libexec/acl/Kbuild
 create mode 100644 libexec/acl/hfa/zxmx_acl_hfa.c
 create mode 100644 libexec/acl/hfa/zxmx_acl_hfa.h
 create mode 100644 libexec/acl/hfa/zxmx_hfa.c
 create mode 100644 libexec/acl/hfa/zxmx_hfa.h
 create mode 100644 libexec/acl/rfc/zxmx_acl.c
 create mode 100644 libexec/acl/rfc/zxmx_acl.h
 create mode 100644 libexec/acl/rfc/zxmx_aclex.c
 create mode 100644 libexec/acl/rfc/zxmx_aclex.h
 create mode 100644 libexec/acl/rfc/zxmx_acsm2.c
 create mode 100644 libexec/acl/rfc/zxmx_acsm2.h
 create mode 100644 libexec/acl/rfc/zxmx_dheap.c
 create mode 100644 libexec/acl/rfc/zxmx_dheap.h
 create mode 100644 mduapi/src/mduapi_acl.c
 create mode 100644 mduapi/src/mduapi_acl.h
 create mode 100644 mduapi/src/mduapi_aclex.c
 create mode 100644 mduapi/src/mduapi_aclex.h
 create mode 100644 mduapi/src/mduapi_rfc.c
 create mode 100644 mduapi/src/mduapi_rfc.h
 mode change 160000 => 120000 sdk/OCTEON-SDK

报文进入
pre {
width: 580px;
margin: 10px 0 0 0;
padding: 10px;
border: 0;
border: 1px dotted #785;
background: #f5f5f5;
font-family: "Courier New",monospace;
font-size: 12px;
}
900005968985

(http://github.com/sqm2050/wiki/raw/master/fmt_field.png)


 md_ctl_t;
==========
typedef union {
	struct {
		union {
			struct {
				u32 mac:8,
				    type:7,
				    cmd:1,
				    rsv:16;
			} hdr;
			struct {
				u32 hdr:16,
				    acl0:16;
				u32 acl1:16,
				    iif:6,
				    rsv0:2,
				    fmt_first:1,
				    oif:6,	/* Output interface ID */
				    fmt_val:1;  /*hit fmt packet*/
				u32	rsv1:7,
					idx:25;	/* Hash index of packet, RO */
				u16 proto;
				u8 iphdr[0];
			} pkt;	/* Normal IP Packet */
			struct {
				u32 hdr:16,
				    acl0:16;
				u32 acl1:16,
				    rsv0:2,
				    iif:6,
				    first:1,
				    oif:6,
				    fmt_val:1;/*hit fmt packet*/
				u32	rsv1:7,
					idx:25;	/* Hash index of packet, RO */
				u32 proto:16,
				    rsv2:8,
				    ft_proto:8;
				u32 sip;
				u32 dip;
				u32 sp:16,
				    dp:16;
				u32 rsv3;
				u8 iphdr[0];
			} pkt_ex;	/* Extend IP Packet */
			struct {
				u32 hdr:16,
				    tim_in_wqe:8,
				    rsv:8;
				u32 rsv0;
				u32 idx:25,
				    grp:4,
				    rsv1:3;
				u32 rsv5;
				u32 rsv2;
				u32 proto:16,	/* ETH_P_FMT */
				    rsv3:16;
				u32 rsv4;
				fmt_key_t f;	/* Flow tuple */
			} st;		/* stat packet*/
			struct {
				u32 hdr:16,	/* Header above, RO */
				    tim_in_wqe:8,
				    rsv:8;
				u32	rsv0;
				u32 idx:25,
				    grp:4,
				    rsv1:3;
				u32 vlan_out_prot:16,	/*0x8100*/
				    vlan_out_prio:3,
				    vlan_out_cfi:1,
				    vlan_out_tag:12;
				u32 vlan_in_prot:16,	/*0x8100*/
				    vlan_in_prio:3,
				    vlan_in_cfi:1,
				    vlan_in_tag:12;
				u32 rsv2;
				u32 proto:16,
				    rsv3:16;
				u32 rsv4;
				fmt_key_t f;	
			} flow;		
		};
	};
	u8 pad[64];
} md_ctl_t;

typedef union __md_fmt_t {
	struct {
		union {
			struct {
				u64 mac:8,
				    type:7,
				    cmd:1,
				    tim_in_wqe:8,
				    next_ptr:40;
			};
			u64 dword0;
		};
		union {
			struct {
				u32 idx:25,
				    grp:4,
				    is_head:1,
				    tag_type:2;
				struct {
					u32 eth_proto:16,
					    pri:3,
					    cfi:1,
					    tag:12;
				} vlan_out;
			};
			u64 dword1;
		};
		union{
			struct{
				struct{
					u16 eth_proto;
					u16 tag;
				}vlan_in;
				s32 cnt1;
			};
			u64 dword2;
		};
		union {
			union {
				struct {
					u64 proto:16,
					    list:48;
				};
				struct {
					u32 rsv1;
					cvmx_spinlock_t lock;
				};
			};
			u64 dword3;
		};
		fmt_key_t k;
	};
	u8 pad[64];
	u64 data_64[8];
} md_fmt_t;