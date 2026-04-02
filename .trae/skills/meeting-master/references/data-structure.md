# data.js 数据结构说明

本文档说明 meeting-guide 生成的 data.js 文件的数据结构。

## 页面基本信息

```javascript
const pageTitle = '会议标题';
const pageSubtitle = '副标题';
const organizers = '整理人姓名';
const meetingDate = '2026年4月15日';
const meetingLocation = '会议地点';
const attendees = '参会人员描述';
const audioCount = '5个录音';
const photoCount = '12张照片';
const footerText = '页脚描述';
const footerDate = '制作日期：2026年4月16日';
```

## 导航栏配置

```javascript
const navLinks = [
    { label: '概览', href: '#overview' },
    { label: '照片', href: '#photos' },
    { label: '录音', href: '#audios' },
    { label: '核心信息', href: '#insights' }
];
```

## 会议议题列表

```javascript
const meetingTopics = [
    '议题1',
    '议题2',
    '议题3'
];
```

**生成规则**：
- 优先级：md文件中的标题 > 文件名
- 从每个md文件中提取第一个标题作为议题

## 演讲嘉宾列表

```javascript
const speakers = [
    { name: '姓名', title: '职务' },
    { name: '姓名', title: '职务' }
];
```

**生成规则**：
- 从md文件的"纪要"章节中提取发言人信息
- 如果无法提取，则留空数组

## 核心总结

```javascript
const coreSummaries = [
    '总结要点1',
    '总结要点2'
];
```

**生成规则**：
- AI 汇总所有 md 文件中的重要观点
- 每条不超过 40 字
- 每个 md 文件最多贡献 2 条
- 如果没有重要观点，可以为空数组

## 照片数据

```javascript
const photos = [
    '../photos/photo1.jpg',
    '../photos/photo2.jpg'
];
```

**生成规则**：
- 遍历 photos 目录中的所有图片文件
- 支持的格式：jpg, jpeg, png, gif, webp
- 文件路径使用相对路径，从 result 目录指向同级的 photos 目录（如 `../photos/xxx.jpg`）

## 录音数据

```javascript
const audios = [
    {
        id: 1,
        title: '录音标题',
        file: '../audios/audio1.mp3',
        speaker: '主讲人（可选）'
    }
];
```

**生成规则**：
- id：按顺序编号
- title：从 md 文件标题或文件名提取
- file：对应的 mp3 文件路径，使用相对路径从 result 目录指向同级的 audios 目录（如 `../audios/xxx.mp3`）
- speaker：从 md 内容中提取（可选）

## 录音详情数据

```javascript
const audioData = {
    1: {
        summary: `纪要内容（Markdown格式）`,
        transcript: `速览内容（Markdown格式）`
    }
};
```

**生成规则**：
- key 为录音 id
- summary：对应 md 文件的"纪要"章节内容
- transcript：对应 md 文件的"速览"章节内容

## 会议议题与结论时间线

```javascript
const timelineItems = [
    {
        title: '议题标题',
        points: ['讨论要点1', '讨论要点2'],
        conclusion: '结论内容'
    }
];
```

**生成规则**：
- 每个录音对应一个时间线项目
- title：录音标题
- points：从纪要中提取的关键点（3-5条）
- conclusion：AI 生成的简短结论

## 发言人观点摘要

```javascript
const speakerQuotes = [
    {
        name: '姓名',
        title: '职务',
        avatar: '姓',
        quote: '观点引用',
        audioId: 1
    }
];
```

**生成规则**：
- 从每个 md 文件中提取重要发言人的观点
- avatar：取姓名的第一个字
- quote：不超过 50 字的重要观点
- audioId：关联的录音编号
