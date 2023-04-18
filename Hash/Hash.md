# Hash

### Hash is the process of generation fixed size output from the variable size using mathematical formulas called `hash function`. This technique determines the index or location for the storage of item in a data structure 

## Components hashing

-> key : Anything string or integer which give input to hash function.<br />
-> hash function : function receive input key and return the index of an element in a array using mathematical formulas. <br />
-> hash table : It is a data structure that map the key to value using hash function. Hash table store data same has array. It has unique index.<br />


## Type of hash function 

<ul>
  <li>Division method</li>
  <li>Multiplication method</li>
  <li>Mid square method</li>
  <li>Digit folding method</li>
</ul>

## implementation of hashing

```
class HashTable{
  constructor(size){
    this.table = new Array(size);
    this.size = size;
  }

  // creation of key index or location

  hash(key){
    const total = 0;
    for(let i = 0; i< key.length; i++){
      total += key.charCodeAt(i) // it will convert character into numeric
    }
    return total % this.size
  }

  // set value into table

  set(key, value){
    const index = this.hash(key)
    this.table[index] = value
  }

  // get value from the table

  get(key){
    const index = this.hash(key)
    return this.table[index]
  }

  //remove value from the table

  remove(key){
    const index = this.hash(key)
    this.table[index] = undefined
  }

  //print all the values in the table

  display(){
    for(let i = 0; i < this.size; i++ ){
      if(this.table[i]){
        console.log(i, this.table[i]);
      }
    }
  }
}
```

### usage of hash table

```

// creation of hash table 
const hashTable = new HashTable(5)

hashTable.set("name", "Adam")
hashTable.set("age", "18")
hashTable.display()
console.log(hashTable.get("name"))
hashTable.remove("age")
hashTable.display()
hashTable.set("name", "Eve")
hashTable.display()
```

when you run this code you may figured out that the name "Adam" is override by the name "Eve" which is not good. This is the one of the problem that we wanna take care of it 

## Collision

Hashing process generate small number for big key. So there is a possibility that key could reproduce which replace the existing value in table.

This collision can handle through two method:
<ul>
  <li>Separate Chaining (open hashing)</li>
  <li>Open addressing (close hashing)</li>
  <ul>
    <li>Linear probing</li>
    <li>Quadratic probing</li>
    <li>Double probing</li>
  </ul>
</ul>

## minimization of collision from previous example

```
class HashTable {
  constructor(size){
    this.table = new Array(size)
    this.size = size
  }
  _hash(key){
    let prime = 31 // to make less collision
    let total = 0
    for(let i = 0; i < key.length; i++ ){
      total = total * prime + key.charCodeAt(i)
    }
    return total % this.size
  }
  set(key, value){
    const index = this._hash(key)
    if(!this.table[index]){
      this.table[index] = []
    }
    this.table[index].push([key, value])
  }
  get(key){
    const index = this._hash(key)
    if(this.table[index]){
    const item = this.table[index].find(arr=> arr[0] == key)
    return item
    }
    return undefined 
  }
  remove(key){
    const index = this._hash(key)
    if(this.table[index]){
      for(let i = 0; i < this.table[index].length; i++){
        if(this.table[index][0] === key){
          this.table[index].splice(i, 1)
        }
        if(this.table[index].length === 0){
          this.table[index] = undefined
        }
      }
    }
    return undefined
  }
}
```