# Cheatsheet questions for nodejs
1. What is nodejs?<br/>It's JavaScript(JS) runtime environment. It uses v8 engine of chrome(google) to run the JavaScript. NodeJs allows JS code to be run outside chrome. This allows JS to be used as a backend language.

2. What is json?<br/>Json is JavaScript Object Notation. Json is a way of writing a JS object. That way is using curly brackets to repsent the entire JS object. Example:
```
{
  "name": "Abhishek",
  "age": 23,
  "leftEye": {
    "color": "black",
  },
}
```
<br/>
This is very similar to Java. Example:

```
class Human {
  String name;
  int age;
  Eye leftEye;
}
class Eye {
  String color;
}
Eye leftEye = new Eye("black");
Human h = new Human("Abhishek", 23, leftEye);
```

4. What is package.json?<br/>Package json is a json file which is present at the root directory of the project. It contains metadata of the project. It is used to manage dependencies of the projects, scripts of the projects and a lot more. This is the most important file of the node project as everything starts from here.

5. What is npm?<br/>npm is node package manager tool. It uses package.json to manage the node project. For example, it can be used to run any script; it can be used to download any dependency etc.

6. What is mainModule in package.json?<br/>When we run `meteor run`, then meteor checks the value of mainModule in package.json. It goes to those mainModule files to run server and client.

7. What happens when you run `meteor run`?<br/>On running `meteor run`, the main module file of the server is started. Client's main module is not started. mainModule is found from package.json

8. What usually happens in main module of server?<br/>We run `Meteor.startup()` to start up the server. This does a lot of things: i) it starts the http server, ii) it starts the application server, iii) it starts the database server. After all these servers are started, we can run a method of our own. For example: pre populating the database.

9. How to create a mongodb collection or make updates in it using meteor?<br/>Meteor has a library called mongo. We can use this library to create a collection object. We can use this collection object to insert or make updates in the collection. `new Mongo.Collection('appointmentProfile')` is used to create a collection called appointment profile. Mongo library of meteor takes care of creating the database connections etc.

10. Why do we use `Accounts` library to create/update users instead of directly creating users using `users` collection?<br/>`users` collection usually invoves security, authentication etc. For this, Meteor provides us `Accounts` library in which it handles all the security, authentication etc. So we use `Accounts` library instead of directly creating users.

11. Which library `Accounts` library uses to encrypt the password?<br/>`bcrypt`

12. What happens when client hits the url?<br/>When client hits url, the request goes to the http server. In response, http server sends all the html, css, jsx files to the client. In the client browser, html of main module is shown and jsx of main module is run. main module of client can be found in the package.json file. 

13. What does main.jsx do?<br/>We call `Meteor.startup()`. This call is very different from the `Meteror.startup()` of server's maon module. Client's startup calls sets up the DOM, sets up the meteor in the client browser. Once the setup is done, the post startup method is run. In post startup method, we render the `<App/>` component in one of the DOM's element.

14. What is difference between document of mongodb and document in client browser?<br/>In mongodb, a collection(table) has various documents(rows). In client browser, document represents the DOM root.

15. What is the difference between js file and jsx file?<br/>jsx file can have both javascript and xml but the js file has only js.

16. What does xml in the jsx represent?<br/>In jsx, xml is the component which will eventually be a part of DOM. Remaining js part is pure javascript which will run in js engine.

17. What does `export` mean in js or jsx?<br/>If we use `export` in front of any variable or function, it can be used outside that file using import.

18. What is jsx component?<br/>jsx component is a lambda function. A jsx component has js code and xml code. Return type of this lambda method is xml. This xml will eventually be part of DOM.

19. How to call a jsx component?<br/>Jsx component is a lambda function but we don't use typical way of calling lambda i.e. `App()` is not used where App is component name. Instead, to call a jsx component, we use `<App/>`. Similary if a jsx component takes some args, then we don't use `App("Abhishek")`. Instead we use `<App name="Abhishek" />`

20. How to write js and xml in jsx?<br/>We start with js. We can directly write xml in js if it's of one line. If xml is of multiple lines, then use small brackets. Once we are in xml, if we want to js, use curly brackets to enter into js mode.

21. Why useState is used?<br/>useState is a nice feature of reactjs. If we have a requirment where we want to update the DOM automatically whenever a JS variable changes, then we use useState. When we use a useState variable, react maintains a map between the variable and DOM element in which it is used. React also tracks that this js variable is changed or not. Whenever the js variable changes, react tracker gets to know about it and it refreshes the DOM element in which it is used.

22. Why useTracker is used?<br/>useState is used for JS variable but not for JS methods. If we have a requriement where we want to update the DOM automatically whenever a JS method returns some different output, then we use useTracker. useTracker is a feature of meteor which internally uses useState of reactjs. 

23. What are methods to handle login in Meteror client side?<br/> `Meteor.user()` gives us the logged in user. `Meteor.loginWithPassword()` logs in the user. `Meteor.logout()` logs out the user.

24. How to create a user in client side?<br/> In server side, we use `Accounts` library but we can't use `Accounts` library directly in client side. So, to create a user, we add a `method` in server side and call it using `Meteor.call()`.

25. How Meteor takes care of request response model aka http calls?<br/> In server side, create a method using `Meteor.methods()`. In client side, call that method using `Meteor.call()`.

26. How Meteor takes care of push mode aka one request-multiple response?<br/> In server side, create a `publish` method. In client side, `subscribe` to that published method.

