# String Calculator Kata

<details><summary><strong>How to use this starter</strong></summary>
- ensure you have NodeJS installed (via installer, package or nvm -- should be at least version 8)
- clone this somewhere (fork first if you want to, of course)
- I suggest using Visual Studio Code. If you are using VSCode, open the folder where you've put this starting-point, and press Ctrl-~ to open the inbuilt terminal for running the following commands. If you're using another environment, I suggest using an inbuilt terminal if available (eg in WebStorm), otherwise, open a terminal, cd to where this code lives and run:
    - `npm install`
    - `npm run autotest`
- If you're using VSCode, I suggest opening this README.md and pressing Ctrl+Shift+V (default keybinding on windows) to open this document in Markdown preview. If that keybinding doesn't work, try opening the command pallete (Ctrl+Shift+P on windows & linux, Cmd+Shift+P on mac) and typing "Markdown", then selecting "Markdown: Open Preview".
</details>

#### Before you start:

- Try not to read ahead
- Do one task at a time. The trick is to learn to work incrementally. Solve each requirement with the simplest code. Scenarios outside of the specified requirements are not supported and any error which arises from them is _perfectly fine_
- _Make sure you only test for correct inputs. there is no need to test for invalid inputs for this kata. This is part of the design of the kata: implement **only** what is necessary_
- **NB**: When implementing new features, it's important to remember that
existing features _should continue to work as specified_.

<details><summary>Initial spec</summary>

    Create a simple String calculator class with a method named Add which takes in a string and returns an integer.

    The method can take 0, 1 or 2 numbers, and will return their sum (for an empty string it will return 0)
        for example “” or “1” or “1,2”

    Start with the simplest test case of an empty string and move   to 1 and two numbers

    Remember to solve things as simply as possible so that you force yourself to write tests you did not think about

    Remember the TDD cadence:
        RED
        GREEN
        REFACTOR
</details>

<details><summary>New feature: more inputs</summary>

    Allow the Add method to handle an unknown amount of numbers
</details>

<details><summary>New feature: more delimiters</summary>

    Allow the Add method to handle new lines between numbers (instead of commas).

    Example of supported syntax:
        “1\n2,3”  (will equal 6)

    Example of unsupported syntax:
        “1,\n” (clarification: no need to test around this)
</details>

<details>
<summary>New feature: support any single-char delimiter</summary>

    To set the delimiter, the beginning of the string will contain a separate line that looks like this:   “//[delimiter]\n[numbers…]”

    For example: given “//;\n1;2” should return 3
</details>

<details><summary>New feature: handle negative numbers</summary>

    Calling Add with a negative number should throw an exception

    The error should have a message starting with “negatives not allowed”

    The error should contain the negative number that was passed in

    If there are multiple negatives, show all of them in the exception message.
</details>

<details><summary>New feature: handle large numbers</summary>

    Numbers bigger than 1000 should be ignored

    For example, attempting to add  2 + 1001 should return 2
</details>

<details><summary>New feature: multi-length delimiters</summary>

    Delimiters can be of any length with the following format:
    “//[delimiter]\n”

    For example: “//[***]\n1***2***3” should return 6
</details>

<details><summary>New feature: multiple delimiters</summary>

    Allow multiple delimiters like this:  “//[delim1][delim2]\n”

    For example “//[*][%]\n1*2%3” should return 6.
</details>