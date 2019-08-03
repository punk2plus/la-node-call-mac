# ll-node-call-mac/介绍

A Node x-callback-url client for bi-directional communication with x-callback-url enabled macOS applications.

node调用 x-callback-url ,实现代码和mac 原生app进行通讯。

### Requires:
- macOS
- Node
- Uses xcall (included).

### Usage/用法

Create with a scheme (`bear`). Call with an action (`open-note`) and params (`{ id: yourNoteId }`). Returns a promise with results.

```
const llNodeCallMac = require('ll-node-call-mac');
const client = new llNodeCallMac('bear');

client.call('open-note', { id: noteId }).then((note) => {
  console.log(note);
});
```

```
{
  "note" : "# Test Note\n",
  "modificationDate" : "2019",
  "creationDate" : "2019",
  "title" : "Test Note",
  "is_trashed" : "no",
  "identifier" : "96F620E1-3743-469E-AA45-B863DD67F9E3-36492-0002D30FF2B6AFF5"
}
```

### Other
主要用途：和mac原生的GTD App通讯，实现功能上的互补和二次开发。