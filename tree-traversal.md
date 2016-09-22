# Tree Traversal

### Breadth First Search

- First in, first out of the queue (or stack)
- Does not matter which edge you go to but visit all edges on the level before moving on
- When "e" has no edges, remove from queue

```
* <-- where we are
```

```
Order:E
Queue:E
	*
    |
    E
  / |  \
B   C   G
| /   \ |
A      D
|
F
|
H

Order:E
Queue:EBCG
	
    |
    E*
  / |  \
B   C   G
| /   \ |
A      D
|
F
|
H

Order:EB
Queue:BCGA
	
    |
    E
  / |  \
B*  C   G
| /   \ |
A      D
|
F
|
H

Order:EB
Queue:CGA
	
    |
    E*
  / |  \
B   C   G
| /   \ |
A      D
|
F
|
H

Order:EBC
Queue:CGAD
	
    |
    E
  / |  \
B   C*   G
| /   \ |
A      D
|
F
|
H

Order:EBC
Queue:GAD
	
    |
    E*
  / |  \
B   C   G
| /   \ |
A      D
|
F
|
H

Order:EBC
Queue:AD
	
    |
    E
  / |  \
B   C   G*
| /   \ |
A      D
|
F
|
H

~Skipped a few steps of moving over~

Order:EBCGA
Queue:ADF
	
    |
    E
  / |  \
B   C   G
| /   \ |
A*      D
|
F
|
H


Order:EBCGAD
Queue:DF
	
    |
    E
  / |  \
B   C   G
| /   \ |
A      D*
|
F
|
H

Order:EBCGADF
Queue:FH
	
    |
    E
  / |  \
B   C   G
| /   \ |
A      D
|
F*
|
H

Order:EBCGADFH
Queue:H
	
    |
    E
  / |  \
B   C   G
| /   \ |
A      D
|
F
|
H*

```


### Depth First Search

- Unlike the other algorithm, this one looks at the top of the "stack". It uses the last item added working its way to the first item added.
- Looks at the unvisited vertices in alphabetical order, if any arent "found" vertices yet, add to order and stack. if not pop it off the stack


```
Given: Starting at A

Order:A
Queue:A

B --- F-.
| \   |  \
|  A* |   C
|  | \|     \
|  |   D     H
E--G

Order:AB
Queue:AB

B*--- F-.
| \   |  \
|  A  |   C
|  | \|     \
|  |   D     H
E--G

Order:ABE
Queue:ABE

B --- F-.
| \   |  \
|  A  |   C
|  | \|     \
|  |   D     H
E*-G

Order:ABEG
Queue:ABEG

B --- F-.
| \   |  \
|  A  |   C
|  | \|     \
|  |   D     H
E--G*

//no vertices unvisited so take off last elements till one does (Hint: B->F)

Order:ABEGF
Queue:ABF

B --- F*.
| \   |  \
|  A  |   C
|  | \|     \
|  |   D     H
E--G

Order:ABEGFC
Queue:ABFC

B --- F-.
| \   |  \
|  A  |   C*
|  | \|     \
|  |   D     H
E--G

Order:ABEGFCH
Queue:ABFCH

B --- F-.
| \   |  \
|  A  |   C
|  | \|     \
|  |   D     H*
E--G

Order:ABEGFCHD
Queue:ABFD

B --- F-.
| \   |  \
|  A  |   C
|  | \|     \
|  |  D*     H
E--G

Order:ABEGFCHD
Queue:

B --- F-.
| \   |  \
|  A  |   C
|  | \|     \
|  |  D*     H
E--G



```

https://www.youtube.com/watch?v=we2xFCPkH0Y
https://www.youtube.com/watch?v=bIA8HEEUxZI
