#AppSheet_Inventory_Management 

# Part 1 of 2

## [[Expressions_AIM]]
[[API Script]]
[[JSON PARSING BUG (solved)]]
[[Webhook]]

# Current Progress Point 
## https://youtu.be/IKqm5OzyLZQ?t=2082
📍So far : 12/29/2022
✅ Added 2 tables and columns
✅ Added expressions for auto-dropdown
✅ Used ANY, SELECT,  and REF
✅ Integrated API for count reduction 
	⭐Debugged a situation الحمدلله 

# Now 

1. Add actions
2. Build Expressions
3. Rebuild the app 

✅ add_stocks plus automation webhook
📍undo release stock stock calc webhook

# Minute https://youtu.be/IKqm5OzyLZQ?t=2791

✅Both automations hhtps requests are functioning now
- release_stocks deducts from stocks_inventory available stocks
- add_stocks adds to stocks_inventory available stocks

---
[[📌AppSheet Inventory Management PART 2]]
# VIDEO 2 https://youtu.be/c7pFBnMIX8Y?t=220

📌 GOAL : script to allow for cancelling release_stocks
📌 GOAL : script to allow for cancelling add_stocks
📌GOAL : new table to keep track of these cancellations

> is this guy making too many webhooks ? Isn't there an easier and simpler way to kepp track of these changes?

🚨THIS VIDEO HAS BEEN HELPFUL BUT A _MASSIVE_ DRAG ON TIME

#### Too many things that are not properly explained 

##### HTTPS requests are not organized and coordinated with the columns

###### For example

Subtracting from stocks_inventory is done by a formula but subtraciting from the other one is done via webhook.

I am closing this project on 12/29/2022 #closed
