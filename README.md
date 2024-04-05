# TO-DO-LIST
Add and delete tasks
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>To-Do List</title>
<style>
  body {
    font-family: Arial, sans-serif;
    background-color: pink;
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }
  #container {
    background-color: #fff;
    border-radius: 5px;
    box-shadow: 0 2px 5px rgba(27, 13, 76, 0.1);
    padding: 20px;
    width: 300px;
  }
  h1 {
    text-align: center;
  }
  input{
    width: 280px;
    padding: 10px;
    margin-bottom: 10px;
    border-radius: 3px;
    border: 1px solid #ccc;
    font-size: 16px;
  }
  button {
    padding: 10px 20px;
    border: none;
    background-color: #4caf50;
    color: #fff;
    font-size: 16px;
    border-radius: 3px;
    cursor: pointer;
  }
  button:hover {
    background-color: #45a049;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    background-color: #f9f9f9;
    padding: 10px;
    border-radius: 3px;
    margin-bottom: 5px;
    display: flex;
    justify-content: space-between;
  }
  .delete-btn {
    background-color: #f44336;
    color: white;
    border: none;
    border-radius: 3px;
    cursor: pointer;
  }
  .delete-btn:hover {
    background-color: #d32f2f;
  }
</style>
</head>
<body>

<div id="container">
  <h1>To-Do List</h1>

  <input type="text" id="taskInput" placeholder="Enter task...">
  <button onclick="addTask()">Add Task</button>

  <ul id="todo-list"></ul>
</div>

<script>
function addTask() {
  var taskInput = document.getElementById("taskInput");
  var taskText = taskInput.value.trim();

  if (taskText !== "") {
    var listItem = document.createElement("li");
    listItem.textContent = taskText;
    
    var deleteButton = document.createElement("button");
    deleteButton.textContent = "Delete";
    deleteButton.className = "delete-btn";
    deleteButton.onclick = function() {
      listItem.remove();
    };
    
    listItem.appendChild(deleteButton);
    document.getElementById("todo-list").appendChild(listItem);
    taskInput.value = "";
  } else {
    alert("Please enter a task!");
  }
}
</script>

</body>
</html>
