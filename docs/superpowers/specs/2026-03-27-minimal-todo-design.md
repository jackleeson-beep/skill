# Minimal Todo App Design Spec

## Overview
A minimal React-based Todo application designed to demonstrate the AI workflow. It uses a sidebar layout for categorization and stores data locally.

## Architecture & Tech Stack
- **Framework**: React 18 + Vite
- **Styling**: Tailwind CSS
- **State Management**: React Hooks (`useState`, `useEffect`)
- **Persistence**: Browser `localStorage`

## Data Model
- **Category**
  - `id`: string (UUID)
  - `name`: string (e.g., "Work", "Personal")
- **Todo**
  - `id`: string (UUID)
  - `text`: string
  - `completed`: boolean
  - `categoryId`: string (foreign key to Category)

## Scope & Features (MVP)
1. **Sidebar (Categories)**
   - Displays a hardcoded list of categories (e.g., "Work", "Personal").
   - User can click a category to view its associated tasks.
   - *Out of scope for MVP*: Adding, editing, or deleting categories.
2. **Main Content (Tasks)**
   - Top input bar to add new tasks to the currently selected category (press Enter to submit).
   - List of tasks for the active category.
   - Clickable checkbox to toggle task completion status.
   - Delete button for each task.
3. **Persistence**
   - Automatically save and load state from `localStorage` on change/mount.

## UI Layout
- **Left Panel (30% width, min 200px)**: Category list, distinct background color.
- **Right Panel (70% width)**: Task input at the top, list of tasks below.
