- Data shaping is a great way to reduce the amount of traffic sent from the API to the client. It enables the consumer of the API to select (shape) the data by choosing the fields through the query string.
- By giving the consumer a way to select just the fields it needs, we can potentially reduce the stress on the API. On the other hand, this is not something every API needs, so we need to think carefully and decide whether we should implement its implementation because it has a bit of reflection in it.
- ExpandoObject: is a dynamic object in C# that allows you to add or remove properties at runtime. It is part of the `System.Dynamic` namespace and is used to create objects whose structure can change during execution. This is particularly useful when you don't know the shape of the object at compile time or when the properties of the object are determined based on runtime conditions.
- We use ExpandoObject when dealing with Data Shaping as we don't know structure of returned data at compile time, we want simply to supply the client by the data it requires only to reduce stress on Api but since it is determined only at request time so we need Reflection and dynamic behavior of ExpandoObject.
- ExpandoObject **Implements `IDictionary`**: You can interact with `ExpandoObject` like a dictionary using `IDictionary<string, object>` to get or set properties.
- ### Common Use Cases for `ExpandoObject`:

1. **Dynamic APIs**: It's often used when working with dynamic APIs where the shape of the response can vary, like when deserializing JSON with a changing schema.
2. **Data Shaping**: In scenarios like the one mentioned earlier, `ExpandoObject` is used to shape data dynamically, where only a subset of fields is selected based on runtime conditions.
3. **Prototyping**: It’s helpful in cases where you might want to prototype objects without defining a rigid class structure.
