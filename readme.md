# "Hakuna Matata" 🙏
> ## 🚀 All about YAML

### Overview
YAML - A complete course for developers covers YAML fundamentals, practical syntax, advanced features like anchors and tags, and best practices for using YAML in development workflows.

📝Basics of YAML Syntax
- File extension: .yaml or .yml.
- Human-readable structure: uses indentation (spaces only) to denote nesting; no tabs.
- Key value pairs: key: value for simple mappings; values can be strings, numbers, booleans, null, sequences, or nested mappings.
- Comments: start with # and run to the line end; useful for documentation inside YAML files. No multi-line comment present.
- Indentation is very important and most important (2 spaces: in my case Tab intentation is saved for 2 space and most Tab takes 4 space, so use as per the config)

🫀Core Data Types and Representations
- Scalars: plain strings, quoted strings ("..." or '...'), numbers, booleans (true/false), and null (null or ~).
- Sequences (lists): dash - at same indent level for each item. Example:
- languages:
- - Python
- - JavaScript.
- Mappings (objects/dictionaries): parent: followed by indented child: value lines for nested structures.
- Multi-line strings: block style | preserves newlines; folded style > folds newlines into spaces for wrapped paragraphs.

🧩Advanced Features
- Anchors and Aliases: define reusable content with &anchorName and reuse with *anchorName to avoid duplication and keep templates DRY.
- Merges: use <<: *alias to merge mappings from aliases into a mapping.
- Tags and Types: explicit type tags (e.g., !!str, !!int) allow forcing or clarifying types when needed.
- Custom tags: supported for application-specific typed nodes; handled by YAML processors in code.

🤝Common Usage Patterns
- Configuration files: hierarchical configs for apps, CI, Kubernetes manifests, and more; maps and sequences model settings and lists respectively.
- Templates and DRY configs: use anchors/aliases to share repeated configuration across environments or services.
- Combining YAML with tools: be mindful that tools (Kubernetes, CI systems) may require specific quoting or types for values like booleans and numbers.

💎Best Practices and Pitfalls
- Always use spaces for indentation; avoid tabs to prevent parsing errors.
- Prefer explicit quoting when values could be interpreted as non-string (like yes, no, on, off, or numeric-looking strings) to avoid accidental type coercion.
- Keep files small and modular: split large configs into multiple files or templates and reuse anchors where helpful.
- Validate YAML before use with linters or validators to catch syntax and type issues early.
- Be careful with multi-line scalars: choose | vs > depending on whether you need preserved newlines or folded paragraphs.

👉Short Examples
- Mapping: languages:
  frontend: React
  backend: Node.js.
- Sequence: services:
  - api
  - worker
  - scheduler.
- Anchor and Alias: default: &def
  retries: 3
serviceA:
  <<: *def
  name: serviceA.



