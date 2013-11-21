# Polymorphic tree documents

People use tools to structure their data. There are several
incompatible structures that documents need to include: text, tables, pictures,
etc. Let's make it explicit. Why have a spreadsheet and a word processor
separated? Why think which type of document to create?

Also, do away with the paper-page representation of a document. Parts may have
whatever sizes they need.

## Document is a tree anyway

The section - chapter - paragraph structure is a tree. Decent editors allow to
show it like that. Make it explicit. Allows easy text folding, focusing, etc.

### Folding

* A node can be _folded_, so that it and all its (grand-)children are reduced to
  one small fragment.
* A node can be _minified_, so that its content is reduced, but its children are
  visible.
* A node can be _curbed_ (better word?), so that it is visible, but its children
  are folded.
* A node can be _focused_ so that it and its children are fully visible but its
  parent and siblings are folded.
  
Works great with plain texts in word processors already. HTML DOM is somehow
similar.

### Views and input focus

Multiple windows can show different subnodes of a document. Easy to compare or
refer to without scrolling.

Only one node has input focus. The focused node, if large, can take up the
window, its scrolling controls, etc.

Keyboard shortcuts work within the focused node. Different types of nodes can
have duplicate shortcuts without conflicting. Inter-node navigation shortcuts
are consistent, though.

Search and replace can be filtered by node type(s); compare with filtering by
styles in a word processor.

## Need tables!

Make a table (spreadsheet) a separate tree node type. A document with just one
large table is like a spreadsheet. Several such nodes are like pages in
traditional spreadsheet apps.

### Child nodes to a table node

Lookup tables, explanation texts, pictures, etc, all clearly in context. Easy to
relatively address from the table.

### No child nodes in cells

Cells are single text nodes, with no children. Else it grows geometrically
unmaintainable.

Cells can refer to table's child nodes using formulas.

### Derived representations

Charts naturally become tables' child nodes.

Various auto-updated filtered views, 'reports', etc.

If the parent node is minified, they become prominent without losing logical connection.

## Need pictures!

Imported 'binary-blob' pictures, not directly editable, but resizable,
etc.

No text flow around them in the tree view. No big deal.

Small picture nodes can be shown in rows under their parent node.

_Do subnodes under pictures make sense?_ For instance, for meta-information,
titles, etc. 

## More niceties

Filesystems are trees, too, so many tricks can be borrowed.

* Navigation is obvious.
* 'Check out' parts of tree for [concurrent] modification.
* Easy diffs of changes, like in a VCS.
* Graft separate trees as subtrees into larger trees (like symlinks).

Actually we could use a file system to provide [parts of] the tree
structure. Usually inconvenient. 

## Problems

Cross-referencing over a tree structure is inconvenient. _Some_ nodes would
rather have more than one parent. Alas, it's common for tree structures.

Tree is not a paper-friendly. A typesetting layer will be needed if
'business-class documents' are to be produced from it, like from a traditional
word processor.
