# SD500-Classes

Complete the code for the `MyStorage` class that will be used to add, read, update, and remove key-value pairs in the `state` immutable private property.
```typescript
interface State<T> { data: Array<{ [key: string]: T; }>; }

class MyStorage<T> {
    private state: State<T> = Object.freeze({ data: [] });

    getItem(key: string): T | null {  }
    setItem(key: string, value: T): void { }
    removeItem(key: string): void { }
    getStorage() { return this.state; }
}

// Test with this code
const storage = new MyStorage<string>();
storage.setItem("firstname", "Asaad");
storage.setItem("lastname", "Saad");
console.log(storage.getStorage()); // { data: [ { firstname: "Asaad" }, { lastname: "Saad" } ]}

storage.removeItem("lastname");
console.log(storage.getStorage()); // { data: [ { firstname: "Asaad" } ]}

storage.updateItem("firstname", "Theo");
console.log(storage.getItem('firstname')); // Theo
console.log(storage.getStorage()); // { data: [ { firstname: "Theo" } ]}
```
