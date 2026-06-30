# COMPONENT_CATALOG

## V1 page type
Portfolio onepager

## Approved component policy
The AI may only compose from approved components.
It may not invent new component types in V1.

## Component 1: Hero
### Required props
- `headline`
- `subheadline`
- `primaryCtaLabel`
- `primaryCtaHref`

### Optional props
- `eyebrow`
- `secondaryCtaLabel`
- `secondaryCtaHref`
- `profileImage`

### Constraints
- headline should be concise
- must clearly identify the person / role / value

## Component 2: About
### Required props
- `title`
- `body`

### Optional props
- `highlights`
- `profileFacts`

### Constraints
- body should explain background, focus, and style of work

## Component 3: Projects
### Required props
- `title`
- `items`

### Each project item requires
- `projectTitle`
- `summary`

### Optional project item props
- `impact`
- `tags`
- `link`

### Constraints
- portfolio pages should normally include Projects
- if omitted, the system must record an explicit reason

## Component 4: SkillsServices
### Required props
- `title`
- `items`

### Constraints
- represent either skills or services, not an uncontrolled mix

## Component 5: TestimonialsProof
### Required props
- `title`
- `items`

### Each proof item requires at least one of
- `quote`
- `metric`
- `clientName`
- `proofLabel`

## Component 6: ContactCTA
### Required props
- `title`
- `ctaLabel`
- `ctaHref`

### Optional props
- `email`
- `socialLinks`
- `availabilityNote`

## Mandatory structure recommendation
Recommended order:
1. Hero
2. About
3. Projects
4. SkillsServices
5. TestimonialsProof
6. ContactCTA

## Render safety rule
If a section lacks required props, the entire output fails validation.
