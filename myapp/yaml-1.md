# Java Developer Copilot Agents Reference

This document lists all **custom Copilot agents** for Java development, their **purpose, tools, skills**, **predefined prompts**, and a **visual diagram** for quick reference.

---

## 1️⃣ Java Debugging Assistant

**Purpose:**  
Analyze runtime errors, exceptions, and stack traces to identify root causes and suggest fixes.

**Tools:**  
- `codebase` → Reads project code  
- `terminal` → Suggests debugging commands  
- `problems` → Reads VS Code Problems panel  

**Skills:**  
- Detects NullPointerException, SQLTimeoutException, and other runtime errors  
- Suggests code fixes, null checks, and exception handling  
- Provides logging improvement recommendations  
- Suggests terminal commands for debugging  

**Predefined Prompts:**  
- Analyze this exception stack trace and suggest a fix  
- Explain the root cause of this NullPointerException in OrderService.java  
- Find recurring runtime errors in this module  
- Suggest debugging commands to diagnose memory leaks  
- Why is my Spring Boot service crashing repeatedly?  
- Check this stack trace and recommend null checks or fixes  
- Summarize the cause and impact of this SQLTimeoutException  

---

## 2️⃣ Database & SQL Advisor

**Purpose:**  
Analyze SQL queries, database schema, and ORM usage to detect performance issues, N+1 problems, and improve database efficiency.

**Tools:**  
- `codebase` → Reads Java ORM/Hibernate code  
- `terminal` → Suggests SQL or database commands  
- `problems` → Detects ORM misconfigurations  

**Skills:**  
- Detects N+1 query issues  
- Suggests missing indexes and query optimization  
- Reviews Hibernate queries for performance issues  
- Suggests caching strategies  

**Predefined Prompts:**  
- Optimize this SQL query for better performance  
- Check for N+1 issues in OrderService module  
- Suggest indexes for this table to improve query speed  
- Analyze Hibernate queries for performance issues  
- Detect potential SQL injection risks in this module  
- Recommend schema improvements for the orders database  
- Suggest caching strategies for frequently accessed queries  

---

## 3️⃣ Architecture Guidance Agent

**Purpose:**  
Provide system design recommendations, modularization, and scalability guidance for Java projects.

**Tools:**  
- `codebase` → Reads project code structure  
- `terminal` → Suggests commands for deployment/analysis  

**Skills:**  
- Suggests design patterns and modularization  
- Recommends microservice boundaries or monolith refactoring  
- Suggests cloud-native architecture patterns  
- Identifies architectural smells, tight coupling, and layering issues  

**Predefined Prompts:**  
- Review the architecture of this Java project and suggest improvements  
- Suggest microservice boundaries for this monolithic application  
- How can I improve modularity in this module?  
- Recommend design patterns for this payment workflow  
- Is this system scalable for 1M users?  
- Help refactor this tightly coupled module  
- Provide cloud-native design recommendations for this microservice  

---

## 4️⃣ Log & Anomaly Detection Agent

**Purpose:**  
Analyze application logs to detect anomalies, recurring failures, and performance issues.

**Tools:**  
- `codebase` → Links log issues to code  
- `terminal` → Can run log commands or scripts  
- `clipboard` → Reads pasted logs  

**Skills:**  
- Detects recurring errors and anomalous spikes  
- Suggests improvements to logging structure and observability  
- Prioritizes critical issues and performance warnings  

**Predefined Prompts:**  
- Analyze logs for errors and anomalies  
- Detect recurring failures in the application logs  
- Summarize root cause of these logs  
- Suggest logging best practices for this module  
- Identify performance issues from log patterns  
- Flag unusual spikes or rare events in these logs  
- Recommend monitoring improvements based on logs  

---

## 5️⃣ Java Testing Expert

**Purpose:**  
Generate and improve unit and integration tests, identify missing coverage, and fix failing tests.

**Tools:**  
- `codebase` → Reads project source for test generation  
- `problems` → Reads failing test errors  
- `terminal` → Can suggest test execution commands  

**Skills:**  
- Generates JUnit tests and Mockito mocks  
- Identifies missing test scenarios and coverage gaps  
- Analyzes test failures and recommends fixes  

**Predefined Prompts:**  
- Generate unit tests for this Java class  
- Fix failing JUnit test cases  
- Improve test coverage for this module  
- Suggest mocks for this service using Mockito  
- Analyze test failures and explain the cause  
- Generate integration tests for this REST API  
- Identify missing test scenarios for this class  

---

## 6️⃣ Security Auditor Agent

**Purpose:**  
Detect security vulnerabilities in code, SQL queries, and logging, providing actionable fixes.

**Tools:**  
- `codebase` → Reads Java code and queries  
- `terminal` → Suggests security testing commands  
- `files` → Reads config files for sensitive data handling  

**Skills:**  
- Detects SQL injection risks, unsafe logging, insecure serialization  
- Audits authentication/authorization flows  
- Provides security best practices for sensitive data  

**Predefined Prompts:**  
- Check code for SQL injection vulnerabilities  
- Audit authentication and authorization flows  
- Find insecure logging statements  
- Suggest security improvements for this module  
- Analyze REST APIs for security risks  
- Detect unsafe serialization or deserialization  
- Recommend best practices for sensitive data handling  

---

## 7️⃣ Java Full Dev Workflow Agent

**Purpose:**  
Perform a full development workflow: debugging, architecture improvements, database optimization, logging, testing, and security auditing.

**Tools:**  
- `codebase`, `terminal`, `problems`, `clipboard`, `files`  

**Skills:**  
- Combines the capabilities of all other agents  
- Provides multi-step, end-to-end recommendations  
- Generates prioritized action plan for code, database, logs, tests, and security  

**Predefined Prompts:**  
- Perform a full development workflow on this Java module: debug, suggest code/architecture improvements, optimize DB queries, improve logging, suggest tests, and audit security  
- Here is a stack trace and log excerpt: [Paste here]. Analyze errors, suggest fixes, and recommend improvements  
- Analyze this Java project and suggest full-stack improvements: architecture, database, logging, testing, security  
- Check this service for runtime errors, performance bottlenecks, N+1 queries, and logging issues. Suggest fixes and test cases  
- Perform end-to-end review of this codebase for maintainability, scalability, and security  

---

## 🖼 Visual Diagram (Mermaid)

```mermaid
graph TD
    A[Java Developer Copilot Agents] --> B[Java Debugging Assistant]
    A --> C[Database & SQL Advisor]
    A --> D[Architecture Guidance Agent]
    A --> E[Log & Anomaly Detection Agent]
    A --> F[Java Testing Expert]
    A --> G[Security Auditor Agent]
    A --> H[Java Full Dev Workflow Agent]

    B --> B1[Purpose: Analyze exceptions, stack traces, runtime errors]
    B --> B2[Tools: codebase, terminal, problems]
    B --> B3[Skills: Root cause analysis, null checks, logging, debugging commands]

    C --> C1[Purpose: Optimize SQL, detect N+1 issues, suggest indexes]
    C --> C2[Tools: codebase, terminal, problems]
    C --> C3[Skills: Query optimization, schema improvements, caching, ORM analysis]

    D --> D1[Purpose: Architecture review, design patterns, scalability guidance]
    D --> D2[Tools: codebase, terminal]
    D --> D3[Skills: Microservices boundaries, modularization, cloud-native patterns, architectural smells]

    E --> E1[Purpose: Log anomaly detection, recurring failures, observability]
    E --> E2[Tools: codebase, terminal, clipboard]
    E --> E3[Skills: Error detection, anomaly alerts, logging improvements, monitoring suggestions]

    F --> F1[Purpose: Generate and improve unit/integration tests]
    F --> F2[Tools: codebase, problems, terminal]
    F --> F3[Skills: JUnit, Mockito, coverage analysis, test fixes, integration tests]

    G --> G1[Purpose: Security auditing of code, queries, and configs]
    G --> G2[Tools: codebase, terminal, files]
    G --> G3[Skills: SQL injection detection, logging risks, authentication/authorization, best practices]

    H --> H1[Purpose: End-to-end Java Dev workflow]
    H --> H2[Tools: codebase, terminal, problems, clipboard, files]
    H --> H3[Skills: Combines all other agents: debugging, architecture, DB, logs, testing, security]