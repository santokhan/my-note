# duplicate nav matcher

```javascript
const matcher = ({ nav = '', label = '', pathname = '/properties' }) => {
  const pathList = pathname.split('/').filter((e) => e);
  let isSingleMatch = false;

  if (pathList.includes('properties')) {
    if (label.includes('buy')) {
      if (isSingleMatch) {
        return false; // Multiple matches found
      }
      isSingleMatch = true;
      return true;
    } else if (label.includes('rent')) {
      if (isSingleMatch) {
        return false; // Multiple matches found
      }
      isSingleMatch = true;
      return true;
    }
    return false;
  } else {
    if (isSingleMatch) {
      return false; // Multiple matches found
    }
    isSingleMatch = true;
    return pathList.includes(nav);
  }
};
```
