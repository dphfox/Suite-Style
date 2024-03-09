# Structure

The high-level structure of a file should be consistent at a basic level, with deviations explicitly justified by what
they achieve.

## Metadata [...](metadata)

```Lua
--!strict
-- By Fusion, licensed under MIT
```

## Explanation [...](explanation)

```Lua
-- These types may be used internally so Fusion code can type-check, but
-- should never be exposed to public users, as these definitions are fair game
-- for breaking changes.

-- Instead, re-exports for public use can be found in PubTypes.
```

## Imports [...](imports)

```Lua
local Lighting = game:GetService("Lighting")
local Workspace = game:GetService("Workspace")

local Types = require("fusion/Core/Types")
local Children = require("fusion/Roblox/Children")
local New = require("fusion/Roblox/New")
local Computed = require("fusion/State/Computed")
local Value = require("fusion/State/Value")
```

## Typedefs [...](typedefs)

```Lua
type Set<T> = {[T]: true}
type Child = Instance | {Child} | Types.StateObject<Child>
```

## Constants [...](constants)

```Lua
local ENABLE_DEBUG_CHECKS = true
local TAU = 6.283185307179586
```

## Globals [...](globals)

```Lua
local counter = 0
local isCounting = false
```

## Functions [...](functions)

```Lua
local function reset()
	counter = 0
	isCounting = false
end

local function count(
	amount: number
)
	if isCounting then
		counter += amount
	end
end
```

## Return [...](return)

```Lua
return {
	reset = reset,
	count = count
}
```