# Sample Report - Web SQL Injection

> ⚠️ **This is a formatting reference only.** The scenario, app name, and
> payloads below are a hypothetical example (a fictional bookstore app),
> not the actual PortSwigger Academy labs assigned in Level 3. Solve the
> real labs yourself - the technique transfers, but the specific payload
> that works on the real lab will likely differ from this example.

---

## Example Scenario: "ExampleCorp Bookstore" - Filtering by Category

*(A stand-in for a lab with a similar shape to the assigned "retrieval of
hidden data" lab - not the real one.)*

The app has a category filter that builds a query like:

```sql
SELECT * FROM products WHERE category = 'Fiction' AND released = 1
```

Only "released" products are meant to be visible. The goal in a lab like
this is usually to reveal hidden (unreleased) items by manipulating the
`category` parameter.

### Step 1 - Confirming the Injection Point

I first tried breaking the query with a single quote to see if the app
errored out, which would confirm the input is dropped straight into SQL
without sanitization:

```
category=Fiction'
```

This produced a database error page - a strong signal that the
`category` parameter is unescaped.

### Step 2 - Building the Payload

Since the query is followed by `AND released = 1`, appending a comment
marker after my own condition lets me cut that clause off entirely:

```
category=Fiction' OR 1=1--
```

This closes the string, adds a condition that's always true (`1=1`), and
comments out the rest of the original query with `--`. In theory, this
would return every row in the table regardless of category or release
status.

### Step 3 - Result

*(In a real report, this is where you'd paste the actual response -
screenshot or raw HTML snippet showing the extra rows returned, plus the
lab's "solved" banner.)*

**Payload used:** `Fiction' OR 1=1--`
**Why it works:** it turns the WHERE clause into a tautology, so the
database's filtering condition no longer restricts which rows come back.

---

## What Your Real Report Needs

For each of the two assigned labs, include:

- 🔗 The **exact lab name** from the Academy
- 💉 The **exact payload** you used, in the actual parameter/field it went into
- 🧠 A short explanation of **why** that payload defeats the query's logic
- 🖼️ A **screenshot of the "Congratulations, you solved this lab" banner**

## Notes

- Comment syntax differs by database - `--` (with a trailing space) works
  on MySQL and PostgreSQL, `--` alone doesn't always comment reliably
  depending on context, and Oracle typically wants a different approach
  entirely. Part of the exercise is noticing which database you're
  talking to.
- A login-bypass style lab uses the same core idea (turning a WHERE
  clause into something always-true) but the injection point is
  typically a login form field rather than a URL parameter - the
  technique carries over, the exact field and payload won't.

---

*Your actual report should follow this same shape: injection point →
payload → why it works → proof it worked, for each of your two real labs.*
