# Assignment Submission

## Project Selected: TodoMVC

## I. Introduction
- The purpose of this section is to show our understanding with test cases and our ability to understand why each test case is important in retrospect to the software that the code is desgined for. It also gives us the chance to practice working with the gherkin format whcih is important because it allows us to simplify what the test is doing by breaking it into steps. For these test cases I chose one that tests what happens to a list if a user clicks the enter key to add items to it and a test that checks if the page is open. I chose these tests because one tests what happens when a user is interacting with the website while the other tests that state of the page and if it is opened or not.

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
- The inital state of this test is for the user to be on the items page on the website. This is because the test is involved with if clicking enter will update the items stored in the item list. If the user is not on this page then the following actions would not be resulted. 
### F. Transition
- Some actions that will impact the state will be clicking the enter button to update the list and view the new item, the user picking the item they want to add to the item list because this will determine the name of the item and how the list will update. And if the user decides to remove and item the list should be able to adjust to that as well. 
### G. Expected State
-The expected result of this test case is when the user clicks enter to submit a new item it should add that item to the item list and it should the "New item" text should be that of the item that just got added to the list by the user.

## III. Test Case 2: [test.describe]
### A. Description
- 
### B. Gherkin Syntax (if applicable)
- Feature: Initial Page Behavior

- Scenario: Focusing on the todo input field

- When the page is initially opened
- 
  Then the todo input field should be focused

### C. Test Steps
1. test.describe('When page is initally opened') checks if the page is already opened
2. 
### D. Code Segments Under Test
- Identify specific code segments or functions that are being tested in this case.
```Java
test.describe('When page is initially opened', function () {

			test.it('should focus on the todo input field', function (done) {
                    testOps.assertNewInputFocused()
                    .then(function () { done(); });
                    });

                    });
```
### E. Initial State
- The inital state of this test case is for the page to be opened. Although this applies to a lot of test cases this test case focuses on if the page is opened.
### F. Transition
- What impacts the state of this test case is the state of the page whether it is opened or not. This is different from the previous test because it depended on the action of the user. This test case focuses on the current condition of the software. When the page is already open then it will check if the software will begin going through the other input fields.
### G. Expected State
- Clearly outline the expected state or outcome after the test steps have been completed.

