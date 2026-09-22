# Creative Workspace Design System Skill

## Purpose

Use `design-tokens.json` as the primary machine-readable knowledge source for future UX and UI work based on the **Creative Workspace Design System** FIG source.

The source file contains 102 canvas pages. The page manifest in `design-tokens.json` preserves the exact page names, including repeated `---` pages and `Internal Only Canvas`.

## Source of truth

1. Treat the extracted source data as authoritative.
2. Do not invent a component, state, token, color, interaction, or UX rule that is not supported by the source.
3. When the source does not define something, say `Not defined in source`.
4. Do not merge visually similar source components unless the source establishes that they are the same component.
5. Do not split a source component into artificial components just to make the schema look cleaner.

## Before creating anything new

Always search in this order:

1. `foundations.tokenSets`
2. `components.sourceComponentPages`
3. `variants.sourceObservedVariantCombinationStrings`
4. `states`
5. `assets`
6. `pageManifest` and `pages`
7. `pagePatterns`
8. `cognitiveDecisioning`

Only create a new pattern when the source does not contain an appropriate existing pattern.

## Page awareness

The 102 pages are part of the design knowledge. Do not treat the FIG as only a component library.

Relevant source pages include:

- 👋 Getting Started
- 🖼 Cover
- 🔥 Tokens
- 🌈 Colors
- ⚡️ Icons
- Projects Covered
- 🔷CW Components
- Internal Only Canvas
- Primitives
- Blocks
- Compare Flows
- The component reference pages beginning with `❖`
- ❖ Animated Loader

Repeated `---` pages are separate source pages and must remain separate.

When a requirement references an existing pattern, search the complete page manifest before deciding that the pattern does not exist.

## Token usage

The source contains these token sets:

- `aura/primitive`
- `aura/semantic`
- `aura/semantic/light`
- `aura/semantic/dark`
- `aura/component`
- `aura/component/light`
- `aura/component/dark`
- `app`

Use the exact source token name and source value. Preserve token references such as `{{primary.color}}` style relationships rather than replacing them with arbitrary new values.

## Color rule

The source contains a `purple.*` primitive scale, but the semantic primary tokens are defined separately. In the extracted source:

- Light `primary.color` resolves through `{primary.500}`.
- Dark `primary.color` resolves through `{primary.400}`.
- Purple exists as a primitive scale and must not automatically be treated as the semantic primary.

Therefore, when a future requirement says to use the Creative Workspace primary color, resolve the actual source token instead of hardcoding a guessed purple.

## Component states and properties

The source contains explicit property combinations such as button severity, state, disabled, icon-only, raised, rounded, text, outlined, and link combinations. It also contains component-specific state/property combinations for inputs, selection controls, toggles, and other components.

Use only combinations represented by the source.

Do not add a common state just because a component normally has it in another design system.

## Typography

The source includes Inter-based typography styles and named styles such as:

- `text-base/semibold/lineheight-150`
- `text-xl/semibold/lineheight-120`
- `text-2xl/semibold/lineheight-120`
- `text-3xl/semibold/lineheight-120`
- `text-4xl/semibold/lineheight-120`
- `text-5xl/semibold/lineheight-120`
- regular and bold equivalents
- `h6/semibold-600/line-height-1.2`
- `h6/regular-400/line-height-1.2`
- `h6/bold-700/line-height-1.2`

Prefer exact source styles and token references.

## SVG and vector reuse

When a future implementation needs an icon or vector, search the source asset inventory and page knowledge first. Do not substitute a generic icon library when a source asset exists.

## Cognitive Decisioning

The source contains explicit Cognitive Decisioning material, including:

- `Cognitive Decision Icon`
- icon types such as `Gray-collapsed`, `Gray-expanded`, and `White`
- `AI Score /Light theme`
- `Citation Score`
- `Decision Strength`
- `CD Score/Green`
- `Citation Relevance`

Preserve these source patterns and their relationships. Do not invent scoring behavior, meaning, thresholds, or decision logic that is not represented in the source.

## UX interpretation rules

### Intuitive

Treat `make it more intuitive` as a UX clarity requirement. Check:

- cognitive load
- information hierarchy
- competing actions
- primary action clarity
- labels and terminology
- grouping
- visual noise
- affordances
- feedback
- system status
- error recovery
- interaction sequence
- scanning
- spacing

Do not respond by automatically adding more colors, icons, tooltips, controls, or decoration.

### Minimalist

Treat `minimalist` as reduced unnecessary visual and cognitive complexity while keeping the information and actions needed for task completion.

### User centric

Check the user's goal, task completion, discoverability, hierarchy, feedback, recovery, clarity, accessibility, consistency, and predictability while remaining inside the existing design system.

## Content and labels

Use clear, specific, concise, action-oriented, context-appropriate language. Avoid ambiguous labels, unnecessary jargon, generic wording, and redundant explanations.

## Validation before delivery

Before delivering a new design, verify:

- an existing source component was considered
- an existing source state or variant was considered
- an existing token was considered
- an existing page pattern was considered
- an existing SVG/vector asset was considered
- page context is preserved
- source component boundaries are preserved
- unsupported states were not invented
- new colors were not invented
- new interactions were not invented

## Important extraction status

`design-tokens.json` explicitly records that the runtime verified the 102-page manifest and decoded the embedded token JSON, but did not have a full semantic Kiwi node-tree decoder available. Fields marked `Not semantically decoded` must never be interpreted as zero or as evidence that the source contains nothing there.

If a task requires exact node geometry, auto-layout, parent-child hierarchy, vector paths, or per-node visual properties, perform a full Kiwi semantic decode before making source-specific claims.


Use the Creative Workspace Global AI Design System as the visual source of truth.

First identify the closest existing component or custom Creative Workspace pattern.

Reuse existing component variants and states.

Use semantic tokens before primitive tokens.

Use the Aura collection as the primary global token source unless the requested component belongs to a clearly defined custom Creative Workspace pattern.

Preserve Inter typography.

Preserve the existing spacing, radius, border, focus, surface, and elevation system.

Use the existing Light or Dark mode values instead of manually transforming colors.

Do not invent colors, typography, component states, or spacing when an existing token or component already satisfies the requirement.

When a new pattern is genuinely required, construct it using existing primitives and semantic tokens and keep the naming structure consistent with the existing design system.

Before finalizing the design, check component selection, typography, color semantics, spacing, radius, states, focus behavior, disabled behavior, and accessibility.

When implementing a new requirement, explain the design decision only when requested. Otherwise apply the system directly.
