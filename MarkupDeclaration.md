# Markup Declaration

| Code | Name | Example | Declared in | Purpose |
| - | - | - | - | - |
| `>` | Empty Markup Declaration | `<!>` |
| `--` | Comment | `<!--Some comment-->` |
| `[` | Marked Section | `<![CDATA[Some Character Data]]>` |
| `ENTITY` | Entity | | DOCTYPE, LINKTYPE |
| `DOCTYPE` | Document Type | `<!DOCTYPE html>` | `SGML document` < `SGML document entity` < `prolog` < `document type declaration`
| `ELEMENT` | Element | | DOCTYPE | 
| `ATTLIST` | Attribute List | | DOCTYPE, LINKTYPE |
| `NOTATION` | Notation | `<!NOTATION tex PUBLIC "-//local//NOTATION TeX Formula//EN">` | DOCTYPE | Defines a data content notation, so that the content type inside an element can be understood depending on the attribute value on the element, containing the notation name. |
| `SHORTREF` | Short Reference | | DOCTYPE |
| `USEMAP` | Use Map | | CONTENT, DOCTYPE |
| `LINKTYPE` | Link Type | | `SGML document` < `SGML document entity` < `prolog` < `link type declaration` |
| `LINK` | Link | | LINKTYPE |
| `IDLINK` | Id Link | | LINKTYPE |
| `USELINK` | Use Link | | LINKTYPE |
| `SGML` | Standard Generalized Markup Language | | `SGML document` < `SGML document entity` < `SGML declaration`
| `SYSTEM` | System | | - | Defines the declarations for a specific SGML system can deal with. This tag is only allowed standalone, so it will be never seen in any SGML document for this purpose. |
