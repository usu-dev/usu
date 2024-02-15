# usu stores usu

<p align='center'>
<img src="https://raw.githubusercontent.com/usu-dev/usu/main/assets/logo.svg" width=200>
</p>

Equivalent data structures written in usu vs json.

<table>
<tr><td>usu</td><td>json</td></tr>
<tr><td>

```usu
:key value
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
["1","2","3","4","5"]
```
</td></tr>
<tr><td>

```usu
:key (
 :nested-key value
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
:package usu
:version 0.1.0
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
:inline-list (list of strings)
:multiline-list: (
  here newlines can end strings
  meaning these are each one string
)
:string unquoted string
```
</td><td>

```json
{
  "inline-list": ["list", "of", "strings"],
  "multiline-list": [
    "here newlines can end strings",
    "meaning these are each one string"
  ],
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

## Implicit Features

When the first non-whitespace/comment is a key the top level map is implied meaning the following documents are equivalent.

```usu
(:key value :second-key value)
```

```usu
:key value :second-key value
```

Things `usu` can do that json can't:
```usu
# this is a comment
#(
  this is block comment
)#

:unquoted unquoted strings
:single-quoted 'single quoted'
:double-quoted "double quoted"
:backtick-quoted `This'll escape all quotes`

:multiline-string
  This string has newlines and starts at the
  first non-whitespace character,
  with leading whitespace removed.
  And a trailing newline

:folded-string >
  This string has no newlines
  and will replace any newlines with
  a single space
```


&nbsp;

<p align="center"><img src="https://raw.githubusercontent.com/usu-dev/usu/main/assets/footer.svg" width="100%"></p>
<p align="center">Copyright &copy; 2023-present <a href="https://github.com/usu-dev" target="_blank">Usu Org</a>
<a>
