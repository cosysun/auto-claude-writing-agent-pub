# Specification: Topic Research and Tool Usage

**Date**: 2026-01-21
**Status**: Draft
**Version**: 1.0

---

## ADDED Requirements

### Requirement: Tool Selection Rules

AI writing agent SHALL prioritize WebFetch over WebSearch when acquiring information.

#### Scenario: Fetching from known Chinese platforms
- **GIVEN** AI needs to get hot topics or recent articles
- **WHEN** the target is a specific Chinese platform (sspai.com, jiqizhixin.com, 36kr.com)
- **THEN** AI SHALL use WebFetch with the specific URL
- **AND** AI SHALL NOT use WebSearch for this purpose

#### Scenario: Researching unknown concepts
- **GIVEN** AI needs to research a new concept or technology
- **WHEN** the information source is unknown
- **THEN** AI MAY use WebSearch as the first attempt
- **AND** AI SHOULD specify clear search keywords related to the concept

#### Scenario: Getting official documentation
- **GIVEN** AI needs to access official documentation
- **WHEN** the documentation URL is known or can be inferred
- **THEN** AI SHALL use WebFetch with the documentation URL
- **AND** AI SHALL NOT use WebSearch if URL is available

---

### Requirement: Localized Heat Assessment

AI writing agent SHALL perform localized heat assessment before topic recommendation.

#### Scenario: Assessing topic heat for Chinese audience
- **GIVEN** AI is about to recommend article topics
- **WHEN** working on WeChat Official Account content
- **THEN** AI SHALL fetch information from Chinese platforms (sspai.com, jiqizhixin.com, etc.)
- **AND** AI SHALL analyze social media trends (Weibo, Zhihu if accessible)
- **AND** AI SHALL check peer account topics
- **AND** AI SHALL document heat sources for each topic

#### Scenario: Foreign tech news without Chinese validation
- **GIVEN** AI discovers news from foreign tech media (TechCrunch, Hacker News)
- **WHEN** the news has not been discussed in Chinese platforms
- **THEN** AI SHALL NOT recommend it as a hot topic
- **AND** AI MAY mention it as "emerging trend, heat to be validated"

#### Scenario: Multiple heat sources validation
- **GIVEN** AI is evaluating a potential topic
- **WHEN** preparing the topic recommendation
- **THEN** AI SHALL validate heat from at least 2 of the 3 dimensions:
  - Social media heat (Weibo, Zhihu, XiaoHongShu)
  - Peer topics (similar accounts, tech media)
  - User feedback (comments, community, messages)
- **AND** AI SHALL document specific heat indicators (rankings, view counts, discussion volume)

---

### Requirement 3: Topic Recommendation Format Enhancement

AI writing agent SHALL include heat justification in every topic recommendation.

#### Scenario: Providing topic recommendations
- **GIVEN** AI is presenting topic options to user
- **WHEN** in Step 3 (Topic Discussion)
- **THEN** each topic SHALL include a "热度依据" (Heat Justification) section
- **AND** the section SHALL contain:
  - Social media heat with specific data or observations
  - Peer topic references with examples
  - User demand indicators with sources
- **AND** topics SHALL be rated with stars (⭐⭐⭐⭐⭐) based on heat level

#### Scenario: Topic without sufficient heat validation
- **GIVEN** AI cannot find sufficient heat indicators for a topic
- **WHEN** still considering including the topic
- **THEN** AI SHALL mark it as "热度待验证" (Heat To Be Validated)
- **AND** AI SHALL explain why it's included despite low heat
- **AND** AI SHOULD recommend it as lower priority

---

### Requirement 4: Information Source Documentation

AI writing agent SHALL maintain and reference a curated list of Chinese information sources.

#### Scenario: Using Chinese information sources
- **GIVEN** AI needs to research hot topics
- **WHEN** Step 2.5 (Heat Assessment) is triggered
- **THEN** AI SHALL reference the file `_writing_reference/china-info-sources.md`
- **AND** AI SHALL select sources appropriate for the topic category
- **AND** AI SHALL use WebFetch for accessible sources

#### Scenario: Source access failure
- **GIVEN** AI attempts to fetch from a Chinese platform
- **WHEN** the request fails (403, 302 login redirect)
- **THEN** AI SHALL try alternative sources from the documented list
- **AND** AI SHALL document which sources were inaccessible
- **AND** AI MAY ask user for manual input if all sources fail

---

### Requirement 5: Heat Assessment Process (Step 2.5)

AI writing agent SHALL execute a dedicated heat assessment step between information search and topic discussion.

#### Scenario: New writing task with topic ideation needed
- **GIVEN** user requests a new article without specific topic
- **WHEN** completing Step 2 (Information Search)
- **THEN** AI SHALL proceed to Step 2.5 (Heat Assessment)
- **AND** AI SHALL use WebFetch to gather heat indicators from Chinese platforms
- **AND** AI SHALL analyze and filter topics based on channel positioning
- **AND** AI SHALL output a heat report with 3-5 hot topics
- **THEN** AI SHALL proceed to Step 3 (Topic Discussion) with heat-validated topics

#### Scenario: Brief already contains specific topic
- **GIVEN** user provides a brief with a specific topic already decided
- **WHEN** the topic is clear and non-negotiable
- **THEN** AI MAY skip Step 2.5 (Heat Assessment)
- **OR** AI MAY perform light heat validation to inform writing strategy
- **AND** AI SHALL document the decision to skip or simplify this step

---

### Requirement 6: Think Aloud for Tool Selection

AI writing agent SHALL explain tool selection reasoning.

#### Scenario: Choosing between WebFetch and WebSearch
- **GIVEN** AI is about to use WebFetch or WebSearch
- **WHEN** making the tool selection decision
- **THEN** AI SHALL use Think Aloud to explain:
  - Why this tool was chosen
  - What specific information is needed
  - Why the alternative tool is not suitable for this case
- **AND** the explanation SHALL be visible to the user

---

### Requirement 7: Channel Positioning Filter

AI writing agent SHALL filter topics through the channel positioning lens.

#### Scenario: Filtering topics for "AI技术拆解师" channel
- **GIVEN** AI has gathered hot AI-related topics from various sources
- **WHEN** evaluating which topics to recommend
- **THEN** AI SHALL apply channel positioning filters:
  - Does it fit "让人人都懂技术"? (Make tech understandable for everyone)
  - Does it relate to "如何使用AI提效"? (How to use AI for efficiency)
  - Is it actionable for target audience? (non-tech + tech users wanting quick grasp)
- **AND** AI SHALL exclude topics that:
  - Are too theoretical without practical application
  - Require deep technical background
  - Don't relate to AI tools, productivity, or understanding AI
- **AND** AI SHALL document why certain hot topics were excluded

---

## Non-Functional Requirements

### Performance
- Heat assessment (Step 2.5) SHALL complete within 10 minutes
- WebFetch requests SHOULD be made in parallel when possible
- Total overhead of heat assessment SHALL NOT exceed 15% of total workflow time

### Usability
- Heat justification format SHALL be easy to scan (星级+三维度)
- Tool selection explanation SHALL be concise (2-3 sentences)
- Information source list SHALL be categorized and annotated

### Maintainability
- Information source list SHALL be in a separate markdown file
- Heat assessment process SHALL be modular and independently updatable
- Version changes SHALL be documented in CLAUDE.md version history

---

## Acceptance Criteria

### For the overall change:
- [ ] All high-priority tasks in tasks.md are completed
- [ ] CLAUDE.md version updated to v1.5
- [ ] OpenSpec validation passes without errors
- [ ] At least one complete workflow test passes with new requirements
- [ ] User feedback indicates improved topic quality ("选题比之前好")

### For tool selection (Requirement 1):
- [ ] WebFetch is used for all known Chinese platform URLs
- [ ] Tool selection is explained with Think Aloud
- [ ] No user correction needed for tool choice in testing

### For heat assessment (Requirement 2, 5, 7):
- [ ] Step 2.5 is properly documented in CLAUDE.md
- [ ] Heat indicators come from Chinese platforms
- [ ] Topics are filtered through channel positioning
- [ ] Each recommended topic has documented heat justification

### For topic format (Requirement 3):
- [ ] Topic recommendation template includes "热度依据" section
- [ ] Heat justification covers 2-3 dimensions
- [ ] Star rating reflects actual heat level

### For information sources (Requirement 4):
- [ ] `china-info-sources.md` is created with 10+ sources
- [ ] Sources are categorized by type and accessibility
- [ ] Alternative sources are provided for login-required platforms

---

## Test Scenarios

### Test 1: Complete workflow with heat assessment
```
1. User provides brief: "写一篇关于AI提效的文章"
2. AI executes Step 1-2 (Brief + Info Search)
3. AI executes Step 2.5:
   - Uses WebFetch on sspai.com, jiqizhixin.com
   - Extracts AI-related hot topics
   - Filters through "AI技术拆解师" positioning
   - Outputs 3-5 topics with heat justification
4. AI proceeds to Step 3 with heat-validated topics
5. User feedback: topics are relevant and timely

Expected: All topics have documented heat sources, pass positioning filter
```

### Test 2: Tool selection correctness
```
1. AI needs to check sspai.com for hot articles
   - Expected: Uses WebFetch with sspai.com URL
   - Expected: Think Aloud explains why WebFetch
2. AI needs to research "DeepSeek Engram" concept
   - Expected: Uses WebSearch for broad research
   - Expected: Think Aloud explains information source unknown
3. AI needs official Gemini documentation
   - Expected: Uses WebFetch with docs URL if known
   - Expected: Uses WebSearch if URL unknown

Expected: Correct tool choice in all 3 cases, clear reasoning
```

### Test 3: Foreign tech news handling
```
1. AI discovers: "Mastra 1.0 released" on Hacker News
2. AI checks Chinese platforms: no discussion found
3. AI evaluates: does not fit "让人人都懂技术" (too niche for developers)
4. AI decision: exclude from recommendations or mark as "emerging, heat TBV"

Expected: AI does not recommend as high-priority hot topic
```

### Test 4: Heat justification quality
```
1. User receives topic recommendations
2. Each topic contains:
   - 星级评价 (⭐⭐⭐⭐⭐)
   - 社交媒体热度 (with specific observation)
   - 同行选题 (with example)
   - 用户需求 (with source)
3. User can quickly judge which topic is hottest

Expected: Format is clear, information is specific (not vague)
```

---

## Migration Notes

### Backward Compatibility
- Old workflow (without Step 2.5) still works
- Step 2.5 is RECOMMENDED but not strictly REQUIRED
- Existing briefs with specific topics can skip heat assessment

### Breaking Changes
- None. This is an additive change.

### Deprecation
- None. No existing features are deprecated.

---

## References

- Design Document: `design.md`
- Task List: `tasks.md`
- Proposal: `proposal.md`
- Main Rules: `mp-wechat/CLAUDE.md`
- Information Sources: `mp-wechat/_writing_reference/china-info-sources.md` (to be created)
