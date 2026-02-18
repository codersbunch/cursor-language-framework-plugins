---
name: render-optimizer
description: Identify and fix unnecessary React re-renders using memoization, stable references, and component splitting.
---

# Render Optimizer

## When to use

- When UI feels sluggish or janky
- After React DevTools Profiler shows excessive renders
- Before shipping performance-sensitive components

## Instructions

1. **Identify re-render causes**:
   - Props changing on every parent render (inline objects/functions)
   - Context value changing too broadly
   - State updates triggering large subtree re-renders
   - Missing or incorrect memo/useCallback/useMemo

2. **Apply fixes**:
   - Wrap stable functions with `useCallback`
   - Memoize expensive derived values with `useMemo`
   - Split context into smaller, focused contexts
   - Use `React.memo` on leaf components with stable props
   - Move state down to the component that needs it
   - Use `useRef` for values that don't need to trigger renders

3. **Measure improvement** with React DevTools Profiler before/after

## Output

- List of components with unnecessary re-renders
- Root cause for each
- Fixed code with explanation
- Expected render count reduction
