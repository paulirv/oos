# Requirements System

This directory tracks requirements and solutions for this project.

## Structure

```
requirements/
├── README.md                    # This file
├── REQUIREMENTS-INDEX.md        # Index of all requirements (auto-generated)
├── requirements/                # Requirement specifications
│   └── REQ-0001-example.md
├── solutions/                   # Solution proposals
│   └── SOL-0001-example.md
└── templates/                   # Document templates (symlinked)
```

## Prerequisite

Requirements are derived from the **Product Specification**. Create the spec first:

```bash
/spec vision    # Optional - project vision
/spec create    # Required - product specification with capabilities
/spec approve   # Approve before creating requirements
```

## Commands

- `/requirement propose` - Propose a candidate requirement (needs approval)
- `/requirement approve REQ-NNNN` - Approve requirement for implementation
- `/requirement reject REQ-NNNN` - Reject a candidate requirement
- `/requirement create REQ-NNNN` - Add detailed specification to approved requirement
- `/requirement list` - List all requirements by status
- `/requirement view REQ-NNNN` - View a specific requirement
- `/requirement update-ac REQ-NNNN AC-NN complete` - Update acceptance criteria
- `/solution create` - Create a solution proposal

## Requirement Lifecycle

```
candidate ──► approved ──► draft ──► active ──► implemented ──► completed
    │             │
    └── rejected  └── deprecated
```

## Workflow

1. **Spec First** - Create and approve product specification
2. **Propose** - Use `/requirement propose` to create candidates from capabilities
3. **Approve** - Review and approve requirements for implementation
4. **Specify** - Add detailed acceptance criteria
5. **Design** - Use `/solution create` to propose approaches
6. **Track** - Update acceptance criteria as work progresses
7. **Complete** - Mark requirements done when all criteria verified
