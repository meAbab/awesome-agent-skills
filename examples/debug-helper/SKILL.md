---
name: debug-helper
description: Help debug code by analyzing error messages, identifying root causes, and providing fix suggestions.
license: CC0-1.0
---

# Debug Helper

> Help debug the code, analyze error messages, locate the root cause of the problem, and provide repair suggestions.
>
> Help debug code by analyzing error messages, identifying root causes, and providing fix suggestions.

## When to Use

Use this skill when the user requests the following operations:
- Debug code
- Analyze error messages
- Fix bugs
- Understand exception causes
- Troubleshoot issues

## Instructions

### Debugging Steps

1. **Collect information** - Get error information, stack traces, related code
2. **Analyze errors** - Understand the error type and message meaning
3. **Locate the root cause** - Find the code location that causes the problem
4. **Provide solutions** - Give specific repair suggestions
5. **Prevention Suggestions** - Provides suggestions to avoid similar problems

### Common Error Types

| Error Types | Possible Causes |
|----------|----------|
| TypeError | Type mismatch, null value operation |
| ReferenceError | Undefined variables, scope issues |
| SyntaxError | Syntax error, missing brackets/quotes |
| RuntimeError | Runtime logic error |
| NetworkError | Network request failed, timed out |

### Analysis Framework

For each error, it is necessary to analyze:
- **What**: What error occurred
- **Where**: Where the error occurred
- **Why**: Why does
happen - **How**: How to fix

### Output Format

uses the `templates/debug-report.md` template to format the output.

Use the `templates/debug-report.md` template to format output.

```markdown
## Debug Analysis Report

### Error Summary
[Error type and brief description]

### Root Cause
[Detailed analysis]

### Fix
[Specific code modification]

### Prevention
[How to avoid similar problems]
```

## Examples

### Input

Error message:
```
TypeError: Cannot read properties of undefined (reading 'map')
    at UserList (UserList.jsx:15:23)
    at renderWithHooks (react-dom.development.js:14985:18)
```

Related codes:
```jsx
function UserList({ users }) {
  return (
    <ul>
      {users.map(user => (
        <li key={user.id}>{user.name}</li>
      ))}
    </ul>
  );
}
```

### Output

## Debug Analysis Report

### Error Overview
`TypeError: Cannot read properties of undefined (reading 'map')`

When calling `.map()` on line 15 of the `UserList` component, the `users` variable is `undefined`.

### Root Cause

1. **Direct Cause**: Trying to call `.map()` method on `undefined`
2. **Deep Cause**:
- The parent component may not have passed the `users` prop
- The component has been rendered when the data acquisition has not yet completed
- The API return format is not as expected

### Fixes

**Scenario 1: Add default value (recommended)**
```jsx
function UserList({ users = [] }) {
  return (
    <ul>
      {users.map(user => (
        <li key={user.id}>{user.name}</li>
      ))}
    </ul>
  );
}
```

**Option 2: Conditional rendering**
```jsx
function UserList({ users }) {
  if (!users || users.length === 0) {
    return <p>No users found</p>;
  }

  return (
    <ul>
      {users.map(user => (
        <li key={user.id}>{user.name}</li>
      ))}
    </ul>
  );
}
```

**Option 3: Optional chain operator**
```jsx
function UserList({ users }) {
  return (
    <ul>
      {users?.map(user => (
        <li key={user.id}>{user.name}</li>
      ))}
    </ul>
  );
}
```

### Prevention recommendations

1. **Use TypeScript** - Add type checking
   ```typescript
   interface Props {
     users: User[];
   }
   ```

2. **Add PropTypes** - Runtime type checking
   ```jsx
   UserList.propTypes = {
     users: PropTypes.array.isRequired
   };
   ```

3. **Check data sources** - Ensure parent component passes data correctly
4. **Handle loading status** - Show loading indicator during data retrieval
