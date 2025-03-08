<%*
const heading = await tp.system.prompt("Enter heading:");
const selectedCallout = await tp.system.suggester(Object.values(callouts), Object.keys(callouts), true, 'Select callout type.');
tR += `# ${heading}

- [ ] **Overall Done** <!-- This gets checked when all sub-checkboxes are checked -->
  - [ ] Article  
  - [ ] YouTube  
  - [ ] Note  

`;
%>
