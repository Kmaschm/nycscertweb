# CSCI 70300 - Data Structures in a High Level Language

We have covered:
* ArrayLists
* LinkedLists
* LinearSearch
* BinarySearch
[more to fill out]

Here is my code from LinkedList:

```Java
import java.io.*;
import java.util.*;

/* Collaborators:
* kate Maschmeyer, Christoper de Silva, Shana Elizabeth Henry, Ashley Ufret
*
*/

/**
For all attempted methods, make sensible decisions for error and
edge cases (such as indexing out of bounds).

Basic
-----
add(string value) ✅
get(int index); ✅
toString() ✅


Intermediate (at least add, size + one of the other two)
------------
size() ✅
add(int index,String value) ✅
indexOf(String value); ✅
toArray() ✅


Challenge
--------
remove(int index); ✅
*/

public class LinkedList{

  private Node head;

  public LinkedList(){
    head = null;
  }

  /**
  Parameters:
  value - the new string to add to the list

  Adds a new node containing value to the front of the list.
  */
  public void add(String value){
    // Node n = new Node(value);
    // n.setNext(this.head);

    // after demo, thanks Jessica Novillo!
    Node n = new Node(value, head);
    // equivalent to above (create new node with data == value, and next == head)
    
    head = n;
  }

  /**
  Returns the String in the node at location index.
  */
  public String get(int index){
    int count = 0;
    Node walker = this.head;
    String s = "Invalid index";

    if(index < 0 ) { // badness
      return s;
    }
    
    while(count <= index && walker != null) {
      if(count == index) {
        s = walker.getData();
      }
      walker = walker.getNext();
      count++;
    }
    return s;
  }

  /**
  Return a string representation of the list
  */
  public String toString(){
    String s = "";
    Node walker = this.head;
    while(walker != null) {
      s = s + walker;
      walker = walker.getNext();
    }
    s = s + "null";
    return s;
  }

  /**
  returns the number of elements in the list
  */
  public int size(){
    int count = 0;
    Node walker = this.head;
    while(walker != null) {
      count++;
      walker = walker.getNext();
    }
    return count;
  }



  /**
  Parameters:
  index - an int with the location to add
  value - the new value

  Adds a new node with the String value to the list.
  The new node should be added at the location specified by the index.

  For example, given the list:
  "a" -> "b" -> "c" -> "d"

  add(1,"z") results in:
  "a"-> "z" -> "b" -> "c" -> "d"

  */
  public void add(int index, String value){
    if(index > this.size() || index < 0) { // 
      System.out.println(index + " is an invalid index. " + value  + " node not added"); 
    } else if(index == 0) { // if adding to the front
      this.add(value);
    } else {
      int count = 0;
      Node walker = this.head; 
      Node n = new Node(value);

      // we want the node *before* the one at index
      while(count <= (index-1) && walker != null) {
        if(count == (index - 1)) {
          n.setNext(walker.getNext());
          walker.setNext(n);
        } 
        walker = walker.getNext();
        count++;
      }
    }
    
    
        
  }


  /**
  Returns the index (location) of the first node in the list
  that contains value.

  Example:
  Given the list:
  "a"->"b"->"c"->"d"->"e"
  indexOf("d") would return 3 since "d" is at location 3.

  */
  public int indexOf(String value){
    Node walker = head;
    int count = 0;
    while (walker != null) {
      if(walker.getData() == value) {
        return count;
      }
      count++;
      walker = walker.getNext();
    }

    System.out.println(value + " not found.  Returning -1");
    return -1;  // if not found, return -1 
  }



  /**
  This routine should create a new array that is the same
  size as the number of Nodes in the list.

  It should then copy all of the values to the array and return
  the array.

  */
  public String[] toArray(){
    String[] a = new String[this.size()];
    Node walker = head;

    for(int i = 0; i < a.length; i++) {
      a[i] = walker.getData();
      walker = walker.getNext();
    }
    return a;
  }



  /**
  Remove the Node at location index from the list.

  Ex:
  
  Given the list:
  "a"->"b"->"c"->"d"->"e"

  remove(2) results in:
  "a"->"b"->"d"->"e"
  */
   public void remove(int index){
    if(index == 0 ) {    
      head = head.getNext(); // head will point to next one
    } else if(index < 0 || index > this.size()) {
      System.out.println("Invalid index.  Nothing to remove");
    } else {
       int count = 0;
        Node walker = head;
    
        while (walker != null && count <= (index-1)){
          if(count == (index-1) ) {
            walker.setNext(walker.getNext().getNext()); 
          } 
          walker = walker.getNext();
          count++; 
        }
    }
  }
}
```
