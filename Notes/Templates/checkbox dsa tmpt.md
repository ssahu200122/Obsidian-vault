<%*
const heading = await tp.system.prompt("Enter heading:");

tR += `# ${heading}

- [ ] **Overall Done** <!-- This gets checked when all sub-checkboxes are checked -->
  - [ ] Article  
  - [ ] YouTube  
  - [ ] Note  

\`\`\`dataviewjs
const overall = dv.container.querySelector("ul > li:first-child input");
const subCheckboxes = dv.container.querySelectorAll("ul > li > ul > li input");

function updateOverall() {
    overall.checked = [...subCheckboxes].every(cb => cb.checked);
}

subCheckboxes.forEach(cb => cb.addEventListener("change", updateOverall));
\`\`\`
`;
%>
