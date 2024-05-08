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
### Stacks applications: Polish Notation
- Polish Notation: application on stacks.
- We read and write Infix, however we compute in Postfix !!
- Computer has to convert to, e.g., Postfix before evaluation.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/3c397b14-0e7e-4e0f-8d11-eb1ac998ce5c)
---
- How do we really do it?
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/a931688c-9888-4ec7-9c09-560b4b65b93f)
---
- InfixToPostfix.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/776798d7-c6e8-4fca-a7df-f55773176d12)
---
- Obvious Limitations:
1. Only single digit integers.
2. Only positive integers.
3. No unary operators allowed.
4. No brackets !!!
5. No handling for invalid expr.
- Extra operators.
- Invalid Ordering.
6. No characters allowed.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/9ba71b44-8fd3-4a75-98ca-2ab6a363841b)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/0ae2ebb4-8d4d-47c4-802f-ed057a64fb3b)
---
- Big Surprise!
- We cannot combine both routines, InfixToPostfix and Evaluate Postfix, in a single program because of different element types!!!
- Solutions will be provided in: ("Abstraction and Implementation Related Issues").
- Until we reach it, a good programming style to cope with different types and configurations is via compiler directives, e.g., #define, #ifdef, ...
- This way, you will change only a single line of code instead changing the whole Stack.h.
![7](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/3235f5be-cc5f-4b89-bc1e-437393875e1b)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/e2238143-de7f-405f-a2fd-5d7252e2b9ad)
---
### Queues: Array-based implementation
##### Motivation: Why Queue? First In First Out (FIFO)
- In a queue,
- new values are always added at the rear of the list.
- values are removed from the opposite end of the list, the front.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/bb0e325b-8cbd-4c56-8bad-2ff08b0a3cb5)
##### Examples of queues
- checkout at supermarket
- Toll Station
Car comes, pays, leaves
- Check-out in Big super market
Customer comes, checks out and leaves
- More examples: Printer, Office Hours,
---
##### E.g., Printing Queue
- A.doc, B.doc, C.doc arrive to printer.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/81d30386-d698-422b-8369-e5feea13cc09)
---
##### Array Implementation1: Physical Model (Front is fixed as in physical lines)
- Shifting all items to front in the array when dequeue operation. (Too Costly...)
- Why this was not a problem in the array implementation of Stacks?
- Because we were dealing with top.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/f494e9c0-bc54-4785-9a2b-b57e13238eb7)
---
##### Array Implementation2: Linear Model (Two indices, front and rear) 
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/c1110e1d-66fe-4ee9-bac9-b707d8e68198)

- The problem is that there will be many empty places in the front of array and rear is always incremented.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/dba004b5-26c5-4760-b875-43027d262fc5)

---
##### Array Implementation 3: Circular Implementation
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/96cb0cff-a052-4548-8857-e3bab30ebb41)

---
##### Checking the boundary conditions
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/370f5157-534c-4b9c-889a-74dd6fda72c3)

- Better solution: Use indicator variable to distinguish between Empty and Full conditions.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/da02dbb3-b66b-48e6-90b5-137419e16629)

---
##### Again: Definitions, where every thing should start from!
- Definition: type is a set of values and a set of operations on those values.
- Example: We can define a datatype boolean that takes the set of values {0, 1} together with the operations AND, OR, and NOT.
- Example: int, in C, is the set consisting all of the integers between INT MIN (-(2^15 — 1)) and INT MAX (2^15 – 1), which are defined in the header file limits.h
- Definition: A Sequence of length 0 is empty. A sequence of length n ≥ 1 of elements from a set T is an ordered pair (Sn- 1,t) where Sn-1 is a sequence of length n-1 of elements from T, and t is an element of T.
- Definition: A queue of elements of type T is a finite sequence of elements of T together with the following operations:
1. Create the queue, leaving it empty.
2. Determine whether the queue is empty or not.
3. Determine whether the queue is full or not.
4. Find the size of the queue.
5. Append a new entry onto the top of the queue, provided the queue is not full.
6. Retrieve the front entry in the queue, provided the queue is not empty.
7. Serve (and remove) the front entry from the queue, provided the queue is not empty.
8. Traverse the queue, visiting each entry.
9. Clear the queue to make it empty.
---
- Queue q;
![12](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/2c308422-c5f2-4f3d-8d1e-4b59d522322d)
---
- CreateQueue(&q)
![13](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/b4816866-0184-4616-9c77-b7ac0f0dda67)
---
- Append(e, &q)
![15](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/71014ac6-2b36-4eb5-a8ff-d06c94704239)
---
- Serve(e, &q)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/348663d6-bb16-438c-886d-b4ebf4fdbcf5)
---
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/01f14b5d-cbf9-44c4-abd8-d62f950a0c00)

---
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/427cb978-548e-42cd-8598-3bea1a2c3bed)

---
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/a74725d4-66aa-4c96-8a25-70c55056db98)

---
### Queues: Linked-based implementation
##### Linked Queues (to overcome fixed size limitations): Just get the idea now, do not worry about details.
![1](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/f8f4ff54-29f1-4e82-b28f-7131085d557b)

---
#### How to insert a node.
![2](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/8640878f-0dc5-48a6-8f24-16c9b7cdb87a)

---
#### How to serve a node.
![3](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/4809c6e2-45ad-42d6-be27-3adcddcecc05)
![4](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/2387a212-ebbd-40cc-a6e2-4c23d3f8a665)

---
#### Type Definition:
![5](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/148a3727-e201-481e-957f-4de349ff29ae)

---
#### CreateQueue(&q)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/079ddbee-4201-435b-ac7d-6881eb46f42f)

---
#### Append(e, &q)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/bf1af1d7-dc8d-4332-96ba-7849c994994a)
- Always take care of special cases(queue is empty)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/4f3bad34-a2da-45d4-888b-aa97a5b48c7b)
---
#### Serve(&e, &q)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/eb48938b-908f-4d06-b4ec-2fe76bddeac9)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/4c209dff-116a-42cf-8f26-dd7704260e1b)
- Always take care of special cases: Only one element exists.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/cef94c96-60be-44ef-9173-99e5a1334b60)
---
#### QueueEmpty(&q), QueueFull(&q), QueueSize(&q)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/087b9006-3554-4a5e-b330-e589298b568e)

---
#### ClearQueue(&q)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/818fd8ac-fc92-49e5-afb9-bce34d4fb7a9)

---
#### TraverseQueue(&q, &pf)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/41ce887a-d3a6-4130-a0a3-af89f1d501e7)

---
- Very important note for all linked structures. E.g., in Queues: In Push and Append we have to check for exhausted memory. The code can be modified to:
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/87ad8fb9-a04c-4c45-82a2-09f963ad5daa)
---
### Abstraction & Implementation-Related Issues
- How to use a queue, a stack, and other data structures with the same element type in the same program?
- Since the element type of the stack, queue, and the main program is the same, we need to be more structured define this common element type in a separate file Global.h. In this file we should have all the definitions that are common to all of the three modules;
![1](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/fd20bd60-1d97-440a-9d64-6d2e33ca2c75)
---
- Stack.cpp must include Stack.hand the latter includes Global.hwhy?
- Queue.cpp must include eue.h and the latter includes Global.h.
- Finally, Main.cpp includes all the three header files; why?
- However, this will cause a "redefinition" error since the definitions in Global.hwill appear again in the other two included header files because they also include Global.h.
- To resolve this problem, we need to start Global.h by:
![2](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/7d19ed62-09de-4cec-b836-9799e3e4e9d0)
- These statements are "Preprocessor Commands" that are processed before compilation. More explanation will be provided in labs; you can also refer to your C language text book.
---
#### Notice that:
- Each of the previous definition starts with "...of elements of type T is a finite sequence of elements of T together with the following operations:". it is apparent that Stacks, Queues, and Lists differ only in the set of operations defined on each of them.
- The method of implementation is NOT mentioned in the definition.
- The interface of the ADT (the header file in case of C programming, along with the pre- and post-conditions of the functions) defines the contract between users and implementers that provides a precise means of communicating what each can expect from the other.
---
- How can we selected among different implementations?
- Should information about the efficiency of implementations be included in the interface so that the user chooses between different complexities (of course without letting him involved in the implementation details)?
- Possible Solution:
- Tell the user to write in Queue.h the following if he cares about memory utilization than speed
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/f56824d3-8477-4c22-9a32-80e09c3df2eb)
- Then, in Queue.cpp write the two implementations of Queue with the following pre-processor:
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/d8c52b76-cf6a-4bba-9b65-e6ffb5ce2525)
---
- What about hiding the type definition from the header files?
- Possible Solution: we define the stack to be pointer to struct; this struct will be defined only in the stack.cpp
![5](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/f017d0f8-4d29-493f-86ef-c4f71625e657)
---
- The only difference will be in the functions that change ps; namely, CreateStack and ClearStack.
![6](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/7db9d92e-0148-458a-be8d-532800a637a0)
---
- What about using different element types in the same ADT? For example, StackEntryl and StackEntry2?
- Imagine!! So far we cannot use:
- more than one stack with different homogeneous element type.
- or even, a single stack of non- homogeneous element types.
- Solution 1: (but very un-smart)
- Combine the fields of the different possible types in one data type.
- Add an extra field, name it etype, and give it a code for every type.
- Then, it is the responsibility of the user level to check for etype.
![7](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/10cdd0bb-a822-48f3-8bf6-5e7b27f7eda1)
---
- Solution 2: (Unions to save memory)
![8](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/7eae12b8-15f7-47d8-ad42-9d06d46468e1)
---
- Solution 3 (much smarter): not only solves the issue but also allows commercializing Stack.obj without the dependency on Stack.h
- Notice: Push calls malloc(sizeof (StackNode)) and StackNode contains StackEntry, which was compiled already into Stack.obj. If the user defines another StackEntry in Global.h this will cause a runtime problem! (Try it home).
- The solution, allows user for using both:
- more than one stack with different homogeneous element type.
- or even, a single stack of non- homogeneous element types.
---
![10](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/9511880a-64e9-4abd-a2f0-ec889280a2bd)

---
- Solution 4 (most efficient solution): using C++ (OOP language) supporting the definition of an object of undetermined type known by Templates:
![11](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/7b79e661-52ef-4c81-8a3d-89f34922918d)
---
- More subtle issues and some answers: We just open the door for deeper thinking and robust design.
- Much more of these issues are out of the scope of our course. They are classified as low-level Software Engineering aspects.
- Also, solutions to these raised issues are language dependent. E.g., the definition of the structure completely disappeared from the header file by defining a pointer to an undefined structure. In some languages, e.g., Java, this is not available since there is no pointers.
- However, the student should be aware of them at the level that we discussed here.
---
### Lists Array-based implementation
#### Motivation:
##### Why Lists?
- In a general list:
- new values are added in position determined by the user.
- Element is removed from a position determined by the user.
##### Important notice:
- if we keep adding and removing from the first position (the head of the list) the general list will behave as a stack.
- If we keep adding from one end and removing from another end the list will behave as a queue.
##### Application:
- In queues, sometimes we need a priority for some elements. We may need to put an emergency call prior to others.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/2fe6cef3-8597-4b8a-a9f1-e41bc4630b8e)
---
- Definition: A general list of elements of type T is a finite sequence of elements of T together with the following operations:
1. Create the list, leaving it empty.
2. Determine whether the list is empty or not.
3. Determine whether the list is full or not.
4. Find the size of the list.
5. Insert a new entry in the position 0 ≤ p ≤ size.
6. Delete an entry from the position 0 ≤ p ≤ size-1
7. Traverse the list, visiting each entry.
8. Clear the list to make it empty.
---
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/97199239-5fa7-4872-802b-99db19ae40a3)

---
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/6a78a560-6a7c-47ea-8771-515c3d32b5a6)

---
#### InsertList(p, e, &l)
- Let's take a look at pre-conditions and post-conditions for InsertList.
- Precondition:
1. The list pl has been created.
2. not full.
3. 0 <p< size.

- Postcondition:

1. e has been inserted at position p.
2. all elements at old positions p, p+1, ..., size-1 are incremented by 1.
3. size increases by 1.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/3d0f9b10-32b6-4021-ad22-bd2b17730b88)
---
#### DeleteList(p, &e, &l)
- Let's take a look at pre-conditions and post-conditions for DeleteList.
- Precondition:
1. The list pl has been created.
2. The list pl is not empty.
3. 0≤ p ≤ size-1.
- Postcondition:
1. e has been retrieved from position p.
2. All elements at old positions p+1, ..., size-1 are decremented by 1.
3. size decreases by 1.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/343378f8-1989-4c61-85c4-43e41bd1bf9f)
---
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/4b003c83-c023-4199-a9bf-a32b351c247b)

![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/f08b7a3b-2f83-4e76-bee2-e52d77f581c0)

---
- Issues at the user level:
- How to insert at the beginning of the List?
- InsertList (0, e, &1);
- How to insert at the end of the List?
- InsertList (ListSize(&l), e, &1);
- How to use it as a stack?
- If we keep adding and removing from the first position (the head of the list).
- Insert at last and pop from it.
- How to use it as a queue?
- If we keep adding from one end and removing from another end.
- Insert at rear and pop from front.
---
### Lists: Linked-based implementation
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/052ddd95-9595-4640-9b17-ad1c105937ed)

---
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/ca0e1434-8232-4fcd-80b6-8609fe8457a0)

---
#### CreateList(&l), ListEmpty(&l), ListFull(&l), ListSize(&l)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/9ccc7516-446c-4f38-89f4-7817f01784b3)

---
#### DestroyList(&l), TraverseList(&l, &Visit)

![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/05fab853-b96e-4ef9-a31e-51d00f41fa17)

---
#### InsertList(pos, e, &l)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/b6bfb253-a6cb-4d61-a415-d72221690f50)

---
#### DeleteList(pos, &e, &l)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/717f1feb-3bcf-4232-82be-72865b3d3ec8)

---
#### RetrieveList(pos, &e, &l), ReplaceList(pos, e, &l)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/dd7ae9ff-01ff-4ea7-b586-5e670e9ab1f1)

---
- Comparison between the array-based and the linked implementation: "Which is always better?" is a wrong question!
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/25ccbde8-6584-4731-aefb-97595bdf9b15)
- InsertList is very time consuming for Array-based because of copying elements, especially if the elements are large records.
- RetrieveList and ReplaceList are always better for contiguous implementation.
- Read the book very well.
---
- Design Enhancement: Learn how you modify your design to enhance the performance.
- Many applications processes the entries in order, i.e., moving from one entry to the next.
- Many other applications refer to the same entry many times.
- Then, our current linked implementation is very inefficient, since it moves from the head to the element every time!
- Then, we need to remember the last position currentpos and start navigating from it, and we use current to start walking from currentpos.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/0622ff89-b473-46a0-acc8-b5714215a646)
- Of course, this will not help if the new element is preceding the last element visited.
- Only the type definition, InsertList, DeleteList, ReplaceList, and RetrieveList will change.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/abf979bb-758f-4fd5-8bd2-65efaba9ddbc)

---
- Let's modify InsertList.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/c0d34e55-423c-48a6-a6ad-e344f304a6dc)
---
- Let's modify DeleteList.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/15b4dacb-244d-4117-abd0-1a539fab41fd)
---
- You have to modify ReplaceList and RetrieveList in the same manner. (Do it as a homework). Check also for other functions, e.g., CreateList (for initialization)
- Compare the previous functions to the functions of the book, where it has a function Set Position that is called from within InsertList and DeleteList.
- Having this function may simplify the code for the case of having current and currentpos.
---
- Design Enhancement: Learn how you modify your design to enhance the performance.
- Accessing the list at a position preceding currentpos will be slow, since we cannot move back. A possible remedy is using doubly linked list.
- We need just a pointer, current, not necessarily point to the first node. currentpos will always indicates the order of the current node.
- Read the code from the book and solve the review problems.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/ba967443-12e1-46eb-b7e6-df1da479d62c)
---
### Search and Analysis of Algorithms
#### Motivation: Why Search?
- To find things.
- We will be concerned only with internal searching in the memory, i.e., in data structures not in external searching in secondary memory, i.e., in files. Nevertheless, there is a strong relationship.
- Of course we assume that each element has a key to be used for searching. To have our code as general as possible we do not write the code for particular data type.
- Always, think generally before you start coding; this is to minimize upgrading and modifying your code later on.
- Our purpose is to study data structures not algorithms, but we want to see the deep connection between both through studying sequential and binary search.
- Let us see the implementation in C.
---
#### TypeDefinition:
![2](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/45958b95-1d35-43c6-9717-8343c7c7680e)

---
#### SequentialSearch()
- Let's take a look at pre-conditions and post-conditions for SequentialSearch.
- Precondition: List is created.
- Postcondition: Return the location if element exists O.W return -1.
- This code is implementation-independent.
![3](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/383c5ebf-d8fe-4372-8d32-3f86989b6905)
---
#### Analysis Of Algorithms:
- Definition: The behavior of a key-comparison (because there are other searching techniques) searching algorithm is measured in number of key comparisons.
- Sequential search: From the previous algorithm it is obvious that if the element is in position i, the number of comparisons k is given by:
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/23b3bd4c-bc52-4dd0-a22c-d1dfe2f9db19)
- k in any algorithm is a random variable whose mean (average) depends on the distribution of the data. The mean is given by:
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/10ab229a-44a5-400d-9f85-86af1da2d105)
- Then, for any algorithm we have to assume a probability distribution for the data. This is a field by itself known as probabilistic analysis of algorithms. For easier analysis we usually assume uniform distribution, i.e.,
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/1b8b41e4-ddef-4814-a9ad-d5653cdd270e)
- This is what is called in book "on average”; they means on average with uniform dist.
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/aa8b5cea-02a2-4f80-af9f-e5942c026147)
- The worst case scenario is when the search is unsuccessful or the element is in last entry. In this case the number of comparisons is n
- The best case is when the element is in the first position, then the number of comparison is 1.
#### For unsuccessful search:
- There is only one case of unsuccessful search that takes n comparisons.
---
#### Binary Search
- Can we speed up the search time? We will assume that we will search in an ordered list.
- Definition: An ordered list is a list in which each entry contains a key, such that the keys are in order. That is, if entry i comes before entry j in the list, then the key of entry i is less than or equal to the key of entry j.
- This requires replacing the Insert List with InsertOrder. See the connection between enhancing the algorithms and designing the data structures.
- We will consider only the second implementation of Binary search, i.e., Binary2 Search. Read the first version from the book.
- Let us first write InsertOrder.
---
#### InsertOrder()
- Let's take a look at pre-conditions and post-conditions for InsertOrder.
- Precondition: List is created, not full and ordered.
- Postcondition: E inserted in order. if the new element has a key equal to an element in the list it will be inserted before it.
![7](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/a060022c-0629-48bb-bbe2-ebf49daf41fd)
- The following representation is from Knuth "The art of computer programming" (Sec. 6.2.1):
![8](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/a3c1c37f-4d2a-4379-93a3-7e136c69e2e2)
![9](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/d88709b4-6406-42d6-ab4a-88c0d2b803fb)
- It looks recursive; let us try it. The interface has to be:
##### int RecBinary2Search (KeyType, List *)
- However, it seems from the table that we need to specify the start and the end.
- indices. Therefore, we have to write another recursive function and call it in the above.
---
#### BinarySearch()
- Let's take a look at pre-conditions and post-conditions for BinarySearch.
- Precondition: List is ordered.
- Postcondition: Location returned, O.W. return -1
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/41fe2592-a89f-4b2f-bf4f-bc037edcf98c)
---
#### RecBinary2Search (KeyType, List *)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/1ba0c8ca-5581-40f1-b585-f151af653676)

---
- Let's try it but this time without using stack for wasting of memory, we'll make it iterative...
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/4d78154f-6d8d-4648-bc90-b821678950d8)
---
#### Comparison between recursive and iterative side-by-side
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/deb35b18-4c75-4c2e-96f8-9bb16d83078d)

---
- Another important connection between algorithms and data structures is this. Binary Search is suitable only for the contiguous implementation. However, if we have to place the data in a linked structures (linked list) and be able in the same time to fasten the search what should we do?
- This will be achieved by implementing the linked list as a binary tree as we will see later (Ch. 9). To see the connection let us see first how we analyze binary search. The idea comes from analyzing the binary search for contiguous implementation.
- The analysis of Binary Search requires basic definitions and mathematical relations for trees as a mathematical structure NOT yet an ADT data structure.
![14](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/7c10553b-5e45-4071-a441-600f84e65185)
---
#### How the different topics are related to each other(Different order of study)
![image](https://github.com/A8N0RMAL/Data-Structures-With-C/assets/119806250/5fad71d1-aae6-40af-831a-5787e79101fe)

---
