# Change: Update Illustration Style to Remove Character Elements

## Why

The current illustration guide includes character elements (a cartoon character with glasses) in Style A (Tech Breakdown style), which presents several challenges for WeChat Official Account article illustrations:

1. **Attention Distraction**: Characters can draw attention away from core technical concepts in article context
2. **Consistency Issues**: AI-generated characters lack consistency across different images, undermining brand identity
3. **Platform Mismatch**: WeChat articles prioritize information density over personality, unlike video platforms
4. **Professional Perception**: Pure information graphics appear more professional and authoritative for technical content
5. **Brand Development Stage**: The account hasn't established this character as a recognized brand asset yet

## What Changes

### Updated Illustration Strategy
- **Remove character elements** from Style A (Tech Breakdown)
- Replace character visual focus with **3D icons, glowing magnifying glass, and abstract elements**
- Maintain the "breakdown/deconstruction" visual language through **modular/layered graphics**
- Update prompt templates to generate character-free illustrations
- Add clear guidance in CLAUDE.md Step 10 on when to use each style

### Style Distribution for Articles (5-8 images)
- **Style A (40%)**: Cover/hero images, concept explanations, comparisons
  - Deep/tech backgrounds + 3D visualization + deconstruction elements
  - **No characters** - use icons and abstract visual elements
- **Style B (60%)**: Process flows, step-by-step tutorials, summaries
  - White background + card layout + arrows + icons
  - Already character-free

### Integration with Writing Workflow
- Reference `illustration-guide.md` automatically in Step 10
- Provide style selection guidance based on image purpose
- Generate 3 prompt versions per image (General, Enhanced, MidJourney)

## Impact

### Affected Specs
- `mp-wechat-illustration`: New specification defining illustration generation rules

### Affected Code
- `mp-wechat/CLAUDE.md`: Step 10 (Image Preparation) - add style selection guidance
- `mp-wechat/_templates/illustration-guide.md`: Update Style A to remove character elements
- No code changes - this is a documentation/workflow project

### Benefits
- ✅ Higher quality AI-generated images (fewer consistency issues)
- ✅ More professional appearance for technical content
- ✅ Better information focus (no attention distraction)
- ✅ Clearer brand positioning as "technical dismantler" not personality-driven
- ✅ Easier to maintain visual consistency across articles

### Migration Path
- Existing published articles: No changes needed
- Future articles: Follow new illustration guidelines
- Optional: Users can still add characters later if brand develops
