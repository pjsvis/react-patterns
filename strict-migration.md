# strict null checks

## vscode 2019 

- [Blog Post](https://code.visualstudio.com/blogs/2019/05/23/strict-null)
- VSCode team strictNullChecks => `...allow us to both move faster and to ship a more stable product...`
- `a plan that would incrementally bring the benefits of strict null checking to all engineers on the team, starting right away`

### process

- create a new TypeScript project file called tsconfig.strictNullChecks.json 
- enable strict null checking and initially consists of zero files. 
- selectively add individual files to this project, fix the strict null errors in those files, and then check in the change. 
- As long as we added files that either had no imports or only imported other already strict null checked files, we only had to fix a small number of errors each iteration.
- add a CI step that compiled tsconfig.strictNullChecks.json to ensure that checkins that regressed strict null checking would break the build.

## figma 2020

- [Blog Post](https://www.figma.com/blog/inside-figma-a-case-study-on-strict-null-checks/) describing process and utility scripts
- script to produce acyclic tree of files and dependencies ![](https://cdn.sanity.io/images/599r6htc/production/5015e3af4761ded281ce47e4b267dce52e97580c-2204x1121.png?w=670&q=75&fit=max&auto=format&dpr=2)
- dependency graph visualiser ![](https://cdn.sanity.io/images/599r6htc/production/b66935925d2d13b88f1deb31f09eeb56e9a10dff-2048x1226.png?w=670&q=75&fit=max&auto=format&dpr=2)
- problems with [barrel imports](https://basarat.gitbook.io/typescript/main-1/barrel) `...simplest both for the migration and the codebase simply to remove them...`
- problems with dependency cycles => `treat each cycle as a strongly-connected component, which effectively becomes a single node in the dependency graph.`
- ![](https://cdn.sanity.io/images/599r6htc/production/3aafbec1d7b9ab24c6775cb94f637e34c63fb947-1608x1054.png?w=670&q=75&fit=max&auto=format&dpr=2)
- `... initial phase of “scouting out” the landscape — setting up tooling and removing blockers like cycles...`
- `...establish guidance around how much effort to spend migrating each individual file....`
- `...the biggest benefit, though hard to measure, is probably the increased readability of our code...`
- [figma repo](https://github.com/figma/strict-null-check-migration-tools)
- [qerko mod to figma scripts](https://github.com/qerko/strict-null-check-migration-tools)
- [migration techniques](https://dev.to/viridia/typescript-strictnullchecks-a-migration-guide-3glo)

## other options

- [betterer](https://dev.to/phenomnominal/stricter-typescript-compilation-with-betterer-dp7) with VSCode extension
- [strict mode plugin](https://github.com/allegro/typescript-strict-plugin) that allows turning on strict mode in specific files or directories.
