The Password Checker

This project checks the password in the system, to ensure that passwords are changed,
if the passwords are found many times to exist in multiple apps. After checking the final
product, the password checker indeed works.

The API request function:

The password_checker uses an api and its tail component to check for front hashes and back
hashes to see if passwords used over and over again, are secured. The following is the proper
way to use the api from pwned passwords, which is a website dedicated to password checks.

    pwned passwords api:
    'https://api.pwnedpasswords.com/range/' + 'CBFDA'

Once the appropriate API and its query char ('CBDA') are applied, the request and the status
code is then to be conditioned into the function. A status code '200' is a green light that
the api is able to request the server and return a "it's a go" resposne. A '400' status code
yields "a no go".

The Password leaks function:

The function get_password_leaks_count uses a technique known as a tuple comprehension, which
is similar to list comprehension, but gives us the result for a tuple instead of a list. The
code is similar to a list comprehension. Although we use a for loop on a tuple comprehension,
the for loop below is meant to take hashes argument, which is the first 5 characters of a
hashed password from passwodgenerator.net to check for a password that is hashed. An unhashed
password leads to an error and defeats the point of a secured way to search for a password that
may or may not be comopromised. The hash algorithm that is applied to this code is SHA1 hashed
password. The second for loop checks for a list of the password that matches the first 5 characters
and then gives you a list. It also counts how many times that the password has been checked
and possibly compromised. If the count is not found, meaning the password is still secured, the
search gets a 0 count.

The API check function:

The function pwned_api_check deals more with checking the password. The function above,
dealt with coming up with a resulting list, so that the password being searched is found
among the hashed passwords. The first5_char variable mathces everything that starts with the
characters that match all of the resulting tuple list. The tail end of the password are the
hashed passwords that are unique to a resulting search. That way, when you are searching for
the password for a possible comprimise of that password, it can run throuhg that list.

The main(args) function:

The main function is the function that gives teh result of the overall program.
The point of this function is to take the functions above and apply the main purpose of
this code to get the python passwordcheck.py 'query_char'. This will then yield one of the
conditional responses. To understand, password is the argument that comes from the pwned_api_check
funciton. count comes from get_password_leaks_count. The conditional, is to use the variable args.
args is used from all of the functions above, so that all of the variables resused from previous
functions are not restated, but called from args as the arrgument overall.

Result:

The result of the password check results from the following command:

    python password_checker.py 'password'

The command will display result in terms of one of two possibilities:

    {password} was found {count} times...you should change your password!'

or:

    '{password} was NOT found. Carry on!'

The latter is what everybody should be aiming for, or change their passwords as indicated.



