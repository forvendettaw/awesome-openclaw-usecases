---
name: life-memory-logger
description: 人生记忆日志Skill。帮助用户记录和管理人际关系中的重要细节（生日、喜好、承诺、约定等），在需要时提醒用户。适合重视人际关系、专业人士建立客户关系、或希望在人际交往中更加细心的人。
---

# 人生记忆日志 (Life Memory Logger)

## 定位

帮助用户捕捉和保存日常互动中的重要信息——生日、饮食偏好、承诺的后续事项等。让 fleeting moments 变成 lasting knowledge。

## 触发条件

用户提到：
- 记录某人的信息
- 记住关于某人的事情
- 人生memory
- 人际关系记录
- 提醒我关于...
- 生日提醒
- 后续跟进提醒

---

## 核心功能

### 1. 快速记忆格式

**快速记忆**:
```
Remember: [人] likes/dislikes [细节]
例: "Remember: Sarah likes dark chocolate, not milk chocolate"
```

**对话记录**:
```
From conversation with [人]: [细节]
例: "From conversation with Mom: She's planning to visit in March"
```

**事件记忆**:
```
[人] [事件] on [日期]
例: "Alex is starting new job on March 15th"
```

**跟进提醒**:
```
Follow up with [人] about [主题] in [时间]
例: "Follow up with client about proposal in 3 days"
```

---

## 记忆分类

### 👤 人物档案
- 生日和纪念日
- 偏好（食物、饮料、爱好、颜色）
- 过敏和饮食限制
- 家庭成员和关系
- 人生大事（新工作、搬家、毕业）
- 目标和愿望
- 厌恶的事物

### 📅 日期与事件
- 提到的计划
- 预约
- 承诺的截止日期
- 旅行计划
- 庆祝日期

### 💼 职业背景
- 客户偏好和历史
- 项目详情和状态
- 会议笔记和待办事项
- 职业目标和挑战

### 🔗 关系与连接
- 如何认识
- 建立的联系
- 共享的连接

### 🎯 承诺与跟进
- 作出的承诺
- 需要回顾的事项
- 需要买的礼物
- 需要跟进的推荐

---

## 记忆存储

### 文件结构
```
~/.openclaw/memory/life-memories/
├── people/
│   └── [person-name].json
├── upcoming-events.json
├── follow-ups.json
└── master-index.json
```

### JSON格式示例
```json
{
  "person": "Sarah Johnson",
  "last_updated": "2026-02-28",
  "facts": [
    {
      "category": "food_preference",
      "detail": "Allergic to peanuts — severe reaction",
      "source": "Conversation Feb 2026",
      "date_added": "2026-02-28"
    }
  ],
  "conversations": [
    {
      "date": "2026-02-28",
      "summary": "Discussed upcoming vacation to Japan",
      "action_items": ["Send Tokyo restaurant recommendations"]
    }
  ]
}
```

---

## 定时任务

### 每日记忆处理 (22:00)
1. 回顾今天添加的记忆
2. 确认保存正确
3. 发送确认摘要

### 每周回顾 (周日 19:00)
1. 回顾本周添加的所有记忆
2. 检查模式或关联
3. 识别未来7天的事件
4. 发送摘要

### 月度整合 (每月最后一天)
1. 清理重复记忆
2. 更新变化的信息
3. 创建月度亮点

### 生日检查 (每日 9:00)
1. 检查未来7天的生日
2. 发送提醒

---

## 提醒系统

### 生日提醒 (提前1周)
```
🎂 [人] 的生日快到了 ([日期])。
记忆: [偏好/礼物建议]
```

### 跟进提醒 (到期时)
```
⏰ 跟进提醒: 你承诺关于 [主题] 联系 [人]
```

### 事件提醒 (前一天)
```
📅 提醒: 明天与 [人] 的 [事件]
相关记忆: [可能有帮助的上下文]
```

---

## 查询功能

用户可以问：
- "关于Sarah我知道什么？" → 返回关于该人的所有事实
- "Alex的生日是什么时候？" → 返回特定日期
- "我有哪些待处理的跟进？" → 返回按日期排序的所有待办
- "我承诺给谁发送推荐？" → 搜索行动项目和对话
- "我记录了什么饮食偏好？" → 搜索所有人的饮食相关事实

---

## 隐私与伦理规则

1. **同意优先**: 只存储用户愿意记住的信息
2. **敏感信息**: 标记敏感细节（健康、财务、冲突）并确认后再存储
3. **删除权**: 用户说 "Forget that" 立即删除
4. **不分享**: 绝不将一人的信息分享给另一人
5. **透明**: 如果有人问"你怎么知道的？"，应诚实说明使用记忆系统

**自动标记确认**:
- 健康信息
- 财务细节
- 关系冲突
- 第三方私人信息

---

## 智能提取

从对话中提取：
- 提及的姓名和他们是谁
- 日期和截止日期
- 偏好和观点
- 承诺和待办
- 情绪状态
- 可能以后重要的上下文

**示例输入**:
"今天和Mike吃饭。他很兴奋得到晋升，但第一次管理人很紧张。他妻子怀孕了，6月预产期。他推荐了Main Street那家新泰国餐厅，说pad thai特别好吃。"

**提取的记忆**:
- Mike得到晋升
- Mike对第一次管理角色感到紧张
- Mike妻子怀孕，2026年6月预产期
- Mike推荐Main Street的泰国餐厅，特别推荐pad thai

---

## 使用示例

```
用户: Remember: 张总喜欢喝茅台，不喝洋河
→ 提取: 人=张总, 偏好=茅台
→ 保存到: ~/.openclaw/memory/life-memories/people/张总.json

用户: 我跟李总约了周一开会
→ 提取: 人=李总, 事件=开会, 日期=周一
→ 保存到: upcoming-events.json

用户: 提醒我下周和王总跟进那个项目
→ 保存到: follow-ups.json
→ 到期时发送提醒
```

---

## 协同Skills

- `memory-core`: 记忆存储和检索
- `message`: 发送Telegram提醒
- `apple-reminders`: 同步到Apple Reminders

---

## 输出示例

### 每日确认
```
✅ 今天保存了3条记忆:
• Sarah 的过敏信息
• Alex 的新工作
• Mom 的博物馆访问计划
```

### 每周回顾
```
📚 本周记忆回顾

新增记忆: 5条
关于: Sarah, Alex, Mom, 张总

🔔 即将到来:
• 张总生日 - 3月5日
• 与李总会议 - 3月2日

💡 洞察:
• 本月提到3个人换了新工作

🎯 建议跟进:
• 给Mike发送东京餐厅推荐
```
