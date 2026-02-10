1. Describe the path an HTTP Request takes from a browser to your GitHub Pages site.

    a. The url in the browser, which contains information such as indication of https protocol and the host name. The host name, which comes after the two slashes, is passed onto Domain Name Service (DNS) which sends back the correct IP address. The browser then creates a connection to the correct server using a socket. 
    
    B. The browser sends a GET request for the associated url. 

    C. The server locates the necessary files and prepares a response. It sends an OK status code with the needed files. 

    D. The browser renders them on the page. 


 2. We discussed Docker Containers in class. Explain how a Docker Container differs from the
    environment provided by GitHub Pages.

    As discussed in class, a Docker enviroment would provide a containerized setup in which many different kinds of code necessary for an application to run correctly would be packaged so that it could reliably run on different machines.  A Docker container would include all necessary dependencies and libraries to make sure it would execute consistently.

    The environment provided by Github pages provides a simpler environment in which static files can be stored on a server and retrieved in order to run something like a web page in a browser. Github pages would not store libraries, dependencies or other code  that is needed to perform some other task beyond rendering a webpage.


3. While I tried to keep use of AI minimal at first, I did consult specific layout designs on Wix with the goal of attempting to replicate their functionality on my own. My layout is specifically an attempt to emulate this page: 

https://www.wix.com/website-template/view/html/2748?originUrl=https%3A%2F%2Fwww.wix.com%2Fwebsite%2Ftemplates%2Fhtml%2Fportfolio-cv%2Fresumes-cvs&tpClick=view_button&esi=a5832b56-6c36-4534-9563-9d2b8d97a212


However, I gave myself the constraint that anything beyond the scope of what we'd covered so far that I didn't know how to do without consulting AI too much was off limits. I have some experience with web development, but it has been a long time, so I wanted to challenge myself and I found I remmebered less than I thought.

Eventually, I wound up needing to consult ChatGPT to figure out the correct way to split the page and keep scrolling on one side while hiding the the scroll bars. I gave it the following prompt:

- can you give me code that splits a webpage in half using css but hides the scroll bars

and got this response: 

CSS (Split page + hidden scrollbars)
/* Reset */
html, body {
  margin: 0;
  height: 100%;
  overflow: hidden; /* Prevent body scroll */
}

/* Layout */
.container {
  display: flex;
  height: 100vh;
  width: 100vw;
}

/* Shared pane styles */
.left, .right {
  width: 50%;
  height: 100%;
  overflow-y: scroll;
  padding: 20px;
  box-sizing: border-box;

  /* Hide scrollbar – Firefox */
  scrollbar-width: none;

  /* Hide scrollbar – IE/Edge */
  -ms-overflow-style: none;
}

/* Hide scrollbar – Chrome/Safari */
.left::-webkit-scrollbar,
.right::-webkit-scrollbar {
  display: none;
}

/* Optional visuals */
.left {
  background: #f4f4f4;
}

.right {
  background: #ffffff;
}


As you can see in my final code, I wound up integrating some of this, but also had to consult stackoverflow and other sources to figure out how to apply this specifically to what I was trying to do. This code provided by chatGPT left both sides scrollable and did not provide an easy way to center the photo in the right panel or have the text scroll verically the way I wanted. In researching how to achieve a static, centered layout similar to the Wix reference, I found that using flexbox was most appropriate. You can see my changes reflected in the following code from my css file: 


.page {
    display: flex;
    height: 100vh;
}

.rightside {
    width: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #89a27e;
}

Overall, my AI use regarded mostly this prompt as well as syntax checks along the way where I would provide my code as written and ensure its logic was correct. 

Google AI overview results returned from stack overflow were also occassionally integrated, but were for generalized conceptual questions and not code output from generative prompts like with chatGPT.