# Open Source Software and Hosting 
2025/10/16 - Laura Hae Mi Kang  

## Basic Formatting 
### Headings 
- Frequently used on websites, magazines, articles and notices to draw attention
#### How to format a heading
- Preface the phrase with a hash mark
  
e.g. # Heading1
- Headers one and six should be used sparingly!

### Paragraphs and linke breaks 
#### Bold
- Basic element in text formatting

e.g. **Word** ("**" at the beginning and at the end of a phrase)  

#### Italic
- Basic element in text formatting

e.g. _Word_ ("_" at the beginning and at the end of a phrase) 

#### Combination of bold and italic 

**_Word_** ("**_" at the beginning and at the end of a phrase) 

#### Strikethrough 

~~Word~~ ("~~" at the beginning and at the end of a phrase) 

#### Inline Code 

## Lists
### Unordered Lists
#### Bullet Points 
* Word

#### Ordered Lists
1 Word

#### Nested Lists
* Word
  * Word
 
Note: More than three levels of indent and sub-lists should be avoided. Otherwise the text might become too messy. 

## Links and Images 
There are two different types of link types in Markdown. However, they render in the exact same way.
* To link a text: [URL]
* Link: (URL)

--> These are combinable with headers, bold text, etc. 

### Reference-style Links
* Reference links do not appear in the rendered Markdown

e.g.  
Do you want to [see something fun][a fun place]?  
    [a fun place]: www.xy.com 

### Images 
#### Inline Image Link 
![alt text](link)  
Alt text --> A phrase or sentence that describes the image for visually impaired 

#### Reference Image 
![alt text][Image tag]  
    [image tag]: link 

## Code and Technical Content 
### Inline Code
* To highlight a short piece of code, variable name or filename without breaking the sentence flow.

e.g.  
`Word` --> The text is wrapped with `

### Fenced Code Blocks
* Is used to to display multi-line codes

e.g 
```
Code
```

--> The code block is wrapped with ```

### Syntax Highlighting 
* Feature to distinguish parts of a code
* Highlighting rules are language specified

e.g. (python)
```python
def goodbye(name):
  print (goodbye(Lisa))
```

--> Code is wrapped in ``` (Fenced Code Blocks)
--> At the beginning programming language is added (Python, R, HTML, etc.)

## Quotes and Notes 
* Call special attention to a quote from another source or design a pull quote for a magazine article
### Blockquotes 
* Sentence or paragraph that’s been specially formatted to draw attention to the reader

e.g.  
> Text
* Blank lined must contain the caret character to ensure the entire blockquote is grouped

### Nested Blockquotes 
* Quotes within quotes (e.g. replies)

e.g.  
> Blockquote 1
> > Blockquote 2

### Blockquotes with Formatting 
e.g. 
> **Blockquotes** _with_ formatting 

## Tables 
* Data in rows and columns
### Basic tables
e.g. 
|Name|Age|
|----|---|
|Lisa|28|

### Alignment
* Control horizontal alignment of table columns

e.g. 
|Name|Age|
|---:|---|
|Lisa|28|

## Dividers & Layout
* Dividers between sections to seperate topics 
### Horizontal rules
e.g. 

---
***
___
### Line breaks
- Moves text without creating a new paragraph

e.g.  
Hello 1   
Hello 2  
--> Two spaces at the end + ENTER

## Online and collaborative editors

### Markdown-based editors
## Platform/Tool Specific: GitHub

Task lists
## Mentioning users (@username)

## Automatic linking of issues/PRs

## Emoji shortcodes


 








