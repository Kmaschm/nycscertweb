# Kate Maschmeyer's Hunter CS Adv Cert Portfolio

## Intro
Hi, my name is Kate and this is my Hunter CS Adv Cert Program portfolio.  Please click on a class name for more info.

## Summer 2022 Courses
* [CSCI 70900 - Programming in a High-Level Language](programming.md)
* [CSCI 70300 - Data Structures in a High-Level Language](datastructures.md)
* [SEC 70300 - Methods for Teaching Computer Science](methods)

### CSCI 70900 - Programming in a High-Level Language

Here's a special method I wrote for the Craps prework:

```java
/**
 * Prints ASCII art of specified result of 6-sided die roll
 *
 * Uses ACSII drawings inspired by text result in 
 https://codereview.stackexchange.com/questions/111337/pretty-print-dice-faces-from-multiple-rolls-of-multi-sided-dices
 * 
 * @param rollVal integer, value rolled on 6-sided die
 */
 public static void drawRoll(int rollVal) {
    if(rollVal == 1) {
        System.out.println("+-----+\n|     |\n|  o  |\n|     |\n+-----+");
      } else if(rollVal == 2) {
        System.out.println("+-----+\n|     |\n| o o |\n|     |\n+-----+");
      } else if(rollVal == 3) {
        System.out.println("+-----+\n| o   |\n|  o  |\n|   o |\n+-----+");
      } else if(rollVal == 4) {
         System.out.println("+-----+\n| o o |\n|     |\n| o o |\n+-----+");
      } else if(rollVal == 5) {
         System.out.println("+-----+\n| o o |\n|  o  |\n| o o |\n+-----+");
      } else { // rolled a 6
        System.out.println("+-----+\n| o o |\n| o o |\n| o o |\n+-----+");
      }
 }

```

### CSCI 70300 - Data Structures in a High-Level Language

Here's code on removing a node from a linked list:

```java
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
```


### SEC 70300 - Methods for Teaching Computer Science

Here is my scaffolded activity: [Coding from a Plan in p5](https://github.com/hunter-teacher-cert/cohort-3-summer-work-Kmaschm/blob/master/methods/06_scaffold_activity.md)

### Testing TeX/LaTeX

$$x = \frac{-b \pm sqrt{b^2 - 4ac}}{2a}$$ 
