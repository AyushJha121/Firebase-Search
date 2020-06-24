# Firebase-Search
Here is the code for a demo search algorithm in firebase
## Initialization
Will start off by putting a text box for searching and a table for displaying the records. I already have attach an event listener on document loaded for our scripts to be added later on.
![alt text](https://miro.medium.com/max/1400/1*SULoHUBAP_-bAU85gBfdIA.png)
## Generating Records
Lets generate 200 random names using tools like Mackaroo. It should have properties: name (object) and keywords (array). The keywords field will be populated with strings of all the possibilities of a name is being search. Take note that array-contains is case sensitive, it would be much better that our names are formatted in lowercase. Lets create a function that would generate those keywords.
![alt text](https://miro.medium.com/max/1400/1*RJCl-GVRh3aGD8nx01SY7A.png)
Calling the generateKeywords([‘john’, ‘the’, ‘dough’, ‘jr’]) would produce the output of:
![alt text](https://miro.medium.com/max/1400/1*QWZrj7rkxyZEM-zCxUoFnw.png)
Going back to our 200 random JSON names. We’ll iterate to each one of it and add the keywords property with a value getting from the generateKeywords function. Then add the document in people collection onto Firestore.
![alt text](https://miro.medium.com/max/1400/1*1NVf1xZ2HaDbb0d7uuqk1Q.png)
After running that script, our collection should look something like this:
![alt text](https://miro.medium.com/max/1254/1*NS5nWVCoup24uaK7Wx4TPQ.png)
## Implementing Search
Inside DOMContentLoaded event handler, lets create a function that takes a search as an argument which retrieves those documents from people collection and returns a markup to be pass on later to the tbody.
![alt text](https://miro.medium.com/max/1400/1*xWYdTcl5qNF7rMD95-koEg.png)
Invoke the searchByName with a empty string to display all people.
![alt text](https://miro.medium.com/max/1400/1*35T0q8VK4DewUei0_tWCQA.png)
Run your application and you should see an error in the console saying:
![alt text](https://miro.medium.com/max/1222/1*m6s58n6agbR196fUhrBqOg.png)
Click on that link to build the index, wait for it to finish and then run or refresh your application again.
As we type in the search box, the table is not being filtered. We must attach a keyup event handler on the text box.
![alt text](https://miro.medium.com/max/1400/1*Jcp5jnExAELwLzB8tE49GQ.png)
Try searching by last name, first name or first name first.
![alt text](https://miro.medium.com/max/1400/1*325kKycGzjxPFbLQwvRv_Q.gif)

### This is a sample search algorithm for searching in firestore you can modify it for real estate data set.
