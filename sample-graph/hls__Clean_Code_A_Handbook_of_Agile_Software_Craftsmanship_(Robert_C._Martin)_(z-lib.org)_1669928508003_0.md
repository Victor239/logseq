file-path:: ../assets/Clean_Code_A_Handbook_of_Agile_Software_Craftsmanship_(Robert_C._Martin)_(z-lib.org)_1669928508003_0.pdf

- “Honesty in small things is not a small thing.” It was a good omen consistent with what I already wanted to say here. Small things matter. This is a book about humble concerns whose value is nonetheless far from small. God is in the details, said the architect Ludwig mies van der Rohe. 
  ls-type:: annotation
  hl-page:: 20
  hl-color:: yellow
  id:: 638a3b7f-565d-4a29-a870-ab87da058d63
- A place for everything, and everything in its place. A piece of code should be where you expect to find it—and, if not, you should re-factor to get it there.
  ls-type:: annotation
  hl-page:: 21
  hl-color:: yellow
  id:: 638a3c1e-979c-4eab-ace8-63c5b5723b59
- What do the authors here say about littering your code with comments and commented-out code lines that capture history or wishes for the future? Get rid of them.
  ls-type:: annotation
  hl-page:: 21
  hl-color:: yellow
  id:: 638a3c2d-d4e5-4461-ad37-44ed74be40c8
- As Fred Brooks admonishes us, we should probably re-do major software chunks from scratch every seven years or so to sweep away creeping cruft. Perhaps we should update Brooks’ time constant to an order of weeks, days or hours instead of years. That’s where detail lies.
  ls-type:: annotation
  hl-page:: 22
  hl-color:: yellow
  id:: 638a3c64-c29e-42bb-b172-d9b62e0f57ac
- You should name a variable using the same care with which you name a first-born child.
  ls-type:: annotation
  hl-page:: 22
  hl-color:: yellow
  id:: 638a3ca8-7501-42e1-8369-1611b7b1b519
- Clean Code
  ls-type:: annotation
  hl-page:: 32
  hl-color:: yellow
  id:: 638a3e23-1c62-4e60-81cc-0b47c91a2233
- I know of one company that, in the late 80s, wrote a killer app. It was very popular, and lots of professionals bought and used it. But then the release cycles began to stretch. Bugs were not repaired from one release to the next. Load times grew and crashes increased. I remember the day I shut the product down in frustration and never used it again. The company went out of business a short time after that. Two decades later I met one of the early employees of that company and asked him what had happened. The answer confirmed my fears. They had rushed the product to market and had made a huge mess in the code. As they added more and more features, the code got worse and worse until they simply could not manage it any longer. It was the bad code that brought the company down.
  ls-type:: annotation
  hl-page:: 34
  hl-color:: yellow
  id:: 638a3ed2-c357-4749-a91c-d3464891b2c8
- The degree of the slowdown can be significant. Over the span of a year or two, teams that were moving very fast at the beginning of a project can find themselves moving at a snail’s pace. Every change they make to the code breaks two or three other parts of the code. No change is trivial. Every addition or modification to the system requires that the tangles, twists, and knots be “understood” so that more tangles, twists, and knots can be added. Over time the mess becomes so big and so deep and so tall, they can not clean it up. There is no way at all.
  ls-type:: annotation
  hl-page:: 35
  hl-color:: yellow
  id:: 638a3f2f-27e5-4e4c-92f9-f5d951a62cfb
- I like my code to be elegant and efficient. The logic should be straightforward to make it hard for bugs to hide, the dependencies minimal to ease maintenance, error handling complete according to an articulated strategy, and performance close to optimal so as not to tempt people to make the code messy with unprincipled optimizations. Clean code does one thing well.
  ls-type:: annotation
  hl-page:: 38
  hl-color:: yellow
  id:: 638a4048-4d4b-4735-8381-e2a2431f4fc4
- Clean code is simple and direct. Clean code reads like well-written prose. Clean code never obscures the designer’s intent but rather is full of crisp abstractions and straightforward lines of control.
  ls-type:: annotation
  hl-page:: 39
  hl-color:: yellow
  id:: 638a4081-77a3-4ac6-8d05-2016789079a2
- Clean code can be read, and enhanced by a developer other than its original author. It has unit and acceptance tests. It has meaningful names. It provides one way rather than many ways for doing one thing. It has minimal dependencies, which are explicitly defined, and provides a clear and minimal API. Code should be literate since depending on the language, not all necessary information can be expressed clearly in code alone.
  ls-type:: annotation
  hl-page:: 40
  hl-color:: yellow
  id:: 638a409e-1ea8-452d-8ee8-1a53c57bc78f
- I could list all of the qualities that I notice in clean code, but there is one overarching quality that leads to all of them. Clean code always looks like it was written by someone who cares. There is nothing obvious that you can do to make it better. All of those things were thought about by the code’s author, and if you try to imagine improvements, you’re led back to where you are, sitting in appreciation of the code someone left for you—code left by someone who cares deeply about the craft.
  ls-type:: annotation
  hl-page:: 41
  hl-color:: yellow
  id:: 638a40dd-e460-443c-bb0c-968ff98fffdf
- In priority order, simple code:• Runs all the tests;• Contains no duplication;• Expresses all the design ideas that are in the system;• Minimizes the number of entities such as classes, methods, functions, and the like.
  ls-type:: annotation
  hl-page:: 41
  hl-color:: yellow
  id:: 638a4102-567c-4995-bca8-33e9eafbd844
- xpressiveness goes11The Total Cost of Owning a Mess beyond names, however. I also look at whether an object or method is doing more than one thing. If it’s an object, it probably needs to be broken into two or more objects
  ls-type:: annotation
  hl-page:: 41
  hl-color:: yellow
  id:: 638b485c-9dc9-46cc-8766-d86faca88580
- beyond names, however. I also look at whether an object or method is doing more than one thing. If it’s an object, it probably needs to be broken into two or more objects
  ls-type:: annotation
  hl-page:: 42
  hl-color:: yellow
  id:: 638b4863-a705-440c-965b-59e16b3add96
- It’s
  ls-type:: annotation
  hl-page:: 45
  hl-color:: yellow
  id:: 638b9a27-0036-4f37-b084-e680ed9252cc