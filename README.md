```lua
-- try to follow glualint formatting (https://github.com/FPtje/GLuaFixer)
-- use single tab for indenting

-- avoid defining on the global table _G
-- make your variables and functions local whenever possible or defined on bs

-- methods defined on bs should be PascalCase
function bs.MyFunction() end

-- try to avoid shared scripts when possible
-- if the serverside and clientside part of your code can be easily separate, make them
-- sh_myscript.lua -> sv_myscript.lua, cl_myscript.lua

-- everything that can be identified with a string should have "BS_" or "bs_" prepended before it
-- in order to avoid collisions with other addons

-- hooks, named timers, vgui elements, etc. prepended with "BS_" and PascalCase
hook.Add("OnGamemodeLoaded", "BS_MyHook", function() end)
timer.Create("BS_MyTimer", 60, 1, function() end)
vgui.Register("BS_MyElement", PANEL, "DPanel")
ent:CallOnRemove("BS_MyRemoveCallback", function() end)

-- server-related sents, sweps, tools, etc. prepended with "bs_" and lowercase (they are case-insensitive)
-- bs_myentity, bs_myweapon, bs_mytool

-- network strings prepended with "bs_" and lowercase (they are case-insensitive)
util.AddNetworkString("bs_mynetstr")

-- use lua's function definition syntax to define functions when possible
-- incorrect:
local foo = function()
  print(1)
end
-- correct:
local function bar()
  print(1)
end

-- avoid lines longer than 120 characters
-- if required you may break up a line (double-indent the second part)
foo(supercalifragilisticexpialidocious, theQuickBrownFox, 12, 121241241,
    loremIpsum, abraCadabra)

-- do not use c-style syntax
-- incorrect: !=, //, &&, ||
-- correct: ~=, --, and, or

-- anything in parenthesis should not be spaced
-- incorrect: foo( a, b, c )
-- correct: foo(a, b, c)

-- anything in curly braces SHOULD be spaced
-- varchar can be an exception
-- the difference is to help differentiate from normal parenthesis better
-- incorrect: {1, 2, 3}
-- correct: { 1, 2, 3 }, { ... }, {...}

-- always space out comma separated lists
-- incorrect: foo(1,2,3)
-- correct: foo(1, 2, 3)

-- conditions in statements should be written plainly without parenthesis
-- incorrect:
if (true) then
  print(1)
end
-- correct:
if true then
  print(1)
end

-- single-line if statements are only allowed for returns
-- this helps with understanding code control flow at a glance if reading by indent
-- the exception is to compress big rows of return conditions at the start of functions
-- incorrect:
if true then print(1) end
-- correct:
if true then
  print(1)
end
if true then
  return 1
end
if false then return 2 end

-- single-line functions are only allowed for empty functions
-- same reasons as above
-- incorrect:
local function foo() print(1) end
-- correct:
local function bar()
  print(1)
end
local function tar() end

-- avoid adding comments explaining your code
-- (make your code explain itself instead!)
-- code-explaining comments are often unchanged even when the code changes,
-- and they are rarely as helpful as code that is self-explanatory

-- flatten out your code/minimize nesting as much as possible
-- https://www.martin-paucot.fr/blog/stop-nesting-your-code-4ng8

-- use empty lines to separate your code into readable chunks
-- no special rules here, but avoid having 2+ empty lines in a row

-- avoid having trailing whitespace on lines
```
