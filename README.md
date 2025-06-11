# Add_To_do_using_HTML_CSS_JS

# 📝 Simple Todo List (Vanilla JS)

This is a **minimalistic Todo list app** built using **pure HTML and JavaScript**.  
It allows users to add and delete tasks dynamically using unique IDs.

---

## 🔧 Features

- ✅ Add tasks via input field
- 🗑️ Delete individual tasks
- 🔢 Each task has a unique ID (e.g., `todo-1`)
- ⚡ Built using basic JavaScript DOM manipulation

---

## 📂 Project Structure


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Simple Todo App</title>
</head>
<body>
    <h2>Simple Todo List</h2>
    <input type="text" placeholder="Enter a task">
    <button onclick="addTodo()">Add Todo!</button>

    <script>
        let ctr = 1;

        function deleteTodo(index) {
            const element = document.getElementById("todo-" + index);
            element.parentNode.removeChild(element);
        }

        function addTodo() {
            const inputEl = document.querySelector("input");
            const value = inputEl.value.trim();

            if (value === "") {
                alert("Please enter a task!");
                return;
            }

            const newdivEl = document.createElement("div");
            newdivEl.setAttribute("id", "todo-" + ctr);
            newdivEl.innerHTML = "<div>" + value + "</div><button onclick='deleteTodo(" + ctr + ")'>Delete</button>";

            ctr += 1;
            document.body.appendChild(newdivEl);

            inputEl.value = ""; // Clear input
        }
    </script>
</body>
</html>
