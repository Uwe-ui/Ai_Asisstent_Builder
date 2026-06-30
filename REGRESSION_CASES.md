# PROMPT_CONTRACTS

## Rule
All AI outputs must be structured and schema-validated.
No free-form prose is accepted as a final system artifact.

## Contract 1: RouterOutput
### Purpose
Classify the incoming request.

### Required fields
- `workflowType`
- `confidence`
- `reason`

### Allowed values for `workflowType`
- `create_page`
- `revise_section`
- `rewrite_copy`
- `change_style`
- `explain_failure`

## Contract 2: PageBrief
### Purpose
Convert user intent into a structured planning brief.

### Required fields
- `pageType`
- `audience`
- `tone`
- `goals`
- `requiredSections`
- `constraints`

## Contract 3: PageSpec
### Purpose
Represent the canonical page structure.

### Required top-level fields
- `pageId`
- `version`
- `pageType`
- `theme`
- `sections`

### Required fields for every section
- `id`
- `type`
- `props`

## Contract 4: SectionPatch
### Purpose
Apply a targeted revision without changing unrelated sections.

### Required fields
- `targetSectionId`
- `changeType`
- `changedFields`
- `reason`

## Contract 5: ValidationResult
### Required fields
- `passed`
- `errors`
- `warnings`
- `nextAction`

## Prompt discipline rules
- Prompts must refer to allowed components only.
- Prompts must specify what may change and what must remain unchanged.
- Prompts must ask for structured output only.
- Prompts must stay compact and avoid repeating full history.
