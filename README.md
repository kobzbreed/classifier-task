# WEEK-2-TASK-NODE




# Engineering Problems




This repo contains questions the classifier problem you should be able to solve in a reasonable amount of time. It tests your understanding of JavaScript fundamentals.




## Running tests




First, you need to install the dependencies for the project by running




```sh

yarn

```




Then, you can run the tests by running




```sh

yarn test

```




While in active development, you can run the tests by running




```sh

yarn test --watch

```




## Stretch Goals




You can also choose to solve this challenge in [typescript](https://www.typescriptlang.org) by changing the file extension of the `.js` file in the `src` folder to `.ts`. i.e rename `src/classifier.js` to `src/classifier.ts`




Your file would be typechecked when you run the test. This project is already configured to run the tests either in js or ts.




# Classifier




Given an input containing a list of students' names, dates of birth, and their registration number.




Write a program that classifies the students into groups where




1. Each group has a maximum of 3 students.

2. No student is in more than 1 group.

3. The difference in years of the ages of student in any particular group is not more than 5.




`Your solution should include in its output`




1. The groups: with the name, dob, regNo and age of its members.

2. The age of the oldest member in each group.

3. The sum of ages of students in each group.

4. The regNo of students in each group in ascending order.




## Constraints




You cannot use any third party modules. i.e You should not modify the package.json file. Also assume the current year is 2019.




## Example input




```js

const input = [

  {

    name: "Hendrick",

    dob: "1853-07-18T00:00:00.000Z",

    regNo: "041",

  },

  {

    name: "Albert",

    dob: "1879-03-14T00:00:00.000Z",

    regNo: "033",

  },

  {

    name: "Marie",

    dob: "1867-11-07T00:00:00.000Z",

    regNo: "024",

  },

  {

    name: "Neils",

    dob: "1885-10-07T00:00:00.000Z",

    regNo: "02",

  },

  {

    name: "Max",

    dob: "1858-04-23T00:00:00.000Z",

    regNo: "014",

  },

  {

    name: "Erwin",

    dob: "1887-08-12T00:00:00.000Z",

    regNo: "09",

  },

  {

    name: "Auguste",

    dob: "1884-01-28T00:00:00.000Z",

    regNo: "08",

  },

  {

    name: "Karl",

    dob: "1901-12-05T00:00:00.000Z",

    regNo: "120",

  },

  {

    name: "Louis",

    dob: "1892-08-15T00:00:00.000Z",

    regNo: "022",

  },

  {

    name: "Arthur",

    dob: "1892-09-10T00:00:00.000Z",

    regNo: "321",

  },

  {

    name: "Paul",

    dob: "1902-08-08T00:00:00.000Z",

    regNo: "055",

  },

  {

    name: "William",

    dob: "1890-03-31T00:00:00.000Z",

    regNo: "013",

  },

  {

    name: "Owen",

    dob: "1879-04-26T00:00:00.000Z",

    regNo: "052",

  },

  {

    name: "Martin",

    dob: "1871-02-15T00:00:00.000Z",

    regNo: "063",

  },

  {

    name: "Guye",

    dob: "1866-10-15T00:00:00.000Z",

    regNo: "084",

  },

  {

    name: "Charles",

    dob: "1868-02-14T00:00:00.000Z",

    regNo: "091",

  },

];

```




## Example Output




```js

const exampleOutput = {

  noOfGroups: 7,

  group1: {

    members: [

      { name: 'Paul', dob: '1902-08-08T00:00:00.000Z', regNo: '055', age: 120 },

      { name: 'Karl', dob: '1901-12-05T00:00:00.000Z', regNo: '120', age: 121 },

    ],

    oldest: 121,

    sum: 241,

    regNos: [55, 120],

  },

  group2: {

    members: [

      {

        name: 'Louis',

        dob: '1892-08-15T00:00:00.000Z',

        regNo: '022',

        age: 130,

      },

      {

        name: 'Arthur',

        dob: '1892-09-10T00:00:00.000Z',

        regNo: '321',

        age: 130,

      },

      {

        name: 'William',

        dob: '1890-03-31T00:00:00.000Z',

        regNo: '013',

        age: 132,

      },

    ],

    oldest: 132,

    sum: 392,

    regNos: [13, 22, 321],

  },

  group3: {

    members: [

      { name: 'Erwin', dob: '1887-08-12T00:00:00.000Z', regNo: '09', age: 135 },

      { name: 'Neils', dob: '1885-10-07T00:00:00.000Z', regNo: '02', age: 137 },

      {

        name: 'Auguste',

        dob: '1884-01-28T00:00:00.000Z',

        regNo: '08',

        age: 138,

      },

    ],

    oldest: 138,

    sum: 410,

    regNos: [2, 8, 9],

  },

  group4: {

    members: [

      {

        name: 'Albert',

        dob: '1879-03-14T00:00:00.000Z',

        regNo: '033',

        age: 143,

      },

      { name: 'Owen', dob: '1879-04-26T00:00:00.000Z', regNo: '052', age: 143 },

    ],

    oldest: 143,

    sum: 286,

    regNos: [33, 52],

  },

  group5: {

    members: [

      {

        name: 'Martin',

        dob: '1871-02-15T00:00:00.000Z',

        regNo: '063',

        age: 151,

      },

      {

        name: 'Charles',

        dob: '1868-02-14T00:00:00.000Z',

        regNo: '091',

        age: 154,

      },

      {

        name: 'Marie',

        dob: '1867-11-07T00:00:00.000Z',

        regNo: '024',

        age: 155,

      },

    ],

    oldest: 155,

    sum: 460,

    regNos: [24, 63, 91],

  },

  group6: {

    members: [

      { name: 'Guye', dob: '1866-10-15T00:00:00.000Z', regNo: '084', age: 156 },

    ],

    oldest: 156,

    sum: 156,

    regNos: [84],

  },

  group7: {

    members: [

      { name: 'Max', dob: '1858-04-23T00:00:00.000Z', regNo: '014', age: 164 },

      {

        name: 'Hendrick',

        dob: '1853-07-18T00:00:00.000Z',

        regNo: '041',

        age: 169,

      },

    ],

    oldest: 169,

    sum: 333,

    regNos: [14, 41],

  },
