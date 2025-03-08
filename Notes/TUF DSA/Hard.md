# dklsjf

- [ ] **Overall Done** <!-- This gets checked when all sub-checkboxes are checked -->
  - [x] Article ✅ 2025-03-08
  - [x] YouTube ✅ 2025-03-08
  - [x] Note ✅ 2025-03-08

```dataviewjs
const overall = dv.container.querySelector("ul > li:first-child input");
const subCheckboxes = dv.container.querySelectorAll("ul > li > ul > li input");

function updateOverall() {
    overall.checked = [...subCheckboxes].every(cb => cb.checked);
}

subCheckboxes.forEach(cb => cb.addEventListener("change", updateOverall));
```

