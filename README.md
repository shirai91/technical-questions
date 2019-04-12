# technical-questions
My personal answers for some technical questions

## Questions
1.	[What did you learn this past week?](#question-1)
2.	When building a new web site or maintaining one, can you explain some techniques you have used to increase performance?
3.	Can you describe some SEO best practices or techniques you have used lately?
4.	Can you explain any common techniques or recent issues solved in regards to front-end security?
5.	What actions have you personally taken on recent projects to increase maintainability of your code?
6.	Can you describe your workflow when you get a design to create a web page?
7.	If you have 5 different stylesheets, how would you best integrate them into the site?
8.	How many resources will a browser download from a given domain at a time?
o	What are the exceptions?
9.	Name 3 ways to decrease page load (perceived or actual load time)
10.	Explain some of the pros and cons for CSS animations versus JavaScript animations.
11.	How would you approach fixing browser-specific styling issues?
12.	How do you serve your pages for feature-constrained browsers?
o	What techniques/processes do you use?
13.	Can you explain the difference between coding a web site to be responsive versus using a mobile-first strategy?
14.	How do you organize your code? (module pattern, classical inheritance?)
15.	What are the advantages and disadvantages of using Ajax?
16.	Create a for loop that iterates up to 100 while outputting "hello" at multiples of 3, "bitrep" at multiples of 5 and "hello bitrep" at multiples of 3 and 5
17.	What are the differences between ES6 class and ES5 function constructors?
18.	What is your process to find a performance bug in your code and what tools do you use?
19.	What are some ways to improve your websites scrolling performance?
20.	Is it better to serve your site assets from multiple domains?  Why or why not?
21.	Explain in as much detail as possible what happens when you enter a URL into a web browser.
22.	[Is What is the difference btwn onClick={() => this.props.onClick()}
and onClick={this.props.onClick()} ?  Which component type would use which?](#question-22)

## Answers

### Question 22
In react, if you use
```javascript
onClick={() => this.props.onClick()}
```
everytime host component trigger `render()`, onClick prop will change value to new created function (created by `()=>this.props.onClick()`), and component has above `onClick` prop trigger a re-render, as react component only re-render when props or state change, or you trigger component.forceupdate() function, which will cause performance issue especially on a page with large amount of components
But when you are using
```javascript
onClick={this.props.onClick()}
```
everytime host component trigger `render()`, onClick prop will still have same value with previous props, and component attached with above `onClick` will not trigger re-render
