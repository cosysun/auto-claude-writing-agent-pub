# Specification Delta: WeChat Official Account Illustration Generation

## ADDED Requirements

### Requirement: Illustration Style Selection

The system SHALL select appropriate illustration styles based on image purpose within WeChat Official Account articles.

#### Scenario: Cover image generation
- **WHEN** generating the first/cover image for an article
- **THEN** the system SHALL use Style A (Tech Breakdown) with deep tech background and deconstruction elements
- **AND** the image SHALL NOT include character/human elements
- **AND** the prompt SHALL reference `illustration-guide.md` Style A specifications

#### Scenario: Process flow image generation
- **WHEN** generating images for step-by-step processes or tutorials
- **THEN** the system SHALL use Style B (Visual Guide) with white background and card layout
- **AND** the image SHALL include numbered cards, arrows, and clear visual hierarchy

#### Scenario: Concept explanation image generation
- **WHEN** generating images to explain technical concepts or comparisons
- **THEN** the system SHALL use Style A (Tech Breakdown) with 3D visualization and breakdown elements
- **AND** the image SHALL focus on modular/layered representations without characters

### Requirement: Style A Character-Free Constraint

Style A (Tech Breakdown) illustrations SHALL NOT include anthropomorphic characters or human figures.

#### Scenario: Replace character focus with visual elements
- **WHEN** generating a Style A image that would traditionally include a character
- **THEN** the system SHALL use 3D icons (magnifying glass, building blocks, gears) as focal points
- **AND** the system SHALL use glowing effects, arrows, or spotlight elements to guide attention
- **AND** the breakdown concept SHALL be conveyed through modular/exploded view structures

#### Scenario: Maintain brand recognition without characters
- **WHEN** generating multiple Style A images across different articles
- **THEN** images SHALL maintain visual consistency through color palette (deep blue/purple + yellow highlights)
- **AND** images SHALL use consistent visual metaphors (LEGO blocks for modularity, X-ray for transparency, layers for depth)
- **AND** the "tech dismantler" brand positioning SHALL be conveyed through deconstruction visual language

### Requirement: Image Combination Strategy

For standard WeChat Official Account articles, the system SHALL generate 5-8 images with specific style distribution.

#### Scenario: Standard article image set
- **WHEN** creating images for a technical article
- **THEN** the system SHALL generate:
  - 1 cover image using Style A (必须)
  - 0-1 problem introduction image using Style A (可选)
  - 1-2 concept explanation images using Style A
  - 2-3 process/tutorial images using Style B
  - 1 summary/recap image using Style B (推荐)
- **AND** the total SHALL be 5-8 images
- **AND** Style A SHALL comprise approximately 40% of images
- **AND** Style B SHALL comprise approximately 60% of images

### Requirement: Prompt Template Structure

For each image, the system SHALL generate 3 versions of prompts following `illustration-guide.md` specifications.

#### Scenario: Three-version prompt generation
- **WHEN** creating prompts for an illustration
- **THEN** the system SHALL generate:
  - Version 1 (通用版): Doubao/general AI generator compatible format
  - Version 2 (细节增强版): Enhanced detail version for Doubao
  - Version 3 (风格化版): Midjourney-specific format with parameters
- **AND** each version SHALL clearly specify Style A or Style B
- **AND** prompts SHALL reference specific template from `illustration-guide.md`

#### Scenario: Style A prompt must be character-free
- **WHEN** generating prompts for Style A images
- **THEN** prompts SHALL NOT include character descriptions (e.g., "戴眼镜的卡通男生", "cartoon character")
- **AND** prompts SHALL include alternative focal elements (e.g., "发光的放大镜图标", "3D立体积木")
- **AND** prompts SHALL maintain dark tech background and deconstruction visual language

### Requirement: Reference Illustration Guide Document

The system SHALL reference `mp-wechat/_templates/illustration-guide.md` when generating image prompts.

#### Scenario: Load illustration guidelines at Step 10
- **WHEN** executing Step 10 (Image Preparation) in the writing workflow
- **THEN** the system SHALL read `illustration-guide.md` specifications
- **AND** the system SHALL identify applicable scene templates from the guide
- **AND** the system SHALL apply style-specific formatting rules

#### Scenario: Apply scene templates
- **WHEN** determining the type of image needed (e.g., concept breakdown, process flow)
- **THEN** the system SHALL select the appropriate scene template from illustration-guide.md
- **AND** the system SHALL customize the template with article-specific content
- **AND** the system SHALL preserve the structural elements defined in the template

### Requirement: Visual Consistency Across Article Set

Images within a single article SHALL maintain visual consistency while using appropriate styles.

#### Scenario: Multi-style consistency
- **WHEN** an article uses both Style A and Style B images
- **THEN** color palette SHALL remain consistent across styles (blue for AI/tech, orange for action, green for outcomes)
- **AND** icon design language SHALL be consistent
- **AND** typography style SHALL be consistent
- **AND** the overall visual narrative SHALL flow logically from cover to summary

## MODIFIED Requirements

_None - this is a new capability specification_

## REMOVED Requirements

_None - this is a new capability specification_

## RENAMED Requirements

_None - this is a new capability specification_
