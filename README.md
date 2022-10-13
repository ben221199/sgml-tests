# SGML Tests

<table>
<tr><th>SGML</th><th>Logs</th><th>Objects</th></tr>
<!--###################################################################-->
<tr><td>

```html
<!NAME>
```
</td><td>

```log
CON
CON -> MD @MDO		<!
       MD #DCL		N
       MD		AME
CON <- MD @MDC		>
CON
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
<!DOCTYPE html>
```
</td><td>

```log
CON
CON -> MD @MDO		<!
       MD #DCL		D
       MD		OCTYPE html
CON <- MD @MDC		>
CON
```

</td><td>

```java
MarkupDeclaration{
	items=[
		"DOCTYPE",
		new Seperator(" "),
		"html"
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

```log
CON
CON -> MD @MDO		<!
       MD @COM #DCL	--
       MD		COMMENT_TEXT
       MD @COM		--
CON <- MD @MDC		>
CON
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

```log
CON
CON -> MD @MDO			<!
       MD -> DSM? @DSO #DCL	[
       MD <- DSM? @DSC		]
CON <- MD @MDC			>
CON
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
<![CDATA[SomeTextOrSomething]]>
```
</td><td>

```log
CON
CON -> MD @MDO			<!
       MD -> DSM? @DSO #DCL	[
             DSM?		CDATA
             DSM? -> CON @???	[
                     CON	SomeTextOrSomething
       MD <- DSM? <- CON @MSC	]]
CON <- MD @MDC			>
CON
```
<i>Note: The specification is not clear about marked sections.</i>
</td><td>

```java
MarkupDeclaration{
	items=[
		DeclarationSubset{items=[
			"CDATA",
			DeclarationSubset{items=[
				"SomeTextOrSomething"
			]}
		]}
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

```log
CON
CON -> MD @MDO		<!
CON <- MD @MDC #DCL	>
CON
```

</td><td>

```java
MarkupDeclaration{items=[]}
```

</td></tr>
</table>
