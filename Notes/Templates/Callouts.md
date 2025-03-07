<%*

const callouts = {
   note:     '🔵 ✏ Note',
   info:     '🔵 ℹ Info',
   todo:     '🔵 🔳 Todo',
   tip:      '🌐 🔥 Tip / Hint / Important',
   abstract: '🌐 📋 Abstract / Summary / TLDR',
   question: '🟡 ❓ Question / Help / FAQ',
   custom_question: '🟡 📝 Custom Question',  // Custom Question Type
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

// Ask for question content **only if** 'question' or 'custom_question' is selected
let questionContent = '';
if (type === 'question' || type === 'custom_question') {
   questionContent = await tp.system.prompt('Enter Question Content (New line -> Shift + Enter):', '', true, true);
   questionContent = questionContent.split('\n').map(line => `> ${line}`).join('\n');
}

// Always ask for solution content
let solutionContent = await tp.system.prompt('Enter Solution Content (New line -> Shift + Enter):', '', true, true);
solutionContent = solutionContent.split('\n').map(line => `> ${line}`).join('\n');

// Generate the main callout
tR += `> [!${type}]${fold}${type === 'question' || type === 'custom_question' ? ' question' : ''}\n`;

// Add question content only if it's a question-type callout
if (questionContent) {
   tR += `> #question\n${questionContent}\n`;
}

// If it's a question-type callout, **nest the solution inside a `[!done] Solution` callout**
if (type === 'question' || type === 'custom_question') {
   tR += `>> [!done] Solution\n>> \`\`\`\n${solutionContent}\n>> \`\`\``;
} else {
   // If it's NOT a question, just insert the solution normally
   tR += `> \`\`\`\n${solutionContent}\n> \`\`\``;
}

-%>
