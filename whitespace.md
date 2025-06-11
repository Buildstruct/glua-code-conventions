# Whitespace

### Indenting and Scope
* Use **a single tab** for indents.
  * Tabs can have a customizable width on text editors, allowing readers to set the indent width to their preference.
* Code of a lower scope should be indented further to convey the scope at a glance.
  * This is the fundamental reason indents are used.
* The finishing line (almost always `end`) of any conditional or function should be on the same indent depth as the starting line.
  * This makes it much easier to see when a code body ends as opposed to the final line being on any other indent depth.
* Keep the starting line of conditionals and functions in one line if possible.
  * It's easier to see when the starting line ends if it's at the end of the same line and it distinguishes when the conditional might be split up between multiple lines (see the next point).
* If the starting line is too long, the line can be broken up after an operator. Double-indent the extra lines and add another empty line before the code body.
  * Double-indenting the extra lines helps convey that they're not part of the code body and are attached to the first line. Breaking up the line *after* an operator is closest to how lines may be broken up in poetry.
```lua
function foo()
	if bar and x1 and x2 and x3 and x4 and x5 and x6 and
			x7 and x8 then

		local x = 12
		bar(x)
	end

	if true then
		bar(6)
	end
end
```

### Empty lines
* Never have 2 or more empty lines in a row.
  * Double or triple empty lines are not a good way to distinguish segments; they simply create more space.
* Never start or finish a code body with an empty line (with one exception, see above).
  * Similar reasoning to above.
* Try to have empty lines between different *steps* or *processes* in the code (like separating stanzas in a poem).
  * This makes it easier to see those steps and processes as distinct from each other.
* Usually, a return/break/continue statement should have an empty line between it and the preceeding code.
  * Returns, breaks, and continues have a strong impact on how the code is processed, so they should stand out.

###
