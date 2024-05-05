This file is made up of functions. Firstly we run the startTimer and chat functions which run the inject function and the chat function respectively.

The chat function handles the getting of all chat from WhatsApp web and passes it back to the index.js file which we saw earlier.

The inject function is called when we click both the Activate button and Kill All button from the extension view(index.js file).

If the Kill All button was what triggered this function, it simply kills all interval running and terminates at line 48, thereby stopping all current running trackers.

If the Activate button was what triggered this function, it enters the selected chat(Line 56), gets the values and responses required from chrome storage, then runs the monitorChatsfunction every 200 milliseconds. This function watches the current messages drop in the selected chat for any new one. Once it observes a new one has been added, it then looks up the value of the message against the one supplied in our form(where we inputted values to watch out for)(Line 86).

Once it finds a match, it loops through all our desired responses (Line 92) which have been converted from strings to an array by splitting. Line 93–97 then simulates entering each response in the chatbox, simulate clicking on the send button(using Mouse Events, by calling the eventFire function), which then sends the actual response(s).

And that's it, we have successfully built a WhatsApp tracker that not only monitors chats but also compares it with our provided keywords and responds seamlessly with our desired response.
