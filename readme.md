# Task App

This is a simple web-based task management application where users can add tasks to a list.

## Features
- Users can add a task by typing in the input field and clicking the "Add Task" button.
- The tasks are displayed in a table format.
- The app prevents the default form behavior (page refresh) when submitting tasks.

## Structure

### HTML
- The main structure consists of:
  - A table that displays the list of tasks, with a single column labeled "Task Name."
  - A form containing an input field and a button to add a new task.
  
```html
<table>
  <thead>
    <tr>
      <th>Task Name</th>
    </tr>
  </thead>
  <tbody id="tasks">
    <!-- Tasks will be appended here -->
  </tbody>
</table>
```

### JavaScript
- The JavaScript adds interactivity to the app.
- It listens for the `submit` event on the form, preventing the default behavior using `e.preventDefault()`.
- Once a task is added, it is fetched from the input field and appended to the table as a new row.

```javascript
document.querySelector('form').addEventListener('submit', function(e) {
  e.preventDefault();
  var task = document.querySelector('#task-input').value;
  var tasks = document.querySelector('#tasks');
  var newTask = document.createElement('tr');
  newTask.innerHTML = '<td>' + task + '</td>';
  tasks.appendChild(newTask);
});
```

## How to Use
1. Open the `index.html` file in any web browser.
2. Enter a task in the input field and click "Add Task."
3. The task will appear in the table.

## Future Improvements
- Adding a "delete" button next to each task to remove tasks.
- Persisting tasks in local storage so they are not lost on page refresh.
- Adding validation to prevent empty tasks from being added.

---

This file provides a brief yet complete explanation of how the app works. Let me know if you'd like to add more details or features!
