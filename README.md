# Week 5 Practical 2: Web Accessibility
Stage 1 is about developing a better understanding of WCAG. Stage 2 is a more complex development challenge--your task is to make an inaccessible sliding image game accessible. 

## Stage 1
### Exercise 1.1: WCAG 2.0
But first, we need to have a better understanding of what web accessibility means and what guidelines are in place for designers and developers. So, open the [WCAG 2.0 guidelines](https://www.w3.org/TR/WCAG20/) and explore them. Make notes on what it means for a website to be:
- perceivable,
- operable,
- understandable and
- robust.

The WCAG guidelines are often intimidating and verbose. Record your notes in language that is accessible for you to quickly understand and apply to a website. 

### Exercise 1.2: York Sport Analysis
Open the [York Sport website](https://www.york-sport.com/) and try to use the site using ONLY the keyboard and not the mouse. Nielson has written [some guidance](https://www.nngroup.com/articles/keyboard-accessibility/) on how to approach this.

Take notes on whether you can:
- Navigate through the different menu items.
- Tab through all the page content in a logical order.
- Easily identify what is in focus from the keyboard. When you tab through the content the current active link is shown in the bottom left of the google chrome window.
- Use the forms on the webpage (e.g. the sign-up form)

Next, put the website through the Chrome Developer Tools accessibility audit, as we did in lecture:
1.	With the website open in Chrome, open Developer Tools by going to View > Developer > Developer Tools
2.	In the Developer Tools pane, go to the Lighthouse tab. It’s quite a few places right from the first tab, Elements. If your browser window is small, you might need to click the >> symbol to find the Lighthouse tab.
3.	Lighthouse presents a number of options. Under "Mode", select "Navigation". Under "Device", select "Desktop". Under "Categories", tick "Accessibility" and untick any other options. Finally, click "Analyze page load" to generate the report. It will take a few seconds.

What accessibility problems are identified? Note, these problems are identified in terms of the WCAG 2.0 criteria that may (or may not) be violated. You can find more detail on each problem, including the specific elements affected, by clicking on the problem description. For each problem, follow the "Learn more" link in the problem details.

## Stage 2
Open the starter code in the slidingPuzzle folder in this repo. Run sliding-puzzle.html and try playing the game with your mouse / trackpad. 

Next, try playing the game using only your keyboard. You will find it impossible because the code suffers from a number of accessibility problems.

## Exercise 2.1: Using the right HTML elements for the job
In general, UI objects that are intended to be selectable should be made from elements designed to be interactive: buttons, links, and other input elements. These elements natively support keyboard interaction. In the sliding puzzle game, the puzzle tiles and the control buttons are created with div tags, which do not natively support keyboard interaction.

Replace the divs with class "tile" and "menu-item" with more appropriate HTML elements. Buttons will work best but you may want to try using a link or two to see the effect.

## Exercise 2.2: Using the right JavaScript events
After completing the previous exercise, try playing the game with your keyboard again. You will find the tiles are now keyboard focusable but not selectable--presing enter or space while a tile is in focus should have the same effect as clicking it. A tiny, one-word change in theJavaScript can address this issue. See if you can find it and fix it.

## Exercise 2.3: Focus order should be logical
Notice that when tabbing through the two menu buttons, the focus moves from right to left instead of left to right, the order that users would read the buttons in English. This issue may seem trivial in this instance but illogical or out-of-order keyboard navigation is a common accessibility issue, particularly when there are lots of navigable items.

Try editing the HTML/CSS for the menu so that keyboard focus moves from left to right while maintaining the right-aligned menu.

## Exercise 2.4: Don't forget the alt tags
The puzzle tiles are now keyboard accessible but they contain images that don't have the alt tag that screen readers use to provide their users with information about what is in the image. Currently, a low vision user would be able to tell when a tile is focused but they would not have any information about whether that tile is in the correct place. Add informative alt descriptions to each image. Remember, alt tags should describe the meaning of the image in the context of use.

## Exercise 2.5 (optional): Add styling on focus
Keyboards are used for navigation by diverse users who may or may not have vision impairments. For sighted users, it can be helpful to add visual styling to a keyboard focus, similar to adding hover styles to links and buttons. Consider adding [focus styling](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus) to the image tiles and menu buttons.