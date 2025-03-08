<%*
const heading = await tp.system.prompt("Enter heading:");

tR += `# ${heading}

- [ ] **Overall Done**
  - [ ] Article
  - [ ] YouTube
  - [ ] Note

\`\`\`dataviewjs
const overallCheckbox = dv.el("input", "", { type: "checkbox", class: "overall-checkbox" });
const subCheckboxes = [
    dv.el("input", "", { type: "checkbox", class: "sub-checkbox" }),
    dv.el("input", "", { type: "checkbox", class: "sub-checkbox" }),
    dv.el("input", "", { type: "checkbox", class: "sub-checkbox" })
];

subCheckboxes.forEach(cb => cb.addEventListener("change", () => {
    overallCheckbox.checked = subCheckboxes.every(cb => cb.checked);
}));
\`\`\`
`;
%>
