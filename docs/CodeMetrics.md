# Code Metrics
SonarQube is used to create code metrics and analyze the application code.
On every push to the repository SonarQube automatically analyzes the code and gives feedback.

The three code metrics we focussed on are:
- Code Smells – Minor issues that don’t break functionality but may impact maintainability.
- Cognitive Complexity – A readability-focused improvement over Cyclomatic Complexity.
- Duplications – Measures how much of the code is repeated unnecessarily.

Results at the end of our development are:

Code Smells: 22 code smells that should be fixed.
![image](https://github.com/user-attachments/assets/2eba0ded-2146-485d-8c8c-0e6601e7b860)


Duplications: 1.9%
![image](https://github.com/user-attachments/assets/a71d0813-bdfc-4cbc-af5e-e33a9d355ad6)

Cognitive Complexity:
There are some modules that clearly need refactoring to improve the code quality.
![image](https://github.com/user-attachments/assets/bce3b5e4-fde8-406d-b342-493642f8c0ed)

