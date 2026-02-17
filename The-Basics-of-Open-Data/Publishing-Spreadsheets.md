# Publishing Spreadsheets

## Introduction

Comma Separate Values (CSV) is an excellent format to use for many types of data—a layperson can open the files in any of dozens of programs (Excel, Google Sheets, Gnumeric, LibreOffice, Numbers, OpenOffice, etc.), they’re easy to produce, they’re compact, and they’re easy to parse. But there are right and wrong ways to produce CSV.

## Guidelines

The following is based on the rules provided at [clean-sheet.org](http://www.clean-sheet.org/).

1. The first row of the spreadsheet must be column headers, with one header for each column that has data.
1. All data must be in rows and columns, as a lookup table. Every row stores a different record, every cell corresponding to its column.
1. Do not format fields. Omit dollar signs, commas, footnote symbols, etc. For example, represent dollar values as `100002.25`, not `$100,002.25`.
1. Adhere to ISO standards for fields. Refer to countries by their [ISO 3166](https://en.wikipedia.org/wiki/ISO_3166) code, dates in the [ISO 8601 format](https://en.wikipedia.org/wiki/ISO_8601), etc.
1. If no value is available for a field, leave it blank. Do not write `N/A` or provide an explanatory note in the field.
1. Do not provide additional data in the same file, such as a key, aggregate statistics, a description of methodologies, etc. These belong elsewhere.

## Examples

### A Good Spreadsheet

<table>
<thead>
<tr><th>name</th><th>state</th><th>district</th><th>year_elected</th></tr>
</thead>
<tbody>
<tr><td>Ralph Abraham</td><td>LA</td><td>5</td><td>2015</td></tr>
<tr><td>Alma Adams</td><td>NC</td><td>12</td><td>2014</td></tr>
<tr><td>Robert Aderholt</td><td>AL</td><td>4</td><td>1997</td></tr>
<tr><td>Pete Aguilar</td><td>CA</td><td>31</td><td>2015</td></tr>
</tbody>
</table>

### A Bad Spreadsheet

<table>
<thead>
<tr><th colspan="4">Members of Congress</th></tr>
<tr><th>name</th><th>state</th><th>district</th><th>year_elected</th></tr>
</thead>
<tbody>
<tr><td>Ralph Abraham</td><td>Louisiana</td><td>5th</td><td>2015*</td></tr>
<tr><td>Alma Adams</td><td>N. Carolina</td><td>12th</td><td>2014</td></tr>
<tr><td colspan="2">Adams was appointed by the governor to complete Smith’s term.</td><td colspan="2">NC is redistricting.</td>
<tr><td>Robert Aderholt</td><td>Alabama</td><td>N/A</td><td>1997</td></tr>
<tr><td>Pete Aguilar</td><td>California</td><td>31st</td><td>2015</td></tr>
<tr><td></td><td></td><td></td><td></td></tr>
<tr><td colspan="4">* Special election</td></tr>
<tr><td></td><td></td><td></td><td></td></tr>
<tr><td></td><td></td><td></td><td></td></tr>
<tr><td></td><td></td><td></td><td></td></tr>
<tr><td colspan="4">Methodology: All data was gathered from Congress.gov on January 21, 2015, with the ...</td></tr>
</tbody>
</table>
