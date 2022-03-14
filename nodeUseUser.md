# Node Use User

Useful with Firebase auth to lockdown API routes. Modified from using Typescript and Admin checks.

```javascript
export default async function nodeUseUser(req, removeAuth) {
    if (removeAuth) return { action: 'authorized' };
    if (req.headers.token) {
        const claims = await db.verifyIdToken(req.headers.token);
        if (typeof claims.uid !== 'undefined') {
            return { action: 'authorized' };
        } else {
            return { action: 'unauthorized' };
        }
    } else {
        return { action: 'no token passed' };
    }
}
```
