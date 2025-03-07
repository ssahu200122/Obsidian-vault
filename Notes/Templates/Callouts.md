<%*
const questionContent = await tp.system.prompt("Enter the QUESTION content (new line → Shift+Enter):", "", true, true);
const solutionContent = await tp.system.prompt("Enter the SOLUTION content (new line → Shift+Enter):", "", true, true);
const imagePath = await tp.system.prompt("Enter the image file name (or leave blank):", "", false);

let output = "";
output += "> [!question]-\n";
output += "> #question\n";

// Insert image if provided
if (imagePath && imagePath.trim() !== "") {
    output += `> ![[${imagePath.trim()}]]\n`;
}

// Add the question content, each line prefixed with "> "
if (questionContent) {
    const qLines = questionContent.split('\n').map(line => `> ${line}`).join('\n');
    output += qLines + "\n";
}

// Start the solution block
output += ">> [!done] Solution\n";

// Add the solution content, each line prefixed with ">> "
if (solutionContent) {
    const sLines = solutionContent.split('\n').map(line => `>> ${line}`).join('\n');
    output += sLines + "\n";
}

tR += output;
-%>
