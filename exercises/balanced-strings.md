# Balanced strings

A string containing grouping symbols `{}[]()` is said to be balanced if every open symbol `{[(` has a matching closed symbol `)]}` and the substrings before, after and between each pair of symbols is also balanced. The empty string is considered as balanced.

For example: `{[][]}({})` is balanced, while `][`, `([)]`, `{`, `{(}{}` are not.

Implement the following method:

```java
public static boolean isBalanced(String str) {
    ...
}
```

`isBalanced` returns `true` if `str` is balanced according to the rules explained above. Otherwise, it returns `false`.

Use the coverage criteria studied in classes as follows:

1. Use input space partitioning to design an initial set of inputs. Explain below the characteristics and partition blocks you identified.
2. Evaluate the statement coverage of the test cases designed in the previous step. If needed, add new test cases to increase the coverage. Describe below what you did in this step.
3. If you have in your code any predicate that uses more than two boolean operators, check if the test cases written so far satisfy *Base Choice Coverage*. If needed, add new test cases. Describe below how you evaluated the logic coverage and the new test cases you added.
4. Use PIT to evaluate the test suite you have so far. Describe below the mutation score and the live mutants. Add new test cases or refactor the existing ones to achieve a high mutation score.

Write below the actions you took on each step and the results you obtained.
Use the project in [tp3-balanced-strings](../code/tp3-balanced-strings) to complete this exercise.

## Answer

| Characteristics | Blocks      |                    |                                        |                            |                          |                    |
| --------------- | ----------- | ------------------ | -------------------------------------- | -------------------------- | ------------------------ | ------------------ |
|                 | b1          | b2                 | b3                                     | b4                         | b5                       | b6                 |
| Input           | Empty       | Odd number of char | Contains a not opening or closing char | Starting with closing char | Ending with opening char | Valid balanced string |

| Input      | Blocks     |
| ---------- | ---------- |
| ` `        | b1         |
| `{}}`      | b2         |
| `a`        | b2 b3      |
| `)(`       | b4 b5      |
| `][[]`     | b4         |
| `())(`     | b5         |
| `()`       | b6         |
| `[{}({})]` | b6         |
| `[{}]()`   | b6         |

For each statement above, there's a Unit test (see class `StringUtilsTest.java`), and some more for testing an other method created.

First results with PIT:
74% Line Coverage
69% Mutation Coverage

PIT results after adding test for `getBalancingChar()`:
95% Line Coverage
92% Mutation Coverage
