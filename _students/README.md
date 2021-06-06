# Adding a student

- Step 1. Create a new `*.md` in `_students` with a unique name (alias).
- Step 2. Copy the below template and fill it in. Note: Leave not applicable fields blank.

```md
---
alias: same as filename
name: ...
lab: VA Lab | Polo Club of Data Science | Information Interfaces Group | Friendly Cities Lab | EntSci Lab | James Foley's Group
degree_level: PhD | BS | MS | PostDoc
major: CS | HCC | CSE | ML | CRP | IsYE | HCI | (add new acronym if required)
graduation_year: YYYY
graduation_semester: Spring | Summer | Fall
role: Scientist, ABC Software
research_interests: 
    - Natural Interaction
    - ...
faculty_advisor:
    - John Stasko | Alex Endert | Polo Chau | Clio Andris | Rahul Basole | James Foley
    - ...
image: /assets/images/people/....png
website: ...
email: ...
linkedin: 
twitter: 
---
```

To mark a person as an alumnus:
- Add `graduation_year: YYYY`, e.g., 2020
- Add `graduation_semester: Spring | Summer | Fall`, e.g., Fall
- Add `role: ...` to display the alumnus' role after graduation, e.g., "Scientist, ABC"

Note:
- Add images to the [assets](/assets/images/students) directory and reference their paths accordingly.
- Please send a Pull Request with the changes and an admin will merge it.