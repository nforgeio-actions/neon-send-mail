# send-mail

**INTERNAL USE ONLY:** This GitHub action is not intended for general use.  The only reason why this repo is public is because GitHub requires it.

Sends the email from the MSFT 365 account specified by the user's 1Password credentials

## Examples

**Send a simple email:**
```
uses: nforgeio-actions/send-mail 
  with:
    to: sally@test.com
    subject: Hello World!
    body: |
      This is a test message.
```

**Send email to multiple recipients:**
```
uses: nforgeio-actions/send-mail 
  with:
    to: sally@test.com, bob@test.com
    cc: mary@test.com
    bcc: john@test.com, billy@test.com
    subject: Hello World!
    body: |
      This is a test message.
```

**Send an HTML message:**
```
uses: nforgeio-actions/send-mail 
  with:
    to: sally@test.com
    subject: Hello World!
    bodyAsHtml: true
    body: |
      <b>This is a test message.</b>
```

**Include up to 10 attachment files:**
```
uses: nforgeio-actions/send-mail 
  with:
    to: sally@test.com
    subject: Hello World!
    body: |
      This is a test message.
    attachment0: C:\attachment0.txt
    attachment1: C:\attachment1.txt
    attachment2: C:\attachment2.txt
    attachment3: C:\attachment3.txt
    attachment4: C:\attachment4.txt
    attachment5: C:\attachment5.txt
    attachment6: C:\attachment6.txt
    attachment7: C:\attachment7.txt
    attachment8: C:\attachment8.txt
    attachment9: C:\attachment9.txt
```

## Implementation Note

This action assumes that it's being run on a specially configured self-hosted (Windows) jobrunner with the relevant neonFORGE repos already cloned to specific directories.  Generic jobrunners are not supported.
