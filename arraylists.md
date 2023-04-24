# ArrayList


## What are ArrayLists?
An ArrayList is a collection that stores objects. To create an ArrayList, declare a variable with a data type of ArrayList, and point it to a new ArrayList object. The initial size of an ArrayList is zero. The size of an ArrayList depends on the methods called.

Creating an Arraylist:
ArrayList<type> nameofarraylist= new ArrayList<type>();

```
ArrayList<Integer> list = new ArrayList<Integer>();
```


## Useful Arraylist Methods
The following are commonly used methods for ArrayList:

```
arrayList.add(element);
arrayList.add(index, element);
arrayList.set(index, element);
arrayList.remove(index);
arrayList.get(index);
```


## Iterating through an Arraylist
```
// Using an enhanced for loop
ArrayList<Integer> list = new ArrayList<Integer>();
list.add(1);
list.add(2);
list.add(3);
list.add(4);
list.add(5);
for (Integer element: list) {
    System.out.println(element);
}
```
```
1
2
3
4
5
```
```
// Using a for loop
for (int i = 0; i < list.size(); i++) {
    System.out.println(list.get(i));
}
```
```
1
2
3
4
5
```

## Arraylist Hacks:
Choose two of these options to do.
- Test if two arraylists contain the same elements in reverse order
- Overwrite all the elements in an arraylist with the alphabet
- Remove every other element from an arraylist
