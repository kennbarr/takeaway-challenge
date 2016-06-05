Takeaway Challenge
=================
Travis says..... ![travis build status](https://travis-ci.org/kennbarr/airport_challenge.svg?branch=master)

```
    __
   /
.-/-.
|'-'|
|   |
|   |   .-""""-.
\___/  /' .  '. \   \|/\//
      (`-..:...-')  |`""`|
       ;-......-;   |    |
        '------'    \____/

```

Summary
---------

* Created TakeAway, Order, Menu and Text classes

######TakeAway
* Point of interaction for user
* Passes user's order to the Order class
* Forwards the menu on to the user for viewing when requested
* Completes order and directs the Text class to send sms confirmation

######Order
* Stores order details
* Displays current order summary when requested

######Menu
* Stores menu details
* Has add/remove methods allowing the menu to be altered
* Displays the current menu when requested

Sample Interface
-------

######Can view the menu to decide what to order
```
$ irb
2.3.1 :001 > takeaway.view_menu
Menu
========================================
Dish                               Price
----------------------------------------
hamburger                         £ 3.00
cheeseburger                      £ 4.00
quarter pounder                   £ 6.00
curry chips                       £ 3.00
chips                             £ 2.00
chicken wrap                      £ 4.00
veggie burger                     £ 5.00
========================================
```

######Items can be ordered, order summary displayed after each addition
```
$ irb
2.3.1 :002 > takeaway.order
Enter dish:
hamburger
How many would you like?
2
Order Summary
============================================================
Dish                                  Price   Qty      Total
------------------------------------------------------------
hamburger                            £ 3.00     2   £   6.00
============================================================
                                        Total cost: £   6.00

2.3.1 :003 > takeaway.order

Enter dish:
chips
How many would you like?
1
Order Summary
============================================================
Dish                                  Price   Qty      Total
------------------------------------------------------------
hamburger                            £ 3.00     2   £   6.00
chips                                £ 2.00     1   £   2.00
============================================================
                                        Total cost: £   8.00

2.3.1 :004 > takeaway.order
Enter dish:
cheeseburger
How many would you like?
2
Order Summary
============================================================
Dish                                  Price   Qty      Total
------------------------------------------------------------
hamburger                            £ 3.00     2   £   6.00
chips                                £ 2.00     1   £   2.00
cheeseburger                         £ 4.00     2   £   8.00
============================================================
                                        Total cost: £  16.00                    
```

######Can remove dishes from order
```
$ irb
2.3.1 :005 > takeaway.remove
Enter dish:
hamburger
Order Summary
============================================================
Dish                                  Price   Qty      Total
------------------------------------------------------------
chips                                £ 2.00     1   £   2.00
cheeseburger                         £ 4.00     2   £   8.00
============================================================
                                        Total cost: £  10.00
```

######Sends confirmation text on order completion
```
$ irb
2.3.1 :006 > takeaway.complete_order
```
