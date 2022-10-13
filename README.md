# SGML Tests

<table>
<tr><th>SGML</th><th>Objects</th></tr>
<!--###################################################################-->
<tr><td>

```html
<!NAME>
```
</td><td>

```java
MarkupDeclaration{
	items=[
		"NAME"
	]
}
```

</td></tr>
<!--###################################################################-->
<tr><td>

```html
<!--COMMENT_TEXT-->
```
</td><td>

```java
MarkupDeclaration{
	items=[
		Comment{value="COMMENT_TEXT"}
	]
}
```

</td></tr>
<!--###################################################################-->
<tr><td>

```html
<![]>
```
</td><td>

```java
MarkupDeclaration{
	items=[
		DeclarationSubset{items=[]}
	]
}
```

</td></tr>
<!--###################################################################-->
<tr><td>

```html
<!>
```
</td><td>

```java
MarkupDeclaration{items=[]}
```

</td></tr>
</table>
