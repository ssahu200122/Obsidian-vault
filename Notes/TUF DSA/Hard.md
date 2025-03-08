# dlkalf

- [ ] **Overall Done**
  - [x] Article ✅ 2025-03-08
  - [x] YouTube ✅ 2025-03-08
  - [x] Note ✅ 2025-03-08

```js
document.addEventListener("DOMContentLoaded", () => {
    const checkboxes = document.querySelectorAll("input[type='checkbox']");
    
    function updateOverall() {
        const overallCheckbox = checkboxes[0]; // First checkbox is "Overall Done"
        const subCheckboxes = Array.from(checkboxes).slice(1); // Rest are sub-tasks

        overallCheckbox.checked = subCheckboxes.every(cb => cb.checked);
    }

    checkboxes.forEach(cb => cb.addEventListener("change", updateOverall));
});
```

