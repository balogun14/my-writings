## Table of Contents
1. What is Regex?
2. Why Use Regex?
3. Basic Syntax
4. Common Patterns
5. Quantifiers
6. Character Classes
7. Anchors
8. Groups and Capturing
9. Practical Examples
10. Common Use Cases
11. Testing Your Regex
12. Best Practices
13. Further Reading
## What is Regex?

Regular Expressions (Regex or RegExp) are powerful patterns used to match character combinations in strings. Think of them as a search pattern that can find, match, and manipulate text based on specific rules.

**Simple Analogy:** Imagine regex as a very smart "Find & Replace" tool that can understand patterns instead of just exact words.

![[Pasted image 20250525000404.png]]

## Why Use Regex?

Regex is incredibly useful for:
- **Validation**: Check if email addresses, phone numbers, or passwords are valid
- **Search**: Find specific patterns in large amounts of text
- **Replace**: Replace text based on patterns
- **Extract**: Pull out specific information from strings
- **Split**: Break text into parts based on patterns

## Basic Syntax

### Literal Characters
The simplest regex matches exact characters:

```regex
hello
```
This matches the word "hello" exactly.

### Special Characters (Metacharacters)
These characters have special meanings in regex:

```
. ^ $ * + ? { } [ ] \ | ( )
```

To match these literally, you need to escape them with a backslash (`\`):

```regex
\$100  # Matches "$100"
\.     # Matches a period
```

![[Pasted image 20250525000755.png]]

![[Pasted image 20250525000822.png]]
## Common Patterns

### The Dot (.)
Matches any single character except newline:

```regex
c.t
```
Matches: "cat", "cot", "cut", "c5t", "c@t"

### Alternation (|)
Acts like "OR":

```regex
cat|dog
```
Matches: "cat" OR "dog"

### Escaping Special Characters
Use backslash to match special characters literally:

```regex
\$\d+\.\d{2}
```
Matches: "$25.99", "$100.00"

## Quantifiers

Quantifiers specify how many times a character or group should be matched:

### Basic Quantifiers
- `*` - Zero or more times
- `+` - One or more times  
- `?` - Zero or one time (optional)
- `{n}` - Exactly n times
- `{n,}` - n or more times
- `{n,m}` - Between n and m times

### Examples

```regex
colou?r        # Matches "color" and "colour"
\d+            # Matches one or more digits
\d{3}          # Matches exactly 3 digits
\d{2,4}        # Matches 2 to 4 digits
a*             # Matches zero or more 'a's
```

![[Pasted image 20250525000932.png]]

## Character Classes

### Predefined Character Classes
- `\d` - Any digit (0-9)
- `\w` - Any word character (letters, digits, underscore)
- `\s` - Any whitespace character (space, tab, newline)
- `\D` - Any non-digit
- `\W` - Any non-word character
- `\S` - Any non-whitespace character

### Custom Character Classes
Use square brackets to define your own:

```regex
[abc]          # Matches 'a', 'b', or 'c'
[a-z]          # Matches any lowercase letter
[A-Z]          # Matches any uppercase letter
[0-9]          # Matches any digit
[a-zA-Z0-9]    # Matches any alphanumeric character
[^abc]         # Matches anything EXCEPT 'a', 'b', or 'c'
```

### Examples

```regex
[aeiou]        # Matches any vowel
[^aeiou]       # Matches any consonant
[0-5]          # Matches digits 0 through 5
```

![[Pasted image 20250525001035.png]]

## Anchors

Anchors don't match characters; they match positions:

- `^` - Start of string/line
- `$` - End of string/line
- `\b` - Word boundary
- `\B` - Non-word boundary

### Examples

```regex
^Hello         # Matches "Hello" at the start
world$         # Matches "world" at the end
^Hello world$  # Matches exactly "Hello world"
\bcat\b        # Matches "cat" as a whole word
\Bcat\B        # Matches "cat" inside another word
```

## Groups and Capturing

### Parentheses for Grouping
Parentheses group parts of your pattern:

```regex
(abc)+         # Matches "abc", "abcabc", "abcabcabc"
(cat|dog)s     # Matches "cats" or "dogs"
```

### Non-Capturing Groups
Use `(?:...)` when you want to group but not capture:

```regex
(?:Mr|Mrs|Ms)\. \w+
```
Matches titles with names but doesn't capture the title separately.

![[Pasted image 20250525001112.png]]

## Practical Examples

### Email Validation (Simple)
```regex
^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$
```

**Breakdown:**
- `^` - Start of string
- `[a-zA-Z0-9._%+-]+` - Username part (letters, numbers, special chars)
- `@` - Literal @ symbol
- `[a-zA-Z0-9.-]+` - Domain name
- `\.` - Literal dot
- `[a-zA-Z]{2,}` - Domain extension (2+ letters)
- `$` - End of string

### Phone Number (US Format)
```regex
^\(?(\d{3})\)?[-.\s]?(\d{3})[-.\s]?(\d{4})$
```

Matches formats like:
- (555) 123-4567
- 555-123-4567
- 555.123.4567
- 5551234567

### Password Strength
```regex
^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}$
```

**Requirements:**
- At least 8 characters
- One lowercase letter
- One uppercase letter
- One digit
- One special character

![[Pasted image 20250525001454.png]]
![[Pasted image 20250525001551.png]]
## Common Use Cases

### 1. Form Validation
```regex
# Name (letters and spaces only)
^[A-Za-z\s]+$

# ZIP Code (US)
^\d{5}(-\d{4})?$

# Credit Card (basic)
^\d{4}[\s-]?\d{4}[\s-]?\d{4}[\s-]?\d{4}$
```

### 2. Text Processing
```regex
# Find all URLs
https?://[^\s]+

# Extract hashtags
#\w+

# Find dates (MM/DD/YYYY)
\d{1,2}/\d{1,2}/\d{4}
```

### 3. Data Cleaning
```regex
# Remove extra whitespace
\s+

# Find duplicate words
\b(\w+)\s+\1\b

# Extract numbers from text
\d+(\.\d+)?
```

## Testing Your Regex

### Online Tools
1. **regex101.com** - Best for learning with explanations
2. **regexpal.com** - Simple and fast
3. **regexr.com** - Visual and interactive
4. https://regex101.com 

### Browser Console
```javascript
// Test if pattern matches
/pattern/.test("string to test")

// Find matches
"string to search".match(/pattern/g)

// Replace using regex
"string".replace(/pattern/g, "replacement")
```


## Best Practices

### 1. Start Simple
Build your regex step by step:
```regex
# Step 1: Match basic email structure
\w+@\w+

# Step 2: Add domain extension
\w+@\w+\.\w+

# Step 3: Handle special characters
[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}
```

### 2. Be Specific
Instead of `.+` (matches everything), be more specific:
```regex
# Bad: Too broad
.+

# Good: More specific
[a-zA-Z0-9\s]+
```

### 3. Use Comments (in some languages)
```regex
# JavaScript example with comments
(?x)              # Enable extended mode
^                 # Start of string
[a-zA-Z0-9._%+-]+ # Username part
@                 # @ symbol
[a-zA-Z0-9.-]+    # Domain
\.                # Dot
[a-zA-Z]{2,}      # Extension
$                 # End of string
```

### 4. Test Edge Cases
Always test your regex with:
- Valid inputs
- Invalid inputs
- Empty strings
- Very long strings
- Special characters

### 5. Consider Performance
- Avoid excessive backtracking
- Use non-capturing groups when possible
- Be specific rather than greedy

## Common Mistakes to Avoid

1. **Forgetting to escape special characters**
   ```regex
   # Wrong
   $100
   
   # Right
   \$100
   ```

2. **Being too greedy**
   ```regex
   # Wrong: Matches too much
   <.*>
   
   # Right: Matches specific tags
   <[^>]*>
   ```

3. **Not anchoring when needed**
   ```regex
   # Wrong: Matches partial emails
   \w+@\w+\.\w+
   
   # Right: Matches complete emails only
   ^\w+@\w+\.\w+$
   ```

4. **Overcomplicating**
   - Start simple
   - Add complexity gradually
   - Test each addition


## Conclusion

Regular expressions are powerful tools for text processing, but they can seem intimidating at first. Remember:

1. **Start with simple patterns**
2. **Build complexity gradually**
3. **Test frequently**
4. **Use online tools to experiment**
5. **Practice with real-world examples**

The key to mastering regex is practice. Start with simple patterns and gradually work your way up to more complex ones. Don't try to learn everything at once!

## Quick Reference Card

```regex
# Basic Patterns
.          # Any character
\d         # Digit
\w         # Word character
\s         # Whitespace
^          # Start of string
$          # End of string

# Quantifiers
*          # Zero or more
+          # One or more
?          # Optional
{n}        # Exactly n times
{n,m}      # Between n and m times

# Character Classes
[abc]      # Any of a, b, c
[a-z]      # Any lowercase letter
[^abc]     # Anything except a, b, c

# Groups
(abc)      # Capturing group
(?:abc)    # Non-capturing group
```

Happy regex matching! 🎯
 `@TechPylon` 