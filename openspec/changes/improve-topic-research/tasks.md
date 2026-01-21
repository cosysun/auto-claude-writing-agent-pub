# Tasks: Improve Topic Research and Tool Usage

**Date**: 2026-01-21
**Status**: Draft

---

## Task Categories

### 1. Documentation Updates (文档更新)

#### Task 1.1: 更新Step 2（信息搜索）
- **File**: `mp-wechat/CLAUDE.md`
- **Action**: 在Step 2中增加工具使用规范
- **Details**:
  - 明确WebFetch vs WebSearch的使用场景
  - 提供具体示例
  - 说明优先级

**Acceptance Criteria**:
- [ ] 文档清晰说明两个工具的区别
- [ ] 提供3个以上使用示例
- [ ] AI能根据文档正确选择工具

---

#### Task 1.2: 新增Step 2.5（本地化热度评估）
- **File**: `mp-wechat/CLAUDE.md`
- **Action**: 在Step 2和Step 3之间插入新步骤
- **Details**:
  - 定义"本地化热度评估"的目标
  - 提供热度评估三要素
  - 给出具体操作流程
  - 列出可用的中文信息源

**Acceptance Criteria**:
- [ ] 新步骤位置正确（在Step 2之后，Step 3之前）
- [ ] 包含具体的信息源列表
- [ ] 包含热度评估的检查清单
- [ ] 标注为⭐关键步骤

---

#### Task 1.3: 更新Step 3（选题讨论）
- **File**: `mp-wechat/CLAUDE.md`
- **Action**: 修改选题讨论的要求
- **Details**:
  - 要求每个选题必须注明热度依据
  - 增加"热度评估"部分
  - 更新选题模板

**Acceptance Criteria**:
- [ ] 选题模板包含"热度依据"字段
- [ ] 要求说明热度来源（社交媒体/同行/用户）
- [ ] 提供热度评估示例

---

#### Task 1.4: 更新版本号和变更记录
- **File**: `mp-wechat/CLAUDE.md`
- **Action**: 更新版本信息
- **Details**:
  - 版本号：v1.4 → v1.5
  - 更新日期：2026-01-21
  - 记录变更内容

**Acceptance Criteria**:
- [ ] 版本号已更新
- [ ] 版本历史已添加新条目
- [ ] 变更描述清晰完整

---

### 2. Content Creation (内容创建)

#### Task 2.1: 创建中文信息源清单
- **File**: `mp-wechat/_writing_reference/china-info-sources.md`（新建）
- **Action**: 整理可用的中文信息源
- **Details**:
  - 社交媒体平台（微博、知乎、小红书）
  - 科技资讯平台（少数派、机器之心、36氪、虎嗅）
  - 同行公众号推荐
  - 访问方式和限制说明

**Acceptance Criteria**:
- [ ] 列出10+个可用信息源
- [ ] 每个信息源注明类型和用途
- [ ] 说明访问限制和替代方案

---

#### Task 2.2: 创建热度评估模板
- **File**: `mp-wechat/_templates/topic-heat-check.md`（新建）
- **Action**: 提供可复用的热度评估模板
- **Details**:
  - 热度评估检查清单
  - 信息源记录表格
  - 热度判断标准

**Acceptance Criteria**:
- [ ] 模板包含3个维度的检查项
- [ ] 提供具体的判断标准
- [ ] 易于填写和使用

---

### 3. Examples and References (示例和参考)

#### Task 3.1: 添加工具使用示例
- **File**: `mp-wechat/CLAUDE.md` Step 2
- **Action**: 在工具使用部分添加示例
- **Details**:
  - WebFetch示例3个（不同类型网站）
  - WebSearch示例2个（概念性搜索）
  - 错误使用示例1个（反面教材）

**Acceptance Criteria**:
- [ ] 示例覆盖常见场景
- [ ] 包含具体的prompt和url
- [ ] 说明为什么选择该工具

---

#### Task 3.2: 添加选题热度评估示例
- **File**: `mp-wechat/CLAUDE.md` Step 2.5
- **Action**: 提供完整的热度评估案例
- **Details**:
  - 展示如何从社交媒体获取热度
  - 展示如何分析同行选题
  - 展示如何结合频道定位筛选

**Acceptance Criteria**:
- [ ] 包含完整的评估过程
- [ ] 展示正面案例和反面案例
- [ ] 说明筛选标准

---

### 4. Validation (验证)

#### Task 4.1: 创建测试场景
- **Action**: 设计测试用例验证改进效果
- **Details**:
  - 场景1：AI推荐选题，检查是否有热度依据
  - 场景2：AI选择工具，检查是否正确
  - 场景3：完整的选题流程，检查步骤完整性

**Acceptance Criteria**:
- [ ] 测试场景覆盖核心改进点
- [ ] 测试结果符合预期
- [ ] 无明显遗漏或错误

---

#### Task 4.2: OpenSpec验证
- **Action**: 运行openspec验证命令
- **Command**: `openspec validate --strict`
- **Details**:
  - 检查文档结构
  - 检查规范完整性

**Acceptance Criteria**:
- [ ] 验证通过无错误
- [ ] 所有必需文件已创建
- [ ] 符合OpenSpec规范

---

## Task Priority

### High Priority（必须完成）:
1. Task 1.1 - 更新Step 2工具使用规范
2. Task 1.2 - 新增Step 2.5热度评估
3. Task 1.3 - 更新Step 3选题讨论
4. Task 1.4 - 更新版本号

### Medium Priority（重要）:
5. Task 2.1 - 创建信息源清单
6. Task 3.1 - 添加工具使用示例
7. Task 3.2 - 添加热度评估示例

### Low Priority（可选）:
8. Task 2.2 - 创建热度评估模板
9. Task 4.1 - 创建测试场景
10. Task 4.2 - OpenSpec验证

---

## Estimated Effort

- **High Priority Tasks**: 2-3 hours
- **Medium Priority Tasks**: 1-2 hours
- **Low Priority Tasks**: 0.5-1 hour
- **Total**: 4-6 hours

---

## Dependencies

- Task 1.2 依赖 Task 2.1（需要先有信息源清单）
- Task 1.3 依赖 Task 1.2（需要先定义热度评估流程）
- Task 4.2 依赖所有其他任务（最后验证）

---

## Notes

- 本次变更主要集中在Step 2和Step 3
- 不影响其他步骤的流程
- 向后兼容，旧的工作流程仍然有效
- 重点是"增强"而非"替换"
