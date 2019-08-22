# Smart reporting user guide

### Special tags

- `<c>` : this is the main tag which identifies the whole record (most often a control) which you want to capture as a seperate line in the spreadsheet
- `[...]` : square brackets are used to capture ids of issues or other elements which are repeated within the main record (i.e. several issues per control, several management responses per control etc..). Square brackets must appear immediately after the tag in order to be captured by the analytics See the example further below.

### Tag dictionary

The following tags will be replaced with the corresponding headings:

```javascript
      let dictionary = {
        ID: 'Id',
        NA: 'Name',
        OB: 'Objective',
        DE: 'Description',
        RG: 'Region',
        BU: 'Business Unit',
        FR: 'Frequency',
        IS: 'Issue',
        IDS: 'Issue Id',
        RS: 'Management response'
      }
```

### Example - test content

Below is some test content you can copy paste to see how the tool works

```html
some random text 1 - should be skipped
<c>
    <id>C01</id>
    random text 2
    <na>Control name 1</na>
    <ob>Control objective 1</ob>
    <de>Control description 1</de>
    <rg>Region 1</rg>
    <bu>Business 1</bu>
    <fr>Frequency 1</fr>
    <is>[C01.D.1] Issue 1a</is>
    <is>[C01.D.2] Issue 2a</is>
    <is>[C01.E.1] Issue 3a</is>
    <rs>[C01.D.1] Response 1a</rs>
    random text 3  - should be skipped
    <rs>[C01.D.2] Response 2a</rs>
    <rs>[C01.D.4] Issue 4a</rs>
    <random>random marker</random>
    random text 4  - should be skipped
</c>
random text 5 - should be skipped
<c>
    <id>C02</id>
    <na>Control name 2</na>
    <ob>Control objectve 2</ob>
    <de>Control description 2</de>
    <rg>Region 2</rg>
    <bu>Business 2</bu>
    <fr>Frequency 2</fr>
    <is>Issue 2</is>
    <another>hello, another random marker</another>
</c>
random text 6  - should be skipped
```
