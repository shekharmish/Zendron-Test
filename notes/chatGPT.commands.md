---
id: hbl89tecm3lg63wb4z2i8k9
title: command
desc: ''
updated: 1679521139596
created: 1679521138281
---
## Print Conversation as Markdown

1. `Fn12` or equivalently  "right click > inspect."
2. Go to Console.
3. Paste the below command.

    ```javascript
    function h(html) { return html.replace(/<p>/g, '\n\n').replace(/<\/p>/g, '').replace(/<b>/g, '**').replace(/<\/b>/g, '**').replace(/<i>/g, '_').replace(/<\/i>/g, '_').replace(/<code[^>]*>/g, (match) => { const lm = match.match(/class="[^"]*language-([^"]*)"/); return lm ? '\n```' + lm[1] + '\n' : '```'; }).replace(/<\/code[^>]*>/g, '```').replace(/<[^>]*>/g, '').replace(/Copy code/g, '').replace(/This content may violate our content policy. If you believe this to be in error, please submit your feedback — your input will aid our research in this area./g, '').trim(); } (()=>{ const e=document.querySelectorAll(".text-base");let t="";for(const s of e)s.querySelector(".whitespace-pre-wrap")&&(t+=`**${s.querySelector('img')?'You':'ChatGPT'}**: ${h(s.querySelector(".whitespace-pre-wrap").innerHTML)}\n\n`);const o=document.createElement("a");o.download="Conversation with ChatGPT.md",o.href=URL.createObjectURL(new Blob([t])),o.style.display="none",document.body.appendChild(o),o.click()})();
    ```

4. Copy past markdown to file.

### Source

- [Reddit Post](https://www.reddit.com/r/ChatGPT/comments/zm237o/save_your_chatgpt_conversation_as_a_markdown_file/)
  - Apparently the code itself was written by chatGPT.
