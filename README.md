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

### Why Data Structures
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

### Warming up:
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

### Stacks: Array-based implementation
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
---
- StackEntry and MAXSTACK should be defined in the User Level, because they concern the uer.
- Also, they have to be defined in the implementation level, because they are referenced in Stack.cpp
- Therefore, they have to be defined in Stack.h which is included in both Stack.cpp and the user main file.
- So, the main file will compile even if stack.cpp is not compiled yet.
![Stack h](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/52025350-be82-4628-908f-b4638ac2db08)
---
### Stacks: Linked-based implementation
- Linked stacks (to overcome fixed size limitations), Just get the idea now, don't worry about details.
![1](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/0d8d52c0-7da5-4aa7-a3e9-ebfa8d6927e2)
---
- Let's take a look at how to insert a node(graphically for now).
![2](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/79ed9096-edf9-4d29-ad01-49f03b9f0214)
![3](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/b808f7af-7ed8-4a18-8627-06ddf9b3f3b1)
![4](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/260ad052-807e-43ad-b098-dba73877327d)
---
- Let's take a look at how to delete a node(graphically for now).
![5](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/c1dfa439-c1dc-452d-8ff1-4345ec15190d)
![6](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/8a56f180-da2f-412c-b217-537117602fad)
---
- Type Definition:
![7](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/c7a8f71d-b134-44aa-bee6-fdc791bed177)
- Why not? Typedef StackNode *Stack;
1. To make logical distinction between the stack itself and its top, which points to a node.
2. To be consistent with the definitions of other DS.
3. For upgradability (adding more functions) that may need other other pieces pieces of information to be saved than top. (we will see).
---
#### CreateStack(&s)
![9](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/86c0311f-5ff5-47b3-8227-8e651bc14398)

- The execution time doesn't depend anything, therefore the complexity is: θ(1)
---
#### Push(e, &s)
- Let's take a look at Pre and Post conditions for Push.
- Pre: The stack exists and it is initialized.
- Post: The argument item has been stored at the top of the stack.
- pn is just a temporary pointer holding the location of stack node to free it(Considering to OS this place is free).
![10](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/cc2ba0b2-855e-493e-b7a4-0599e867f020)
![11](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/b053baf5-0093-4d8e-8cb2-c2b9dc48fd5c)
![12](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/88363a6e-6e4e-4cd0-a6f5-a3941179f87d)
---
#### Pop(&e, &s)
- Let's take a look at Pre and Post conditions for Pop.
- Pre: The stack exists and it it not empty.
- Post: The item at the top of the stack has been removed and returned in *pe.
![13](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/ae1c3a56-bb03-4131-a704-df78a10f79ab)
![14](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/33e5f151-d848-48af-8bfc-22fd8ce4a4fd)
![15](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/e7e7757c-118b-4835-9237-ebb8c723bed5)
---
- Always take care of special cases: If you have just one element:
![16](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/1f3d39e6-54c3-4b05-855f-703b74093ed8)
![17](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/c5f43a57-d0b3-43bf-a4b9-14eb9c5f55d5)
---
#### StackEmpty(&s)
- Let's take a look at Pre and Post conditions for StackEmpty.
- Pre: The stack exists.
- Post: returns the status, 1 or 0.
- Complexity is: θ(1).
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/6b6178eb-8d18-4222-87f7-6118b8756168)
---
#### StackFull(&s)
- Let's take a look at Pre and Post conditions for StackFull.
- Pre: The stack exists.
- Post: returns the status, 1 or 0(In this case it is always 0).
- Complexity is: θ(1).
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/968d732b-f04a-4646-8811-ab864d19def2)
- For any function that does not change the stack there is no problem in passing the stack itself s rather than a pointer to it ps. This will not copy the elements as opposed to the array-based implementation. However, of course, we do not do that to keep the code at the user level unchanged.
---
#### ClearStack(&s)
- Let's take a look at Pre and Post conditions for ClearStack.
- Pre: The stack exists.
- Post: All the elements are freed.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/a7447c66-1d22-489c-b118-a9c6af5b6162)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/a2ef3889-1835-4101-84fb-7fa9f51bd3a7)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/cc31caac-1c7d-4b49-85de-cc08b0c8f574)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/4908bf5d-2f31-45b4-b71f-0ade0e354eb1)
- You can replace qn by ps->top
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/1e1cfa4d-d500-4927-8d75-45a36aa32861)
- Complexity is: θ(N).
- Total time = N * time of one loop.
---
#### TraverseStack(&s, &pf)
- Let's take a look at Pre and Post conditions for TraverseStack.
- Pre: The stack exists.
- Post: Function is passed to process every element.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/cab1f7cc-4abe-4cf7-a5c8-ccb87f94dc3a)
---
#### StackSize(&s)
- Let's take a look at Pre and Post conditions for StackSize.
- Pre: The stack is initialized.
- Post: returns how many elements exists.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/f4ba1d01-f7fa-4063-a1a3-a03dc082c652)
- Comments: This function is (N), i.e., the execution time is proportional to the size! Because, we have to traverse the stack node- by-node to count. (this statement is not precise).
- Can we modify the structure to decrease the complexity of this algorithm?
- We add extra field, called, size in struct stack. Then, we need to add just one statement to: CreateStack, Pop, Push, ClearStack.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/6b01fcaa-5f6b-4187-b8cd-288bfa949f28)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/7dd1ee60-af7e-461e-9f57-eb20f20d644e)
- What happened is that, we added extra field in the data structure, which is size (2 bytes). But, this saves us time by reducing the complexity of the algorithm of the function StackSize.From (N) to (1).
- This is a typical trade-off between time and space.
---
- Comparison between the array-based and the linked implementation: "Which is always better?" is a wrong question!
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/62acb1ed-8f7e-4c91-80cf-5fd86747bc45)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/82a01f22-17da-4d49-bfaa-a0a2c9f1805e)
- Then, there are advantages and disadvantages for every implementation. Which one is better really depends on the application.E.g.,
- If ClearStack is extensively used then, may be array-based implementation is better.
- If the memory is very limited, then may be the linked implementation is better.
- The rule is: Know very well the pros and cons of each implementation and decide based on your application needs.
---
### Stacks applications: Recursion
- Program M starts, then calls A, which calls B, which ends then A calls C...
- All local parameters and return address of each function has to be stored. •Return is in LIFO order.
- Space required is the height of this tree.
- OS has to use a stack to keep track of this storage sequence.
- When a function calls itself, this is recursion.
- Still stack is needed, no difference between A call B, or B calls itself.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/b393ac69-f5b8-41dc-9fba-6a0afd3d80b0)
---
- Applications: Towers of Hanoi, a game of 19th century.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/565ca578-044a-4942-a58c-e05a9a03370a)
#### Solution:
1. To move the largest disk from 1 to 3, we have to move first all others from 1 to 2 !!!
2. Move the largest from 1 to 3.
3. Move all others from 2 to 3.
- Then the solution is:
- MoveDisks (6, 1, 2, 3); "Move disk 7 from 1 to 3′′ MoveDisks (6, 2, 3, 1);
- This is the idea of recursion; define a base step then do the same thing again.
- This is the same concept of divide and conquer: To solve a problem, we split it into smaller and smaller parts.
---
#### Every recursive process consists of two parts:
1. A smallest, base case that is processed without recursion.
2. A general method that reduces a particular case to one or more of the smaller cases, thereby making progress toward eventually reducing the problem all the way to the base case.
void MoveDisks (int count, int start, int finish, int temp);
- Pre Conditions:
- There are at least count disks on the tower start.
- The top disk on each of towers temp and finish is larger than any of the top count disks on tower start.
- Post Conditions:
- The top count disks on start have been moved to finish;
- temp (used for temporary storage) has been returned to its starting position.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/d6d33cc2-6bbb-44fe-ad30-311c816561c4)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/0a9b055d-b46b-448d-bae4-512596d3fa8d)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/974f531b-5fee-47b3-aa12-aba2e2c6dd42)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/43290931-c56c-4eb4-b961-f855e226df58)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/1676e9f3-324a-4763-8692-695cbd762997)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/3ef070d5-7d5c-4002-92cf-9712f1d66a06)
---
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/48d35e8c-711d-441a-873e-6849f6bb3ae7)

- The largest size of the stack until the function returns to the main program is 4. But the number of function calls is:
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/23ff0646-7274-412a-9d30-2d010f676bfd)
- If count = 64 (for example), there will be no stack overflow problem. But the number of steps = the number of function calls (since every function has one printf) = 1.6 E19 !!!
---
- Can we write the function Move iteratively, i.e., not recursively?
- In this case, we will find that we really need to build a stack. We will find that the nature of the problem necessitates that we first solve the problem at size count-1 then return back to the original problem. To return back we had to save it in a stack!
- In such cases defining the problem recursively is much better, since you let the OS build the stack itself which is much more efficient than your stack.
- However, there are some cases in which solving the problem iteratively is better if the iterative algorithm does not need a stack. Hence, solving it recursively builds an unnecessarily stack, which wastes memory and time consumed in function return. Example is the factorial.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/faec35a7-772c-40ae-b30e-496b3efda811)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/6032180a-8a7c-4a64-b63e-e80ec3e95d93)

- The recursive version: First convince yourself that Factorial really returns the factorial except for the base condition:

![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/614a4ebe-aa17-4ee5-9ca3-4f38ed560363)

---
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/cadad480-9e38-4152-9f75-fe2bccbf6093)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/b43da0f2-e542-4812-b70a-8aef9c22a064)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/2b9129ff-8f50-4fe4-a6fb-6a75909a60d5)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/d6f2d7c6-226a-4cfa-9cd1-afc49d99e861)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/5f0ced60-45b7-4bbd-8235-e4445240813c)
- Now:
1. what is the need of this built stack? Why do we exhaust the memory with all these formal parameter?
2. Also, why do we waste the time of function calls and returns. In this case, absolutely the iterative version is faster and more economic in memory utilization.
- The recursion tree is simply a chain, which means that designing the algorithm does not need recursion.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/c62b68ff-1752-41ab-9251-c2ed37eb2231)
---
- More extreme example for un-necessary recursion, the Fibonacci function;
- although many thinks that it is the best example for recursion!!
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/b670fd99-d1b2-438e-aef3-e0e2ee9de918)
- Although the mathematical form of the function itself is recursive (this what tempts some people to code it recursively), however we can find an iterative algorithm for solving it. First, we need to analyze the recursive version.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/4732dbf4-15f8-4062-9249-0db854d46560)
---
- Recursion Tree helps determining whether the recursion is necessary or not.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/525386c5-85ac-42d8-b10a-de98c6d3f99f)
1. The common problems with unnecessarily stack building are:
- waste of time
- waste of memory.
2. For this particular function we have another serious problem, which is needlessly repeating the Fibonacci of many numbers.
- The complexity is exponential, i.e., O(c")
---
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/b4fd540a-db22-4f5c-9085-a9dc6c30d6b7)

---
#### Designing Recursive Algorithms
- Find the key step. Begin by asking yourself, "How can this problem be divided into parts?" or "How will the key step in the middle be done?"
- Check termination. Verify that the recursion will always terminate. Be sure that your algorithm correctly handles extreme cases.
- Draw a recursion tree. The height of the tree is closely related to the amount of memory that the program will require, and the total size of the tree reflects the number of times the key step will be done.
- Find a stopping rule. This stopping rule is usually the small, special case that is trivial or easy to handle without recursion.
- Outline your algorithm. Combine the stopping rule and the key step, using an if statement to select between them, while convincing yourself that the function performs well in the non-base case.
---
#### Execution tree and stack size:
- The OS saves all the parameters of every function and the return address in a stack, so that it returns in LIFO order (See the top of stack in figure).
- The stack size is the depth of the tree.
- The number of calls, which determines the complexity and the execution time, is the number of nodes in the tree.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/4bc63d58-92c5-42a6-8105-dacb84835fb9)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/66c33999-b988-4131-ab96-9cec4d50ae4f)
---
- Tail Recursion : The last statement in a function is a call to itself.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/b2ef8c2f-c88a-4519-a902-be0f81c9461a)
- No need to keep the space of the function in the stack, since it will return to itself. So, just pass the new parameters to the function itself. This reduces the stack size not the complexity of the algorithm.
- This call can be eliminated by reassigning the calling parameters to the values specified in the recursive call, and then repeating the whole function.
##### With tail recersion
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/dda40dbd-af95-4053-8c13-c37f11326374)

---
#### Removing the tail recursion
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/5a8b90ed-e687-4aec-9ca2-1d204403a527)

---
