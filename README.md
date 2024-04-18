# Data-Structures-With-C
In this repo, I'll try to talk about Data Structures
### Course Outlines
1. Stacks (array-based and linked based implementations).
2. Queues (array-based and linked based implementations).
3. General Lists (array-based and linked based implementations).
### 4. Search Algorithms in Lists.
   - Linear Search.
   - Binary Search.
   - Mathematical Analysis of Linear and Binary Search.
5. Binary Search Trees.
6. Introduction to Graphs.
7. Appendix: Introduction to Mathematical Analysis of Algorithms.
- This is a "Data Structures" course, not "Data Structures and Algorithms".
- Why "Analysis of Algorithms" in a "Data Structures" course?
- Why Data Structures in C and not in pseudo-code or any other language?

---

#### Why Data Structures
##### Stack Structure (LIFO) that's for Last in First out.
![1](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/cb7eb037-f22b-4e47-9a7b-4791b294541d)

##### Queue Structure (FIFO) that's for First in First out.
![2](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/11fa576c-bf93-4fc0-8271-55b8c09705e1)

##### Tree Structure.
- There are 3 nodes, each node can be a mathematical expression, so i need a structure to have these expressions then i can process them, It's called Treee structure.
- Data is operator or operand, each operand can be an expression.
- Tree structure is a special case from Graph structure.
- In this case it's binary tree.
![3](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/33cd8a13-a1a4-4901-a369-085c3aaef0c1)

##### Graph Structure
- It shows connectivity.
- think of it like u have N users, everyone of them could be connected with the rest of users (N-1)users.
- All these combinations in a structure called Graph structure.
![4](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/1a0eb7b0-a7ec-4b92-88de-b505da0739ce)

#### Warming up:
#### Shifting from "Hello World"-like programs to structured programs
##### Guidelines for choosing variable names:
1. Give special care to the choice of names for functions, and constants.
2. Use common prefixes or suffixes to associate names of the same general category.
3. Avoid deliberate misspellings and meaningless suffixes to obtain different names.
4. Avoid choosing names that are close to each other in spelling or otherwise easy to confuse.
5. Be careful in the use of the letter "I" (small ell), "O" ( capital oh") and "O" (zero).

#### Documentation Guidelines:
##### 1. Place a prologue at the beginning of each function with.
   - Identification (programmer's name, date, version).
   - Statement of the purpose of the function and method used.
   - Pre- and Post conditions.
2. Comment on the use of variables.
3. Introduce each significant part of the program with a statement of purpose.
4. Indicate the end of each significant section.
5. Avoid comments that parrot what code does or that are meaningless jargon.
6. Explain any statement that employs a trick or whose meaning is unclear. Better still, avoid such statements.
7. The code itself should explain how the program works.
8. The documentation should explain why it works and what it does.
9. Be sure to modify the documentation along with the program.

---

#### Stacks: Array-based implementation I
- MAXSTACK should be defined in the User Level.
- For the moment forget about them. We will
mention later how they should be defined.
![0](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/0837b60c-01e6-49d1-a1bf-38df256e3d09)
---
##### CreateStack(&s)
![1](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/ffde05fd-a1b1-443b-8fa6-20c2c2edf0f4)
- This is not the way we gonna use CreateStack() with, because the original stack will remain the same, so we have to pass the stack address to the function and deal with it using a pointer *PS
![2](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/355d6dd2-bf65-42ac-8dd5-47977dd3d03d)
- The execution time doesn't depend on n, therefore the complexity is: θ(1)
- top is the index of the first available place.
---
#### Push(e, &s)
- For now we have created a stack but we don't initialized it yet.
- CreateStack(s) -> for Initializing stack, we already created the stack at the previous step.
- So, we will initialize stack using CreateStack(s), this function exactly initializing stack not creating stack we have already created it in the first step.
- ps->top =0 or *ps.top=0
- ps->Entry[ps->top++]=e : put e on top and increase top by 1
- if top = -1, ps->Entry[++ps->top]=e : increase top by 1and put e on top .
![3](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/772b56ef-dda6-4cfb-bd83-b2b2fa607ea2)
---
- The user has to check before(Pre) and after(post conditions) pushing into the stack.
- Pre: The stack is initialized and not full.
- Post: The element e has been stored at the top of the stack; and e does not change.
![4](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/9c027ebe-237e-490d-acc6-e9fb9c1394a0)
---
#### StackFull(&s)
- We have passed Stack &S by reference to save time and space.
- It could be StackFull(S) but this wastes memory and time of copying.
![5](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/16ee2d36-08dd-4bd6-bca9-3f2bfd1e7310)
---
#### Pop(&e, &s)
![6](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/da4a775d-10d8-4ed6-8bd8-0acc1c770e3b)

---
- Let's take a look at Pre and Post conditions for Pop from the stack.
- Pre: The stack is initialized and not empty.
- Post: The last element entered is returned.
![7](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/ab2543a2-b4f9-4d1b-9ce4-b524c51abf09)
---
#### StackEmpty(&s)
![8](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/18220e85-7ec9-4afa-92dc-3d24fa68e3cc)

---
#### StackTop(&e, &s)
![9](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/37a3434b-fc1a-4731-8b1f-c2af663d7675)

---
#### StackSize(&s)
- Another accessing mechanism that you are gonna use it as a user when u need to konw the stack size.
![10](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/24e4d6b2-5d6c-4fc3-b9a5-209ce4e07d64)
- Let's take a look at Pre and Post conditions for StackSize.
- Pre: The stack is initialized.
- Post: returns how many elements exists.
---
#### ClearStack(&s)
- Let's take a look at Pre and Post conditions for StackSize.
- Pre: stack is initialized.
- Post: destroy all elements. (stack looks initialized).
![11](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/52761b76-c1a1-48ca-92f9-2cabf4d6315a)
---
#### TraverseStack(&s, &Display)
- Pre: The stack is initialized.
- &s only for efficiency as said before.
![TraverseStack](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/133ee22c-91db-4539-80cf-bf0b9e41e95b)
---
#### StackTop(&e, &s)
- How to write the function StackTop in the user level? (e.g., if you do not have the source code of the implementation)
![StackTopUserLevel](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/168e149a-c517-4eb9-b3b8-c9994f340948)

##### Why interface, Pre, Post are crucial: 
- Pop takes a pointer to the element and a pointer to the stack.
- Pre: The stack is initialized and not empty.
- Post: The last element entered is returned.
![StackTopPop](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/a47121c3-317a-43e8-b18e-32d443db5393)
![StackTopPop_](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/5375c8a2-ea21-4f2a-bdb8-4f1c14c51ff7)

- Push takes the element itself and a pointer to the stack
- Pre: The stack is initialized and not full.
- Post: The element e has been stored at the top of the stack; and e does not change.
![StackTopPush](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/e77cdf4e-7d80-46fe-80de-b78cde9f5415)
![StackTopPush_](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/c624d672-8129-4384-ac20-7f74d51db24e)
