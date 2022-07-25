# nycscertweb

## Intro
Hi, my name is Kate and this is my Hunter CS Adv Cert Program portfolio.  Please click on a class name for more info.

## Summer 2022 Courses
* [CSCI 70900 - Programming in a High-Level Language](programming.md)
* [CSCI 70300 - Data Structures in a High-Level Language](datastructures.md)
* [SEC 70300 - Methods for Teaching Computer Science](methods)

### CSCI 70900 - Programming in a High-Level Language

Here's a special method I wrote for the Craps prework:

```Java
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






