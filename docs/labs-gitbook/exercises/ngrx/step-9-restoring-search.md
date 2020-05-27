## Exercise: Restoring Search

With all the NgRx features add, you may have noticed that the *User Search* feature no longer works. Even if we fixed the current RTE, we have an issue with state management.

> When navigating between the list and a contact details, we currently lose the search criteria last used.

For this exercise, we need to:

* support search for users by partial-name searching, 
* save/restore the search criteria whenever we show the contact list
* filter the contacts list to show only the matches to the in-memory, partial-name search 
  
## Scenario

For this exercise, let's:

* enhance our NgRx to manage `searchCriteria` state as part of the `contacts` NgRx features.
* use a Reactive FormControl provide an observable stream of input search changes.
* update the ContactsFacade to provide a `searchCriteria$` observable and a `search()` feature
* listen for input changes and call `ContactFacade::search()`
* use the `ContactsFacade::searchCriteria$` to initialize the search input field with the current searchCriteria value. 
* auto-focus the Search Users input field when activating the ContactsList view.  

## Tasks

1. In **`contacts.reducer.ts`** 
  * use EntityState and EntityAdapter to define your feature state.
  * use `adapter.getInitialState()` to build your initial state
  * update your reducer to use `adapter.addAll()` and `adapter.upsertOne()`
2. Update your **`contacts.selectors`**
  * use `adapter.getSelectors()`
3. Update your **`contacts-ngrx.module.ts`** use the `getContactsInitialState` function to build the initialState 

## Code Snippets

##### `contacts.reducer.ts`

![ngrx9 1](https://user-images.githubusercontent.com/210413/47192883-5b09ba80-d3ac-11e8-85ad-cd6cbfae61fd.jpg)

![ngrx9 2](https://user-images.githubusercontent.com/210413/47192882-5b09ba80-d3ac-11e8-8456-f296c32feb6b.jpg)


##### `contacts.selectors.ts`

![ngrx9 3](https://user-images.githubusercontent.com/210413/47192881-5a712400-d3ac-11e8-9fab-e514fa01fbda.jpg)

##### `contacts-ngrx.module.ts`

![ngr9 4](https://user-images.githubusercontent.com/210413/47192992-19c5da80-d3ad-11e8-905b-dd9389ee3fd3.jpg)


## Next Lab

Congratulations! You are done.
