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

// Ask user to select callout type
const type = await tp.system.suggester(Object.values(callouts), Object.keys(callouts), true, 'Select callout type.');
const fold = await tp.system.suggester(['None', 'Expanded', 'Collapsed'], ['', '+', '-'], true, 'Select callout fold option.');

// Ask for question content if the selected type is 'question' or 'custom_question'
let questionContent = '';
if (type === 'question' || type === 'custom_question') {
   questionContent = await tp.system.prompt('Enter Question Content (New line -> Shift + Enter):', '', true, true);
   questionContent = questionContent.split('\n').map(line => `> ${line}`).join('\n');
}

// Always ask for solution content
let solutionContent = await tp.system.prompt('Enter Solution Content (New line -> Shift + Enter):', '', true, true);
solutionContent = solutionContent.split('\n').map(line => `>> ${line}`).join('\n');
solutionContent = `>> [!done] Solution\n>> \`\`\`\n${solutionContent}\n>> \`\`\``;

// Generate the final callout
tR += `> [!${type}]${fold} ${type === 'question' || type === 'custom_question' ? 'question' : ''}\n`;

if (questionContent) {
   tR += `> #question\n${questionContent}\n`;
}

tR += `${solutionContent}`;

-%>
