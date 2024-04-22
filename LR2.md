# This is lab report 2 for CSE 15 L - Noah Skinner

## Part 1 - `ChatServer` Implementation

Here is the code for my `ChatServer` :

![image](Server1.png).

![image](Server2.png).

To implement the server, I used ChatGPT to help me split the query to pull out the `message` string and the `user` string. 
Below are the prompt that was entered to ChatGPT and the resulting output. 
The code not pictured in the screenshot was not used as it did not pertain to the goal I needed to accomplish.

![image](GPT.png).


## Using the Server

Below is two instances of me using `/add-message` to add another chat to the server 

The first is adding the message 

![image](lr2-2.png)

![image](lr2-3.png)


For both instances of `add-message` , the method `handleRequest` is called. The argument in both cases is the `url` object of type `URI`.

Before the first `add-message` is ran, the value of the `chat` field is `null` since the default value of a `String` is `null`.

After the first request (`/add-message?s=Thisisatest&user=Noah`) , the value of the `chat` field changes so that the only value stored within it is the string `"Noah: Thisisatest"`

After the second `add-message` is ran, the value of `chat` changes from `"Noah: Thisisatest"` to:
`"Noah: Thisisatest"
 "Noah: Woohoo"` because of the second iteration of handleRequest with the `add-message` argument of `/add-message?s=Woohoo&user=Noah`.


 # SSH Keys

 Running `ls` with the absolute path to my private SSH key for `ieng6` on my local terminal
