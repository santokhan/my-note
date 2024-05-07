The best approach to append an array of numbers to the FormData API depends on how you want the data to be received on the server-side:

**1. Appending each value individually:**

```javascript
const element = [1, 2, 3];
element.forEach((e) => {
  formData.append('amenities', e);
});
```

This approach is ideal if your server-side script can handle receiving an array of values for the same field name.  The server-side script would typically loop through each value with the same key and process them individually.

**2. Stringifying the entire array:**

```javascript
formData.append('amenities', JSON.stringify(element));
```

This approach is useful if you want to send the entire array as a single value on the server-side. The server-side script would then need to parse the JSON string back into an array.

**Choosing the right approach:**

- If your server-side script expects an array of values for the same field name, use the first approach (iterating and appending each value).
- If your server-side script expects a single JSON-encoded string, use the second approach (stringifying the entire array).

Here's a table summarizing the approaches:

| Approach | Server-side expectation | 
|---|---|
| Append each value | Array of values for the same field name |
| Stringify entire array | Single JSON-encoded string |
