Hello! Today I solved "Old Sessions" from Cylab's (formerly PicoCTF) Web Exploitation! And this will be my first writeup explaining the steps on how to do it!

This is the challenge (https://learn.cylabacademy.org/library/739?page=1&category=1&workspace=true)



Upon launching an instance, a link will show up so when you login, you will see the main login page of a website.



There is also a register page. To figure this out, you'll have to create a random account and use that to login

Once you do that, you'll enter a "Homepage" where you see 4 comments by random users. And one of them looks interesting.



A page named "/sessions"... You'll have to edit on the current website link by adding /sessions at the end. Enter that and you'll see the list of existing sessions.



Now the second one's key says pico (which is the account I created) hence this would be the existing session right now. The first one apparently exists and that says "admin" hence the username might be "admin". That is where we should check.

Time to do some "inspecting" of the page.



This is because whenever a user logs in, a new session ID is created and sent to the client (the user of the website) in a cookie. Hence it makes sense that the session ID is visible in the Cookies section.

Now the current session ID represents of my account. I see that we can edit the "Value" of session and change it to use the "Value of the admin's session.

When you refresh the page, you'll see the flag on the Homepage. 

