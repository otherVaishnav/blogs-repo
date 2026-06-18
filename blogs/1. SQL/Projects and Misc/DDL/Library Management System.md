---
title: "Library Management System"
description: "Library Management System schema."
pubDate: "2025-06-01"
---

<!-- # Library Management System -->

1. Create a branch table with fields: 
    - branch id
    - name
    - address
    - established date
    - manager name
2. Create a BORROW_RECORD table with columns. 
    - RECORD_ID
    - MEMBER_ID
    - BOOK_ID
    - BOWWOR_DATE
    - DUE_DATE
    - RETURN_DATE

1. Create a book table that includes: 
    - TITLE
    - BOOK_ID
    - AUTHOR
    - GENRE
    - EDITION
    - PRICE
    - BRANCH_ID
    1. Create a MEMBER table with
        - MEMBER_ID
        - NAME
        - JOIN_DATE
        - MEMBERSHIP_TYPE
        - EMAIL

1. Make branch id the primary key(BRANCH)
2. Add a foreign key linking each book to its branch. ( book table )
3. Enforce MEMBERSHIP_TYPE only allows values ‘REGULAR’ , ‘PREMIUM’, ‘STUDENT’. 
4. Use foreign keys referencing MEMBER (child)  and BOOK (parent). ( book_id )

1. ENSURE DUE_DATE > BORROW_DATE. 
2. Alter the BOOK table to include a LAST_DATE column with a default of NULL.
3. Rename MEMBERSHIP_TYPE column to MEMBER_TIER.
4. Drop the PRICE column from the BOOK table.