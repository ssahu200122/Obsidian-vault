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
let content = await tp.system.prompt('Solution Content (New line -> Shift + Enter):', '', true, true);

content = content.split('\n').map(line => `>> ${line}`).join('\n');  // Indent solution content

// Force custom_question to have its own formatting
if (type === 'custom_question') {
   tR += `> [!question]$- \n`;  
   tR += `> #question\n> ![[Pasted image 20250306225048.png]]\n`;
   tR += `>> [!done] Solution\n${content}`;
} else {
   tR += `> [!${type}]${fold} question\n${content}`;
}

-%>
