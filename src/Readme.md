# AD361 – Learning Practice: White Box Testing

**Course:** AD361 – Application Testing  
**Student:** Bashir Abdulkadir  
**Project:** Todo List Application  
**Testing Framework:** Jest and TypeScript  
**GitHub Repository:** https://github.com/Bashir3355/Learning-Practice-White-Box-Testing

---

## 1. Project Overview

This project demonstrates white box testing using a simple Todo List application. The purpose is to examine the application's source code, design automated test cases, and measure code coverage.

The application allows users to create tasks, add tasks to a list, mark tasks as completed, and count completed tasks.

For this learning practice, I tested the three functions in `src/todoUtils.ts` using Jest.

## 2. Learning Objectives

The objectives of this assignment are to:

- Understand statement, branch, and loop coverage.
- Organize automated tests into test suites.
- Write tests that execute statements in a function.
- Test both outcomes of conditional statements.
- Test loops with zero, one, and multiple items.
- Generate and evaluate code coverage reports.

## 3. Project Files

The important files include:

| File | Description |
|---|---|
| `src/todoUtils.ts` | Contains the three functions being tested |
| `src/todoUtils.test.ts` | Contains six automated test cases |
| `src/App.tsx` | React component for the Todo List application |
| `package.json` | Project dependencies and npm scripts |
| `README.md` | Project documentation |

## 4. Testing Tools

- **TypeScript:** Application and test code.
- **Jest:** Automated unit testing and code coverage.
- **VS Code:** Source code editing.
- **Node.js and npm:** Dependency installation and test execution.
- **Git and GitHub:** Version control and project submission.

## 5. Test Cases and Results

I created one test file containing three test suites and six test cases.

### Test Suite 1: Statement Coverage

**Function:** `createTodo(text)`

**Objective:** Verify that the function creates a valid todo object.

**Test Case 1: Create a new todo**

- Input: `"Buy milk"`
- Expected text: `"Buy milk"`
- Expected completion status: `false`
- Expected ID type: `number`
- **Result: PASSED**

This test executes the statements in the `createTodo` function.

### Test Suite 2: Branch Coverage

**Function:** `addTodo(todos, text)`

**Objective:** Test both outcomes of the conditional statement that checks for blank input.

**Test Case 2: Add blank text**

- Input: Whitespace-only text.
- Expected result: The todo list remains empty.
- **Result: PASSED**

**Test Case 3: Add valid text**

- Input: `"Buy milk"`
- Expected result: One new todo is added with the correct text and an initial completion status of `false`.
- **Result: PASSED**

These two tests verify both outcomes of the branch.

### Test Suite 3: Loop Coverage

**Function:** `countDone(todos)`

**Objective:** Verify the loop's behavior with zero, one, and multiple items.

**Test Case 4: Empty todo list**

- Input: Empty array.
- Expected result: `0`
- **Result: PASSED**

**Test Case 5: One completed todo**

- Input: One todo with `done: true`.
- Expected result: `1`
- **Result: PASSED**

**Test Case 6: Multiple todos**

- Input: Three todos, two completed and one incomplete.
- Expected result: `2`
- **Result: PASSED**

These tests verify that the loop correctly counts completed tasks.

## 6. Test Execution

I executed the automated tests using:

```bash
npm test
```

**Verified Results:**

```text
PASS src/todoUtils.test.ts

Test Suites: 1 passed, 1 total
Tests:       6 passed, 6 total
Snapshots:   0 total
```

All six test cases passed successfully.

## 7. Code Coverage Results

I generated the coverage report using:

```bash
npm run coverage
```

The final coverage results were:

| Coverage Metric | Result |
|---|---|
| Statement Coverage | 100% |
| Branch Coverage | 100% |
| Function Coverage | 100% |
| Line Coverage | 100% |

**Overall Result: 100% code coverage for the tested utility code.**

All statements, branches, functions, and lines measured by the coverage report were executed successfully.

## 8. Branch Coverage Experiment

As instructed, I temporarily skipped the test that checks blank text in the `addTodo` function.

I changed the test from `it(...)` to `it.skip(...)` and ran the coverage report again.

**Results with the test skipped:**

| Coverage Metric | Result |
|---|---|
| Statement Coverage | 92.3% |
| Branch Coverage | 75% |
| Function Coverage | 100% |
| Line Coverage | 92.3% |

The results showed that skipping one important test reduced branch coverage from 100% to 75%.

After reviewing the results, I restored the test and reran the coverage report.

**Final result: All six tests passed, and coverage returned to 100%.**

This experiment demonstrated why testing both outcomes of a conditional statement is important.

## 9. How to Run the Project

### Install dependencies

```bash
npm install
```

### Start the application

```bash
npm run dev
```

Open the local URL displayed by Vite in your browser.

### Run automated tests

```bash
npm test
```

### Generate the coverage report

```bash
npm run coverage
```

## 10. What I Learned

Through this practice, I learned how to examine source code and design automated tests based on its internal structure.

I learned that statement coverage checks whether code statements execute, while branch coverage checks different decision outcomes.

I also learned how to test loops using empty, single-item, and multiple-item arrays.

Finally, I used Jest coverage reports to identify untested code and verify the effectiveness of my test cases.

## 11. Conclusion

I successfully completed the White Box Testing learning practice using Jest and TypeScript.

I organized six test cases into three test suites covering statement, branch, and loop testing.

All six tests passed, and the final coverage report showed 100% statement, branch, function, and line coverage for the tested code.

## 12. AI Transparency

I used AI assistance to help explain testing concepts, organize documentation, and troubleshoot the Jest environment. I reviewed the test results and verified the final coverage using Jest in VS Code.
