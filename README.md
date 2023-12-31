# SD500-Classes

Complete the code for the `MyStorage` class that will be used to add, read, update, and remove key-value pairs in the `state` immutable private property. Some methods return a `boolean` to indicate whether the operation was successfull or not.
```typescript
interface Item<T> { [key: string]: T; }
interface State<T> { data: Item<T>[]; }

class MyStorage<T> {
    private state: State<T> = Object.freeze({ data: [] });

    getItem(key: string): T | null {  }
    addItem(key: string, value: T): boolean { }
    updateItem(key: string, value: T): boolean { }
    removeItem(key: string): boolean { }
    getData() { return this.state.data; }
}

// Test with this code
const storage = new MyStorage<string>();
storage.addItem("firstname", "Asaad");
storage.addItem("lastname", "Saad");
console.log(storage.getData()); // [ { firstname: "Asaad" }, { lastname: "Saad" } ]

storage.removeItem("lastname");
console.log(storage.getData()); // [ { firstname: "Asaad" } ]

storage.updateItem("firstname", "Theo");
console.log(storage.getItem('firstname')); // Theo
console.log(storage.getData()); // [ { firstname: "Theo" } ]
```
