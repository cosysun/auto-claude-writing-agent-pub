# Project Context

## Purpose

**AI Writing Agent** is a multi-platform automated writing system designed for content creators. It leverages Claude Sonnet 4.5 to provide a complete, transparent, and structured workflow from content requirements to publication.

### Core Values
- **AI as Partner, Not Replacement**: AI handles 90% repetitive work, humans focus on 10% creativity
- **Process as Guide, Not Dogma**: Flexible workflow with non-negotiable core principles
- **Authenticity > Perfection**: Real data, no fabrication
- **Transparency**: Think Aloud throughout the entire process

### Target Users
- Content creators on platforms like WeChat Official Accounts, X/Twitter, Xiaohongshu, Zhihu
- Technical and non-technical writers who need AI assistance
- Teams requiring consistent content quality with personal voice

## Tech Stack

### Primary Technologies
- **AI Model**: Claude Sonnet 4.5 (100M token context, strong instruction following)
- **Development Tools**: Claude Code, Cursor
- **File Format**: Markdown (.md)
- **Version Control**: Git
- **Search Tools**: Claude built-in search (no external API required)
- **Image Generation**: Prompt-based (supports Midjourney, DALL-E, SD)

### Language & Format
- **Documentation**: Chinese + English
- **Content**: Primarily Chinese (WeChat, Xiaohongshu)
- **Code/Config**: English variable names, Chinese comments
- **All files**: UTF-8 encoding

## Project Conventions

### Code Style
N/A - This is a documentation and workflow project, not a code project.

### File Naming Conventions

#### Brief Files
- Format: `YYYY-MM-DD-主题关键词-brief.md`
- Example: `2025-11-01-deepfake_wan2.2-brief.md`
- Location: `mp-wechat/_briefs/`

#### Draft Files
- Format: `YYYY-MM-DD-主题-draft-v{N}.md`
- Versions: `v1` → `v2` → `v3` → `final`
- Example: `2025-11-01-deepfake爆火-draft-v1.md`
- Location: `mp-wechat/_drafts/`

#### Published Files
- Format: `YYYY-MM-DD-主题-final.md`
- Location: `mp-wechat/_published/`

#### Knowledge Base Files
- Format: `YYYY-MM-DD-主题.md`
- Location: `mp-wechat/_knowledge_base/`

#### Cooperation Files
- Format: `YYYY-MM-DD-主题-协作文档.md`
- Location: `mp-wechat/_cooperation/`

### Directory Structure

```
/
├── CLAUDE.md                    # Master control document for all platforms
├── AGENTS.md                    # Agent instructions (if applicable)
├── README.md                    # Project overview
├── openspec/                    # OpenSpec specifications
│   ├── project.md              # This file
│   ├── AGENTS.md               # OpenSpec agent instructions
│   └── specs/                  # Capability specifications
│
├── mp-wechat/                   # WeChat Official Account (✅ Complete)
│   ├── CLAUDE.md               # Platform-specific rules (1085 lines, v1.3)
│   ├── README.md               # Platform documentation
│   ├── _briefs/                # Requirements
│   ├── _drafts/                # Draft versions
│   ├── _published/             # Published content
│   ├── _personal_materials/    # Personal content library (降AI味核心)
│   ├── _writing_reference/     # Style guides
│   ├── _knowledge_base/        # Research archives
│   ├── _cooperation/           # Collaboration docs
│   ├── _templates/             # Templates
│   └── images/                 # Image assets
│
├── x-twitter/                   # X/Twitter (🔄 Planned)
├── xiaohongshu/                 # Xiaohongshu (🔄 Planned)
└── zhihu/                       # Zhihu (🔄 Planned)
```

### Architecture Patterns

#### Two-Layer Decision Mechanism

**Layer 1: Platform Identification**
- Identify the target platform (WeChat, X, Xiaohongshu, etc.)
- Load the corresponding `CLAUDE.md` rules

**Layer 2: Task Type Classification**
- **Type A**: New writing task with complete brief → Full 10-step workflow
- **Type B**: New writing task without brief → Create brief first, then full workflow
- **Type C**: Modify existing article → Read → Understand → Modify → Review
- **Type D**: Article review/降AI味 → Direct to 3-pass review workflow
- **E**: Quick consultation → Direct answer, no workflow needed

#### Multi-Platform Architecture

Each platform has:
1. **CLAUDE.md**: Complete rules and workflow (platform-specific)
2. **README.md**: Quick start guide
3. **Standardized folders**: `_briefs/`, `_drafts/`, `_published/`, etc.
4. **Personal materials**: `_personal_materials/` (critical for reducing AI flavor)

#### 10-Step Workflow (WeChat Official Account - v1.3)

```
Step 1: Understand Requirements & Save Brief ⭐
Step 2: Research & Knowledge Base ⭐ (must save after search)
Step 3: Topic Discussion ⭐⭐⭐ (NEVER skip - provide 3-4 options)
Step 4: Collaboration Doc (if testing needed)
Step 5: Style Learning & Personal Materials ⭐⭐⭐ (must search)
Step 6: Wait for Test Data (optional)
Step 6.5: Creative Drainage ⭐ (recommended, mandatory for important articles)
Step 7: Draft Creation (v1, strict version control)
Step 8: Three-Pass Review ⭐⭐⭐ (Content→Style→Details, create new version each pass)
Step 9: Title Creation ⭐⭐⭐ (provide 3-5 options)
Step 10: Image Preparation ⭐ (3 versions of prompts)
```

**v1.3 Key Update**: "First Principles" section added to prevent AI from skipping critical steps.

#### Three-Pass Review Mechanism (降AI味 Core)

**Pass 1: Content Review**
- Fact accuracy
- Logic clarity
- Structure soundness
- No fabrication
- Paragraph mini-arguments (new in v1.1)

**Pass 2: Style Review (降AI味)**
- Remove套话 (clichés): "归根结底", "在这个时代"
- Break down complex sentence patterns
- Replace formal vocabulary with conversational language
- Add real details (time, place, numbers, feelings)
- Inject personal attitude

**Pass 3: Detail Polishing**
- Sentence length (15-25 characters, but vary)
- Paragraph length (3-5 lines on mobile)
- Punctuation naturalness
- Rhythm variation ⭐⭐⭐
- Microhumor density ⭐
- Dopamine density ⭐

### Testing Strategy

This is a documentation/workflow project, not a software project, so traditional testing doesn't apply.

**Validation Methods**:
- Real-world content creation testing (already published 1+ articles)
- User feedback on AI flavor detection (<30% target)
- Workflow efficiency measurement (time saved vs manual writing)
- Style consistency verification (compared to historical content)

### Git Workflow

#### Branch Strategy
- **main**: Production-ready, stable versions
- Feature branches: `feature/platform-name` (e.g., `feature/twitter`)
- Version tags: `v1.0`, `v1.1`, `v1.2`, `v1.3`

#### Commit Conventions
- Use descriptive messages
- Format: `type: description`
  - `feat:` - New platform or major feature
  - `update:` - Update to rules or documentation
  - `fix:` - Bug fixes or corrections
  - `docs:` - Documentation only changes
- Example: `feat: add cowork chapter`

#### Version History
- **v1.3** (2025-11-23): Added "First Principles" section, 9 key step checklist
- **v1.2** (2025-11-08): Added complete title creation workflow
- **v1.1** (2025-11-08): Added creative drainage step, 5 core writing techniques
- **v1.0** (2025-10-26): Initial version with complete WeChat Official Account system

## Domain Context

### Content Creation Domain

**AI Flavor (AI味)**: The mechanical, templated quality that makes content immediately recognizable as AI-generated. Key characteristics include:
- Clichés: "在当今时代", "归根结底", "需要强调的是"
- Complex sentence patterns: "不仅...而且...", "既...又..."
- Formal vocabulary over conversational language
- Lack of specific details, numbers, personal feelings
- Monotonous sentence rhythm

**Reducing AI Flavor**: Core strategy involves:
1. **Personal Materials Library** (`_personal_materials/`): Real experiences, opinions, cases
2. **Three-Pass Review**: Systematic AI flavor reduction
3. **Creative Drainage**: Eliminate "dirty water" (cliché ideas) before writing
4. **Microhumor**: Make content engaging (every 200 characters)
5. **Sentence Rhythm Variation**: Create "music" in writing

### Writing Workflow Domain

**Think Aloud**: Transparent thinking process where AI explains every key decision. Critical for user trust and collaboration control.

**Version Management**: Strict versioning for drafts:
- `draft-v1.md`: Initial draft
- `draft-v2.md`: After first review (content)
- `draft-v3.md`: After second review (style/降AI味)
- `final.md`: After third review (details)

**Brief-Driven**: All content creation starts with a brief document containing:
- Topic and purpose
- Target audience
- Key points to cover
- Special requirements

### Platform-Specific Knowledge

#### WeChat Official Account (微信公众号)
- **Word Count**: 2000-4000 characters
- **Images**: 5-8 recommended
- **Style**: In-depth + practical, real cases
- **Audience**: AI Technology Dismantler - making technology accessible and usable
- **Target Readers**:
  - Non-technical users who want to understand AI
  - Technical users who want to quickly grasp new concepts

#### X/Twitter (Planned)
- **Word Count**: 280 characters per tweet, threads for longer content
- **Images**: 0-4
- **Style**: Concise + opinionated, spark discussion
- **Update Frequency**: Daily

#### Xiaohongshu (Planned)
- **Word Count**: 500-1500 characters
- **Images**: 6-9 (first image most important)
- **Style**: Visual + emotional, attention-grabbing
- **Update Frequency**: Daily

## Important Constraints

### Non-Negotiable Core Principles (不可妥协)

#### 1. Never Fabricate Data ❌
- All data must be real or from reliable sources
- Mark uncertain data with "约", "大约", "估计"
- When no data available, say "暂无数据"

#### 2. Never Use Outdated Information ❌
- For time-sensitive topics, must search for latest info
- Technology content prioritizes official documentation
- Mark timeliness: "截至2025年11月"

#### 3. Never Skip Think Aloud ❌
- Explain thinking process before each key decision
- User can see judgment logic
- Format: 【Think Aloud】+ reasoning

#### 4. Never Skip User Confirmation (Important Decisions) ❌
- For topic selection, style, major changes: must ask user
- Provide 2-3 options with pros/cons
- Wait for confirmation before proceeding

### Technical Constraints

- **AI Model**: Must use Claude Sonnet 4.5 (or equivalent 100M+ context model)
- **Context Window**: Requires large context (1M tokens) for processing complete documents
- **File Format**: All content must be in Markdown (.md)
- **Encoding**: UTF-8 only

### Business Constraints

- **Content Ownership**: User owns all generated content
- **Privacy**: Personal materials stored locally, not shared
- **Attribution**: Can be used commercially without "AI-generated" label
- **Quality Standard**: AI flavor detection <30%

## External Dependencies

### AI Services
- **Claude API / Subscription**: Required for Claude Sonnet 4.5 access
- **Claude Code or Cursor**: Recommended IDE for best experience

### Search Services
- **Claude Built-in Search**: Primary search tool (no external API needed)
- **Web Search**: Backup for latest information

### Image Generation (Optional)
- **Midjourney v6**: Recommended for high-quality images
- **DALL-E 3**: Alternative option
- **Stable Diffusion XL**: Open-source alternative
- Note: Only provides prompts, user generates images externally

### No External Dependencies
- No database required (file-based)
- No server required (runs locally)
- No API keys required (except Claude)
- No deployment infrastructure needed

## Key Success Metrics

### Quality Metrics
- AI flavor detection rate: <30% (target)
- Fact accuracy: 100% (no fabrication allowed)
- Style consistency: User satisfaction-based

### Efficiency Metrics
- Time saved vs manual writing: Target 50-70%
- Rework rate: Minimize through topic discussion step
- User confirmation points: 3-5 per article (topic, title, final review)

### Content Metrics
- Word count compliance: Within platform standards
- Image count: Within platform recommendations
- Publication rate: Track completion from brief to published

## Change Management

When making changes to this project:

1. **Rule Changes** (`CLAUDE.md`):
   - Update version number
   - Document in version history
   - Test with real content creation
   - Update README if workflow changes

2. **New Platform Addition**:
   - Create new directory: `platform-name/`
   - Create platform `CLAUDE.md` with platform-specific rules
   - Add entry in master `CLAUDE.md` navigation
   - Update project README

3. **Workflow Optimization**:
   - Document current issues
   - Propose changes with rationale
   - Test with real use cases
   - Update all relevant documentation

4. **Breaking Changes**:
   - Increment major version (e.g., v1.x → v2.0)
   - Provide migration guide
   - Preserve backward compatibility when possible

---

**Last Updated**: 2026-01-21
**Project Version**: v1.3
**Maintained By**: AI Writing Agent Team
