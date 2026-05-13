# layouts.md — 麦肯锡风 Slide 布局骨架

共 8 种布局，覆盖咨询 deck 所有常见页面类型。每种布局直接提供可粘贴的 HTML 骨架。

---

## 主题节奏规划（先做这张表，再选布局）

| Deck 结构位置 | 推荐布局 | 作用 |
|-------------|---------|------|
| 封面 | Layout 1: Cover | 建立项目感，信息最少 |
| 执行摘要 | Layout 2: Executive Summary | 让决策者 30 秒抓到全部结论 |
| 章节分隔 | Layout 3: Section Divider | 结构感，告知受众进入新章节 |
| 核心分析页 | Layout 4: Key Message + Data | 90% 的分析页用这个 |
| 数据密集页 | Layout 5: Data Table / Comparison | 多指标对比、竞争格局 |
| 框架/矩阵页 | Layout 6: 2×2 Matrix / Framework | 战略选项、优先级排序 |
| 流程/时间线 | Layout 7: Process / Timeline | 路线图、实施计划 |
| 结论行动页 | Layout 8: Recommendations | 建议 + 责任人 + 时间线 |

---

## Layout 1：Cover（封面）

**使用场景**：deck 第一页。信息极简，建立项目权威感。

```html
<section class="slide slide-cover">
  <div class="cover-content">
    <div class="cover-tag">CONFIDENTIAL</div>
    <h1 class="cover-title">[项目/议题标题]</h1>
    <p class="cover-subtitle">[副标题：背景或范围说明，不超过 20 字]</p>
    <div class="cover-meta">
      <span>[客户/公司名称]</span>
      <span class="cover-date">[月份 年份]</span>
    </div>
    <div class="cover-prepared">Prepared by [汇报方] | [汇报人姓名]</div>
  </div>
  <div class="cover-accent-bar"></div>
</section>
```

**视觉规则**：
- 背景：深蓝（`var(--primary)`）
- 标题：白色，字号最大（`font-size: 3.2vw`），最多 2 行
- 右侧或底部有一条强调色竖/横线（`var(--accent)`）
- 绝无图片、图表、子弹点

---

## Layout 2：Executive Summary（执行摘要）

**使用场景**：deck 第 2 页。让忙碌的决策者 30 秒内掌握全部结论。

```html
<section class="slide slide-exec-summary">
  <div class="slide-header">
    <h2 class="action-title">[执行摘要：一句话总结核心结论]</h2>
    <div class="slide-number">02</div>
  </div>
  <div class="exec-body">
    <div class="exec-finding">
      <div class="finding-label">发现 01</div>
      <div class="finding-text">[关键发现 1，一个完整论点句子]</div>
      <div class="finding-implication">→ [含义/影响]</div>
    </div>
    <div class="exec-finding">
      <div class="finding-label">发现 02</div>
      <div class="finding-text">[关键发现 2]</div>
      <div class="finding-implication">→ [含义/影响]</div>
    </div>
    <div class="exec-finding">
      <div class="finding-label">发现 03</div>
      <div class="finding-text">[关键发现 3]</div>
      <div class="finding-implication">→ [含义/影响]</div>
    </div>
  </div>
  <div class="exec-action-box">
    <div class="action-box-label">建议行动</div>
    <div class="action-box-text">[核心建议，直接、可操作，不超过 2 句话]</div>
  </div>
</section>
```

**视觉规则**：
- 三个发现等高并排，左侧有强调色竖线
- 底部有独立的"建议行动"色块（用强调色背景）
- 标题必须是完整论点句

---

## Layout 3：Section Divider（章节分隔）

**使用场景**：进入新章节时使用，通常每 3-5 页分析内容插入一次。

```html
<section class="slide slide-divider">
  <div class="divider-number">01</div>
  <div class="divider-content">
    <div class="divider-label">SECTION ONE</div>
    <h2 class="divider-title">[章节标题]</h2>
    <p class="divider-desc">[本章节将回答什么问题，1 句话]</p>
  </div>
  <div class="divider-outline">
    <div class="outline-item active">◉ [当前章节]</div>
    <div class="outline-item">○ [下一章节]</div>
    <div class="outline-item">○ [下下章节]</div>
  </div>
</section>
```

**视觉规则**：
- 大号章节序号（`font-size: 12vw`，颜色极浅作为背景元素）
- 右侧有全局大纲，当前章节高亮
- 背景可用次深色（`var(--primary-light)`），但不能太花哨

---

## Layout 4：Key Message + Supporting Data（核心分析页）⭐ 最常用

**使用场景**：90% 的分析页。每页一个核心论点 + 2-3 个数据支撑。

```html
<section class="slide slide-analysis">
  <div class="slide-header">
    <h2 class="action-title">[核心论点：完整句子，带数据，有 so what]</h2>
    <div class="slide-number">04</div>
  </div>
  <div class="analysis-body">
    <!-- 支撑点 1 -->
    <div class="support-block">
      <div class="support-label">支撑点 1</div>
      <div class="support-chart">
        <!-- SVG 图表内联 -->
        <svg viewBox="0 0 400 200" class="chart-svg">
          <!-- 柱状图示例 -->
          <rect x="50" y="80" width="60" height="120" fill="var(--primary)" />
          <rect x="150" y="40" width="60" height="160" fill="var(--accent)" />
          <text x="80" y="75" class="chart-label">42%</text>
          <text x="180" y="35" class="chart-label highlight">67%</text>
          <!-- X轴标签 -->
          <text x="80" y="215" class="chart-axis">2022</text>
          <text x="180" y="215" class="chart-axis">2024</text>
        </svg>
      </div>
      <div class="support-insight">[这个图说明了什么？so what]</div>
    </div>
    <!-- 支撑点 2 -->
    <div class="support-block">
      <div class="support-label">支撑点 2</div>
      <div class="support-stat">
        <div class="big-number">[核心数字]</div>
        <div class="stat-context">[单位 / 时间段]</div>
        <div class="stat-vs">vs. [对比基准] <span class="delta negative">▼ X%</span></div>
      </div>
      <div class="support-insight">[含义]</div>
    </div>
    <!-- 支撑点 3（可选） -->
    <div class="support-block">
      <div class="support-label">支撑点 3</div>
      <div class="support-bullets">
        <div class="bullet-item">• [关键信息点 1]</div>
        <div class="bullet-item">• [关键信息点 2]</div>
      </div>
      <div class="support-insight">[含义]</div>
    </div>
  </div>
  <div class="slide-source">来源：[数据来源] | [日期]</div>
</section>
```

**视觉规则**：
- Action Title 必须占据顶部全宽，字号 `1.4vw`，粗体
- 三个支撑块等宽并排，顶部对齐
- 每个支撑块底部必须有 insight 文字（so what）
- 右下角注明数据来源

---

## Layout 5：Data Table / Comparison（数据表格/竞争对比）

**使用场景**：多公司/多维度对比，竞争格局分析。

```html
<section class="slide slide-table">
  <div class="slide-header">
    <h2 class="action-title">[竞争格局论点：如"头部三家在X维度形成明显优势"]</h2>
    <div class="slide-number">05</div>
  </div>
  <div class="table-container">
    <table class="mckinsey-table">
      <thead>
        <tr>
          <th class="table-row-header">维度</th>
          <th>[公司A]</th>
          <th class="our-company">[我方/标的]</th>
          <th>[公司B]</th>
          <th>[公司C]</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td class="table-row-header">市场份额</td>
          <td>32%</td>
          <td class="our-company highlight-cell">18%</td>
          <td>25%</td>
          <td>12%</td>
        </tr>
        <tr>
          <td class="table-row-header">毛利率</td>
          <td class="positive">68%</td>
          <td class="our-company negative">41%</td>
          <td class="positive">72%</td>
          <td>55%</td>
        </tr>
        <!-- 更多行 -->
      </tbody>
    </table>
  </div>
  <div class="table-callout">
    <span class="callout-label">关键发现</span>
    [从表格中提炼的核心 so what，一句话]
  </div>
  <div class="slide-source">来源：[数据来源]</div>
</section>
```

**视觉规则**：
- 我方/标的公司列用浅色背景高亮
- 正向指标（优）用绿色数值，负向用红色——只改颜色，不加背景色块
- 表格底部必须有"关键发现"callout，提炼 so what
- 列数最多 6 列，否则拆页

---

## Layout 6：2×2 Matrix / Framework（战略矩阵）

**使用场景**：战略选项排序、优先级分析、BCG 矩阵类分析。

```html
<section class="slide slide-matrix">
  <div class="slide-header">
    <h2 class="action-title">[矩阵结论：如"优先级分析显示X象限为最佳切入点"]</h2>
    <div class="slide-number">06</div>
  </div>
  <div class="matrix-body">
    <div class="matrix-container">
      <!-- Y轴标签 -->
      <div class="matrix-y-label">[Y轴维度：如"市场吸引力"] ↑</div>
      <!-- 矩阵四象限 -->
      <div class="matrix-grid">
        <div class="quadrant q-tl">
          <div class="quadrant-label">高吸引力 / 低优势</div>
          <div class="quadrant-items">[选项或公司名]</div>
        </div>
        <div class="quadrant q-tr highlighted">
          <div class="quadrant-label">高吸引力 / 高优势 ⭐</div>
          <div class="quadrant-items">[优先选项]</div>
        </div>
        <div class="quadrant q-bl">
          <div class="quadrant-label">低吸引力 / 低优势</div>
          <div class="quadrant-items">[选项]</div>
        </div>
        <div class="quadrant q-br">
          <div class="quadrant-label">低吸引力 / 高优势</div>
          <div class="quadrant-items">[选项]</div>
        </div>
      </div>
      <!-- X轴标签 -->
      <div class="matrix-x-label">→ [X轴维度：如"竞争优势"]</div>
    </div>
    <div class="matrix-legend">
      <div class="legend-item"><span class="legend-dot primary"></span>[分类A]</div>
      <div class="legend-item"><span class="legend-dot accent"></span>[分类B]</div>
    </div>
  </div>
</section>
```

**视觉规则**：
- 推荐象限用强调色背景（浅）+ 边框加粗
- 矩阵必须有清晰的 X/Y 轴标签
- 每个象限最多 3 个项目

---

## Layout 7：Process / Timeline（流程/路线图）

**使用场景**：实施路线图、项目计划、转型阶段划分。

```html
<section class="slide slide-timeline">
  <div class="slide-header">
    <h2 class="action-title">[路线图结论：如"分三阶段推进，18个月实现核心目标"]</h2>
    <div class="slide-number">07</div>
  </div>
  <div class="timeline-body">
    <div class="phase-container">
      <div class="phase">
        <div class="phase-label">第一阶段</div>
        <div class="phase-period">Q1–Q2 2025</div>
        <div class="phase-title">[阶段名称]</div>
        <div class="phase-items">
          <div class="phase-item">• [关键行动1]</div>
          <div class="phase-item">• [关键行动2]</div>
        </div>
        <div class="phase-milestone">里程碑：[可量化交付物]</div>
      </div>
      <div class="phase-arrow">→</div>
      <div class="phase">
        <div class="phase-label">第二阶段</div>
        <div class="phase-period">Q3–Q4 2025</div>
        <div class="phase-title">[阶段名称]</div>
        <div class="phase-items">
          <div class="phase-item">• [关键行动1]</div>
          <div class="phase-item">• [关键行动2]</div>
        </div>
        <div class="phase-milestone">里程碑：[可量化交付物]</div>
      </div>
      <div class="phase-arrow">→</div>
      <div class="phase">
        <div class="phase-label">第三阶段</div>
        <div class="phase-period">Q1–Q2 2026</div>
        <div class="phase-title">[阶段名称]</div>
        <div class="phase-items">
          <div class="phase-item">• [关键行动1]</div>
          <div class="phase-item">• [关键行动2]</div>
        </div>
        <div class="phase-milestone">里程碑：[可量化交付物]</div>
      </div>
    </div>
  </div>
</section>
```

**视觉规则**：
- 阶段数最多 4 个；超过 4 个阶段要合并或拆页
- 每个阶段里程碑必须是可量化的（不能写"完成初步评估"，要写"完成 3 个城市试点，NPS > 40"）
- 当前/重点阶段用强调色边框

---

## Layout 8：Recommendations（建议与行动）

**使用场景**：deck 最后 1-2 页，明确建议、责任人、时间线。

```html
<section class="slide slide-recommendations">
  <div class="slide-header">
    <h2 class="action-title">[建议总结：如"建议优先推进三项举措，预期 ROI 达到 3.2×"]</h2>
    <div class="slide-number">08</div>
  </div>
  <div class="rec-body">
    <div class="rec-item priority-high">
      <div class="rec-priority">优先级 1</div>
      <div class="rec-title">[建议1标题]</div>
      <div class="rec-rationale">[为什么？预期影响？]</div>
      <div class="rec-meta">
        <span class="rec-owner">责任方：[部门/人]</span>
        <span class="rec-timeline">时间线：[季度]</span>
        <span class="rec-impact">预期影响：[数字]</span>
      </div>
    </div>
    <div class="rec-item priority-medium">
      <div class="rec-priority">优先级 2</div>
      <div class="rec-title">[建议2标题]</div>
      <div class="rec-rationale">[为什么？预期影响？]</div>
      <div class="rec-meta">
        <span class="rec-owner">责任方：[部门/人]</span>
        <span class="rec-timeline">时间线：[季度]</span>
        <span class="rec-impact">预期影响：[数字]</span>
      </div>
    </div>
    <div class="rec-item priority-low">
      <div class="rec-priority">优先级 3</div>
      <div class="rec-title">[建议3标题]</div>
      <div class="rec-rationale">[为什么？预期影响？]</div>
      <div class="rec-meta">
        <span class="rec-owner">责任方：[部门/人]</span>
        <span class="rec-timeline">时间线：[季度]</span>
        <span class="rec-impact">预期影响：[数字]</span>
      </div>
    </div>
  </div>
  <div class="rec-footer">
    <div class="next-step-box">
      <div class="next-step-label">即时下一步</div>
      <div class="next-step-text">[需要在本次会议结束前决定的事项]</div>
    </div>
  </div>
</section>
```

**视觉规则**：
- 优先级 1 用强调色左边框（最粗）
- 每个建议必须有"预期影响"的量化数字
- 底部"即时下一步"框：逼出决策，这是咨询 deck 的核心技巧
