# Thing1 / Thing2 Runner – Java OOP Demo

A small Java project showing how multiple classes in separate files work together through a `runner` class, plus a `TODO.md` board for simple team project management.

## Files

| File | Role |
|------|------|
| [Thing1.java](Thing1.java) | Class with a **static** method `print()` |
| [Thing2.java](Thing2.java) | Class with a **non-static (instance)** method `print()` |
| [runner.java](runner.java) | Entry point (`main`) that uses both classes |
| [TODO.md](TODO.md) | Task board (Todo / In Progress / Done) |

## OOP Concepts Highlighted

- **Multiple classes, multiple files** – each class lives in its own `.java` file and is compiled together.
- **Static vs. instance methods**
  - `Thing1.print()` is `static`, so it is called on the class itself: no object needed.
  - `Thing2.print()` is an instance method, so you must create an object first: `new Thing2()`.
- **Objects and instantiation** – `Thing2 t2 = new Thing2();` creates an object, then `t2.print();` calls its behavior.
- **Encapsulation / separation of responsibilities** – each class owns its own output; `runner` only coordinates.

```java
public class runner {
    public static void main(String a[]) {
        Thing1.print();            // Static: called on the class
        Thing2 t2 = new Thing2();  // Non-static: create an object first
        t2.print();
    }
}
```

## Run It

```bash
javac *.java
java runner
```

### Output

```text
Im thing 1ß
Im thing 2
```

> Screenshot: save a terminal capture of the output above as `docs/output.png` and embed it with
> `![Program output](docs/output.png)`.

## TODO Extension (CODDX)

Task tracking uses the **TODO** extension by CODDX for VS Code:
<https://marketplace.visualstudio.com/items?itemName=coddx.coddx-alpha>

1. Open VS Code → Extensions (`Cmd+Shift+X`).
2. Search for **TODO by CODDX** (`coddx.coddx-alpha`) and click **Install**.
3. Open [TODO.md](TODO.md); the extension displays it as a Kanban board.
4. Drag cards between **Todo**, **In Progress**, and **Done**.

> Screenshot: add a capture of the board as `docs/todo-board.png` and embed it with
> `![TODO board](docs/todo-board.png)`.

The board is stored as plain Markdown, so it is committed and shared through Git like any other file:

```markdown
### Todo
- [ ] String manipulation function

### In Progress
- [ ] Create string madlib

### Done ✓
- [x] Assign parts to each member
```

## Simple Project Management Instructions (for Students)

Use `TODO.md` to create tasks and assign them to team members.

### 1. Set up
1. One teammate creates the GitHub repository and adds the others as collaborators.
2. Everyone clones it: `git clone <repo-url>`
3. Everyone installs the TODO (CODDX) extension.

### 2. Create tasks
Add a line under `### Todo` for each piece of work, with the owner's name in brackets:

```markdown
### Todo
- [ ] [Alex] Write Thing3 class with a constructor
- [ ] [Sam] Add a method to runner that calls Thing3
- [ ] [Jordan] Write README output section
```

Keep tasks small enough to finish in one sitting.

### 3. Work a task
1. Move your task to `### In Progress` (drag it on the board or edit the file).
2. Write and test your code (`javac *.java && java runner`).
3. Move the task to `### Done ✓` and change `[ ]` to `[x]`.

### 4. Share your work
```bash
git pull                       # get teammates' changes first
git add .
git commit -m "Alex: add Thing3 class"
git push
```

### Team rules
- One owner per task.
- Pull before you start and before you push.
- Only edit your own task lines in `TODO.md` to avoid merge conflicts.
- Review the board together at the start of each work session.
