# Code Review Developer Guide
# 开发者代码评审指南

## Introduction {#intro}

## 序言 {#intro}

A code review is a process where someone other than the author(s) of a piece of
code examines that code.

At Google we use code review to maintain the quality of our code and products.

This documentation is the canonical description of Google's code review
processes and policies.


代码评审是指，除了代码的作者以外的人员对代码进行检查的过程。在 Google 内部，我们通过代码评审来保障代码以及产品的质量。本文档描述的是 Google 的代码评审流程以及机制。


This page is an overview of our code review process. There are two other large
documents that are a part of this guide:

-   **[How To Do A Code Review](reviewer/)**: A detailed guide for code
    reviewers.
-   **[The CL Author's Guide](developer/)**: A detailed guide for developers
    whose CLs are going through review.
    
当前页概述了 Google 的代码评审过程，详细的指南文档包括以下两个部分：

- **[如何进行代码评审](reviewer/)** ：代码评审者的详细指南。
- **[代码作者变更指导](developer/)** ：代码作者变更(CLs)操作的详细指南。

## What Do Code Reviewers Look For? {#look_for}

## 代码评审者关注的内容 {#look_for}

Code reviews should look at:

-   **Design**: Is the code well-designed and appropriate for your system?
-   **Functionality**: Does the code behave as the author likely intended? Is
    the way the code behaves good for its users?
-   **Complexity**: Could the code be made simpler? Would another developer be
    able to easily understand and use this code when they come across it in the
    future?
-   **Tests**: Does the code have correct and well-designed automated tests?
-   **Naming**: Did the developer choose clear names for variables, classes,
    methods, etc.?
-   **Comments**: Are the comments clear and useful?
-   **Style**: Does the code follow our
    [style guides](http://google.github.io/styleguide/)?
-   **Documentation**: Did the developer also update relevant documentation?

See **[How To Do A Code Review](reviewer/)** for more information.

代码评审者需要关注的内容，包括以下：

- **设计**：代码是否按经精心设计并且符合当前系统的要求。
- **功能**：代码是符合作者的设计意图？功能实现是否对使用者友好。
- **复杂度**：代码是否足够简单？其他开发人员在后续接手维护代码时，是否易于理解与上手？
- **测试**：代码是否经过正确且设计良好的自动作测试？
- **命名**：开发人员是否对变量、类、方法，等，进行合理的命名？
- **注释**：代码中的注释是否清晰且有用？
- **风格**：代码是否符合 [Google 的代码风格](http://google.github.io/styleguide/) 要求？
- **文档**：开发人员是否与代码同步更新相关文档？

### Picking the Best Reviewers {#best_reviewers}

### 选择最佳评审者{#best_reviewers}

In general, you want to find the *best* reviewers you can who are capable of
responding to your review within a reasonable period of time.

The best reviewer is the person who will be able to give you the most thorough
and correct review for the piece of code you are writing. This usually means the
owner(s) of the code, who may or may not be the people in the OWNERS file.
Sometimes this means asking different people to review different parts of the
CL.

最佳评审者，是那些针对你所提交的变更代码给出最为详尽以及正确评审意见的人。通常会是代码的原作者（Owner），也可能不是原作者清单（OWNERS）中的人员。这意味着会需要邀请不同的人员来评审 CL 中的不同部分。

If you find an ideal reviewer but they are not available, you should at least CC
them on your change.

如果你理想的评审人员无法对代码进行评审，那么至少应该将 CL 变更抄送给他们。

### In-Person Reviews {#in_person}

### 一对一评审(#in_person}

If you pair-programmed a piece of code with somebody who was qualified to do a
good code review on it, then that code is considered reviewed.

对于采取结对编程的方式，若和你搭挡的人员在你编写代码时，既对代码进行足够的评审，那么这些代码在提交变更时可以被视为已评审。

You can also do in-person code reviews where the reviewer asks questions and the
developer of the change speaks only when spoken to.

在一对一评审过程，代码变更者仅在评审者对代码提出问题时才进行口头回复，其他情况下都应保持沉默。

## See Also {#seealso}

-   [How To Do A Code Review](reviewer/): A detailed guide for code reviewers.
-   [The CL Author's Guide](developer/): A detailed guide for developers whose
    CLs are going through review.

## 更多内容 {#seealso}

- [如何进行代码评审](reviewer/)：代码评审者的详细指南。
- [代码作者变更指导](developer/)：代码作者变更(CLs)操作的详细指南。


