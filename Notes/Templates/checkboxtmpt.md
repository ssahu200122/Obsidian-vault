<%*
const heading = await tp.system.prompt("Enter heading:");

tR += `# ${heading}

### ✅ Overall Progress  
- [ ] **Overall Done** (Automatically checked when all sub-tasks are done)

### 📝 Subtasks
- [ ] Article
- [ ] YouTube
- [ ] Note

### 🔍 Progress Tracker (Auto-updates)
\`\`\`tasks
not done
description includes Article or YouTube or Note
\`\`\`
`;
%>
