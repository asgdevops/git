# Lines and Tables

## Lines
---

To draw a horizontal line write a triple hyphen `---` tag.


## Tables
---

Tables need at least a header element. 

The table columns are enclosed between the pipe `|` tags.

Similarly, the table header requires double hyphen between the pipe tags `|--|`. 

Column alignment depends on the position of the semicolon followed by the dashes

Tag|Alignment
-- | --
`\|--\|`| Default left alignment.
`\|:--\|`| Left alignment.
`\|:--:\|`| Center alignment.
`\|--:\|`| Right alignment.


## Example

<table>
<tr>
  <td>
  
  **Format**
  
  </td>
  <td>
  
  **Syntax**
  
  </td>
</tr>
<tr>
  <td>
  
  |#|Item|Letter|
  |--:|:--|:--:|
  |1|Row 1|A|
  |2|Row 2|B|
  |3|Row 3|C|

  </td>
  <td>

  ```text
  |#|Item|Letter|
  |--:|:--|:--:|
  |1|Row 1|A|
  |2|Row 2|B|
  |3|Row 3|C|
  ```

  </td>
</tr>
</table>