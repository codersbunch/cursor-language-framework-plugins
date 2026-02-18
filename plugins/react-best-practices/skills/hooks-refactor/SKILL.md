---
name: hooks-refactor
description: Refactor React class components to modern functional components with hooks. Converts lifecycle methods, state, and context usage.
---

# Hooks Refactor

## When to use

- Migrating legacy class components to functional components
- Modernizing a codebase to use hooks
- Before adding new features to class components

## Instructions

1. **Analyze class component**:
   - Map `this.state` → `useState`
   - Map `componentDidMount` → `useEffect(fn, [])`
   - Map `componentDidUpdate` → `useEffect(fn, [deps])`
   - Map `componentWillUnmount` → `useEffect` cleanup return
   - Map `shouldComponentUpdate` → `React.memo`
   - Map `contextType` → `useContext`
   - Map `createRef` → `useRef`

2. **Extract custom hooks** for reusable logic

3. **Preserve behavior exactly** - same props API, same rendering output

4. **Add TypeScript types** if codebase uses TypeScript

## Output

- Refactored functional component
- Extracted custom hooks if applicable
- Side-by-side diff showing changes
- Notes on any behavioral differences to verify
