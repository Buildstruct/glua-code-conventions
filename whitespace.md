# Whitespace

### Indenting and Scope
* Use **a single tab** for indents.
  * Tabs can have a customizable width on text editors, allowing readers to set the indent width to their preference.
* Code of a lower scope should be indented further to convey the scope at a glance.
* The finishing line (almost always `end`) of any conditional or function should be on the same indent depth as the starting line.
* Keep the starting line of conditionals and functions in one line if possible.
  * Because indents are mainly to convey scope, we want to minimize when they are used for other purposes.
* If the starting line is too long, the line can be broken up after an operator. Double-indent the extra lines and add another empty line before the code body.
  * We want to show that the extra lines are not part of the code body as clearly as we can.
* Conditionals and functions may only be put into one line if their body is either empty or only has a return statement.
  * This helps show the content of the scope more readily, especially if reading by indent.
  * Return statements are okay to be one-lined partially because they are colored differently and partially because it may be common to see many return conditions in a row.
* Use early returns and function calls over nested code.
  * While indents are useful, they signify something to actively pay attention to. Having many layered scopes in one place can be intensive to read.
```lua
function foo()
	if bar(1) and x1 and x2 and x3 and x4 and x5 and x6 and
			x7 and x8 then

		local x = 12
		bar(x)
	end

	if bar(2) then return end

	if true then
		bar(6)
	end
end
```

### Empty Lines
* Never have 2 or more empty lines in a row.
  * Wider spaces can be difficult to differentiate from thinner ones, so double or triple empty lines really only serves to make the file longer.
* Don't start a code body with an empty line unless the condition has multiple lines or the first line is a comment.
  * We are already using indents to separate scope, so empty lines are not as useful here.
* Don't end a code body with an empty line.
  * Same reasoning as above.
* Try to have empty lines between different *steps* or *processes* in the code. Grouped code like this will be called a stanza.
  * Empty lines between sections of code can be extremely helpful in figuring out what parts are important for a particular process. 
* Stanzas including returns, breaks, or continues shouldn't be longer than 2 lines.
  * Returns, breaks, and continues have a strong impact on how the code is processed, so they should stand out.
```lua
function foo()
	if bar(1) then
		local x = 1 + 2 + 3
		return x
	end

	if bar(2) then
		local x = baz(0)
		local y = baz(1)
		local z = baz(2)

		doTheThing(x, y, z)
		return x, y, z
	end

	if true then

		-- TODO: this bar
		bar(6)
	end
end
```

### Variables and Calls
* Space out text after commas.
  * This makes comma-separated statements match how commas work for English, which can help make them easier to read.
* Add spaces between operators (except for `^`, since it's meant to show an exponent).
* Don't add a space after an opening parenthesis or before a closing parenthesis.
  * This is for a similar reason to above, but it's also to help differentiate them between curly braces.
* Add spaces after an opening curly brace and before a closing curly brace... EXCEPT for `{...}`
  * Curly braces have less of an analogue to English and serve a very different purpose to parenthesis... but they can be hard to tell apart sometimes. The spacing can help as a cue.
  * Not adding spaces for varargs is more of a style choice... periods are very small, so they look almost like a space already.
```lua
function foo(...)
	local x = doTheThing(1, 2 + 2, 3^3, 4^5 * 25, 1 + (2 * 3))
	local y = { x, 6, 7, {...} }

	return x, y
end
```
