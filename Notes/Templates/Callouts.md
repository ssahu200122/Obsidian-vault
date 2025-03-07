<%*

const callouts = {
   note:     '🔵 ✏ Note',
   info:     '🔵 ℹ Info',
   todo:     '🔵 🔳 Todo',
   tip:      '🌐 🔥 Tip / Hint / Important',
   abstract: '🌐 📋 Abstract / Summary / TLDR',
   question: '🟡 ❓ Question / Help / FAQ',
   custom_question: '🟡 📝 Custom Question',  // New custom callout
   quote:    '🔘 💬 Quote / Cite',
   example:  '🟣 📑 Example',
   success:  '🟢 ✔ Success / Check / Done',
   warning:  '🟠 ⚠ Warning / Caution / Attention',
   failure:  '🔴 ❌ Failure / Fail / Missing',
   danger:   '🔴 ⚡ Danger / Error',
   bug:      '🔴 🐞 Bug',
};

// Question popup first
let questionContent = await tp.system.prompt('Enter Question Content (New line -> Shift + Enter):', '', true, true);

// Solution popup second
let solutionContent = await tp.system.prompt('Enter Solution Content (New line -> Shift + Enter):', '', true, true);

// Format question content
questionContent = questionContent.split('\n').map(line => `> ${line}`).join('\n');

// Ensure the solution content is properly formatted inside `[!done] Solution]`
solutionContent = solutionContent.split('\n').map(line => `>> ${line}`).join('\n');
solutionContent = `>> [!done] Solution\n>> \`\`\`\n${solutionContent}\n>> \`\`\``;

// Generate the final callout
tR += `> [!question]- \n`;
tR += `> #question\n${questionContent}\n`;
tR += `${solutionContent}`;

-%>
