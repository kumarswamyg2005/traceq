# Stack trace to search query

Type `=traceq` in the Bolt launcher and paste a stack trace. You get the exception lines only, with your folders, line numbers and memory addresses removed, ready to search or post.

- **Who it is for:** student developers who paste errors into a search engine, a forum or a chat.
- **What it saves:** deleting frames, `/Users/<you>/` folders and `:12:5` by hand before you search, and posting your user name by accident.
- **Kind:** launcher app, pure transform (tier 2, acts inside Bolt).
- **Permissions:** reads what you type or paste into the launcher, and copies the result to your clipboard. No commands, no network, no files.

## Sample

Input:

```
Traceback (most recent call last):
  File "/Users/demo-student/projects/app/main.py", line 12, in <module>
    load("/Users/demo-student/projects/data.csv")
FileNotFoundError: [Errno 2] No such file or directory: '/Users/demo-student/projects/data.csv'
```

Result:

```
FileNotFoundError: [Errno 2] No such file or directory: 'data.csv'
```

It reads Python, pytest, Java, C#, JavaScript, Go and Rust output. Paste text with no exception and it tells you what to paste. Lines over 160 characters, and anything past 8 lines, are cut and marked as cut.

## Tests

19 cases in `bolt-app.json`: the languages above, empty input, text with no exception, repeats, Unicode, shell characters, Windows line endings, both cut limits at their edges, and a second run on its own output.
