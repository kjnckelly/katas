# Strangled Rose Kata #

Start with the [Gilded Rose Kata](https://github.com/emilybache/GildedRose-Refactoring-Kata) 
in the language of your choice: 
[C#](https://github.com/emilybache/GildedRose-Refactoring-Kata/tree/main/csharp), 
[JavaScript](https://github.com/emilybache/GildedRose-Refactoring-Kata/tree/main/js-jest), 
[Kotlin](https://github.com/emilybache/GildedRose-Refactoring-Kata/tree/main/Kotlin), 
[etc.](https://github.com/emilybache/GildedRose-Refactoring-Kata)

Use the **Strangler Pattern** as described in chapter 10 of 
[Code that Fits in Your Head](https://www.amazon.com/Code-That-Fits-Your-Head/dp/0137464401?&_encoding=UTF8&tag=jennsbookclu&linkCode=ur2&linkId=9976dc07c6ee8270b92718a66d1ef3ca&camp=1789&creative=9325) 
to refactor the existing code, and add the new feature (Conjured items).

The code linked above includes "snapshot" tests already.  Your changes 
to the code should be done in microsteps, such that the existing tests 
will pass after each small change made.  

The suggested approach would be to use something like the **Strategy Pattern**
to separate the functionality for the different sellable items in the store.

## Details ##
For completeness, here are some definitions/ explanations.

### Gilded Rose Kata ###
Hi and welcome to team Gilded Rose. As you know, we are a small inn with a 
prime location in a prominent city. We also buy and sell only the finest 
goods. Unfortunately, our goods are constantly degrading in quality as they 
approach their sell by date. We have a system in place that updates our 
inventory for us. It was developed by a no-nonsense type named Leeroy, who 
has moved on to new adventures. Your task is to add the new feature to our
system so that we can begin selling a new category of items. First an 
introduction to our system:

- All items have a SellIn value which denotes the number of days we have 
to sell the item
- All items have a Quality value which denotes how valuable the item is
- At the end of each day our system lowers both values for every item

Pretty simple, right? Well this is where it gets interesting:

- Once the sell by date has passed, Quality degrades twice as fast
- The Quality of an item is never negative
- "Aged Brie" actually increases in Quality the older it gets
- The Quality of an item is never more than 50
- "Sulfuras", being a legendary item, never has to be sold or decreases 
in Quality
- "Backstage passes", like aged brie, increases in Quality as it's SellIn 
value approaches; Quality increases by 2 when there are 10 days or less 
and by 3 when there are 5 days or less but Quality drops to 0 after the 
concert

We have recently signed a supplier of conjured items. This requires an 
update to our system:

- "Conjured" items degrade in Quality twice as fast as normal items

Feel free to make any changes to the UpdateQuality method and add any 
new code as long as everything still works correctly. However, do not 
alter the Item class or Items property as those belong to the goblin 
in the corner who will insta-rage and one-shot you as he doesn't 
believe in shared code ownership (you can make the UpdateQuality 
method and Items property static if you like, we'll cover for you).

Just for clarification, an item can never have its Quality *increase* 
above 50, however "Sulfuras" is a legendary item and as such its 
Quality is 80 and it never alters.

### Strangler Pattern ###
This pattern is one in which an “old” system is put behind an intermediary 
facade. Then, over time external replacement services for the old system 
are added behind the facade, until the point when the old implementation 
can be removed.

### Strategy Pattern ###
This pattern provides a way to extract the behavior of an object into 
separate classes that can be swapped in and out at runtime. This enables 
the object to be more flexible and reusable, as different strategies can 
be easily added or modified without changing the object's core code.
A helpful process for implementing the Strategy pattern is described 
[here](https://www.freecodecamp.org/news/a-beginners-guide-to-the-strategy-design-pattern):

1.  Identify the algorithm or behavior that needs to be encapsulated and made interchangeable.
2.  Define an interface that represents the behavior, with a single method signature that takes in any required parameters.
3.  Implement concrete classes that provide specific implementations of the behavior defined in the interface.
4.  Define a context class that holds a reference to the interface and calls its method when needed.
5.  Modify the context class to allow for the dynamic swapping of the concrete implementations at runtime.
