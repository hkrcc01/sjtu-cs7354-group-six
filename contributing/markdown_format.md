# <a name="markdown_format"></a> Markdown Format

We have made some loose conventions about the general markdown writing format

## <a name="general_format"></a> General Markdown Format

The general markdown structure is as follows:

```markdown
# <a name=<name>></a> Main Topic

## <a name=<name>></a> Subtopic One

## <a name=<name>></a> Subtopic Two
...

## <a name=<name>></a> See Also
```

It contain three part of infomation:

- main topic
- sub topic
- other link

1. With the exception of the first level heading for the mian topic, the other subtopic use the second level heading and below.

2. There must be a blank line between the title and the body.

3. The number of middle subheadings gets longer. Main and sub topic are mandatory, but *see also* part is optional.

4. There must be one empty lines between the title and the header.

5. The following specifications must be used for the use of numerical numbering(That is the secondary title must occasionally have 4 Spaces in the middle.):

```markdown
1.  Foo.
2.  Bar.
    1.1  Foofoo.
    1.2  Barbar.
3.  Baz.
```

6. The title content should be capitalized except for the initial letter of the function word, and use the following format for easy reference.

```markdown
<a name=<name>></a> Topic Name
```