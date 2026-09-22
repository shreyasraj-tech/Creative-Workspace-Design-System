# Creative Workspace Global AI Design System

## 1. Purpose

This document is the global design knowledge source extracted from the Figma file `Creative Workspace Design System.fig`.

The goal is to give an AI enough structured knowledge to design new screens, modify existing screens, create HTML prototypes, generate product UI, and reason about component selection without inventing a new visual language.

The AI should treat the existing design system as the source of truth.

## 2. Extraction scope

The file contains:

* 102 Figma canvas pages
* 70,902 decoded node changes
* 10,780 text nodes
* 22,694 instances
* 14,397 frames
* 11,815 symbol masters
* 3,853 local variables
* 75 variable collections
* 81 Prime component documentation pages
* A dedicated `🔷CW Components` page containing 85 custom component symbols
* Dedicated pages for colors, tokens, icons, getting started material, animated loader material, primitives, and project examples

The machine readable companion files contain the detailed token and component data.

## 3. Global design system structure

The Figma file contains several layers of design language.

### Layer 1. Primitive color system

The Aura collection contains the main primitive color families.

The observed families are:

* Emerald
* Green
* Lime
* Red
* Orange
* Amber
* Yellow
* Teal
* Cyan
* Sky
* Blue
* Indigo
* Violet
* Purple
* Fuchsia
* Pink
* Rose
* Slate
* Gray
* Zinc
* Neutral
* Stone

Each family uses numeric steps from 50 through 950.

### Layer 2. Semantic color system

Semantic tokens describe how colors should be used rather than only defining raw color values.

Important semantic groups include:

* `primary`
* `surface`
* `button`
* `badge`
* `tag`
* `message`
* `focus`
* `highlight`
* `overlay`
* `form`
* `navigation`
* `content`
* `action`

When a semantic token exists, the AI should use the semantic token instead of directly choosing a primitive color.

### Layer 3. Component tokens

The Aura collection contains component specific tokens for:

* Buttons
* Forms
* Inputs
* Selects
* Checkboxes
* Radio buttons
* Toggle switches
* Date pickers
* Auto complete
* Cascade select
* Multi select
* Listbox
* Tree select
* Data table
* Tree table
* Data view
* Paginator
* Tabs
* Stepper
* Accordion
* Panels
* Cards
* Dialogs
* Drawers
* Popovers
* Tooltips
* Menus
* Menubars
* Context menus
* Toasts
* Messages
* Badges
* Tags
* Avatars
* Progress components
* Sliders
* Rating
* File upload
* Image components
* Navigation components
* Many additional Prime component families

Component tokens should be preferred over manually recreating component styling.

### Layer 4. Custom Creative Workspace components

The `🔷CW Components` page contains product specific patterns.

Observed custom areas include:

* Watch Me Work
* Checkbox and multi select
* Single select button
* Cognitive Decisioning
* LSC Main
* Cards
* Citations
* Slot
* Chat related components
* Attachment components
* File type components
* Status labels
* CD icon states
* Accordion LSC
* Score related components
* Stepper related components
* Loading and final stage components

Custom Creative Workspace components should take precedence when a requirement belongs to the Creative Workspace product rather than a generic Prime component.

## 4. AI design decision hierarchy

When generating a new UI, follow this order.

1. Reuse an existing custom Creative Workspace component when the requested pattern matches it.
2. Reuse an existing documented Prime component when no custom pattern exists.
3. Use the semantic component token for the selected component.
4. Use the semantic global token for color, surface, focus, or status.
5. Use primitive tokens only when a semantic token does not exist.
6. Create a new value only when the requested requirement cannot be represented using the existing system.
7. When a new value is unavoidable, keep it visually consistent with the nearest existing token and clearly identify it as a new token candidate.

The AI should not replace an existing token with a visually similar invented value.

## 5. Primary brand system

The primary brand color is:

`#5925DC`

The Figma file also defines the primary scale.

### Primary scale

* 50: `#FCFAFF` in Light mode and `#FAF5FF` in Dark mode
* 100: `#F4F3FF` in Light mode and `#F3E8FF` in Dark mode
* 200: `#D9D6FE`
* 300: `#BDB4FE`
* 400: `#9B8AFB`
* 500: `#7B67EA`
* 600: `#6938EF`
* 700: `#5925DC`
* 800: `#481FB8`
* 900: `#3E1C96`
* 950: `#281164`

### Primary semantic behavior

* `primary/color` is `#5925DC`
* `primary/hover/color` is `#6938EF` in Light mode
* `primary/hover/color` is `#BDB4FE` in Dark mode
* `primary/active/color` is `#5925DC` in Light mode
* `primary/active/color` is `#D9D6FE` in Dark mode
* `primary/contrast/color` is `#FFFFFF` in Light mode
* `primary/contrast/color` is `#18181B` in Dark mode

Primary should be used for important actions, active controls, selected states, focus treatment, links when the pattern calls for an interactive accent, and important product emphasis.

Primary should not be used as a decorative color everywhere. It should communicate interaction, emphasis, selection, or product identity.

## 6. Surface system

The surface scale supports Light and Dark modes.

* 0: Light `#FFFFFF`, Dark `#FFFFFF`
* 50: Light `#F8FAFC`, Dark `#FAFAFA`
* 100: Light `#F1F5F9`, Dark `#F4F4F5`
* 200: Light `#E2E8F0`, Dark `#E4E4E7`
* 300: Light `#CBD5E1`, Dark `#D4D4D8`
* 400: Light `#94A3B8`, Dark `#A1A1AA`
* 500: Light `#64748B`, Dark `#71717A`
* 600: Light `#475569`, Dark `#52525B`
* 700: Light `#334155`, Dark `#3F3F46`
* 800: Light `#1E293B`, Dark `#27272A`
* 900: Light `#0F172A`, Dark `#18181B`
* 950: Light `#020617`, Dark `#09090B`

Use surface tokens for backgrounds, containers, panels, cards, overlays, navigation regions, and contrast surfaces.

Do not invent a separate gray background when an appropriate surface token exists.

## 7. Primitive palette

The complete primitive palette is available in `creative_workspace_design_tokens.json`.

The main families are:

* `emerald`: 50 #ECFDF5, 100 #D1FAE5, 200 #A7F3D0, 300 #6EE7B7, 400 #34D399, 500 #10B981, 600 #059669, 700 #047857, 800 #065F46, 900 #064E3B, 950 #022C22
* `green`: 50 #F0FDF4, 100 #DCFCE7, 200 #BBF7D0, 300 #86EFAC, 400 #4ADE80, 500 #22C55E, 600 #16A34A, 700 #15803D, 800 #166534, 900 #14532D, 950 #052E16
* `lime`: 50 #F7FEE7, 100 #ECFCCB, 200 #D9F99D, 300 #BEF264, 400 #A3E635, 500 #84CC16, 600 #65A30D, 700 #4D7C0F, 800 #3F6212, 900 #365314, 950 #1A2E05
* `red`: 50 #FEF2F2, 100 #FEE2E2, 200 #FECACA, 300 #FCA5A5, 400 #F87171, 500 #EF4444, 600 #DC2626, 700 #B91C1C, 800 #991B1B, 900 #7F1D1D, 950 #450A0A
* `orange`: 50 #FFF7ED, 100 #FFEDD5, 200 #FED7AA, 300 #FDBA74, 400 #FB923C, 500 #F97316, 600 #EA580C, 700 #C2410C, 800 #9A3412, 900 #7C2D12, 950 #431407
* `amber`: 50 #FFFBEB, 100 #FEF3C7, 200 #FDE68A, 300 #FCD34D, 400 #FBBF24, 500 #F59E0B, 600 #D97706, 700 #B45309, 800 #92400E, 900 #78350F, 950 #451A03
* `yellow`: 50 #FEFCE8, 100 #FEF9C3, 200 #FEF08A, 300 #FDE047, 400 #FACC15, 500 #EAB308, 600 #CA8A04, 700 #A16207, 800 #854D0E, 900 #713F12, 950 #422006
* `teal`: 50 #F0FDFA, 100 #CCFBF1, 200 #99F6E4, 300 #5EEAD4, 400 #2DD4BF, 500 #14B8A6, 600 #0D9488, 700 #0F766E, 800 #115E59, 900 #134E4A, 950 #042F2E
* `cyan`: 50 #ECFEFF, 100 #CFFAFE, 200 #A5F3FC, 300 #67E8F9, 400 #22D3EE, 500 #06B6D4, 600 #0891B2, 700 #0E7490, 800 #155E75, 900 #164E63, 950 #083344
* `sky`: 50 #F0F9FF, 100 #E0F2FE, 200 #BAE6FD, 300 #7DD3FC, 400 #38BDF8, 500 #0EA5E9, 600 #0284C7, 700 #0369A1, 800 #075985, 900 #0C4A6E, 950 #082F49
* `blue`: 50 #EFF6FF, 100 #DBEAFE, 200 #BFDBFE, 300 #93C5FD, 400 #60A5FA, 500 #3B82F6, 600 #2563EB, 700 #1D4ED8, 800 #1E40AF, 900 #1E3A8A, 950 #172554
* `indigo`: 50 #EEF2FF, 100 #E0E7FF, 200 #C7D2FE, 300 #A5B4FC, 400 #818CF8, 500 #6366F1, 600 #4F46E5, 700 #4338CA, 800 #3730A3, 900 #312E81, 950 #1E1B4B
* `violet`: 50 #F5F3FF, 100 #EDE9FE, 200 #DDD6FE, 300 #C4B5FD, 400 #A78BFA, 500 #8B5CF6, 600 #7C3AED, 700 #6D28D9, 800 #5B21B6, 900 #4C1D95, 950 #2E1065
* `purple`: 50 #FCFAFF, 100 #F4F3FF, 200 #D9D6FE, 300 #BDB4FE, 400 #9B8AFB, 500 #7B67EA, 600 #6938EF, 700 #5925DC, 800 #481FB8, 900 #3E1C96, 950 #281164
* `fuchsia`: 50 #FDF4FF, 100 #FAE8FF, 200 #F5D0FE, 300 #F0ABFC, 400 #E879F9, 500 #D946EF, 600 #C026D3, 700 #A21CAF, 800 #86198F, 900 #701A75, 950 #4A044E
* `pink`: 50 #FDF2F8, 100 #FCE7F3, 200 #FBCFE8, 300 #F9A8D4, 400 #F472B6, 500 #EC4899, 600 #DB2777, 700 #BE185D, 800 #9D174D, 900 #831843, 950 #500724
* `rose`: 50 #FFF1F2, 100 #FFE4E6, 200 #FECDD3, 300 #FDA4AF, 400 #FB7185, 500 #F43F5E, 600 #E11D48, 700 #BE123C, 800 #9F1239, 900 #881337, 950 #4C0519
* `slate`: 50 #F8FAFC, 100 #F1F5F9, 200 #E2E8F0, 300 #CBD5E1, 400 #94A3B8, 500 #64748B, 600 #475569, 700 #334155, 800 #1E293B, 900 #0F172A, 950 #020617
* `gray`: 50 #F9FAFB, 100 #F3F4F6, 200 #E5E7EB, 300 #D1D5DB, 400 #9CA3AF, 500 #6B7280, 600 #4B5563, 700 #374151, 800 #1F2937, 900 #111827, 950 #030712
* `zinc`: 50 #FAFAFA, 100 #F4F4F5, 200 #E4E4E7, 300 #D4D4D8, 400 #A1A1AA, 500 #71717A, 600 #52525B, 700 #3F3F46, 800 #27272A, 900 #18181B, 950 #09090B
* `neutral`: 50 #FAFAFA, 100 #F5F5F5, 200 #E5E5E5, 300 #D4D4D4, 400 #A3A3A3, 500 #737373, 600 #525252, 700 #404040, 800 #262626, 900 #171717, 950 #0A0A0A
* `stone`: 50 #FAFAF9, 100 #F5F5F4, 200 #E7E5E4, 300 #D6D3D1, 400 #A8A29E, 500 #78716C, 600 #57534E, 700 #44403C, 800 #292524, 900 #1C1917, 950 #0C0A09

## 8. Typography

The file uses Inter as the primary font family.

Observed font weights include:

* Regular
* Medium
* Semibold
* Bold

The dedicated typography variables include:

* Body XS: 14
* Body S: 16
* Body M: 18
* Body L: 20
* H1: 48
* H2: 40
* H3: 36
* H4: 30
* H5: 24
* Label: 12

The file also contains a larger set of Figma text styles using sizes such as:

* 10.5
* 12.25
* 14
* 17.5
* 21
* 24.5
* 28
* 35

Observed line height systems include:

* 1
* 1.2
* 1.5
* Automatic
* Explicit pixel values such as 14, 17, 18, 20, 21, 24, 28, 31.5, 42, and 60

Typography should preserve the relationship between font size, weight, and line height.

Do not change font family or weight simply to make a component visually stronger.

Use hierarchy through size, weight, spacing, and semantic placement.

## 9. Typography naming behavior

The Figma file contains multiple naming systems.

Examples include:

* `text-xs`
* `text-base`
* `text-xl`
* `text-2xl`
* `text-3xl`
* `text-4xl`
* `text-5xl`
* `h6`
* `body`
* `header`
* `content`
* `title`
* `subtitle`
* `message`
* `summary`
* `tooltip`

The AI should preserve the established typography style when editing an existing screen.

When creating a new screen, prefer the global typography variables and then map them to the semantic text role.

## 10. Border radius

The core radius scale observed in the Aura collection is:

* None: 0
* XS: 2
* SM: 4
* MD: 6
* LG: 8
* XL: 12

Additional component specific radius tokens exist for individual components.

The AI should use the component radius token when a component already defines one.

## 11. Focus system

The global focus ring uses:

* Width: 1
* Color: `#5925DC`
* Offset: 2

Focus should be visible and consistent.

The AI should not remove focus treatment from interactive elements.

A focus treatment should not be replaced by a hover treatment.

## 12. Button system

The file defines semantic button variants with default, hover, active, border, and text behavior.

Observed default colors include:

* `primary`: default #5925DC, hover #6938EF, active #5925DC, text #FFFFFF
* `secondary`: default #F1F5F9, hover #E2E8F0, active #CBD5E1, text #475569
* `info`: default #0EA5E9, hover #0284C7, active #0369A1, text #FFFFFF
* `success`: default #22C55E, hover #16A34A, active #15803D, text #FFFFFF
* `warn`: default #F97316, hover #EA580C, active #C2410C, text #FFFFFF
* `help`: default #7B67EA, hover #6938EF, active #5925DC, text #FFFFFF
* `danger`: default #EF4444, hover #DC2626, active #B91C1C, text #FFFFFF
* `contrast`: default #020617, hover #0F172A, active #1E293B, text #FFFFFF

The button token family also contains:

* Primary
* Secondary
* Info
* Success
* Warning
* Help
* Danger
* Contrast
* Outlined variants
* Text variants
* Rounded variants
* Raised variants
* Icon only variants
* Small and large sizing
* Focus ring tokens
* Label typography tokens

When a button action is primary, use the primary button pattern.

When an action is destructive, use the danger pattern.

Do not use danger styling only to attract attention.

Use secondary, outlined, text, or contrast patterns for supporting actions according to hierarchy.

## 13. Component states

The component pages repeatedly use state patterns including:

* Default
* Hover
* Focus
* Active
* Selected
* Disabled
* Invalid
* Filled
* Highlight
* Expanded
* Collapsed
* Loading
* Completed
* Error
* Success
* Warning
* Small
* Normal
* Large

When a component state is requested, use the existing state variant instead of creating a new visual treatment.

## 14. Form system

The file contains a broad form system.

Observed form patterns include:

* Input text
* Textarea
* Input number
* Input group
* Select
* Multi select
* Auto complete
* Cascade select
* Listbox
* Tree select
* Checkbox
* Radio button
* Toggle switch
* Toggle button
* Slider
* Rating
* Password
* Date picker
* Color picker
* Editor
* File upload
* Float label
* Ifta label

Input examples include:

* Basic
* Placeholder
* Helper text
* Invalid
* Disabled
* Filled
* Focus
* Hover
* Left icon
* Right icon
* Float label

Form labels and helper text should preserve the existing hierarchy.

Validation should use the established semantic status colors and not rely only on color.

## 15. Data display system

The file includes:

* Data table
* Data view
* Order list
* Organization chart
* Paginator
* Pick list
* Timeline
* Tree
* Tree table
* Meter group
* Progress bar
* Progress spinner
* Skeleton

Data table examples explicitly cover:

* Small
* Default
* Large
* Grid lines on
* Grid lines off
* Sortable
* Hover
* Selected
* Striped
* Ascending
* Descending
* Row toggle button
* Image
* Checkbox
* Radio button
* Tag
* Rating
* Text

When creating data heavy interfaces, reuse these patterns instead of designing a new table style.

## 16. Navigation system

Navigation related component pages include:

* Breadcrumb
* Context menu
* Dock
* Menu
* Menubar
* Mega menu
* Panel menu
* Tiered menu
* Toolbar

Navigation should use the established surface, spacing, typography, focus, and selected state tokens.

## 17. Overlay system

Overlay related pages include:

* Confirm dialog
* Confirm popup
* Dialog
* Drawer
* Popover
* Tooltip

The file includes dedicated overlay token families for:

* Border radius
* Background
* Shadow
* Focus
* Title typography
* Content typography
* Close controls

Use the appropriate overlay component based on interaction intent.

Use a dialog for blocking or confirmation workflows.

Use a popover for contextual interaction.

Use a tooltip for short supporting information.

Do not use a tooltip as a substitute for important instructions.

## 18. Feedback system

Feedback related components include:

* Message
* Toast
* Badge
* Tag
* Progress bar
* Progress spinner
* Skeleton

The semantic status vocabulary includes:

* Success
* Info
* Warning
* Danger
* Secondary
* Contrast

Status styling should remain consistent across message, toast, badge, and tag patterns.

## 19. Card and panel system

The file contains:

* Card
* Panel
* Fieldset
* Accordion
* Divider
* Scroll panel
* Splitter
* Stepper
* Tabs
* Toolbar

Cards and panels should use the existing surface hierarchy, border radius, border, spacing, and typography tokens.

Avoid adding heavy shadows to every container.

Use elevation only when the component needs separation from the surface behind it.

## 20. Icon system

The file contains a dedicated `⚡️ Icons` canvas.

It also includes Prime icon usage throughout the component pages and custom icon usage inside the Creative Workspace component page.

Icon behavior should follow these rules:

* Reuse an existing icon when the meaning already exists.
* Preserve the established icon size.
* Keep icon alignment consistent with text.
* Use semantic icon color tokens when available.
* Do not create decorative icons where the component already has an established icon.
* Do not use a different icon family for one state of an existing component.

## 21. Creative Workspace custom system

The `🔷CW Components` page is a product specific layer above the generic component library.

Observed custom symbols include:

* `State=Expanded`
* `State=Collapsed`
* `State=Citation Below`
* `State=CD Icon Expand`
* `State=CD Icon - Collapsed`
* `State=Confirmed`
* `State=Cancelled`
* `State=Scheduled`
* `Type=Expand Chat`
* `Type=Expand Rulebook`
* `Type=Detailed`
* `Type=Summarised`
* `Citation=Detailed`
* `Citation=Summarised`
* `Status=Default`
* `Type=Excel`
* `Type=Stormee`
* `Type=GPT`
* `Type=Video`
* `Type=Web`
* `Type=image`
* `Type=Upload`
* `Type=Codebase`
* `Type=Doc`
* `Type=Meetings`
* `Type=Image`
* `Property 1=AI Output`
* `Property 1=User Input`
* `Type=User`
* `Type=AI`
* `State=Without attachment`
* `State=With attachment`
* `State=attachment expanded`
* `State=Input entered`
* `State=Project Selected`
* `State=Cognitive Search Card`
* `State=On CD icon expand`
* `State=Accordion LSC`
* `type=with stroke, state=open`
* `type=without stroke, state=open`
* `type=with stroke, state=close`
* `type=without stroke, state=close`
* `Type=Critical`
* `Type=Warning`
* `Type=High`
* `State=large expanded`
* `State=large collapsed`
* `State=small expanded`
* `State=Small Collapsed`
* `Property 1=Loading`
* `Property 1=Final Stage`
* `Property 1=Stage 1`
* `State=Completed`
* `State=Completed expanded`
* `State=Stepper expanded`
* `State=Stepper collapsed`

These should be treated as product specific patterns.

## 22. Custom component sizing examples

Observed custom symbol dimensions include:

* Cognitive Decisioning style cards around 596 wide
* Chat and citation layouts around 739 wide
* Chat or rulebook views around 925 wide
* Attachment patterns around 293 wide
* Input patterns around 540 wide
* Search card patterns around 596 wide
* Custom badge and status patterns around 20 to 76 high
* Custom stepper patterns around 191 to 425 wide

Exact dimensions for all custom symbols are available in `creative_workspace_component_catalog.json`.

## 23. Design tokens page

The `🔥 Tokens` page visually organizes the system into:

* Semantic
* Primitive
* Panel
* File
* Overlay
* Misc
* Messages
* Menu
* Media
* Form
* Data
* Button

This organization should be preserved when the AI explains or creates new tokens.

## 24. Color usage rules

The AI should use this semantic order.

* Primary for important interaction and brand emphasis
* Surface for backgrounds and containers
* Gray or surface text tokens for neutral content
* Green or success tokens for successful outcomes
* Red or danger tokens for destructive or invalid outcomes
* Yellow or warning tokens for caution
* Blue or info tokens for informational content
* Purple and primary tokens for product specific AI or important Creative Workspace emphasis when the existing component pattern uses them

Avoid arbitrary color mixing.

Avoid using multiple accent colors for the same semantic purpose.

Avoid using a primitive color directly when a semantic token already exists.

## 25. Spacing rules

The file contains multiple spacing systems, including component specific spacing and a dedicated `Spacing` collection.

The AI should use existing spacing variables and component spacing tokens.

Spacing should be consistent within a component.

A larger gap should communicate a larger hierarchy boundary.

A smaller gap should communicate stronger content grouping.

Do not use random one off spacing values when an existing spacing token is available.

## 26. Layout rules

The file makes heavy use of Figma auto layout patterns.

When implementing layouts:

* Prefer flexible container sizing
* Preserve horizontal and vertical padding
* Preserve item spacing
* Preserve component intrinsic sizing
* Use existing stack behavior
* Keep content alignment consistent
* Avoid absolute positioning unless the source component uses it
* Preserve component minimum and maximum sizing when present
* Keep repeated elements aligned through shared component structure

## 27. Responsive behavior

The component library contains small, normal, and large variants across many components.

The AI should prefer component size variants instead of scaling the whole component arbitrarily.

Responsive changes should preserve hierarchy and interaction behavior.

A component that has a dedicated small variant should use that variant rather than reducing every dimension independently.

## 28. Accessibility rules

The design system includes focus states and disabled states, and the Figma schema contains accessibility related fields.

The AI should:

* Preserve visible keyboard focus
* Preserve disabled state distinction
* Preserve invalid state distinction
* Keep text readable against its background
* Avoid relying only on color for status
* Keep interactive targets visually distinct
* Preserve labels and helper text
* Preserve semantic state communication

## 29. Dark mode

The Aura collection explicitly contains Light and Dark modes.

When a design is requested for Dark mode:

* Keep the same semantic token names
* Change values through the Dark mode token
* Do not manually invert colors
* Do not replace Light mode tokens with unrelated Dark mode colors
* Preserve primary brand identity
* Preserve component hierarchy
* Preserve status meaning

## 30. Shadows and elevation

The Figma file contains more than 6,800 effect records.

The most frequently observed shadow patterns include:

* Drop shadow with zero horizontal offset, one pixel vertical offset, two pixel blur, and five percent dark opacity
* Drop shadow with zero horizontal offset, one pixel vertical offset, five pixel blur, and twelve percent dark opacity
* Drop shadow with zero horizontal offset, two pixel vertical offset, two pixel blur, and fourteen percent dark opacity
* Drop shadow with zero horizontal offset, three pixel vertical offset, one pixel blur, negative two pixel spread, and twenty percent dark opacity
* Larger elevation patterns using 4 by 6 and 12 by 16 style offsets and blur values
* Focus style shadows using semantic primary or error colors

Use shadows to communicate elevation or focus.

Do not add a shadow simply because a container is a card.

## 31. Component selection rules

When the user asks for a UI element, map the request to the closest existing component.

Examples:

* Text input request → InputText
* Multiselect request → MultiSelect
* Search suggestion request → AutoComplete
* Date selection request → DatePicker
* Confirmation request → ConfirmDialog or ConfirmPopup
* Contextual action request → Popover
* Short explanatory hint → Tooltip
* Navigation path → Breadcrumb
* Large dataset → DataTable
* Tabbed content → Tabs
* Collapsible content → Accordion
* Side workflow → Drawer
* Temporary feedback → Toast
* Persistent feedback → Message
* Status label → Tag or Badge
* Progress state → ProgressBar or ProgressSpinner
* Loading placeholder → Skeleton

Use the custom Creative Workspace component when the requested interaction matches an existing custom pattern.

## 32. AI generation rules

Before generating UI, the AI should identify:

1. The requested interaction
2. The closest existing component
3. The required component variant
4. The semantic color
5. The typography role
6. The spacing relationship
7. The state
8. The Light or Dark mode
9. The accessibility state
10. Whether a custom Creative Workspace pattern exists

The AI should then build the UI from those decisions.

## 33. Rules for modifying existing screens

When modifying an existing screen:

* Preserve the existing component family
* Preserve existing typography
* Preserve existing color hierarchy
* Preserve spacing relationships
* Preserve interaction states
* Preserve component dimensions unless the requirement explicitly changes them
* Preserve existing icons
* Preserve the existing visual density
* Reuse existing variants
* Avoid introducing a second visual language

## 34. Rules for new components

A new component should be created only when no existing component or custom pattern satisfies the requirement.

A new component should define:

* Purpose
* Anatomy
* Variants
* States
* Sizes
* Typography
* Colors
* Border
* Radius
* Spacing
* Icon behavior
* Focus behavior
* Disabled behavior
* Error behavior
* Responsive behavior

The new component should reuse existing primitive and semantic tokens.

## 35. Rules for token creation

If a new token is required:

* First search for an existing semantic token
* Then search for an existing primitive token
* Then search the component token family
* Reuse an existing token whenever possible
* Create a new semantic token only when the meaning is genuinely new
* Keep naming consistent with the existing slash based naming system
* Avoid creating duplicate values with different names unless they have different semantic meanings

## 36. Token naming convention

The file heavily uses slash based hierarchical names.

Examples:

* `primary/color`
* `primary/hover/color`
* `button/primary/background`
* `button/primary/hover/background`
* `surface/50`
* `surface/text/gray/normal`
* `border/radius/md`
* `focus/ring/color`
* `inputtext/border/radius`
* `message/error/shadow`

When adding new tokens, follow the same hierarchy.

## 37. Existing external token references

The file contains variables whose values are references to external variable assets.

These are preserved in the machine readable token file.

The AI should not treat an unresolved external reference as permission to invent a replacement value.

If an external value is unavailable, use the nearest locally available semantic token and explicitly preserve the token name when implementation requires it.

## 38. Source precedence recommendation

The file contains several token collections and component layers.

For AI generation, use this practical precedence:

1. Existing custom Creative Workspace component
2. Aura component token
3. Aura semantic token
4. Aura primitive token
5. Tokens collection
6. BPA Colours or other project specific supplemental token
7. External asset reference
8. New token only when necessary

This precedence is a design usage recommendation based on the structure observed in the file. It is not presented as an explicit Figma governance rule.

## 39. What the AI should never do

The AI should never:

* Invent a new purple when the primary purple system already exists
* Replace Inter with another font without a requirement
* Create a new button style when an existing button variant works
* Use arbitrary border radius values when a radius token exists
* Remove focus treatment
* Use a random shadow on every container
* Mix unrelated color systems without a clear semantic reason
* Create a new status color for an existing status
* Use a tooltip for important information that needs to remain visible
* Create custom input styling when InputText or another form component exists
* Change component state styling independently from the component system
* Ignore Dark mode tokens when a Dark mode design is requested
* Use a component from another product area when a Creative Workspace custom component already exists

## 40. Implementation guidance

For HTML prototypes:

* Use CSS variables named after semantic tokens
* Keep CSS variables centralized
* Build components from the same semantic variables
* Keep state styles together
* Use the exact token values from the JSON source
* Keep JavaScript behavior separate from visual token definitions
* Avoid hard coded visual values when a token exists

For React or frontend implementation:

* Map Figma token names to the project token layer
* Map component variants to Figma component properties
* Preserve semantic state names
* Preserve Light and Dark modes
* Avoid creating component specific values outside the token layer

## 41. Knowledge source files

Use the following files together.

`creative_workspace_global_ai_design_system.md`

This is the AI reasoning and usage layer.

`creative_workspace_design_tokens.json`

This is the machine readable token layer containing 3,853 variables and their mode values, aliases, collections, and resolution chains.

`creative_workspace_component_catalog.json`

This contains the 81 Prime component pages, their sections, symbol variants, observed dimensions, and the 85 custom Creative Workspace symbols.

`creative_workspace_node_inventory.json`

This is the detailed audit layer containing the extracted node properties for the design file.

## 42. AI instruction block

The following instruction can be placed directly before a future design requirement:

```text
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
```

## 43. Final design system summary

The Figma file represents a mature component driven system with a large Prime based component library, an Aura semantic token layer, extensive primitive color scales, Light and Dark modes, and a separate Creative Workspace product layer.

The most important visual anchors are:

* Inter typography
* Primary purple `#5925DC`
* Purple semantic scale
* Surface based backgrounds
* Compact radius scale from 0 to 12
* Visible purple focus treatment
* Semantic component states
* Reusable Prime component patterns
* Product specific Creative Workspace components
* Token driven Light and Dark modes

The AI should preserve these relationships rather than copying isolated visual values.

The complete machine readable data is provided in the companion JSON files.
