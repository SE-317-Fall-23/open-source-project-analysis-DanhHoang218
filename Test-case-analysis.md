# Assignment Submission

## Project Selected: TodoMVC

## I. Introduction
- Briefly introduce the purpose of this section, which is to provide a detailed description of two test cases in the selected open-source project.

## II. Test Case 1: [this.enterItem]
### A. Description
- This test case is found in the 'test' folder and it titled 'page.js'. The objective of the tests in class is to test the functionality of the page. This includes seeing if certain messages or pop ups appear on the webpage. It also tests if the page will respond as expected such as from clicking a certain symbol with the mouse or pressing a key on the keyboard.
### B. Gherkin Syntax (if applicable)
- Feature: Add a new item to the list

- Scenario: User adds a new item to the list

- Given the user is on the list page
- 
  When the user checks the current number of items in the list
- 
  And the user waits for the new item input field to become available
- 
  And the user enters "New Item" into the input field
- 
  And the user submits the new item
- 
  Then the new item should appear in the list
- 
  And the new item's text should be the "New Item"

### C. Test Steps
1. self.getListItem() retrieves the current items in the list and storing them in nitems
2. Wait for the next input field to be available
3. The function then uses the newItemInput.sendKeys(itemText) to enter the item into the itemText
4. Now the code will simulate the action of repeatedly clicking the enter key until the item goes away
5. self.waitForElement then waits for the next item in the list to appear
6. It will then check if the new item will match what is in the itemText
### D. Code Segments Under Test
- Identify specific code segments or functions that are being tested in this case.

```Java
this.enterItem = function (itemText) {
        var self = this;
        var nItems;
        return self.getListItems()
        .then(function (items) {
        nItems = items.length;
        })
        .then(this.waitForNewItemInputField.bind(this))
        .then(function (newItemInput) {
        return newItemInput.sendKeys(itemText).then(function () { return newItemInput; });
        })
        .then(function (newItemInput) {
        return browser.wait(function () {
        // Hit Enter repeatedly until the text goes away
        return newItemInput.sendKeys(webdriver.Key.ENTER)
        .then(newItemInput.getAttribute.bind(newItemInput, 'value'))
        .then(function (newItemInputValue) {
        return newItemInputValue.length === 0;
        });
        }, DEFAULT_TIMEOUT);
        })
        .then(function () {
        return self.waitForElement(self.getLastListItemLabelCss(nItems));
        })
        .then(this.waitForTextContent.bind(this, itemText.trim(),
        'Expected new item label to read ' + itemText.trim()));
        };
```
### E. Initial State
- Describe the initial state or conditions of the system or component before executing the test.
### F. Transition
- Explain the actions or events that trigger a change in the system's state.
### G. Expected State
- Clearly outline the expected state or outcome after the test steps have been completed.

## III. Test Case 2: [Name of Test Case]
### A. Description
- Provide a concise overview of the purpose of the second test case.
### B. Gherkin Syntax (if applicable)
- If you choose to use Gherkin syntax, write the Gherkin scenario for this test case.
### C. Test Steps
- Enumerate the sequence of steps or actions involved in this test case.
### D. Code Segments Under Test
- Identify specific code segments or functions that are being tested in this case.
```Java
// Enter code
```
### E. Initial State
- Describe the initial state or conditions of the system or component before executing the test.
### F. Transition
- Explain the actions or events that trigger a change in the system's state.
### G. Expected State
- Clearly outline the expected state or outcome after the test steps have been completed.

