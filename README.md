# ⚙️ KTU CSL331: Compiler Design Lab Manual & Implementation Suite

<div align="center">

[![Language: C](https://img.shields.io/badge/Language-C99-00599C.svg?style=for-the-badge&logo=c)](https://en.cppreference.com/w/c)
[![Lex & Yacc](https://img.shields.io/badge/Tools-Flex%20%26%20Bison-orange.svg?style=for-the-badge)](https://github.com/westes/flex)
[![Curriculum](https://img.shields.io/badge/University-KTU%20CSL331-8B0000.svg?style=for-the-badge)](https://ktu.edu.in)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](LICENSE)

<p align="center">
  <b>Comprehensive laboratory program implementations, parser generators, automaton transformations, and code optimization passes for the APJ Abdul Kalam Technological University (KTU) Compiler Design Course (CSL331).</b>
</p>

</div>

---

## 📌 Overview

This repository contains clean, modular, and thoroughly tested implementations for the complete **Compiler Design Laboratory** syllabus. It traces the full pipeline of modern compilers—from source character ingestion, tokenization, grammar parsing, and intermediate representation, to machine-independent code optimization.

---

## 🗂️ Lab Experiments Directory & Syllabus Map

| # | Experiment Name | Implementation Details | Core Concepts / Tools |
| :-: | :--- | :--- | :--- |
| **01** | **Lexical Analyzer in C** | [`lexical.c`](1)lexicalanalyzerusingc.c/) | Finite state token categorization (Keywords, Identifiers, Operators, Delimiters) |
| **02** | **Lexical Analyzer using Lex/Flex** | [`lexicalanalyzer-lex.l`](2)lexicalanalyzer-lex/) | Regular expressions, pattern matching, token stream generation |
| **03** | **Keyword & Token Counter** | [`lexprgrm2cntkeywords.lex`](2.1)lex%20program%20to%20count%20number%20of%20keywords/) | Lex state rules, symbol counting, comment stripping |
| **04** | **Yacc / Bison Scientific Calculator** | [`calc.l`](3.1)Calculator%20using%20yacc%20tools/), [`calc.y`](3.1)Calculator%20using%20yacc%20tools/) | LALR(1) parsing, grammar rules, arithmetic evaluation, precedence |
| **05** | **NFA to DFA Conversion** | [`nfa-2-dfa.c`](4)convert%20nfa%202%20dfa%20using%20c%20program/) | Subset construction algorithm, transition state mapping |
| **06** | **$\epsilon$-NFA to NFA Conversion** | [`nfae-nfawithoute.c`](5)nfa%20with%20e%20to%20nfa%20without%20e/) | $\epsilon$-closure calculation, null-transition elimination |
| **07** | **Recursive Descent Parser** | [`recursivedecentparser.c`](6)%20Recursive%20decent%20parser%20for%20a%20given%20expression/) | Top-down parsing, predictive grammar procedures, backtrack avoidance |
| **08** | **Operator Precedence Parser** | [`operatorprecedence.c`](7)%20Operator%20Precedence%20Parser/) | Bottom-up shift-reduce parsing using operator precedence relation matrices |
| **09** | **Shift-Reduce Parser** | [`shift.c`](8)Shift%20Reduce%20Parser/) | Stack operations, handle pruning, shift and reduction steps |
| **10** | **FIRST and FOLLOW Set Computation** | [`first&follow.c`](9)%20First%20and%20Follow/) | Context-free grammar analysis, predictive parsing table prerequisites |
| **11** | **Intermediate Code Generator (TAC)** | [`code.c`](10)%20Intermediate%20Code%20Generator/) | Three-Address Code generation, quadruples/triples, temporary variables |
| **12** | **Loop Unrolling Optimization** | [`loopunroll.c`](11)loop%20unrolling/) | Machine-independent optimization, branch reduction, instruction scheduling |
| **13** | **Constant Propagation** | [`constant.c`](12)Constant%20Propagation/) | Data-flow analysis, compile-time algebraic simplification |

---

## 🛠️ Build & Execution Instructions

### Prerequisites
Install GCC compiler and the Flex/Bison lexer/parser generator tools:

```bash
# On Debian / Ubuntu / Kali Linux:
sudo apt update
sudo apt install build-essential flex bison -y

# On macOS (via Homebrew):
brew install gcc flex bison

# On Windows:
# Install MinGW-w64 or use WSL (Windows Subsystem for Linux)
```

---

### Compilation Cheat Sheet

#### 1. Compiling Pure C Programs (e.g., Lexical Analyzer, NFA to DFA)
```bash
gcc -Wall -Wextra "1)lexicalanalyzerusingc.c/lexical.c" -o lexical_analyzer
./lexical_analyzer
```

#### 2. Compiling Lex/Flex Programs
```bash
cd "2)lexicalanalyzer-lex"
flex lexicalanalyzer-lex.l
gcc lex.yy.c -o lex_analyzer -lfl
./lex_analyzer < input.c
```
*(Note: If compiling without `-lfl`, ensure `yywrap()` returns 1 in your `.l` file or compile with `gcc lex.yy.c -o lex_analyzer`).*

#### 3. Compiling Lex & Yacc Calculator
```bash
cd "3.1)Calculator using yacc tools"
yacc -d calc.y
flex calc.l
gcc y.tab.c lex.yy.c -o calculator -lm
./calculator
```

---

## 🧠 Compiler Architecture Reference

```
  Source Code (.c)
         │
         ▼
 ┌────────────────┐
 │ Lexical Phase  │ ──► Generates Token Stream (Lex / Flex)
 └────────────────┘
         │
         ▼
 ┌────────────────┐
 │ Syntax Phase   │ ──► AST / Parse Tree Construction (Yacc / Bison)
 └────────────────┘
         │
         ▼
 ┌────────────────┐
 │ Semantic Phase │ ──► Type Checking, Symbol Table Management
 └────────────────┘
         │
         ▼
 ┌────────────────┐
 │  Intermediate  │ ──► Three-Address Code (TAC) Generation
 └────────────────┘
         │
         ▼
 ┌────────────────┐
 │  Optimization  │ ──► Constant Propagation, Loop Unrolling
 └────────────────┘
         │
         ▼
 ┌────────────────┐
 │Code Generation │ ──► Target Assembly / Machine Instructions
 └────────────────┘
```

---

## 📄 License

This repository is maintained for educational and reference purposes under the [MIT License](LICENSE). Developed by [Akhil Binu](https://akhilbinu.in/).
