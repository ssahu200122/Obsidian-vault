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
const title = await tp.system.prompt('Title:', '', true);
let content = await tp.system.prompt('Solution Content (New line -> Shift + Enter):', '', true, true);

content = content.split('\n').map(line => `>> ${line}`).join('\n');  // Indent solution content

let calloutHead = `> [!${type}]${fold} ${title}\n`;

// Special handling for "custom_question" callout
if (type === 'custom_question') {
   calloutHead += `> #question\n> ![[Pasted image 20250306225048.png]]\n`;
   content = `>> [!done] Solution\n${content}`;
}

tR += calloutHead + content;

-%>
