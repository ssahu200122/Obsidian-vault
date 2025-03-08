<%*
const heading = await tp.system.prompt("Enter heading?");

tR += `# ${heading}

- [ ] **Overall Done**
  - [ ] Article
  - [ ] YouTube
  - [ ] Note

\`\`\`js
document.addEventListener("DOMContentLoaded", () => {
    const checkboxes = document.querySelectorAll("input[type='checkbox']");
    
    function updateOverall() {
        const overallCheckbox = checkboxes[0]; // First checkbox is "Overall Done"
        const subCheckboxes = Array.from(checkboxes).slice(1); // Rest are sub-tasks

        overallCheckbox.checked = subCheckboxes.every(cb => cb.checked);
    }

    checkboxes.forEach(cb => cb.addEventListener("change", updateOverall));
});
\`\`\`
`;
%>

