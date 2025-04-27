# Todo List App

A simple, client-side to-do list application that helps you keep track of tasks directly in your browser. All data is persisted using `localStorage`, so your tasks remain even after you close or refresh the page.

## Features

- **Add Tasks**: Enter a task description and hit **Enter** or click **Add** to save.
- **Edit Tasks**: Click on a task’s text to modify it; changes are saved automatically when you click away.
- **Complete / Uncomplete**: Toggle the checkbox to mark tasks as done or undone.
- **Delete All**: Remove all tasks at once with a single button.
- **Task Count**: Displays the total number of tasks currently in your list.

## File Structure

```
/ (project root)
├─ index.html      # Main HTML structure and container for the app
├─ styles.css      # Styling for layout, flexbox, and disabled task state
├─ script.js       # JavaScript logic for CRUD operations and localStorage
└─ README.md       # This documentation file
```

## How It Works

1. **Data Persistence**: On load, the app reads the `todo` array from `localStorage` (or initializes it empty).
2. **Adding Tasks**:
   - Reads the input value (`todoInput.value`).
   - Trims whitespace; if non-empty, pushes a new object `{ text, disabled }` into the `todo` array.
   - Saves back to `localStorage` and re-renders the list.
3. **Rendering (`displayTasks`)**:
   - Clears the list container.
   - Iterates over `todo`, creates a flex container for each item with:
     - A checkbox (`.todo-checkbox`) bound to the `disabled` state.
     - A clickable `<label>` or `<span>` showing the task text (uses `onclick="editTask(index)"`).
   - Attaches event listeners for toggling completion and editing.
4. **Editing Tasks**:
   - Replaces the text element with an `<input>` for inline editing.
   - On blur, updates the text in the array, saves, and re-renders.
5. **Toggling & Deletion**:
   - Checkbox toggle flips `disabled`, saves, and re-renders.
   - Delete All clears the array, saves, and re-renders.

## Customization

- **Styles**: Modify `styles.css` to change colors, fonts, or layout. By default, `.todo-container` uses `display: flex;` for horizontal alignment.
- **Storage Key**: Change the `localStorage.getItem("todo")` key in `script.js` if you need a different namespace.

## Browser Support

Tested on the latest versions of Chrome, Firefox, Edge, and Safari. No external dependencies are required.

## License

This project is released under the MIT License. See [LICENSE](LICENSE) for details.

---

*Keep track of your day, one task at a time!*

