1. Flex-direction: row will lay the elements in the flexbox out at horizontally whereas flex-direction:column will lay them out vertically.  For example, in my media query I switched from row to column in order to get the nav-bar items to stack on top of eachother verticaly in mobile view. 

2. Fixed pixel amounts become an issue when trying to have responsive design.  When, for example, resizing to mobile view if you are using fixed pixel amounts you will run into formatting problems where the size of the text is way larger than what you intend. Using rem of % makes it so that as the size of the screen changes, the text adapts responsively to the size of the screen it is on. 

3. AI Usage: consulted Claude with the prompt: Help me use CSS to make html grid show as stacked column on mobile.

Provided the following:

.projects-grid {
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
}

However, this did not work for my layout and I wound up changing it to simply this: 

 .projects-grid {
        grid-template-columns: 1fr;
    }

Which forces it to collapse into one column the way I needed. 