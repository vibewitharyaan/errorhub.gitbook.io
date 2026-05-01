---
description: All the exports are server-sided
icon: stack-exchange
---

# Exports

### Is Whitelisted

Checks if a player is whitelisted based on the configured whitelist method.

```lua
exports['eh_antirelease_shield']:isWhitelisted(playerId, function(result)
    if result then
        -- Player is whitelisted
    end
end)
```

**Parameters:**

* `playerId` — Player's server ID
* `callback` — Async callback returning boolean

***

### Add Whitelist

Adds an identifier to the whitelist.

```lua
local success, response = exports['eh_antirelease_shield']:whitelistAdd(identifier)
```

**Parameters:**

* `identifier` — Identifier string (format: `type:value`)

**Returns:** `success` (boolean), `response` (string)

***

### Remove Whitelist

Removes an identifier from the whitelist.

```lua
local success, response = exports['eh_antirelease_shield']:whitelistRemove(identifier)
```

**Parameters:**

* `identifier` — Identifier string (format: `type:value`)

**Returns:** `success` (boolean), `response` (string)
