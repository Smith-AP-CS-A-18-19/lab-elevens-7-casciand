Andrew Cascio

# Elevens 7

Follow the instructions provided for Activity 7 in the student lab guide. This is more of an exploratory lab, so you will not need to copy any of your previous code into the repo. Answer the questions from the Student Guide in this document and ensure that you save and push the repo. You have one week to complete this lab.

1. What items would be necessary if you were playing a game of Elevens at your desk (not on the computer)? List the private instance variables needed for the `ElevensBoard` class.

    * deck, card, suit, rank, pointValue

2. Write an algorithm that describes the actions necessary to play the Elevens game.

    * a. Deal out 9 cards
      b. When 2 cards are chosen with a point value sum of 11, discard them and replace them with 2 new cards from the deck
      c. When a jack, queen, and king are chosen together, discard them and replace them with 3 new cards from the deck.
      d. If 2 cards are chosen and do not have a point value sum of 11, or are not a jack, queen and king, do not discard them or replace with new cards from the deck
      e. If no arrangement of 2 cards add up to 11, end the game and the player loses
      f. When all cards are discarded, end the game and the player wins

3. Now examine the partially implemented `ElevensBoard.java` file found in this repository. Does the `ElevensBoard` class contain all the state and behavior necessary to play the game?

    * No, it does not know to end the game of there are no available matches, or know how to check for those matches.

4. `ElevensBoard.java` contains three helper methods. These helper methods are private because they are only called from the ElevensBoard class.

  * a. Where is the `dealMyCards` method called in ElevensBoard?

      * after anotherPlayIsPossible and before containsPairSum11

  * b. Which `public` methods should call the `containsPairSum11` and `containsJQK` methods?

      * dealMyCards, replaceSelectedCards, anotherPlayIsPossible

  * c. It’s important to understand how the `cardIndexes` method works, and how the list that it returns is used. Suppose that `cards` contains the elements shown below. Trace the execution of the `cardIndexes` method to determine what list will be returned. Complete the diagram below by filling in the elements of the returned list, and by showing how those values index `cards`. Note that the returned list may have less than 9 elements.

    * `cards`

| 0  | 1  |  2   | 3  |  4   |  5   | 6  | 7  |  8   |
|:--:|:--:|:----:|:--:|:----:|:----:|:--:|:--:|:----:|
| J♥ | 6♣ |`null`| 2♠ |`null`|`null`| A♠ | 4♥ |`null`|

   *  * Answer - This list should contain the indices of the cards, not the cards themselves

| 0  | 1  | 2  | 3  | 4  | 5  | 6  | 7  | 8  |
|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| J♥ | 6♣ | 2♠ | A♠ | 4♥ |null|null|null|null|

  * d. Complete the following `printCards` method to print all of the elements of cards that are indexed by `cIndexes`.
```java
public static printCards(ElevensBoard board) {
    List<Integer> cIndexes = board.cardIndexes();
        for(int i = 0; i < cIndexes.size(); i++) {
            System.out.println(cIndexes.get(i));
        }
}
```

  * e. Which one of the methods that you identified in question 4b above needs to call the `cardIndexes` method before calling the `containsPairSum11` and `containsJQK` methods? Why?

      * replaceSelectedCards because there may not be anymore cards in the deck, so it will shift the remaining cards into the open spaces.

## Feedback
4.c was slightly off
19/10

## Feedback
Failed to compile
00/20
