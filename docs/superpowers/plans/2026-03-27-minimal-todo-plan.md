# Minimal Todo App Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a minimal React-based Todo application with a sidebar layout and local storage persistence to demonstrate the AI workflow.

**Architecture:** A pure client-side React SPA initialized with Vite. State is managed via React Hooks and persisted to `localStorage`. Components are split into a Sidebar (for categories) and a Main Content area (for tasks).

**Tech Stack:** React 18, Vite, Tailwind CSS, LocalStorage

---

### Task 1: Project Setup

**Files:**
- Create: `package.json` (via Vite)
- Modify: `index.html`, `src/main.jsx`, `src/App.css`
- Delete: `src/App.css` (we'll use Tailwind)

- [ ] **Step 1: Initialize Vite React project**
Run: `npm create vite@latest . -- --template react`
(Assume this is run in the root directory. If files exist, force or clear them as needed, but for this plan assume clean initialization).
Expected: `package.json` and React boilerplate created.

- [ ] **Step 2: Install dependencies**
Run: `npm install`
Run: `npm install -D tailwindcss postcss autoprefixer`
Run: `npx tailwindcss init -p`
Expected: Dependencies installed, `tailwind.config.js` and `postcss.config.js` created.

- [ ] **Step 3: Configure Tailwind CSS**
Update `tailwind.config.js`:
```javascript
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

- [ ] **Step 4: Add Tailwind directives to CSS**
Overwrite `src/index.css`:
```css
@tailwind base;
@tailwind components;
@tailwind utilities;

body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
    'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
```
Delete `src/App.css` if it exists.

- [ ] **Step 5: Clean up boilerplate App.jsx**
Overwrite `src/App.jsx` with a basic container:
```jsx
import React from 'react'

function App() {
  return (
    <div className="flex h-screen bg-gray-100">
      <div className="flex-1 flex items-center justify-center">
        <h1 className="text-2xl font-bold text-gray-800">Todo App Setup Complete</h1>
      </div>
    </div>
  )
}

export default App
```

- [ ] **Step 6: Commit**
Run: `git add . && git commit -m "chore: setup react vite project with tailwind"`

---

### Task 2: Data Model & Custom Hook (Store)

**Files:**
- Create: `src/hooks/useTodoStore.js`

- [ ] **Step 1: Create the store hook skeleton**
Create `src/hooks/useTodoStore.js`:
```javascript
import { useState, useEffect } from 'react';

const DEFAULT_CATEGORIES = [
  { id: 'cat-1', name: 'Work' },
  { id: 'cat-2', name: 'Personal' }
];

export function useTodoStore() {
  // Initialize state from localStorage or use defaults
  const [categories] = useState(DEFAULT_CATEGORIES);
  
  const [todos, setTodos] = useState(() => {
    const saved = localStorage.getItem('minimal-todos');
    if (saved) {
      try {
        return JSON.parse(saved);
      } catch (e) {
        console.error("Failed to parse todos", e);
        return [];
      }
    }
    return [];
  });

  const [activeCategoryId, setActiveCategoryId] = useState(DEFAULT_CATEGORIES[0].id);

  // Save to localStorage whenever todos change
  useEffect(() => {
    localStorage.setItem('minimal-todos', JSON.stringify(todos));
  }, [todos]);

  // Actions
  const addTodo = (text, categoryId) => {
    const newTodo = {
      id: crypto.randomUUID ? crypto.randomUUID() : Date.now().toString(),
      text,
      completed: false,
      categoryId
    };
    setTodos(prev => [...prev, newTodo]);
  };

  const toggleTodo = (id) => {
    setTodos(prev => prev.map(todo => 
      todo.id === id ? { ...todo, completed: !todo.completed } : todo
    ));
  };

  const deleteTodo = (id) => {
    setTodos(prev => prev.filter(todo => todo.id !== id));
  };

  return {
    categories,
    todos,
    activeCategoryId,
    setActiveCategoryId,
    addTodo,
    toggleTodo,
    deleteTodo
  };
}
```

- [ ] **Step 2: Commit**
Run: `git add src/hooks/useTodoStore.js && git commit -m "feat: add useTodoStore hook for state and persistence"`

---

### Task 3: Sidebar Component

**Files:**
- Create: `src/components/Sidebar.jsx`

- [ ] **Step 1: Create Sidebar component**
Create `src/components/Sidebar.jsx`:
```jsx
import React from 'react';

export function Sidebar({ categories, activeCategoryId, onSelectCategory }) {
  return (
    <div className="w-64 bg-gray-800 text-white flex flex-col h-full">
      <div className="p-4 text-xl font-bold border-b border-gray-700">
        Todo App
      </div>
      <div className="flex-1 overflow-y-auto p-2">
        <div className="text-xs font-semibold text-gray-400 uppercase tracking-wider mb-2 mt-4 px-2">
          Categories
        </div>
        <ul>
          {categories.map(category => (
            <li key={category.id}>
              <button
                onClick={() => onSelectCategory(category.id)}
                className={`w-full text-left px-3 py-2 rounded-md mb-1 transition-colors ${
                  activeCategoryId === category.id 
                    ? 'bg-blue-600 text-white' 
                    : 'text-gray-300 hover:bg-gray-700 hover:text-white'
                }`}
              >
                {category.name}
              </button>
            </li>
          ))}
        </ul>
      </div>
    </div>
  );
}
```

- [ ] **Step 2: Commit**
Run: `git add src/components/Sidebar.jsx && git commit -m "feat: create Sidebar component"`

---

### Task 4: Main Content Component (Task List)

**Files:**
- Create: `src/components/MainContent.jsx`

- [ ] **Step 1: Create MainContent component**
Create `src/components/MainContent.jsx`:
```jsx
import React, { useState } from 'react';

export function MainContent({ 
  activeCategory, 
  todos, 
  onAddTodo, 
  onToggleTodo, 
  onDeleteTodo 
}) {
  const [inputValue, setInputValue] = useState('');

  const handleSubmit = (e) => {
    e.preventDefault();
    if (inputValue.trim()) {
      onAddTodo(inputValue.trim(), activeCategory.id);
      setInputValue('');
    }
  };

  return (
    <div className="flex-1 flex flex-col h-full bg-gray-50">
      <div className="p-6 border-b border-gray-200 bg-white shadow-sm">
        <h2 className="text-2xl font-bold text-gray-800 mb-4">
          {activeCategory ? activeCategory.name : 'Tasks'}
        </h2>
        <form onSubmit={handleSubmit} className="flex gap-2">
          <input
            type="text"
            value={inputValue}
            onChange={(e) => setInputValue(e.target.value)}
            placeholder={`Add a task to "${activeCategory?.name}"...`}
            className="flex-1 px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent shadow-sm"
          />
          <button 
            type="submit"
            className="px-4 py-2 bg-blue-600 text-white rounded-md hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-offset-2 transition-colors"
          >
            Add Task
          </button>
        </form>
      </div>

      <div className="flex-1 overflow-y-auto p-6">
        {todos.length === 0 ? (
          <div className="text-center text-gray-500 mt-10">
            No tasks in this category yet. Add one above!
          </div>
        ) : (
          <ul className="space-y-3">
            {todos.map(todo => (
              <li 
                key={todo.id} 
                className="flex items-center justify-between p-4 bg-white rounded-lg shadow-sm border border-gray-100 hover:shadow-md transition-shadow"
              >
                <div className="flex items-center gap-3">
                  <input
                    type="checkbox"
                    checked={todo.completed}
                    onChange={() => onToggleTodo(todo.id)}
                    className="w-5 h-5 text-blue-600 border-gray-300 rounded focus:ring-blue-500 cursor-pointer"
                  />
                  <span className={`text-lg ${todo.completed ? 'line-through text-gray-400' : 'text-gray-700'}`}>
                    {todo.text}
                  </span>
                </div>
                <button
                  onClick={() => onDeleteTodo(todo.id)}
                  className="text-red-500 hover:text-red-700 p-2 rounded-full hover:bg-red-50 transition-colors focus:outline-none"
                  aria-label="Delete task"
                >
                  <svg xmlns="http://www.w3.org/2000/svg" className="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
                    <path fillRule="evenodd" d="M9 2a1 1 0 00-.894.553L7.382 4H4a1 1 0 000 2v10a2 2 0 002 2h8a2 2 0 002-2V6a1 1 0 100-2h-3.382l-.724-1.447A1 1 0 0011 2H9zM7 8a1 1 0 012 0v6a1 1 0 11-2 0V8zm5-1a1 1 0 00-1 1v6a1 1 0 102 0V8a1 1 0 00-1-1z" clipRule="evenodd" />
                  </svg>
                </button>
              </li>
            ))}
          </ul>
        )}
      </div>
    </div>
  );
}
```

- [ ] **Step 2: Commit**
Run: `git add src/components/MainContent.jsx && git commit -m "feat: create MainContent component for task list"`

---

### Task 5: App Integration

**Files:**
- Modify: `src/App.jsx`

- [ ] **Step 1: Integrate components in App.jsx**
Overwrite `src/App.jsx`:
```jsx
import React from 'react';
import { useTodoStore } from './hooks/useTodoStore';
import { Sidebar } from './components/Sidebar';
import { MainContent } from './components/MainContent';

function App() {
  const {
    categories,
    todos,
    activeCategoryId,
    setActiveCategoryId,
    addTodo,
    toggleTodo,
    deleteTodo
  } = useTodoStore();

  const activeCategory = categories.find(c => c.id === activeCategoryId) || categories[0];
  const activeTodos = todos.filter(t => t.categoryId === activeCategoryId);

  return (
    <div className="flex h-screen overflow-hidden font-sans text-gray-900">
      <Sidebar 
        categories={categories}
        activeCategoryId={activeCategoryId}
        onSelectCategory={setActiveCategoryId}
      />
      <MainContent 
        activeCategory={activeCategory}
        todos={activeTodos}
        onAddTodo={addTodo}
        onToggleTodo={toggleTodo}
        onDeleteTodo={deleteTodo}
      />
    </div>
  );
}

export default App;
```

- [ ] **Step 2: Start dev server to verify visually (Manual step)**
Run: `npm run dev`
Expected: App runs at `http://localhost:5173`. Sidebar shows categories, main content allows adding/toggling/deleting tasks. Refreshing the page preserves tasks.

- [ ] **Step 3: Commit**
Run: `git add src/App.jsx && git commit -m "feat: integrate store, sidebar and main content into App"`
