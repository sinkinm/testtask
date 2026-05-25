# Authentication
* User can log in with valid credentials
* User cannot log in with invalid login
* User cannot log in with invalid password
* User can log out from the account
* Authenticated session persists after page navigation
* Unauthorized users cannot access authenticated pages directly (/catalog, /cart, /profile, etc.)

# Catalog Browsing Content
* Catalog page displays available VM plans
* VM row displays CPU count
* VM row displays RAM size
* VM row displays disk size
* VM row displays disk type
* VM row displays traffic allowance
* VM row displays overage rate
* VM row displays hourly price
* PortaShop offers virtual machine plans across several tiers — Basic, Standard, Pro, Ultra, Storage, Compute, and Mega.

# Cart Management
* User can add VM plan to cart
* Cart counter updates after adding item
* User can add the same VM plan multiple times
* Cart displays correct quantity for duplicated VM plans
* User can delete VM plan from the cart
* Clear Cart button removes all VM plans from the cart
* User cart state is persistent across sessions and devices until explicit action (saved to the profile on a database level)
* After user deletes VM plan from the cart, the “Total per hour” price is updated accordingly
* Clear Cart button is not active when cart is empty
* After clearing the cart, “The cart is empty” message should be shown
* The “Total per hour” price is calculated correctly and equals to the actual VM plans value

# Payment
* User can open payment form via Pay Now button
* Pay Now button is not active if cart is empty
* User can complete purchase using valid card details
* User cannot complete purchase using invalid card details
* User can pay using account balance
* After paying / placing order, cart should be emptied
* User can top up account balance from Catalog page
* User can top up account balance from Profile page
* Top up amount can be only positive number
* Top up amount can be integer or x.yy format, where yy is fractional part
* User can purchase multiple VM instances within a single order
* User is not able to create 0$ order / Pay Now button should be disabled if card is empty

# Owned Assets
* Purchased VMs appear in Owned Assets after successful payment
* Owned Assets counter is shown at /catalog page
* Owned Assets counter is shown at /profile page
* Owned Assets table groups identical VM types into one row
* Owned Assets table displays owned VM quantity
* User can delete owned asset
* Deleted asset is removed from Owned Assets
* Asset deletion does not trigger balance refund

# Profile & Account Management
* Profile page is accessible from every page
* Profile page displays user email address
* Profile page displays first name
* Profile page displays last name
* Profile page displays account balance
* Profile page displays last login time
* User can edit first name
* User can edit last name
* Updated display name is saved successfully
* Logout button logs out the current user

# Table Rendering
* Table is displayed without layout corruption
* Column headers are visible and readable
* Row content is aligned correctly
* Horizontal scrolling works correctly when table width exceeds viewport

# Sorting
* User can sort by sortable columns
* Sorting order toggles between ascending and descending
* Active sorting state is visually distinguishable
* Sorting icon/state updates correctly after interaction
* Sorting is applied to the entire dataset, not only visible rows
* Numeric values are sorted numerically
* Text values are sorted alphabetically
* Dates are sorted chronologically
* Sorting persists after page refresh
* Sorting persists during pagination

# Search
* Only search by name works
* Search input is accessible and editable
* Search starts after user input
* Search results update correctly
* Search resets correctly after clearing input
* Search works with partial matches
* Search is case insensitive
* Search returns empty state for nonexistent values
* Search does not break pagination
* Search finds only displayed pre-filtered items

# Pagination
* Pagination controls are visible
* User can navigate to next page
* User can navigate to previous page
* User can navigate to specific page number
* Current page is visually highlighted
* Pagination displays correct total item count
* Pagination displays correct number of rows per page
* User can change rows-per-page value
* Pagination state persists after sorting (if expected)
* Pagination state persists after filtering (if expected)
* Pagination state persists after page refresh
* Last page handles partial row count correctly
* Prev is disabled on a first page
* Next is disabled on a last page

# Row Interaction
* Row hover state is displayed consistently
* Context actions work correctly

# Accessibility & UX
* Table is navigable via keyboard
* Tab order is logical
* Screen reader labels are present for controls
* Interactive controls have sufficient click area
* Text contrast is sufficient for readability
* Empty states contain meaningful messaging