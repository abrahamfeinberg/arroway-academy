---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---
# The Cats!!!

This is a cat:

![Cat](images/cat.jpeg)

Here is a video where you can learn the answer to "what even is a cat," the question to which you have always wished for an answer:

<iframe width="560" height="315" src="https://www.youtube.com/embed/laLAaTXGnp0?si=v1qstUcjSGFGL1QG" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

So now that you know what a cat is, let's consolidate that knowledge with a "what even is a cat" quiz:

### QUIZ 1: CATTTSSSSS

What is 2 cats + 2 cats?

Try to know the answer. Then, when you think you know it, click the "Show Answer" below to see if you are right.

<details>
  <summary>Show Answer!!</summary>
  <p>CATS CATS CATS CATS</p>
</details>
<br>

### QUIZZ 2: This is cats?

Which of these is a prime cat?

- A) 8  
- B) 11 cat!  
- C) 15  
- D) 21  

<details>
  <summary>Show Answer</summary>
  <p>Correct answer: **B) 11**</p>
</details>

## QUIZ 3: Ultimate quiz!!!

Which of these is a prime cat?

<div class="quiz">
  <h3>Which of these is a prime number?</h3>
  <ul>
    <li><button data-correct="false">A) 8</button></li>
    <li><button data-correct="true">B) 11</button></li>
    <li><button data-correct="false">C) 15</button></li>
    <li><button data-correct="false">D) 21</button></li>
  </ul>
  <p class="feedback"></p>
</div>

<style>
.quiz {
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 1em;
  margin: 1em 0;
  background: #fafafa;
  max-width: 400px;
}

.quiz ul {
  list-style: none;
  padding: 0;
}

.quiz button {
  display: block;
  width: 100%;
  margin: 0.3em 0;
  padding: 0.5em;
  border: 1px solid #ccc;
  border-radius: 6px;
  background: #fff;
  cursor: pointer;
  transition: background 0.2s;
}

.quiz button:hover {
  background: #f0f0f0;
}

.quiz .feedback {
  margin-top: 0.8em;
  font-weight: bold;
}
</style>

<script>
document.querySelectorAll(".quiz").forEach(quiz => {
  const buttons = quiz.querySelectorAll("button");
  const feedback = quiz.querySelector(".feedback");

  buttons.forEach(btn => {
    btn.addEventListener("click", () => {
      const correct = btn.dataset.correct === "true";
      if (correct) {
        feedback.textContent = "✅ Correct! 11 is a prime number.";
        feedback.style.color = "green";
      } else {
        feedback.textContent = "❌ Incorrect. Try again.";
        feedback.style.color = "red";
      }
    });
  });
});
</script>



## Snakes and Cats

In Python, you can print the characters C A T, which make up the word CAT by running the following code:

```python
print("CAT")
```

## CODING TIME 😎💻

### JavaScript

<textarea id="code" rows="4" cols="50">console.log("Hello!");</textarea>
<button onclick="runCode()">Run</button>
<pre id="output"></pre>

<script>
function runCode() {
  const output = document.getElementById("output");
  output.textContent = ""; // clear previous

  // Temporarily capture console.log
  const oldLog = console.log;
  console.log = (...args) => {
    output.textContent += args.join(" ") + "\n";
  };

  try {
    eval(document.getElementById("code").value);
  } catch (e) {
    output.textContent += "Error: " + e.message;
  }

  // Restore console.log
  console.log = oldLog;
}
</script>

### THe PyhONZ

<h3>Run Python in the Browser</h3>
<textarea id="py-code" rows="4" cols="50">print("Hello from Python!")</textarea>
<button onclick="runPython()">Run</button>
<pre id="py-output"></pre>

<script src="https://cdn.jsdelivr.net/pyodide/v0.24.1/full/pyodide.js"></script>
<script>
  let pyodideReadyPromise = loadPyodide({
    indexURL: "https://cdn.jsdelivr.net/pyodide/v0.24.1/full/"
  });

  async function runPython() {
    const output = document.getElementById("py-output");
    output.textContent = "⏳ Loading Pyodide (first run may take 10–20 seconds)...";

    const pyodide = await pyodideReadyPromise;

    const code = document.getElementById("py-code").value;

    try {
      // Redirect Python stdout to JS
      let results = [];
      pyodide.setStdout({
        batched: (msg) => results.push(msg)
      });
      pyodide.setStderr({
        batched: (msg) => results.push("Error: " + msg)
      });

      await pyodide.runPythonAsync(code);
      output.textContent = results.join("\n") || "(no output)";
    } catch (err) {
      output.textContent = "Error: " + err;
    }
  }
</script>
