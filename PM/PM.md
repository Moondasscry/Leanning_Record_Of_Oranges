# Corresponding Code File  
**PM.asm**

# Brief Description  
**PM.asm** is an assembly language program designed to explore and demonstrate key concepts related to the **CPU's protection mode**.
It serves as a practical implementation to understand the mechanisms of protected mode operation, privilege management, and task scheduling.

### Main Features:  
1. **Enter Protection Mode**  
   - The code demonstrates how to transition the CPU from **real mode** to **protected mode**.  

2. **Implement Privileged Segment Switching**  
   - It includes functionality to switch between **privileged segments** (e.g., kernel and user segments),
   -  showcasing how the CPU enforces access control and privilege levels.  

3. **Implement Priority Scheduling for Local Task Switching**  
   - The program incorporates a basic **priority-based scheduling mechanism** to manage and switch between local tasks,
   -  illustrating how the CPU handles multitasking in protected mode.  

---

### Key Learning Objectives:  
- Understanding the **CPU's protection mode** architecture.  
- Exploring **segment-based memory management** and **privilege levels**.  
- Implementing a simple **task scheduler** to manage multiple tasks.  

---

### Relevent Q&A:  

#### Q1 Why the code in the clock handle that come after the **jmp** instruction still get excuted

```text
The code after jmp in your clock handler executes because the jmp SelectorTSS1:0 saves the current task’s state (pointing to .back_1) and suspends it,
rather than terminating it. When a later clock interrupt switches back to the original task,
execution resumes from that saved point, running popad and iret to clean up and return.
```
---
