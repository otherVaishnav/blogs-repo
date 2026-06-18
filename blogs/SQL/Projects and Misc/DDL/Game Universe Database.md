---
title: "Game Universe Database"
description: "Explore the Game Universe Database schema."
pubDate: "2025-06-01"
---

<!-- # Game Universe Database -->

1. Create a PLAYER table: 
    - PLAYER_ID
    - USERNAME
    - EMAIL
    - LEVEL
    - JOIN_DATE
2. Unique constraint on USERNAME and EMAIL.
3. Create a  CHARACTER table with:
    - CHAR_ID
    - PLAYER_ID
    - CHAR_NAME
    - CLASS
    - XP
    - CREATED_AT
4. ADD Foreign key on PLAYER_ID.
5. Create a weapon table: 
    - WEAPON_ID
    - WEAPON_NAME
    - TYPE
    - DAMAGE
    - DURABILITY
6. SET Default durability TO 100.
7. Create a BATTLE table:
    - BATTLE_ID
    - CHAR_ID
    - ENEMY_TYPE
    - OUTCOME
    - BATTLE_DATE
8. Outcome must be ‘WIN’, ‘LOSE’ or ‘DRAW’.
9. Add a GUILD table with
    - GUILD_ID
    - GUILD_NAME
    - LEADER_ID
10. LEADER_ID references PLAYER_ID.
11. Alter the  CHARACTER table to include GUILD_ID and create a foreign key reference to GUILD_ID .
12. Add a CHECK constraint ensuring XP cannot be negative.
13. Drop the DAMAGE column from WEAPON and replace it with MIN_DAMAGE and MAX_DAMAGE.
14. Rename table WEAPON to ARSENAL.
15. Create a new table ITEM_INVENTORY with PLAYER_ID , ITEM_NAME, QUALITY.
16. Add a column STATUS to PLAYER (’ACTIVE’,’BANNED’,’SUSPENDED’).
17. Create a GAME_EVENT table to log schema evolution with columns: EVENT_ID , DESCRIPTION, CHANGE_DATE.
18. A new column RARITY added to ARSENAL .
19. A column GUILD_POINT added to GUILD with default 0.