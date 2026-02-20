PRIVCHECK is a comprehensive static analysis system refactored to align with core Compiler Construction principles. While traditional security tools often rely on simple pattern matching, PRIVCHECK implements a full compiler front-end pipeline—including Lexical, Syntactic, and Semantic analysis—to validate the structural and logical integrity of system scripts.

Key Features & Methodology
The tool effectively audits system commands by moving through three distinct stages:

- Lexical Analysis: Utilizes a DFA-based scanner to transform source scripts into specific tokens such as SUDO, FLAG, PATH, and PERM.

-Syntactic Analysis: Enforces structural standards based on a custom Context-Free Grammar (CFG) and generates an Abstract Syntax Tree (AST) to understand command hierarchies.

-Semantic Analysis: Performs logical verification to detect risks that are syntactically correct but semantically dangerous, such as:

-Redundancy Checks: Flagging redundant privilege escalations like sudo su.

-Context-Aware Permissions: Warning against high-risk commands like chmod 777 on sensitive system paths (e.g., /etc or /root).

-Destructive Bounds: Detecting catastrophic operations such as recursive deletions targeted at the system root (rm -rf /).

Tech Stack

-Language: Python 


-Frontend: Streamlit (featuring real-time risk gauges and animations) 

-Data Visualization: Plotly 


-Logic: Custom Lexer, Parser, and Semantic Engine 

Why this matters
By analyzing the Context (Semantics) and Structure (Syntax) of a script rather than just string matching, PRIVCHECK provides far superior protection against malformed or malicious system code.
