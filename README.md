# is
Lightweight testing mini-framework for Go.

* Easy to write and read
* Simple API: `is.Equal`, `is.OK` and `is.NoErr`
* Use comments to add descriptions which show up when tests fail

![Examples of failures](https://github.com/matryer/is/raw/master/misc/delicious-failures.png)

### Usage

The following code shows a range of useful ways you can use
the helper methods:

```go
func Test(t *testing.T) {

	is := is.New(t)
	
	signedin, err := isSignedIn(ctx)
	is.NoErr(err)            // isSignedIn error
	is.Equal(signedin, true) // must be signed in
	
	body := readBody(r)
	is.OK(strings.Contains(body, "Hi there"))
	
}
```
