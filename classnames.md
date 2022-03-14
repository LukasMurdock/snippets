# Classnames

Useful for combining tailwind strings.

```typescript
export default function classNames(...classes: string[]) {
    return classes.filter(Boolean).join(' ');
}
```
