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

const type = await tp.system.suggester(Object.values(callouts), Object.keys(callouts), true, 'Select callout type.');
const fold = await tp.system.suggester(['None', 'Expanded', 'Collapsed'], ['', '+', '-'], true, 'Select callout fold option.');

let questionContent = "";
let solutionContent = await tp.system.prompt('Solution Content (New line -> Shift + Enter):', '', true, true);

// If user selects "custom_question", ask for question content too
if (type === 'custom_question') {
   questionContent = await tp.system.prompt('Question Content (New line -> Shift + Enter):', '', true, true);
}

// Format question content (add `> ` at the beginning of each line)
questionContent = questionContent.split('\n').map(line => `> ${line}`).join('\n');

// Wrap solution content inside a code block
solutionContent = `>> [!done] Solution\n>> \`\`\`\n${solutionContent}\n>> \`\`\``;

// Force custom_question to have its own formatting
if (type === 'custom_question') {
   tR += `> [!custom_question]${fold} question\n`;  
   tR += `> #question\n${questionContent}\n`;
   tR += `${solutionContent}`;
} else {
   tR += `> [!${type}]${fold} question\n${solutionContent}`;
}

-%>
