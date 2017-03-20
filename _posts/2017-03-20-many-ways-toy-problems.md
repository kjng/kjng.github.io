---
published: false
---
## Many Ways of Solving (Toy) Problems

There are many ways of solving toy problems. I think when starting to code, most beginners strive to reach the perfect, 'right' solution. They view each toy problem (since we all start with and love toy problems) as being uni-directional similar to a footrace.

This post talks more in the perspective of a 'just-starting' coder.

### Toy Problems Represented

Most beginners view toy problems like this:
![Perceived single-line toy problem timeline]({{site.baseurl}}/_posts/perceived.jpg)

I think many coders wish it were this simple, myself included. We could then build up our skills in a linear fashion and become masters someday.

However, this isn't the reality. There are many solutions to the same one. Granted, some solutions may be more optimal, more readable, more whatever, but there are always **tradeoffs** involved.

_This_ is more inline with reality:

![Reality of solving toy problems, complicated line diagram]({{site.baseurl}}/_posts/reality.jpg)

What is represented here?

1. There isn't a single path.
2. You may need to backtrack and undo/redo work.
3. Your solution won't be the only one.

Other things that I didn't represent in this diagram:
- Your solution may be less/more readable to a human
- The path to solving problems will be different each time
- Your path will start shifting to become more like the single-line diagram

**My main takeaways are** to shift expectations from this linear path, not to seek too heavily a 'perfect' solution because there isn't one, and to encourage the growth mindset.

But let's not keep this at an overly high-level discussion. I'll leave you with a simple toy problem code example.

### A Simple Code Example

```javascript
// Determine if a number is odd.
// -----------------------------

var num = 5;

// EXAMPLE 1
var leftover;

while (num > 1) {
	num = num - 2;
}

if (leftover === 1) { return true }
if (leftover === 0) { return false }

// EXAMPLE 2
num = 5;
return num % 2 === 1;
```

Now, I understand this example may be a bit contrived or too simple, but I want to point out that for someone beginning JavaScript, _Example 1_ is **perfectly fine**. There are tradeoffs for _Example 1_ such as more lines of code, more memory space, etc. However, you could equally argue that _Example 2_ is less understandable and harder to read for a beginner. Time and experience will make most coders understand something like _Example 2_ to be superior, but being able to weigh the pros and cons are important.