In JavaScript, you can differentiate between a normal object and a `File` object by checking their types or by using specific properties or methods unique to each type.

Here's how you can differentiate between them:

1. **Checking the type**:

   You can use the `typeof` operator to determine the type of an object. For example:

   ```javascript
   const normalObject = {};
   const fileObject = new File(["content"], "filename.txt");

   console.log(typeof normalObject); // Outputs: "object"
   console.log(typeof fileObject);   // Outputs: "object"
   ```

   Both `normalObject` and `fileObject` will have the type of "object", so this method alone won't help you differentiate them.

2. **Using specific properties or methods**:

   The `File` object has properties and methods specific to file handling, such as `name`, `size`, `type`, etc. You can use these properties/methods to differentiate between a normal object and a `File` object. For example:

   ```javascript
   const normalObject = {};
   const fileObject = new File(["content"], "filename.txt");

   console.log('name' in normalObject); // Outputs: false
   console.log('name' in fileObject);   // Outputs: true
   ```

   In this example, we're checking for the presence of the `name` property, which is specific to `File` objects. If it exists, then it's likely a `File` object.

3. **Using `instanceof` operator**:

   You can also use the `instanceof` operator to check if an object is an instance of a specific class. For example:

   ```javascript
   const normalObject = {};
   const fileObject = new File(["content"], "filename.txt");

   console.log(normalObject instanceof File); // Outputs: false
   console.log(fileObject instanceof File);   // Outputs: true
   ```

   This will return `true` if `fileObject` is an instance of `File`, otherwise `false`.

By using one or a combination of these methods, you can differentiate between a normal object and a `File` object in JavaScript.
