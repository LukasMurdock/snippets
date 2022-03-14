# Fetcher

Useful with SWR.

```typescript
export default async function fetcher(
    url: string,
    token: string,
    email: string
) {
    const res = await fetch(url, {
        method: 'GET',
        headers: new Headers({
            'Content-Type': 'application/json',
            token,
            email,
        }),
        credentials: 'same-origin',
    });
    return res.json();
}
```
