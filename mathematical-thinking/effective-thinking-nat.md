# Effective Thinking - Notes and Thoughts

This course is all about learning to think more effectively. The strategies and concepts discussed in this course should be applicable to most of our lives, not just mathematics.
I'm following [this course](https://courses.edx.org/courses/UTAustinX/UT.9.01x/1T2014) while also at the same time following the [Introduction to Mathematical Thinking](https://www.coursera.org/course/maththink) from Stanford at Coursera.

It's my first course as port of my OSS Journey.

## Topics

0. The five elements and puzzles
1. Numbers
2. Infinity (and beyond)
3. Forth Dimension
4. Koningberg bridge puzzle
5. The world of uncertainity
6. topology
7. concept of elections

## Section 0

### Five elements of Effective Thinking

There are 5 elements that you can refer always back to, that function as the pillars of "Effective Thinking".
In order to remember them easily you could think of the 4 elements of classical thought, plus a 5th additional element added by the Greek and Indians.

1. **Earth**: Deep Knowledge
  + Deep knowledge of _simple_ things is very important. Once you enter more advanced topics and become profound in them, it is important to return to the basics (regularly) and look at these basic concepts with a deeper understanding. You'll notice how you'll see them in a different daylight.
2. **Air**: Raise Questions
  + Asking questions is important. Why is something like it is? Can we do better? What could a different approach be? How did a solve this problem? Asking problems can be helpful as part of solving a problem. It helps us in solving some of the unknowns, which can be especially important when there are to many of these. But asking questions can also be usefull as part of the reflection process. Looking back at that which has been done, goes hand in hand with asking questions.
3. **Fire**: Make Mistakes
  + Mistakes give direction. It's much easier to build gread ideas on top of failures than it is to craft them out of the fog of confusion.
  + Mistakes elimnate wrong directions and highlight correct solutions. They can serve as valuable lessons and give us a deeper understanding of a subject. It's only by trying that you will actually achieve your goals.
4. **Water**: Flow of Ideas
  + It's important that ideass and solutions are build on (mis)conceptions and older ideas. When exploring a problem or idea, it can be very helpful to uncover the flow of ideas and learn from its ancestors.
  + I think it's nice to highlight that these elements can also be combined. And thus you coul for example ask questions about previous elements in this flow such as, what could a variant route in this flow be? Would we get to the same resolution? If not, would it lead to better approaches or just different ones?
  + Uncovering hidden connections between ideas and concepts lead to innovation, especially when you go cross-field. The news is full examples of this, with examples of cross-field innovations of the medical and engineering world.
5. We use the 5th element to represent the changing of things
  + Concepts change, and so do idea's.
  + [TODO] Explore this idea better. I'm assuming that this element will be further uncovered over time.

### The "Meanie Genie" Puzzle

The description of this puzzle was very detailed full of information that can be ignored. Here is my distilled version of the puzzle:

> You have 9 rocks. One of these rocks contain a diamond and is therefore slightly heavier. You have a balance and are allowed to use it 2 times. Can you with complete certainity find the diamond rock. Explain why or why not.

So after thinking about the idea for a while, I decided to go for my first thought:

  > We'll take 2 pairs of 4 rocks, leaving 1 rock on the side. If the 2 pairs are equal, we know the diamond is the 9th rock. That's however quite unlikely, and therefore you are probably left with 4 rocks. You can than do 2 different things. Either you leave 2 on the side and you weight 2 rocks 1-to-1. This gives you a 50% change of finding the rocks as it can be 1 of these 2 rocks. If the 2 balanced rocks are once again equal, than your screwed as you have 2 unknowns left and no more turns. The second approach of using this second balance turn is to weight them in pairs of 2, giving you no rest stones. This however would always lead to 2 unknowns, making it just as useless, if not more useless, as you wouldn't even have the 50% lucky opportunity that you would have actually found the rock.

At this point I was quite stuck and after making some tea and thinking more about it, I gave up. That was my first mistake. If we look back at the 5 elements we can clearly see that _making mistakes_ is one of its elements and at this points we should therefore not give up but triumph. Sadly I didn't do that, and I went straight to watching the video where you could see a student solving the problem himself, robbing myself of the opportunity of solving this problem on my own.

It was great to see that his first approach was the same as my approach. Although looking back at it, it probably also just means that this is the most obvious approach. Why is this obvious? Well, we know that balanacing an odd amount of stones gives us no usuable information at all, as you couldn't with full certainity tell if such a result is helpful or not. Therefore it's quite easy to substract one stone and come to the realisation that you can make 2 pairs of 4 stones, and therefore have a valid pair of set of stones you can balance.

The students looked back at the issue and realised the actual solution:

> We can divide the stones in 3 pairs of 3 stones each, leaving no stones unpaired. We can than measure 2 pairs. If the result is equal, than we know that the diamond is in the 3rd pair. If one the balanced pairs is more heavier than we know the diamond is in that pair. In either case we are left with 3 stones and 1 balance turn. Using our second turn to balance 2 stones 1-to-1, we know which stone contains the diamond. Why? Well, if one of these stones is more heavy, we know it contains the diamond. If both stones however are equal, than we know the diamond can be found in the third stone, the one on the side. This solutions proofs that we can indeed with full certainty find the diamond.

Afterwards we also learned that we could have come to this conclusion faster using a systematic approach.

+ As I explained earlier, balancing an odd amount of stones is not useful.
+ Therefore we can list all different pairs we can make and measure like that.
  + e.g.: {4, 4, 1}, {3, 3, 3}, {2, 2, 2, 2, 1}, {1, 1, 1, 1, 1, 1, 1, 1, 1}
+ This way we can go through each branch and reason in a quick way wether or not that was usefull

This systematic approach is quite usefull in challenging problems as we often resist going down certain paths. It also gives us "a strategy" that we can continiously follow without going in full dispair, as I did. I do believe that a full systematic approach is quite unfeasable for a problem with many possible approaches, and therefore a hybrid form or a completely different strategy will be usefull in such cases. But on the other hand, I do believe that it can be a helpful strategy where applicable.

All in all, I took the time to reflect on 5 elements of Effective thinking. I realize that giving up after my wrong first approach was a mistake. A mistake, nothing more, nothing less. Next time I should use it as a directive, rather than a source of dispair. I'm quite happy with the coursee so far. The professor teaches and talks in a very enjoyable way, and it really makes me reflect and explore the content in a learnful way. It's funny how subjects can seem so trivial, while they are actually not. It's like the difference between thinking you know something and actually truly and deeply know it. It's one of those examples that shows how our mind can tricks us in a way, that makes us live in a parallel universe.

### The puzzles of the pirates and the admirals

> There are 3 pirates and 3 admirals that want to cross a river. They can do this with a boat that they have that fits 2 people at the same time and needs at least 1 person in the boat to move. You can't have more pirates than admirals at any side at any given time as that would give problems. How do you move them all to the other side from the river?

This puzzle was easier for me to solve, and just by trying I managed to do it quite fast. Which is an important lesson: **Always try**! Although you should remember not to get ahead of yourself. Fairlure is also fine and you will get experience either way. A last tip and lsson learned from this and other bonus puzzles is that you should always make sure to **concider each possibility**.

## Section 1

### Understanding simple things deeply: Multiplication


