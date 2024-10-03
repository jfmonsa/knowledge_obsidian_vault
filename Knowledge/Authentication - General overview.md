

![[Pasted image 20240826233806.png]]

# 1. Session Authetication
2. To keep the user looged, you have to have db table named sessions and map users with its user id
3. you stored in sessions the temprary `sessioId`
4. you send the `sessionId` to the web site or app and every time they make a api request you know who the user is

![[Pasted image 20240826222304.png]]
**Benefits**:
+ You can revoke any access any-time by deleting the session in the data base
**Cons**
+ For every time the user makes an api request you have to make a db retrieval just to see who the user is
	+ One solution to this is instead of using a db table to store sessions you can use something like redis 
# 2. JWT (Recommended)
+ It's a special type of token that is created with three inputs:
	1. Data you want to store
	2. JWT_SECRET (criptographically sign the token)
	3. expiration date

+ Any data in a JWT is public, anyone can decode it: jwt.io even if they dont have the secret string
### Validation
it's the reason to sign the token

+ use the JWT_SECRET to validate you made the token
+ part of validation is making sure the token is not expired
+ It's convenient to don't have to make a db call every time you want to validate the token (solving session auth problem)

**You can't invalidate token early...**
+ but the downside it's you can't invalidate that token early if you want to.
+ For exmpale: If you have a button that the user can press to logout in all devices, you need to terminate tokens early to implement that 

**A trick to overcome this problem...**
+ It's having your JWT short-lived: eg 1h, 5min, depending on your needs
+ But you need a second token (if not your users will be logout every: 1h or 5min)

**Second token: Refresh token**
+ A token that last longer
+ So, when the user log-in, you give two jwts, a **short-lived token** and a **Refresh-token**
![[Pasted image 20240826225014.png]]
+ So... when access token is valid, you can do api requests, but when it expires, the server checks the referesh_token
		1. jwt.verify() (verify refresh-token)
		2. check the data_base to make sure the user is still logged in
		3. If so (still logged in) it will create a new access token a give it back to the user (if you want, you can send a new refresh token as well)
+ With this solution, you only have to make a db call each 15 minutes (example), much better that a db call for each api request (session storage case)

**Auth management accross multiple devices from the same user**
+ Store a refresh token version in session (or tokens) (related to userId in users table) table in db and whenever you create a refereshToken save it there
+ each time access token gets invalid, the server will check the user version with the version stored in the db, if is valid, the it will create a new access token and keep going
![[Pasted image 20240826230013.png]]

+ But when the user presses the logout button in all devices, you increment the referesh token version field and inmediatly all tokens get invalidated
![[Pasted image 20240826230419.png]]

# Save auth data in client
+ Whether you use sessions or jwts you still need to decide wheter you want to store it on the client, to keep them logged-in
### React native
+ use secure storage

### On browsers
+ You have to decide between **cookies** or **local storage** 

**Cookies trick...**
+ If set ==credentials to true== whenever you make a fetch requests from the client the browser will automatically send any cookies stored on that domain up to the server without needing to send an auth header or anything 

**Local storage**
+ If you use local storage you have to set the auth header by yourself

### Last step, Frontend Auth Validation
+ It can get tricky if you're using cookies instead of local storage and you have property (you should) `httpOnly: true` that means you cannot access your cookies through javascript, only send it to  the server
+ solution its simple, you make an api call to your server every time the user comes to your website every time the user comes to your website and you ==let the server decide who the user is==

![[Pasted image 20240826233449.png]]

+ Server will read the cookie (if there is one) and the it wil validate it and return your data, if there is not user the server will reply with null and usually redirect them back to Home screm

# Auth cookies, jwt, httpOnly - Overview
![[Pasted image 20240827215933.png]]
+ With this approach we have to create an http proxy :'( ?

And in frontend
![[Pasted image 20240827220318.png]]
+ 
# Resources
1. How to Roll Your Own Auth - https://youtu.be/CcrgG5MjGOk?si=Rei36szUSnh097GG (This video is ultr-amazing)
3. https://vivekkrishnavk.medium.com/using-jwts-as-http-only-cookies-with-react-js-a301991fdfa6 (front + back explanations, cookies httpOnly with diagrams)
4. https://www.bezkoder.com/react-login-example-jwt-hooks/ Otro recurso muy bueno, explica la parte de las requests en services como deben ser

