# Trie

Trie data structure is defined as a tree based data structure that is used for storing some collection of string.
The word derived from re`trie`val which means finding something. <br />

### Application

<ol>
  <li>Auto complete.</li>
  <li>Spell checking.</li>
  <li>IP routing</li>
  <li>Text compression</li>
</ol>

`Trie node`

```js
class TrieNode {
  constructor() {
    this.children = {};
    this.isEndOfWord = false;
  }
}
```

`Trie`

```js
class Trie {
  constructor() {
    this.root = new TrieNode();
  }

  // Insert a string into the Trie
  insert(word) {
    let node = this.root;
    for (let char of word) {
      if (!node.children[char]) {
        node.children[char] = new TrieNode();
      }
      node = node.children[char];
    }
    node.isEndOfWord = true;
  }

  // search the word exist or not
  search(word) {
    let node = this.root;
    for (let char of word) {
      if (!node.children[char]) {
        return false;
      }
      node = node.children[char];
    }
    return true;
  }

  // Check if a given prefix exists in the Trie
  startWith(word) {
    let node = this.root;
    for (let char of word) {
      if (!node.children[char]) {
        return false;
      }
      node = node.children[char];
    }
    return true;
  }

  // suggestion program
  getSuggestion(prefix) {
    let node = this.root;
    for (let char of prefix) {
      if (!node.children[char]) {
        return false;
      }
      node = node.children[char];
    }
    return this._findWords(node, prefix);
  }

  _findWords(node, prefix) {
    const words = [];
    if (node.isEndOfWord) {
      words.push(prefix);
    }
    for (let char in node.children) {
      words.push(...this._findWords(node.children[char], prefix + char));
    }
    return words;
  }
```
lets test

```js
const trie = new Trie();
trie.insert('apple');
trie.insert('ads');
trie.insert('dance');
console.log(trie.search('app')) // true
console.log(trie.search('play')) // false
console.log(trie.getSuggestion('app')); // [ 'apple' ]
console.log(trie.getSuggestion('ad')); // [ 'ads' ]
console.log(trie.getSuggestion('')); // [ 'apple', 'ads', 'dance' ]

```