# Design Document: Character-Free Illustration Strategy

## Context

The AI Writing Agent project uses AI-generated illustrations for WeChat Official Account articles. The current illustration-guide.md includes two styles:
- **Style A (Tech Breakdown)**: Dark tech backgrounds with a cartoon character wearing glasses
- **Style B (Visual Guide)**: White backgrounds with card-based infographic layouts

User feedback and analysis revealed that character elements in Style A may not be optimal for article illustrations.

## Goals

- Improve illustration quality and consistency
- Better align visuals with "technical dismantler" brand positioning
- Maintain the "breakdown/deconstruction" visual language without characters
- Provide clear guidance for AI agents on when to use each style

## Non-Goals

- Not creating a complete brand redesign
- Not establishing a character mascot (may be revisited in future)
- Not changing Style B (already character-free)
- Not requiring changes to existing published content

## Decisions

### Decision 1: Remove Character Elements from Style A

**Rationale:**
1. **Consistency Problem**: AI-generated characters vary significantly between images, undermining brand coherence
2. **Attention Economy**: In article context, characters compete with technical concepts for reader attention
3. **Platform Context**: WeChat articles are information-dense, unlike video platforms where personality drives engagement
4. **Developmental Stage**: The account hasn't established the character as a brand asset yet
5. **Professional Tone**: Pure information graphics convey more authority for technical content

**Alternatives Considered:**
- **Alt 1: Simplify character to silhouette/stick figure** - Still faces consistency issues, loses distinctiveness
- **Alt 2: Keep character but reduce prominence** - Half-measure that doesn't solve core issues
- **Alt 3: Commission professional character design** - Premature at current scale, expensive

**Selected Approach**: Remove characters entirely, replace with 3D icons and abstract visual elements

### Decision 2: Visual Element Replacement Strategy

**What Replaces the Character:**
- **3D icons**: Magnifying glass (investigation), building blocks (modularity), gears (systems)
- **Glowing effects**: Highlight focal points without anthropomorphization
- **Layered/exploded views**: Reinforce "breakdown" concept through structure
- **Directional arrows**: Guide attention without a character pointing

**Maintains Core "Breakdown" Language:**
- Modular/LEGO-style elements → decomposability
- X-ray/transparency effects → seeing beneath the surface
- Layered expansions → peeling back complexity
- Spotlight/magnification → focus on details

### Decision 3: Style Usage Guidelines

**Style A (Tech Breakdown) - 40% of images:**
- Cover/hero images (must grab attention)
- Core concept explanations (need focus)
- Comparison graphics (visual contrast)
- Problem introduction (establish tension)

**Style B (Visual Guide) - 60% of images:**
- Step-by-step processes (clarity over impact)
- Tool/feature listings (information density)
- Summary/recap graphics (comprehensive view)
- Tutorial flows (guide readers)

**Rationale for Split:**
- Most article content is explanatory/instructional → Style B dominant
- Key moments need visual punch → Style A for impact
- Balance professionalism (B) with engagement (A)

## Risks / Trade-offs

### Risk 1: Loss of Brand Character
- **Mitigation**: Develop other brand elements (consistent color palette, typography, layout patterns)
- **Acceptance**: Early stage makes this acceptable; can add character later if needed

### Risk 2: Style A May Seem Generic
- **Mitigation**: Use distinctive visual metaphors (specific to "dismantling tech"), consistent color schemes
- **Monitoring**: Track reader engagement metrics on Style A images

### Risk 3: AI Prompt Complexity
- **Mitigation**: Provide detailed prompt templates with examples
- **Validation**: Test prompts with multiple AI generators before finalizing

## Migration Plan

**Phase 1: Documentation Update (Immediate)**
1. Update illustration-guide.md
2. Update CLAUDE.md Step 10
3. Create OpenSpec specification

**Phase 2: New Content (Immediate)**
- All new articles use updated guidelines
- No retroactive changes to published content

**Phase 3: Monitoring (Ongoing)**
- Track image generation quality
- Monitor reader engagement metrics
- Collect user feedback on visual style

**Rollback Plan:**
- If image quality degrades significantly, can revert illustration-guide.md
- No system changes required - purely prompt-level adjustments

## Open Questions

1. **Character Reintroduction?**
   - When: After 5000+ followers with established content brand
   - How: Professional designer, not AI-generated
   - Why: Brand IP development requires audience base first

2. **Style Ratio Adjustment?**
   - Current: 40% Style A, 60% Style B
   - Monitor: Reader scrolling behavior, time-on-page
   - Adjust: If data shows different engagement patterns

3. **Platform Expansion?**
   - Twitter/X may benefit from different style ratios
   - Xiaohongshu may need more Style A (visual platform)
   - Address in separate proposals when platforms are added

## Success Metrics

- Image generation consistency: Fewer retry prompts needed
- User feedback: Perceived professionalism and clarity
- Engagement: Click-through rates on articles with new style
- Workflow efficiency: Time saved on image iteration
