---
tags: [typescript]
title: typescript-pick
created: '2019-08-03T09:49:47.574Z'
modified: '2019-08-03T09:55:57.969Z'
---

# typescript-pick

If we have a type sat.Report and we want a partial type of some of Report for form data entry we can use Pick to create it

```
type FormValues = Pick<
  sat.Report,
  | 'executiveSummary'
  | 'assumptions'
  | 'recommendations'
  | 'approach'
  | 'projectDescription'
>;
```

- Ref: https://medium.com/@curtistatewilkinson/typescript-2-1-and-the-power-of-pick-ff433f1e6fb

```
$TsFixMe = any;
```
