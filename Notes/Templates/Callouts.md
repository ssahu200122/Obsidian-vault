<%*

const callouts = {
   note:     '🔵 ✏ Note',
   info:     '🔵 ℹ Info',
   todo:     '🔵 🔳 Todo',
   tip:      '🌐 🔥 Tip / Hint / Important',
   abstract: '🌐 📋 Abstract / Summary / TLDR',
   question: '🟡 ❓ Question / Help / FAQ',
   custom_question: '🟡 📝 Custom Question',
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

// Generate the main callout
tR += `> [!${type}]${fold} ${type === 'custom_question' ? 'question' : ''}\n`;

// If "custom_question" is selected, prompt for question content
if (type === 'custom_question') {
   let questionContent = await tp.system.prompt('Enter Question Content:', '', true, true);
   questionContent = questionContent.split('\n').map(line => `> ${line}`).join('\n');  // Proper formatting
   tR += `> #question\n${questionContent}\n\n`;
}

// Always prompt for solution content
let solutionContent = await tp.system.prompt('Enter Solution Content:', '', true, true);

// Insert solution only for "custom_question"
if (type === 'custom_question') {
   tR += `>> [!done] Solution\n>> \`\`\`\n${solutionContent}\n>> \`\`\``;
} else {
   // For other callouts, insert solution as normal text
   tR += `> ${solutionContent}`;
}

-%>
