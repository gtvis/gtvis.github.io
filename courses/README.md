# Adding a course

- Step 1. Create a new `*.md` in `_courses` with a unique name (e.g., CS7450.md where CS7450 is the official course code).
- Step 2. Copy the below template and fill it in. Note: Leave not applicable fields blank.

```md
---
name: Information Visualization
code: CS 7450
level: Graduate | Undergraduate
tags: 
  - Spring | Fall | Summer
  - ...
next_offering: Spring 2022
offerings:
    - year: 2020
      semester: Fall
      instructors:
        - Alex Endert
        - ...
      link: http://va.gatech.edu/courses/cs7450/
    - year: ...
      semester: ...
      instructors:
        - ...
      link: ...
---

This course analyses spatial networks of flights, commuters, migrants, remittances, travel/transportation, social communities, telecommunications, and social media. GIS, statistics and visualization techniques are used to analyze node properties, diffusion, communities and network configurations.
```

- `tags` corresponds to the semesters a course is _generally_ offered.
- Please send a Pull Request with the changes and an admin will merge it.