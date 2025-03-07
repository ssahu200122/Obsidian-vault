<%*
const callouts = {
  note: '🔵 ✏ Note', 
  info: '🔵 ℹ Info',
  todo: '🔵 🔳 Todo', 
  tip: '🌐 🔥 Tip / Hint / Important', 
  abstract: '🌐 📋 Abstract / Summary / TLDR', 
  question: '🟡 ❓ `Question` / Help / FAQ', 
  custom_question: '🟡 ❓ Custom Question (with solution code)',
  quote: '🔘 💬 Quote / Cite', 
  example: '🟣 📑 Example', 
  success: '🟢 ✔ Success / Check / Done', 
  warning: '🟠 ⚠ Warning / Caution / Attention', 
  failure: '🔴 ❌ Failure / Fail / Missing', 
  danger: '🔴 ⚡ Danger / Error', 
  bug: '🔴 🐞 Bug'
};

const selectedCallout = await tp.system.suggester(Object.values(callouts), Object.keys(callouts), true, 'Select callout type.');
const fold = await tp.system.suggester(['None', 'Expanded', 'Collapsed'], ['', '+', '-'], true, 'Select callout fold option.');
const title = await tp.system.prompt('Title:', '', true);

// Use "question" in the header if "custom_question" is selected.
const headerType = selectedCallout === "custom_question" ? "question" : selectedCallout;
const calloutHead = `> [!${headerType}]${fold} ${title}\n#question\n`;

if (selectedCallout === "custom_question") {
    // Custom question callout with dynamic question content, optional image, and solution content as code.
    const questionContent = await tp.system.prompt("Enter the QUESTION content (new line → Shift+Enter):", "", true, true);
    const imagePath = await tp.system.prompt("Enter the image file name (or leave blank):", "", false);
    const solutionContent = await tp.system.prompt("Enter the SOLUTION content (as code, new line → Shift+Enter):", "", true, true);

    let content = "";
    if (imagePath && imagePath.trim() !== "") {
        content += `> ![[${imagePath.trim()}]]\n`;
    }
    if (questionContent) {
        content += questionContent.split('\n').map(line => `> ${line}`).join('\n') + "\n";
    }
    content += ">> [!done] Solution\n";
    content += ">> ```\n";
    if (solutionContent) {
        content += solutionContent.split('\n').map(line => `>> ${line}`).join('\n') + "\n";
    }
    content += ">> ```\n";

    tR += calloutHead + content;
} else if (selectedCallout === "question") {
    // Regular question callout prompts for question content only.
    const questionContent = await tp.system.prompt("Enter the QUESTION content (new line → Shift+Enter):", "", true, true);
    let content = "";
    if (questionContent) {
        content += questionContent.split('\n').map(line => `> ${line}`).join('\n') + "\n";
    }
    tR += calloutHead + content;
} else {
    // For all other callout types, prompt for generic content.
    let content = await tp.system.prompt('Content (New line -> Shift+Enter):', '', true, true);
    content = content.split('\n').map(line => `> ${line}`).join('\n');
    tR += calloutHead + content;
}
-%>
