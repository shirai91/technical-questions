# technical-questions

My personal answers for some technical questions

## Questions

1. [What did you learn this past week?](#question-1)
2. [When building a new web site or maintaining one, can you explain some techniques you have used to increase performance?](#question-2)
3. [Can you describe some SEO best practices or techniques you have used lately?](#question-3)
4. [Can you explain any common techniques or recent issues solved in regards to front-end security?](#question-4)
5. [What actions have you personally taken on recent projects to increase maintainability of your code?](#question-5)
6. [Can you describe your workflow when you get a design to create a web page?](#question-6)
7. [If you have 5 different stylesheets, how would you best integrate them into the site?](#question-7)
8. [How many resources will a browser download from a given domain at a time? What are the exceptions?](#question-8)
9. [Name 3 ways to decrease page load (perceived or actual load time)](#question-9)
10. [Explain some of the pros and cons for CSS animations versus JavaScript animations.](#question-10)
11. [How would you approach fixing browser-specific styling issues?](#question-11)
12. [How do you serve your pages for feature-constrained browsers? What techniques/processes do you use?](#question-12)
13. [Can you explain the difference between coding a web site to be responsive versus using a mobile-first strategy?](question-13)
14. [How do you organize your code? (module pattern, classical inheritance?)](#question-14)
15. [What are the advantages and disadvantages of using Ajax?](#question-15)
16. [Create a for loop that iterates up to 100 while outputting "hello" at multiples of 3, "bitrep" at multiples of 5 and "hello bitrep" at multiples of 3 and 5](#question-16)
17. [What are the differences between ES6 class and ES5 function constructors?](#question-17)
18. [What is your process to find a performance bug in your code and what tools do you use?](#question-18)
19. [What are some ways to improve your websites scrolling performance?](#question-19)
20. [Is it better to serve your site assets from multiple domains? Why or why not?](#question-20)
21. [Explain in as much detail as possible what happens when you enter a URL into a web browser.](#question-21)
22. [Is What is the difference btwn onClick={() => this.props.onClick()} and onClick={this.props.onClick()} ? Which component type would use which?](#question-22)

## Answers

### Question 1

- How facebook testing react app
- How to parse javascript file into ASTtree

### Question 2

- Reduce extra HTTP Requests
- Minify CSS, JS and HTML
- Enable Prefetching
- Using CDN and Caching
- Use Files and images

### Question 3

- Title tags:

  - The title tag should be written like this: Primary Keyword – Secondary Keyword | Brand Name
  - Use a dash in between the keyword phrases and a pipe at the end before the brand name
  - Avoid duplicate title tags
  - Keep title tags at 55 characters or less in length, including spaces.

- Meta descriptions:

  - Write compelling meta descriptions
  - 150 to 160 characters is the recommended length
  - Avoid duplicate meta descriptions
  - Do not use quotes or any non-alpha characters (Google, cuts them out of the meta description)

- Header tags and keyword phrases:

  - Use your keyword phrase once in your H1 tag
  - Use H1 tags on pages you are trying to drive unique traffic to (SEO page)
  - Use H2 tags if there are multiple sections

- Image ALT tags and filenames:

  - Name all of your images in a way that describes what they are
  - Use dashes between the words, rather than underscores ( purple-hat.jpg rather than purple_hat.jpg)
  - Do not use non-alpha characters in your image or file names (so no %, &, \$, etc…)

### Question 4

We resolved the cookie injection by move jwt token and sensitive datas from localStorage to cookie with 'httponly'

### Question 5

- Sometime i refactor old component which outdated with current structure to improve maintainability
- Write instruction about how to start a new feature, and how to use our cli tool
- Write script to auto extract i18n into csv file automatically (previously, it is semi-auto)
- Write custom eslint rules to help code review for common case

### Question 6

1. Figuring out main topic/purpose of the page.
2. Is there a creative commons template exists for this topic?
   1. If exist then customize it, test it, decide if it fits project or not
   2. If not exist then sketch a basic design, improve it, decide if it fits project or not.
3. Review project in every aspect, search and fix bugs, improve things
4. Decide if project seems fine. If its not good enough, go step 4
5. Publish and ask some of your friends to test and review page. If there is bugs or nice suggestions, go, step 4.

### Question 7

if we're not using any post-css tools, i will consider to refactoring CSS in the prespective stylesheet, to prevent duplicated CSS, if we are using a post-css tool(s), i would import them as partials into main stylesheet (also consider to refactoring to prevent duplicated, but we should write a tool/script to do that )

### Question 8

It depend on browser, for chrome, it is 6, firefox 6, and ie 11 is 8. here is a very useful reference website [http://www.browserscope.org/?category=network&v=1](http://www.browserscope.org/?category=network&v=1)

As it limited per domain, so, in theory, if you has multiple domains pointing to the same IP address, we can increase the number of download connection at the same time to our site

### Question 9

- Minify the javascript, and split it to smaller chunks
- Combine and prune CSS files
- Compress image, or use some lazyloading technical.

### Question 10

CSS Animation

- Pros

  - No js, mean can run on browser which have javascript disabled
  - Some major browsers support `hardware acceleration` for CSS animaiton, which can running on difference CPU thread and access to GPU to improve performance, but the effective is minimal
  - Easy to write
  - Can cover atmost all animations

- Cons
  - Cannot handle complexity animations, have limited effects
  - CSS-based animation doesn't work in IE9 or earlier
  - Performance not always better than javascript-based animation in all browsers

Javascript Animation

- Pros
  - Can write animations for supports older browser
  - Can handle complexity animations and effects
  - Some library like GSAP has really good performance vs CSS based-framework
- Cons
  - Need enable javascript to run
  - We need to write and maintain code to perform animations
  - If we use library, our website will take more time to load
  - Javascript need time to execute, and parse, and cause browser re-paint, in some case it will have poor performance

### Question 11

Because fixing crossbroser-style issue is take so much time, and we always needed to rework from begin, while i'm developing a web application, i always follow the guidelines:

- Always build responsive layout
- Check html5 and css3 on `caniuse.com` to avoid things that have sketchy support at this time
- Always test across browser for avoid something will broken on other browser
- Use the knowledge and experience I’ve gained from my years in web development to know in advance what to avoid or what to do to make something work in all the browsers

### Question 12

- We often building an application for modern browsers while ensuring it remains functional in older browsers. (or adding some polyfill)
- We can check for feature support on caniuse.com, if that feature is fully support, i will use it, if some browser not support it, i will find some polyfill, if there is no way to use polyfill for that feature, i will find out an alternative way
- We use Autoprefixer for automatic vendor prefix insertion.

### Question 13

- Responsive design starts on the desktop; that is, at the maximum required resolution, and then scales down to the smallest screen. Even though the content and layout contract to fit smartphones, the navigation, content and download speeds are geared more for your traditional website.
- Mobile-first design is similar to designing a mobile app and then adapting the layout that it can be viewed neatly on tablet and desktop devices without too many modifications. Your whole design and layout are based on providing excellent mobile user-experience: fast download speeds, rich media content to keep your target audience interested, easy touchscreen navigation and so on.

### Question 14

When building a javascript applications, i'm always try to organize my application follow some below approachs:

- Scalable
- Structure folder by feature/module, not by functions-first
- Try to split feature/module to seperate file (physically) (in React, we use code splitting)
- Everything can be replaceable, since we often use an opensource framework, which can drop support after few year/month
  When development with react, i'm prefer duck structure, which splited out view component from logic part. A feature will look like bellow:
  ```
  features
  ├──container.component.jsx
  ├──components
  ├──├── component1.jsx
  ├──├── component2.jsx
  ├──├── component3.js
  ├──duck/
  ├──├── actions.js
  ├──├── index.js
  ├──├── operations.js
  ├──├── reducers.js
  ├──├── selectors.js
  ├──├── tests.js
  ├──├── types.js
  ├──├── utils.js
  ```

The pros of this structure is can support a long-time run project, we can change any blocks in our app
The cons is this structure contains so many file, and complexity, for resolve this issue, i provide some script to generate template file using `plop`, and write some `eslint rule` to make sure team member not put jsx into duck files

### Question 15

- Pros
  - Improve user experience by fetching small data without re-load page
  - Reduced server hit and network load
  - You can develop a standalone web application and integrate it with any kind of server-side
- Cons
  - AJAX only can work on browser which support/turning on javascript
  - Use ajax may cause so many security issues (xss, reverse engineering)
  - In some case, if developer adding some polling system call, it will increase load on server

### Quesstion 16

```javascript
const helloBitrep = () => {
  let output;
  for (let i = 1; i < 101; i += 1) {
    output = "";
    if (!(i % 3)) {
      output += "hello";
    }
    if (!(i % 5)) {
      output += "bitrep";
    }
    if (output) {
      console.log(output);
    }
  }
};
```

### Question 17

Technically, class is just a suger syntax for es5 function constructors, you can micmic all es6 class's features with es5 constructor functions

### Question 18

When a performance bugs happening (which can show as memory leak. fps drop dramatically, some 'delay' and browser 'freeze'), we can use chrome/firefox devtool to find out the problems. chrome devtool has 'performance' tab, which allow you to record and diagnostic everything happen with your pages. I'm often use this workflow:

1. Try to reproduce the issue
2. Open devtool-> performance tool, click record and reproduce the issue.
3. Stop recording, and inspect the report output. The output will showing as a timeline, find the 'event' which cause the issue, and inspect on timeline, if the script's time is high, it caused by that javascript function, check the implementation of that event and find out the root cause
4. If process time for paint or layout is high, we need to check css on that page, and optimize it follow approach: avoid resize element since it will trigger browser relayout the page, and avoid expensive style (like box-shadow).
   NOTE: browsers always ship new version every few months, which improve performance of js,css. so nothing stay the same, so dont follow any outdated `cheat sheet` for finding performance bugs, we should use developer tools for identify where is the root cause of the problem.

### Question 19

I'm not often dealing with scroll performance, but i'm got some basic case which i'm solved by using these solutions:

1. Debounce the scroll event if you need to watch scroll event
2. Use devtool to diagnostic `layout` and `paint`'s time. if it too high and browser cannot render ~60fps. we need to review all css in current rendering page. and optimize it follow this approach : avoid to resize elements. try to avoid expensive styles (like box-shadow)

### Question 20

Yes, because browsers usually have limits on the number of concurrent downloads from a domain at a moment. So, serving assets from multiple domains can increase the concurrent level, so it can improve loading speed of static resource.

### Question 21

When you type url into address bar of your browser

1. The browser checks the cache for a DNS record to find the corresponding IP address of url follow this order: browser cache, OS cache , router cache, IPS cache.
2. If request url is not in the cache, ISP's DNS server initiates a DNS query to find the IP address of the server that host url
3. Browser initiates a TCP connection with the server
4. The browser sends an HTTP request to the webbrowser
5. The server handle request and send back a response.
6. The server sends out an HTTP response.
7. The browser try to parse the response (HTML to DOM and CSS to CSSOM, parse javascript to EStree to execution). if the response is NOT html, browser display it as plain text, or try to parse it based on specific browser.

### Question 22

In react, if you use

```javascript
onClick={() => this.props.onClick()}
```

everytime host component trigger `render()`, onClick prop will change value to new created function (created by `()=>this.props.onClick()`), and component attached with above `onClick` prop will trigger a re-render (as react component only re-render when props or state change, or you trigger component.forceupdate() function), which will cause performance issue especially on a page with large amount of components
But when you use

```javascript
onClick={this.props.onClick()}
```

everytime host component trigger `render()`, onClick prop will still have same value with previous props, and component attached with above `onClick` will not trigger re-render
