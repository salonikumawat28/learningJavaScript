# Cheatsheet questions for nodejs
1. What is nodejs?

It's JavaScript(JS) runtime environment. It uses v8 engine of chrome(google) to run the JavaScript. NodeJs allows JS code to be run outside chrome. This allows JS to be used as a backend language.

2. What is json?

Json is JavaScript Object Notation. Json is a way of writing a JS object. That way is using curly brackets to repsent the entire JS object. Example:
```
{
  "name": "Abhishek",
  "age": 23,
  "leftEye": {
    "color": "black",
  },
}
```

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

4. What is package.json?

Package json is a json file which is present at the root directory of the project. It contains metadata of the project. It is used to manage dependencies of the projects, scripts of the projects and a lot more. This is the most important file of the node project as everything starts from here.

5. What is npm?

npm is node package manager tool. It uses package.json to manage the node project. For example, it can be used to run any script; it can be used to download any dependency etc.

6. What is mainModule in package.json?

When we run `meteor run`, then meteor checks the value of mainModule in package.json. It goes to those mainModule files to run server and client.

7. What happens when you run `meteor run`?

On running `meteor run`, the main module file of the server is started. Client's main module is not started. mainModule is found from package.json

8. What usually happens in main module of server?

We run `Meteor.startup()` to start up the server. This does a lot of things: i) it starts the http server, ii) it starts the application server, iii) it starts the database server. After all these servers are started, we can run a method of our own. For example: pre populating the database.

9. How to create a mongodb collection or make updates in it using meteor?

Meteor has a library called mongo. We can use this library to create a collection object. We can use this collection object to insert or make updates in the collection. `new Mongo.Collection('appointmentProfile')` is used to create a collection called appointment profile. Mongo library of meteor takes care of creating the database connections etc.

10. Why do we use `Accounts` library to create/update users instead of directly creating users using `users` collection?

`users` collection usually invoves security, authentication etc. For this, Meteor provides us `Accounts` library in which it handles all the security, authentication etc. So we use `Accounts` library instead of directly creating users.

11. Which library `Accounts` library uses to encrypt the password?

`bcrypt`

12. What happens when client hits the url?

When client hits url, the request goes to the http server. In response, http server sends all the html, css, jsx files to the client. In the client browser, html of main module is shown and jsx of main module is run. main module of client can be found in the package.json file. 

13. What does main.jsx do?

We call `Meteor.startup()`. This call is very different from the `Meteror.startup()` of server's maon module. Client's startup calls sets up the DOM, sets up the meteor in the client browser. Once the setup is done, the post startup method is run. In post startup method, we render the `<App/>` component in one of the DOM's element.

14. What is difference between document of mongodb and document in client browser?

In mongodb, a collection(table) has various documents(rows). In client browser, document represents the DOM root.

15. What is the difference between js file and jsx file?

jsx file can have both javascript and xml but the js file has only js.

16. What does xml in the jsx represent?

In jsx, xml is the component which will eventually be a part of DOM. Remaining js part is pure javascript which will run in js engine.

17. What does `export` mean in js or jsx?

If we use `export` in front of any variable or function, it can be used outside that file using import.

18. What is jsx component?

jsx component is a lambda function. A jsx component has js code and xml code. Return type of this lambda method is xml. This xml will eventually be part of DOM.

19. How to call a jsx component?

Jsx component is a lambda function but we don't use typical way of calling lambda i.e. `App()` is not used where App is component name. Instead, to call a jsx component, we use `<App/>`. Similary if a jsx component takes some args, then we don't use `App("Abhishek")`. Instead we use `<App name="Abhishek" />`

20. How to write js and xml in jsx

We start with js. We can directly write xml in js if it's of one line. If xml is of multiple lines, then use small brackets. Once we are in xml, if we want to js, use curly brackets to enter into js mode.



