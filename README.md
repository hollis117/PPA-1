# PPA-1
 Software Testing


## Setup
>This project uses 'Windows 8.1', 'npm', and 'Jest ^24.9.0'.

For the setup of this project you will need to follow these steps:
1.  Navigate to the folder containing my code files in the command prompt
2.  Type in 'npm install'
    - Follow install steps
3.  Type in 'npm install --save-dev jest'
4.  In your 'package.json' file make sure the following lines are present:
'''
{
  "scripts": {
    "test": "jest"
  }
}
'''
5.  Now you should be able to type 'npm run test' to see the jest testing output


### Naming and organizational conventions
>I decided that my variables should speak for themselves when looking at the functions and tried to name them descriptively but succinct. All my tests were written in a 'describe()' and 'it()' format and all test files were named after the file they tested with '.test' stuck between the name the '.js'.


#### Report
>My experience with TDD was a lot of me wanting to code the test but stopping myself to write the test first.

>I think TDD can be useful, but I don't think it would be useful for many of the school projects that I have done while at UF.

>I think it would be very useful for a large software project that would take months to years to fully build.

>Benefits of TDD:
- Always know when something being tested breaks after making a change to the code
- Client trust increased due to proof of good code
- When working with a large group you don't need to worry about someone else's code breaking your code without you knowing

>Drawbacks of TDD:
- Can almost double the time of a project
- May not come naturally to coders who have never done it before
- May cause a client to choose someone who will deliver code faster
