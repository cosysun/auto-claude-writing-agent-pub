# Update Illustration Style Change Proposal

## 📋 Summary

This change proposal updates the illustration generation strategy for WeChat Official Account articles by removing character elements from Style A (Tech Breakdown) and providing clear guidance on style selection.

## 🎯 Key Changes

1. **Remove Characters from Style A**: Replace cartoon character with 3D icons and abstract visual elements
2. **Update Prompt Templates**: Revise illustration-guide.md to generate character-free prompts
3. **Add Style Selection Guidance**: Update CLAUDE.md Step 10 with clear when-to-use-which-style rules
4. **Define Standard Image Combination**: 5-8 images per article, 40% Style A + 60% Style B

## 📂 Files in This Change

- `proposal.md`: Problem statement, solution overview, impact analysis
- `tasks.md`: Implementation checklist (21 tasks across 5 categories)
- `design.md`: Detailed design decisions, alternatives considered, risks/mitigations
- `specs/mp-wechat-illustration/spec.md`: Formal requirements specification with scenarios

## ✅ Validation Status

```bash
openspec validate update-illustration-style --strict
```
**Result**: ✅ Valid (7 requirements, 13 scenarios)

## 🚀 Next Steps

### For Review
1. Review the design decisions in `design.md`
2. Check if the style distribution (40% A / 60% B) aligns with your vision
3. Confirm the rationale for removing characters makes sense

### For Implementation
Once approved, implement in this order:
1. Update `illustration-guide.md` (remove character elements)
2. Update `CLAUDE.md` Step 10 (add style selection guidance)
3. Test new prompts with AI image generators
4. Archive this change using `openspec archive update-illustration-style`

## 📊 Impact Assessment

### Low Risk
- Pure documentation change, no code involved
- Existing content unaffected
- Easily reversible if needed

### High Value
- Improved image consistency
- More professional appearance
- Clearer workflow guidance
- Better alignment with brand positioning

## 🔗 Related Documents

- Original discussion: [Conversation about character elements in WeChat articles]
- Illustration guide: `mp-wechat/_templates/illustration-guide.md`
- Writing workflow: `mp-wechat/CLAUDE.md` Step 10
- Project context: `openspec/project.md`

---

**Created**: 2026-01-21
**Change ID**: `update-illustration-style`
**Status**: Awaiting approval
