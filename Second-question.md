## Project Selected: TodoMVC

## I. Introduction
- Provide an overview of the analysis, indicating the goal of describing the types of testing used in the selected open-source project and explaining the rationale behind their choice.

## II. Types of Testing in the Project
### A. Unit Testing
- The purpose of unit testing for this project is to test the indivdual componenets of the code. Since this code works with a lot of small components such as the user pressing certain keys, lists updating and certain actions as a result of certain buttons or keys being pressed. It would be helpful to check each of these functions with a unit test to simplify the testing of those componenets 
- Some of the parts of the code that would be good with unit testing is buttons that will give an expected output, the user clicking a key a unit test to see if it recognizes the key, and something to check if the user clicks on the right button.
- Unit tests are executed by inputting a value or action into the method that we want to test and give an expected and actual result so that we can check if they match up. And example is inputting a user clicking the exit button the expected result is the page closes and we compare it with the actual result. Some types of tools are JUnit, command lines, and code coverage tools.

### B. Integration Testing
- Integration testing is important for this project because it allows us to test a larger group of code. Since this software works with a webpage we should be able to execute tests like having the correct layout of the page be printed out when a button is pressed. Since there are so many small components working together it is important to be able to test them all together.
- Some of these examples are like my test case 2 analysis where it checks if after a page is open the rest of the input fields are executed and applied to that page. Each of these inputs are a part of the page so its better if we are able to see if they interact with each other correctly. Another example is testing if the page will update and change correctly when a button or symbol is pressed. If we aren't able to test the entire page it could result in some inputs not interacting correctly with other aspects.
- Some tools and methods for integration testing is Junit as it allows the developer to test multiple factors at the same time. Another tool is PostMan which allows developers to see certain outcomes that would appear on a webpage of database without having to deal with other factos.

### C. UI (User Interface) Testing
- The important of UI testing is because the software will be used by a user so this type of testing will show failures that the user will most likely experience when they interact with the software. Some important aspects include if the layout of the page correctly correlates with the buttons that are allocated to them since the user will be pressing those buttons or keys to execute certain functions of the software. We also need to check if the updates of the pages are correct based on what the user is trying to do.
- This software tests the useability of the software and the functionality. Examples can be the test case 1 that I did where it checks if when the user presses the enter key it will add the correct item to the item lists even if the user chooses to click the enter key multiple times it will still provide the correct outcome. These test cases also have to take into account for user behavior such as click back and forth on a page or highlighting the text. Similar to the example i gave it should account for a person doing something like clicking a button multiple times because they're impatient it should not change the result of the software.
- Some tools and methods of unit testing are selenium for webapplications and it supports many different languages. Another tool is Jest which allows the developer to also test UI components such as React.

### D. Other Types of Testing (if applicable)
- If there are additional types of testing beyond unit, integration, and UI testing, outline and briefly explain them.
- Provide insights into why these specific types of testing are relevant to the project's goals.

## III. Reasons for Choosing These Testing Types
-These test types are chosen because they provide the best tests for this type of software. Because this software has a lot of small componenets it is good to start off with basic unit tests to check if each function is working like keys or links. As the software becomes more complex and the different feilds begin interacting with each other like a page updating or certain functions happening that cover multiple methods then we would use integration testing to cover a larger portion of the code and assure the fields work properly together. Lastly since the software is a webpage it will also have a frontend and will have people directly interacting with it so we need to test if the front end and back end work correctly together and if the correct keys and buttons are used. We also need to test if the software is robust enough to keep correct functionality even if users do things like click a button repeatedly or switch from one page to another. By using all these different types of test we are able to cover the main purpose of the software and reduce the faults and failures.

## 2. Test Data Generation
### A. Static Test Data
- Explain if and how static test data is used in the project.
- Provide examples of scenarios where static test data is employed.
### B. Dynamic Test Data
- Explain if and how dynamic test data is used in the project.
- Provide examples of scenarios where dynamic test data is generated.

## 3. Test Doubles
- Identify and explain the use of test doubles (e.g., mocks, stubs, fakes) in the project.
- Specify the specific components, functions, or cases where test doubles are applied.
- Discuss the purpose of using these test doubles in the testing strategy.

## 4. Discussion on Testing Practices
<!-- 
To find discussions on testing strategy in a GitHub repository, you can follow these steps:

Visit the GitHub repository for the project you're interested in.
Look for the "Issues" tab on the repository's page.
Use the search bar within the Issues tab to search for terms related to testing, such as "testing strategy," "test cases," or "test automation."
-->
- Investigate any discussions related to testing practices within the project.
- Give a link to the Github PR or issue
- Summarize key points or insights from these discussions.
- Offer your interpretation of how the project's testing practices align with industry standards or best practices.