## Secure code execution with E2B

### How to use the E2B Code Interpreter SDK with Together AI models.


<img width="1280" alt="How E2B Code Interpreter Works" src="https://github.com/tizkovatereza/Together-and-E2B/assets/135881365/608ab4f6-9c74-48cc-8aa3-fb80d04048af">


### Why give your AI app code interpreting capabilities?

E2B is the code execution layer for the AI app. The ability to execute the code as opposed to only generate it has many advantages:

- Better reasoning
- More complex tasks (e.g., advanced data analysis or mathematics)
- Producing tangible results such as charts
- Immediate testing (and correcting) of the produced output.

### E2B as a secure choice for code execution

The open-source [Code Interpreter SDK](https://github.com/e2b-dev/code-interpreter) by [E2B](https://e2b.dev/docs) provides a long-running secure sandboxed environment where you can run the output generated by Together AI's LLMs. This SDK is tailor-made for AI data analysts, coding apps, and reasoning-heavy agents. The SDK quickly creates a secure cloud sandbox. Inside the sandbox is a running Jupyter server which the LLM can use.


### Starting with Code Interpreter SDK

1. Get your E2B API key [here](https://e2b.dev/docs/getting-started/api-key) for free.

2. Install the SDK

JavaScript & TypeScript version:

```sh
npm i @e2b/code-interpreter
```

Python version:

```sh
pip install e2b_code_interpreter
```


3. Execute code with code interpreter inside sandbox

JavaScript & TypeScript version:

```js
import { CodeInterpreter } from '@e2b/code-interpreter'

const sandbox = await CodeInterpreter.create()
await sandbox.notebook.execCell('x = 1')

const execution = await sandbox.notebook.execCell('x+=1; x')
console.log(execution.text)  // outputs 2

await sandbox.close()
```

Python version:

```python
from e2b_code_interpreter import CodeInterpreter

with CodeInterpreter() as sandbox:
    sandbox.notebook.exec_cell("x = 1")

    execution = sandbox.notebook.exec_cell("x+=1; x")
    print(execution.text)  # outputs 2
```


### More about E2B

E2B makes running AI-generated code in secure and isolated sandbox environments easy with the [Code Interpreter SDK](https://github.com/e2b-dev/code-interpreter).

The SDK has a Python and JavaScript/TypeScript version.
E2B works with any LLM and any AI frameworks (e.g., [LangChain](https://github.com/e2b-dev/e2b-cookbook/tree/main/examples/langchain-python), LammaIndex, [Vercel AI SDK](https://github.com/e2b-dev/e2b-cookbook/tree/main/examples/nextjs-code-interpreter), CrewAI, [Autogen](https://github.com/e2b-dev/e2b-cookbook/tree/main/examples/e2b_autogen)).

Check out the [E2B docs](https://e2b.dev/docs) and [E2B Cookbook](https://github.com/e2b-dev/e2b-cookbook/tree/main).
