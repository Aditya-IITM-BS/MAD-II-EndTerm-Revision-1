# End Term Revision

Q1: Consider the following program,

```js
x = [1, 2, 3, 4, 5, 6];
y = [...x, 7, 8, 9];
z = y
  .filter((x) => x % 2 == 0) // 2, 4, 6, 8
  .map((i) => i * i) // 4, 16, 36, 64
  .reduce((a, i) => a + i, (a = 0)); // a= 0, i=4, a=4, 16,
console.log(z);
```

What will be the output of the program?

100
120
140
160

Answer: B

Q2: Consider the below Vue app.

index.html:

```html
<div id="app">{{message}}</div>
<script src="app.js"></script>
```

app.js:

```js
const dataObj = {
  message: "Welcome",
};

const optObject = {
  el: "#app",
  data: dataObj,
};

const app = new Vue(optObject);
app.newMessage = "Welcome to iitm online degree";
```

What will be rendered by the browser?

Welcome

Welcome to iitm online degree

App with throw an error “property or method ‘newMessage’ is not defined on the instance” and will show a blank page.

None of the above

Answer: A

Q3: Which of the following is/are correct regarding the E-Tag and If-Match? // if-None-match

E-Tag is a response header to validate the current version of a resource.
E-Tag is a string of ASCII characters placed between double quotes.
For get and head request, If-Match request header is sent to get the resource only if E-Tag value matches.
For get and head request, If-Match request header is sent to get the resource only if E-Tag value does not match.

Answer: A, B and C

Q4: Consider the following Vue application with markup index.html and JavaScript file app.js

index.html

```html
<div id="app" style="color: white" v-bind:style="divStyle">{{message}}</div>
```

app.js

```js
const dataObj = {
  message: "IITM online",
  divStyle: {
    backgroundColor: "red",
    padding: "20px",
    fontSize: "2em",
  },
};
const optObject = {
  el: "#app",
  data: dataObj,
};

const app = new Vue(optObject);
```

What will be the color, background color and font-size of the div with id “app”?

White, red, 2em
Black, white, 1em
white, white, 1 em
Black, red, 2em

Answer: A

Q5: Consider the following Vue application with markup index.html and JavaScript file app.js.

index.html

```html
<div id="app">
  <p directive1>{{message}}</p>
  <button directive2>click</button>
</div>
```

app.js

```js
const app = new Vue({
  el: "#app",
  data: {
    message: "Hello",
    seen: true,
  },
  methods: {
    toggleSeen() {
      this.seen = !this.seen;
    },
  },
});
```

If you want to toggle between the presence of p element on click of the button element, what are the possible value of directive1 and directive2 and their respective values?

v-if=”seen”, v-on:click=”toggleSeen”
v-if:”seen”, v-on:click:”toggleSeen”
v-if=”seen”, @click=”toggleSeen”
v-if:”seen”, @:click:”toggleSeen”

Answer: A and C

Q6: Consider the following Vue application with markup index.html and JavaScript file app.js,

index.html:

```html
<div id="app">
  <h4>total payable amount is {{totalPayableAmount}}</h4>
</div>
<script src="app.js"></script>
```

app.js:

```js
const app = new Vue({
  el: "#app",
  data: {
    principal: 0,
    annualInterestRate: 0,
    duration: 0,
    totalPayableAmount: 0,
  },
  computed: {
    simpleInterest() {
      return (this.principal * this.annualInterestRate * this.duration) / 100;
    },
  },
});

appData = [
  [2000, 10, 2], // 400 = 8200
  [3000, 20, 3], // 1800 = 7800
  [5000, 30, 4], // 6000
];

let handler = setInterval(() => {
  data = appData.pop();
  app.principal = data[0];
  app.annualInterestRate = data[1];
  app.duration = data[2];
  app.totalPayableAmount += app.simpleInterest;
}, 1000);
```

What will be rendered by the browser after 4 seconds?

total payable amount is 6000
total payable amount is 8200
total payable amount is 1800
total payable amount is 7800

Answer: B

Q7: Consider the following Vue application with markup index.html and JavaScript file app.js,

index.html:

```html
<div id="app">y: {{y}}</div>
<script src="app.js"></script>
```

app.js:

```js
const app = new Vue({
  el: "#app",
  data: {
    x: 0,
    y: 0,
  },
  watch: {
    // p-q = 1
    x(p, q) {
      if (p > q && p > 10) {
        this.y = 1;
      }
    },
  },
});

for (let i = 0; i < 20; i++) {
  app.x++;
}
```

What will be rendered by the browser?

0
y: 1
20
None of the above

Answer: B

Q8: Consider the following Vue application with markup index.html and JavaScript file app.js,

index.html:

```html
<div id="app">y: {{y}}</div>
<script src="app.js"></script>
```

app.js:

```js
const app = new Vue({
  el: "#app",
  data: {
    x: 20,
    y: 40,
  },
  beforeCreate() {
    console.log(this.x);
  },
});
```

What will be logged on console and rendered on screen, respectively?

undefined, 40
undefined, 20
20, 40
40, 40

Answer: A

Q9: Consider the following Vue application with markup index.html and JavaScript file app.js,

index.html:

```html
<div id="app">
  <comp1></comp1>
</div>
<script src="app.js"></script>
```

app.js:

```js
const comp1 = {
  template: "<h4> This is {{name}}</h4>",
  data: {
    name: "component 1",
  },
};

const app = new Vue({
  el: "#app",
  components: {
    comp1,
  },
});
```

What will be rendered by the browser?

This is
This is component 1
No text will be shown on the browser
None of the above

Answer: A

Q10: Consider the following files are present inside the same directory,

index.html:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>repl.it</title>
    <link href="style.css" rel="stylesheet" type="text/css" />
  </head>
  <body></body>
  <script src="app.js"></script>
</html>
```

app.js:

```js
const a = fetch("sample.txt");

a.then((r) => {
  if (!r.ok) {
    throw new Error("HTTP status code: " + r.status);
  }
  return r.text();
})
  .then((d) => {
    console.log("Got the data !!", d);
  })
  .catch((e) => {
    console.log(e);
  });
```

sample.txt:

Hello World !!

What will be shown on the browser console if index.html is rendered with the help of a browser? If there is no network error.

Got the data !! Hello World !!
Hello World !!
Got the data !!
Error: HTTP status code: 404

Answer: A

Q11: Consider the following JavaScript code.

```js
let x = 2,
  n = 3,
  k = 4;

const Promise1 = new Promise((resolved, rejected) => {
  if (k < n) {
    resolved(x);
  } else {
    rejected("Bad Promise");
  }
});

Promise1.then((x) => {
  return x * x;
})
  .then((x) => {
    console.log(x);
  })
  .catch((err) => {
    console.log(err);
  });
```

What will be logged on the console?

2
4
8
Bad Promise

Answer: D

Q12: Consider the following markup index.html and JavaScript file app.js for an application,

Index.html:

```html
<div id="app">
  <named-slot v-slot:header="slotProp">
    Name: {{slotProp.user.name}}, District: {{slotProp.user.dist}}</named-slot
  >
</div>
<script src="app.js"></script>
```

app.js:

```js
const namedSlot = {
  template: `
    <div>
        <slot name = "header" :user="currentUser" city=’’></slot>
    </div>
    `,
  data() {
    return {
      users: [
        {
          user_id: 1,
          name: "Narendra",
          dist: "Ballia",
        },
        {
          user_id: 2,
          name: "Abhisek",
          dist: "Delhi",
        },
      ],
      currentUser: null,
    };
  },
  props: ["current_user_id"],
  created() {
    current_user = sessionStorage.getItem("userId");
    current_user_id = current_user ? current_user : 2;
    this.currentUser = this.users.find(
      (user) => user.user_id == current_user_id
    );
    sessionStorage.setItem("userId", current_user == 1 ? 2 : 1);
  },
};

const app = new Vue({
  el: "#app",
  components: {
    "named-slot": namedSlot,
  },
});
```

Suppose the application is running on port 8080 what will be rendered by the browser when the page index.html loads on the screen for the first time (without refreshing the page)?

Name: Narendra, District: Ballia
Name: Abhisek, District: Delhi
Nothing will be shown on the screen
None of the above

Answer: B

Q13: Consider the following markup index.html and JavaScript app.js for a Vue application.

app.js:

```js
const player = {
  template: `<div>
              <h1> Name: {{ name }}</h1>
    <router-view />
  </div>`,
  props: ["name"],
};

const test = {
  template: "<div><h1> Test Runs: {{ runs }} </h1></div>",
  data() {
    return { runs: 5000 };
  },
};

const oneDay = {
  template: "<div><h1> Oneday Runs: {{ runs }} </h1></div>",
  data() {
    return { runs: 10000 };
  },
};
const routes = [
  {
    path: "/player/:name",
    component: player,
    children: [
      { path: "", component: oneDay },
      { path: "test", component: test },
      { path: "onday", component: oneDay },
    ],
    props: true,
  },
  { path: "*", component: test },
];
const router = new VueRouter({
  routes,
  base: "/",
});

const app = new Vue({
  el: "#app",
  router,
});
```

index.html:

```
<div id="app">
   <router-view></router-view>
</div>
<script src="app.js"></script>
```

Suppose the application is running on <http://localhost:8080>, and user visits the URL “<http://localhost:8080/#/player/rohit”>. What will be rendered by the browser?

Name: Rohit
Oneday Runs: 10000

Test Runs: 5000

Name: Rohit
Test Runs: 5000

Oneday Runs: 10000

Answer. A

Q14: Consider the app.js and index.html given in the Question No.13.

Suppose the application is running on <http://localhost:8080>, and the user visits the URL “<http://localhost:8080/#/player/rohit/test”>. What will be rendered by the browser?

Name: Rohit
Oneday Runs: 10000

Test Runs: 5000

Name: Rohit
Test Runs: 5000

Oneday Runs: 10000

Answer: C

Q15: Consider the app.js and index.html given in the Question No.13.

Suppose the application is running on <http://localhost:8080>, and the user visit the URL “<http://localhost:8080/#/player/rohit/t20”>. What will be rendered by the browser?

Name: Rohit
Oneday Runs: 10000

Test Runs: 5000

Name: Rohit
Test Runs: 5000

Oneday Runs: 10000

Answer. B
