Hello! Today I solved "Old Sessions" from Cylab's (formerly PicoCTF) Web Exploitation! And this will be my first writeup explaining the steps on how to do it!

This is the challenge (https://learn.cylabacademy.org/library/739?page=1&category=1&workspace=true)
<img width="1358" height="627" alt="image" src="https://github.com/user-attachments/assets/4edd2843-55b7-4842-afeb-190ae7232d3a" />



Upon launching an instance, a link will show up so when you login, you will see the main login page of a website.
<img width="1917" height="906" alt="image" src="https://github.com/user-attachments/assets/22dc0754-5df5-4e71-adf5-c06ffe7a0925" />



There is also a register page. To figure this out, you'll have to create a random account and use that to login.
Once you do that, you'll enter a "Homepage" where you see 4 comments by random users. And one of them looks interesting.
<img width="1270" height="857" alt="image" src="https://github.com/user-attachments/assets/5feac449-4d4c-42d5-9fb2-24a466bdf020" />



A page named "/sessions"... You'll have to edit on the current website link by adding /sessions at the end. Enter that and you'll see the list of existing sessions.
<img width="1917" height="246" alt="image" src="https://github.com/user-attachments/assets/05c58e14-9923-459f-9833-957783d99c1c" />


Now besides my account with the username "pico", there's another one which says "admin". This will be useful, because this means someone already entered the page before. You'll have to copy the session value because this will be necessary while we do some "inspecting" of the page.
<img width="1917" height="911" alt="image" src="https://github.com/user-attachments/assets/e7c97980-0852-4237-9ee0-fe57bdd6e8bf" />



This is because whenever a user logs in, a new session ID is created and sent to the client (the user of the website) in a cookie. Hence it makes sense that the session ID is visible in the Cookies section. Now the current session ID represents of my account. I see that we can edit the "Value" of session and change it to use the "Value" of the admin's session.

<img width="1048" height="412" alt="image" src="https://github.com/user-attachments/assets/96a84d4b-2c49-4d8c-94fd-d3a6d99955a3" />
<img width="751" height="240" alt="image" src="https://github.com/user-attachments/assets/a69ae7c2-6e94-4fc3-b99c-e71fc08c6f3a" />


When you refresh the page, you'll see the flag on the Homepage since we used an existing session ID to enter the account of the "admin". 
<img width="1917" height="900" alt="image" src="https://github.com/user-attachments/assets/129e4665-b652-4d36-838d-6c1947a8201d" />

Flag found! I hope you liked the writeup!
