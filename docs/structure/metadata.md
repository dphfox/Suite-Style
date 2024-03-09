```Lua
--!strict
-- By Fusion, licensed under MIT
```

## Luau directives

These always start on line 1, and are never mixed in with other content or empty
lines.

### Type checking level

- This is always on line 1, and is `--!strict` at all times. 
- Do not downgrade to `--!nonstrict` or `--!nocheck`. 
	- Prefer local remedies to type checking problems, explicitly casting to
	`any` where appropriate.

### Native code generation

- This can be enabled at the author's discretion.
- Always benchmark to see whether native code generation is effective.
	- Native code generation may be unavailable on some platforms.
	- Native code generation may be more effective on workloads with a greater
	proportion of time spent on computation.

### Disabling lints

- Prefer fixing linted issues to disabling lints.
- Prefer officially-supported Luau directives where they are available, instead
of lints from external software like Selene.
	- This assumes that external software obeys official Luau directives.
- It is typical to disable the `LocalShadow` lint when these use cases arise:
	- Shadowing variables to cast them to a different type
	- Blocking or redirecting access to upvalues that would otherwise pose a
	hazard.
- It is typical to disable the `LocalUnused` lint when using DSL-like libraries
that import a large number of top-level members.

## License information

- Keep this to an absolute minimum. One line is enough.
- Ensure every file indicates which license is used, and where the code comes
from.
	- Attribute to the project or entity, not the individual.
- Use simple language.
	- For open source licenses, prefer:
	> `By Author, licensed under License`
	- For copyrighted work, prefer:
	> `(c) Author Year. All rights reserved, seek permission before use.`
	- In all other cases, ensure it's clear where the full terms can be viewed,
	and ensure important limitations on usage are clear.