<%*
const heading = await tp.system.prompt("Enter heading:");

tR += `# ${heading}

- [ ] **Overall Done** <!-- This gets checked when all sub-checkboxes are checked -->
  - [ ] Article  
  - [ ] YouTube  
  - [ ] Note  

`;
%>
