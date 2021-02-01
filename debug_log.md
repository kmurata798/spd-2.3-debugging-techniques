# Debug Log

**Explain how you used the the techniques covered (Trace Forward, Trace Backward, Divide & Conquer) to uncover the bugs in each exercise. Be specific!**

In your explanations, you may want to answer:

- What is the expected vs. actual output?
- If there is a stack trace, what useful information does it contain?
- Which technique did you use, on which line numbers?
- What assumptions did you have about each line of code, and which ones were proven to be wrong?

_Example: I noticed that the program should show pizza orders once a new order is made, and that it wasn't showing any. So, I used the trace forward technique starting on line 13. I discovered the bug on line 27 was caused by a typo of 'pzza' instead of 'pizza'._

_Then I noticed another bug ..._

## Exercise 1

[[
    The expected output seems to be the pizza order once a new order is made, but the actual output is an error saying that topping is an invalid word.

    The stack trace tells me "TypeError: 'topping' is an invalid keyword argument for PizzaTopping" which probably means that the code isn't supposed to use topping as the keyword argument, or something is causing topping to not work properly.

    I change PizzaTopping(toppings=topping_str) to PizzaTopping(topping_type=topping_str) since the variable 'toppings' doesn't exist in the PizzaTopping class.
    
    Changed the redirect(url_for("/")) to use "home" instead, since the function is looking for a filename.

    Changed the form.get in to match the names in the order.html form so that the backend can properly grab the user inputs written inside of the form.

    After submitting a pizza order, none of my orders would be displayed.
    The database wasn't storing the data written inside of the order forms.
    I added db.session.commit() to save the order into the database.

    Changed toppings_list form.get to be form.getlist instead.
    This will give back a list of inputs instead of only receiving the first input.

    Changed the for loop to loop through toppings_list instead of ToppingType.
    Looping through ToppingType will give back all the toppings.
    Looping through toppings_list will give back the toppings the user orders.
    
]]

## Exercise 2

[[
    Expected output is data reflecting off of the weather for specific cities.
    Actual output, error page on submission.

    The specific strings used in the request.args.get seem to be causing errors.
    In the /results route, changed the city request.args.get to 'city'
    and changed the units request.args.get to 'units'.

    I wanted to see if I could properly retrieve data from an API request.
    I added '?' to end of url string after looking up the proper url queries for OpenWeatherMap API.

    The request wasn't giving back the expected data so I tried to reorder the keys /values inside of the context dictionary used to retrieve the data.
    I am now receiving more expected data after I changed the ordering of the params dictionary keys to match the api data received.

    I was missing some data from the API request still, so I had to double check the strings used in the context dictionary.
    I was able to obtain the rest of the missing data after I changed 'temperature' to 'temp' inside the 'temp' key within the context dictionary.
    The API data gives back a temp key, not temperature.

]]

## Exercise 3

[[
    Expected output: integer equal to the index of the target value.
    actual output: error message saying list index out of range inside of Merge_sort function.

    List index out of range error: /main.py -> line 8 ==> /utils.py -> line 37.
    Changed line 42 = arr[k] = right_side[j] instead of right_side[i].

    Found error saying that list indices must be integers or slices, not float.
    I realised that the only way I could have gotten a float is by dividing with a single /, so I changed the dividing sign in the binary_search function into a double //.
]]
