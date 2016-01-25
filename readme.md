
---

| Title | Type | Duration | Name | City |
| --- | --- | --- | --- | --- |
| Activity Lifecycle | Lab | "1:00" | James Davis | NYC |

---  
# Activity Lifecycle Lab

## Introduction

Below, you will find three scenarios, and questions following each one.

To the best of your ability, answer the questions **in english**, not in code.

Below the scenarios, you will find a few questions. Answer those however you'd like.

Answer the questions by editing this readme, pushing your changes to your forked repo, and making a pull request.

## Exercise  


####Scenario 1:

Let’s say you made a To Do list app, where you can add things to a list and cross them off. You decide to cross some items off the list and mark them as complete.

When you rotate the device, the things you marked as complete are no longer crossed off.

**Question**: Why did this happen?
<br />Answer: Because when the device is rotated, android destroys the activity. 

**Question**: How do you fix this issue?
<br />Answer: You can store the completed data details to the bundle, using saveInstanceState method. If you want to save it even when the app is completely killed, you can use Sharedpreferences method. 


####Scenario 2:

The Amazon Kindle Android app allows you to open and read eBooks. You discovered a bug! You opened a book, and read it from the beginning up to page 68. Then, you left the app and closed it completely so you can do other things.

When you opened the app again, and opened the book, it started from page 1 (and not page 68 where you left off)!

**Question**: How would you fix this issue?
<br />**Answer**: Save the page number the user read last time into the SharedPreferences object using an editor when the app is closed(onPause). When the user opens up the app again, retrieve the page number from the SharedPreferences by using getInteger method.(onResume).


####Scenario 3:

Facebook for Android added a feature last year where, if you started writing a comment on someone’s post and decided not to do so, the app would save a draft of it just in case you changed your mind.

Take this scenario. On a post on Facebook, you click the “comment” button (which opens a new CommentActivity). You start writing a comment, and then change your mind by pressing the back key (which closes the CommentActivity). You click on the “comment” button again, and in the newly-opened CommentActivity, the comment you were writing is still there.

**Question**: How would you implement this feature? Be specific; what lifecycle methods would you use in CommentActivity, and what techniques would you use?
<br />**Answer**: Store the user draft into the sharedpreferences(onPause), and retrieve it when the user opens up the CommentActivity again(onResume). 



In your own words…
==================

**Question**: What are the methods of the Activity Lifecycle?
<br />**Answer**: onCreate(), onStart(), onResume(), onPause(), onStop(), onDestroy(), onRestart().  

**Question**: What order are the methods called?
<br />**Answer**: onCreate(), onStart(), onResume(). If the user goes to another activity, current activity executes onPause(). And when the secondActivity completes until onResume(), first activity executes onStop(), onDestroy(). 

**Question**: What is a bundle?
<br />**Answer**: Data storage object that can store data. 

**Question**: How do you get the Shared Preferences of an app?
<br />**Answer**: Instantiate the SharedPreference and use the getSharedPrecerences(). 
 SharedPreferences sharedPref = getSharedPreferences(Context.MODE_PRIVATE); 
 Editor editor = sharedPref.edit();
 editor.putString("KEY","DEFAULT");
 editor.commit();
