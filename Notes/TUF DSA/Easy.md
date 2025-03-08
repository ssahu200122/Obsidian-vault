# Largest Element  in an Array


- [ ] Overall Done
  - [ ] [Article](https://takeuforward.org/data-structure/find-the-largest-element-in-an-array/)
  - [ ] [Youtube](https://youtu.be/37E9ckMDdTk)
  - [ ] [Practice](https://bit.ly/3Pld280) 
  - [ ] Note
  - [ ] Revision
<%*
const heading = await tp.system.prompt("Enter heading:");

tR += `# ${heading}

- [ ] **Overall Done** <!-- Auto-checked if all sub-tasks are done -->
  - [ ] Article  
  - [ ] YouTube  
  - [ ] Note  

\`\`\`dataviewjs
const overall = dv.el("input", "", { type: "checkbox", disabled: true });
const checkboxes = dv.current().querySelectorAll("li input[type=checkbox]");

function updateOverall() {
    const allChecked = [...checkboxes].slice(1).every(cb => cb.checked);
    overall.checked = allChecked;
}

checkboxes.forEach(cb => cb.addEventListener("change", updateOverall));
\`\`\`
`;
%>


