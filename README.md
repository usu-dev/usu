# usu stores usu

<p align='center'>
<img src="https://raw.githubusercontent.com/usu-dev/usu/main/assets/logo.svg" width=200>
</p>

Equivalent data structures written in usu vs json.

<table>
<tr><td>usu</td><td>json</td></tr>
<tr><td>

```usu
(:key value)
```
</td><td>

```json
{"key":"value"}
```
</td></tr>
<tr><td>

```usu
(1 2 3 4 5)
```
</td><td>

```json
[1,2,3,4,5]
```
</td></tr>
<tr><td>

```usu
(
  :key (
    :nested-key value
  )
)
```
</td><td>

```json
{
  "key": {
    "nested-key": "value"
  }
}
```
</td></tr>
<tr><td>

```usu
(
  :package usu
  :version "0.1.0"
)
```
</td><td>

```json
{
  "package": "usu",
  "version": "0.1.0"
}
```
</td></tr>
<tr><td>

```usu
(:package usu :version "0.1.0" :dependencies ())
```
</td><td>

```json
{"package": "usu","version": "0.1.0","dependencies":[]}
```
</td></tr>
<tr><td>

```usu
(
  :inline-list (list of strings)
  :multiline-list (
    here newlines can end strings
    meaning these are each one string
  )
  :string unquoted string
)
```
</td><td>

```json
{
  "inline-list": ["list", "of", "strings"],
  "multiline-list": [
    "here newlines can end strings",
    "meaning these are each one string"
  ]
  "string": "unquoted string",
}
```
</td></tr>

<tr><td>

```usu
(
  :empty-list ()
  :empty-map (:)
)
```
</td><td>

```json
{
  "empty-list": [],
  "empty-map": {}
}
```
</td></tr>
</table>


Strings are implicit but can be made explicit
```usu
(
  :int 5
  :float 5.5
  :name John Doe
  :version "0.1.0"
)
```

Things `usu` can do that json can't:
```usu
# this is a comment
#(
  this is block comment
)#
(
  :unquoted unquoted strings
  :single-quoted 'single quoted'
  :double-quoted "double quoted"
  :backtick-quoted `This'll escape all quotes`
  :multiline-string `
    This string has newlines and starts at the
    first non-whitespace character,
    with leading whitespace removed.
    Backticks will escape all characters including
    parenthesis, colons and quotes -> ():'".
    The backticks themselves can be escaped
    with a single backslash i.e. \`
    `
)
```


Space between start/end of values and keys is ignored
```usu
(  :a-key some value :next-key "some other value"  )
 ^^      +          +         +     ^            ^^
# arrows indicate trimmed whitespace
# plus-signs indicate necessary whitespace i.e. between key-values
```
