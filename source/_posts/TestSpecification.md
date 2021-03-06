---
title: 测试流程规范
date: 2019-07-31 16:06:07
tags: 测试规范
categories: 测试
---
# 目的
规范公司的测试流程，保障公司研发项目的质量，提升测试效率
# 适用范围
适用于校精灵技术团队
# 流程
## &nbsp;&nbsp;&nbsp;&nbsp;测试介入时间
- 测试需要在需求评审阶段介入测试，参与需求评审会议并着手准备测试方案及测试用例
- 测试需要在整个开发过程中评估项目风险，如需求评审阶段新增功能或重构功能的影响范围评估，开发阶段新功能造成原有逻辑修改的影响范围评估，测试阶段修改bug造成的相关模块的影响范围评估，尽早发现问题，降低项目风险及问题修复成本

## &nbsp;&nbsp;&nbsp;&nbsp;需求阶段
- 需求评审前尽量提前对方案进行分析，从功能交互、测试要点等方面入手分析，整理问题在需求评审会议中抛出
- 需求评审会议中，对存在疑问的地方需要及时抛出问题，如遇到对原有逻辑影响过大的功能点，需要和开发、产品讨论合理的方案，为后期测试做准备
- 需求评审会议结束后，如果方案有修改，产品经理需要及时同步并通知其他人员，测试人员需要根据修改内容对测试用例进行修改并重新评估风险
- 产品部门需要规范需求文档的书写格式及需求的详细程度

## &nbsp;&nbsp;&nbsp;&nbsp;开发阶段
- 需求评审完成之后，需要编写测试方案及测试用例
- 测试方案一般由测试组长与相关开发人员沟通制定，主要包含测试范围、测试策略、测试资源、测试进度及排期
- 测试用例设计：测试用例是测试思路及测试功能点的体现，原则上要用尽可能少的用例覆盖尽可能多的需求，输出方式为Xmind

## &nbsp;&nbsp;&nbsp;&nbsp;用例评审
- 用例评审内容为冒烟测试用例，参与人：产品、前端、后端
- 用例评审时，可以发现遗漏的测试点，提高用例覆盖率

## &nbsp;&nbsp;&nbsp;&nbsp;测试准备阶段
- 用例评审结束之后，测试组需要准备测试环境，测试数据，并将冒烟测试用例修改后同步给研发同学
- 测试环境准备包含：bug系统迭版本及模块的更新，测试手机的准备、相关测试数据的生成等
<!--more-->

## &nbsp;&nbsp;&nbsp;&nbsp;提测流程
- 根据版本排期，按时提交对应的版本
- 接口提测标准：版本功能已根据产品经理需求实现，接口冒烟通过，开发已完成自测
- 页面提测标准：版本功能已根据产品经理需求实现，页面已和接口联调通过，开发根据冒烟测试用例完成自测
- 提测时，需要提测平台提交提测邮件，表明具体提测的版本，对应的需要测试的功能和开发人员，具体邮件样式请见下方，在测试阶段，修复bug，或提测新功能，均需要发提测邮件
- 接口冒烟标准：根据接口文档定义，输入正常请求参数，接口返回成功，且返回对应的正确响应数据即可（后期开展）
- 页面冒烟标准：输入正常参数，页面新增，编辑，删除，保存操作成功，页面不报错；APP端流程能走通，点击按钮不报错
- 如果冒烟测试未通过，则不能进行下一步测试，需要告知开发返工等待下一次构建

## &nbsp;&nbsp;&nbsp;&nbsp;提测邮件模板
``` text
[项目名称] v1.4已开发完成，提测说明如下:
- 版本号: [项目名称] v1.4
- 自测结果:   通过（通过标准为已发布到测试环境并在测试环境完成自测）                                                                                                                             
- 测试地址：http://dev.xiaojing0.com/admin/workbench（接口和web页面的提测需要必填）
- 版本修改说明：（本次迭代修改内容及需要重点测试的风险点）
  1.优化了考勤相关逻辑，考勤功能需要测试
  2.更换了日期选择器控件
  3.新增了校区搜索功能
```

## &nbsp;&nbsp;&nbsp;&nbsp;测试阶段
- 测试阶段测试人员需要根据测试用例进行测试，使用bug管理工具提交问题并跟踪问题状态，问题被修复之后需要对问题及时进行验证并关闭。
- bug提交规范参照《bug提交规范说明》
- 第一轮测试：根据测试用例进行功能测试
- 第二轮测试：自由测试，对异常操作，边界值等进行测试，尽可能多的找出存在的问题
- 预发布回归：发布当天产品及运营同学进行showcase验收，未能通过则延期发布
- 线上回归：版本上线后，需要在正式环境进行回归测试，如果出现线上bug，需要及时反馈解决，流程参照《线上问题处理流程》

## &nbsp;&nbsp;&nbsp;&nbsp;其他
- 预发布回归通过后，需按照项目输出质量报告，优化的项目不需要输出质量报告，只需邮件同步测试通过即可

# Bug等级规范

| Bug等级定义标准 |
| ------------------------------------------------------------ |
| 需求文档中要求实现的功能未实现，则算作 Bug                   |
| 修改的内容不符合需求文档说明，则算作 Bug                     |
| 修改的内容未在需求文档中指明但应当实现的功能没有实现（如表格，控制错误项），则算作 Bug |
| 修改的内容没有按照 UI 界面规范实现，则算作 Bug               |
| 测试人员认为软件难以理解、不易使用，最终导致用户使用效果不良，则算作建议 |
以下做具体分析:

<style>
table th:nth-of-type(1){
width: 20%;
}
table th:nth-of-type(2){
width: 80%;
}
</style>

| 缺陷等级 |                             描述                             |
| :------: | ---------------------------------------------------------- |
|   紧急   | 页面出现404错误、实现的功能与需求严重不符、逻辑判断错误或未判断导致功能异常（涉钱）、与数据库连接方面的错误 、导致数据库发生死锁、死循环、内存泄漏，系统崩溃、用户数据丢失或破坏、严重的数值计算错误、其它导致无法测试的错误 |
|    高    | 接口导致问题、页面样式存在兼容性问题，严重影响页面样式及交互、功能未实现 、功能错误，业务流程错误或不完整 |
|   普通   | 轻微的数值计算错误、数据显示错误、文字或图片链接有问题，比如：链接的地址打不开，链的是其它页面、页面样式存在兼容性问题，但对页面视觉影响不大,可以正常使用、操作界面错误(包括数据窗口内列名定义、含义是否一致)、边界条件下错误、提示信息错误(包括未给出信息、信息提示错误等)、性能问题、删除操作未给出提示 |
|    低    | 界面辅助说明描述不清楚，提示信息不合理、不准确等、页面样式存在兼容性问题，但对页面视觉影响不大，可以正常使用、光标跳转设置不好，鼠标(光标)定位错误、界面样式等不规范、对于交互、视觉和需求上的建议，由产品经理决定是否采纳、文字排列不整齐、辅助说明描述不清楚、提示说明未采用行业规范语言 |


# Bug提交规范
- 后端 Bug
需要贴上接口请求消息体，和响应消息体，如有日志，需要把日志截图贴出

- 前端 Bug
Bug 标题：【模块】XXXbug标题描述（如：【招生】bug描述）
Bug 详情：
【预置条件】：简单描述测试该 bug 的测试前提条件，如：登录boss校长账号
【测试步骤】：一般为测试用例中的测试步骤，也是重现bug的步骤，方便开发和产品经理复现问题, 如：在意向学员中录入学员，手机号输入13位（如需要多个步骤实现，或者一个 bug 里面需要描述多个问题，则一一描述）
【预期结果】：一般为预置条件和测试步骤应该呈现的测试结果。如：录入失败，提示手机号错误（如有多个预期结果，则一一描述）
【实际结果】： 一般为预置条件和测试步骤目前呈现的测试结果，即详细的bug现象。如：录入失败，但是没有给出友好提示（如有多个实际结果，则一一描述）
【截图】：附上该 bug 的截图即可
