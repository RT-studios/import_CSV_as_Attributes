# Import CSV as Attributes

## Introduction
This add-on allows importing data in typical delimited plain text formats, such as CSV files, into Blender as geometry attributes. The data can then be further processed, for example with Geometry Nodes, to create great visualisations.

Delimited plain text files are popular formats for data distribution. Most online databases and data banks allow exporting as CSV or similar formats. Most spreadsheet tools also allow saving as delimited plain text. The exact file extension is not important, the parsing parameters can be specified manually. 


## Source File Formatting
The tool is compatible with two kind of tabular data, character delimited and width delimited. Character delimited data uses one character, such as comma (,) or semicolon (;), or any consecutive whitespaces as the delimiter to separate columns. Width delimited data is formatted with a fixed width per column, with the data padded if necessary with zeros or whitespaces. Rows are always delimited by newlines.

Some files include header lines before the actual data, to specify column names or other information. Column names, if specified, will be used as the attribute names by the importer.

Data should always be numeric, non numeric data will be automatically replaced by the default value specified in the import settings. If the file in use contains many columns with non-useful data, it may be a good idea to import it in a spreadsheet editor first and trim it down.

## Import Options

image

the following options are available to help the importer parse the data correctly.
- **Add Geometry Nodes Modifier:** This will automatically setup a new Geometry Node Tree for the data, with the attributes available as node inputs.
- **Include Grid Extras:** Will search for gridded attributes in the data, and provide the grid dimensions as integer inputs to the node tree. Gridded attributes are those attributes defining a nD grid, such that the product of their sizes equals the number of data points. There should be at least 2 and at most one less than the total number of columns to be identified correctly. This functionallity is useful to quickly create primitives that fit the data for visualization.
- **Column Names Row:** The row index (1 based) where the attribute names are. Leave at 0 if there is no row for column names.
- **Data Start Row:** The row index (1 based) where the numeric data starts.
- **Data Start Column:** Optionally, the first n columns can be ignored. Sometimes these are filled with an index or other non-useful data. Note that index is a built-in attribute in Blender.
- **Delimiter:** Field to specify how to delimit the data column-wise. It accepts different kind of formatting:
  - If left blank (empty), it will use any consecutive whitespace characters, including tabs, as the delimiter.
  - A single, non-numeric character, shuch as a comma ',' or a semicolon ';', will be used as delimiter character.
  - A single integer value, such as '12', will be used as column width for data formatted with fixed width.
  - A series of integer values separated by commas, such as '12,8,8,10,8' can be used to specify different widths per column.
- **Default Value:** Value used for non-numeric data or empty fields.

## Usage
Tutorial coming soon
