Drupal Configuration Spreadsheet Standard
=========================================

The goal of the Drupal Configuration Spreadsheet Standard is to provide a common format for creating spreadsheets that describe Drupal configuration in a way that is machine-readable, allowing for automatic conversion to other Drupal configuration standards (e.g. Drupal 8's YAML format). As much as possible, the format should be easily readable and editable by humans as well.

## Example

An example document matching this standard is available at https://docs.google.com/spreadsheet/ccc?key=0Ak5zX7FSC8XFdG9GSjNwY0c4WlBaN0N2X3lHa1NyWGc and will be updated along with the standard.

## Worksheets

Specific types of configuration should be described in separate sheets with names that clearly identify the configuration type. Worksheet names must be unique, plural, and case-insensitive. The following worksheet names are defined:

* node types: also known as "content types".
* fields: also known as "base fields" or "field storage".
* image styles: also including effects.
* menus: *not* including menu items, only.
* vocabularies: taxonomy vocabularies, *not* including terms.
* field collections: see https://www.drupal.org/project/field_collection

## Worksheet Columns

The first row of each worksheet is reserved for human-readable information, such as worksheet titles, and should not include any information required by applications.

The second row of each worksheet defines column names. Column names must be unique and case-insenstive. The "notes" column is reserved for human-readable information, and should not include any information required by applications.

### Secondary Configuration Types

Each worksheet may include information about one secondary configuration type, e.g. the "node types" worksheet may include information about field instances for each node type. Secondary configuration columns should appear after the primary configuration type columns. Wherever primary configuration columns are blank, the value from the previous non-blank row should be used.

## Node Types

A node type worksheet may include the following columns:

* name: the human-readable name of the node type. *Optional*, defaults to machine name value.
* machine name: the unique machine-readable name of the node type. *Required*.
* title label: the label of the title field. *Optional*, defaults to "Title".
* description: text describing the node type and how it should be used. *Optional*, defaults to empty.
* publish: Y or N, indicating whether nodes should default to published. *Optional*, defaults to Y.

A node type worksheet may also include field instance columns:

* label: the human-readable name of the field. *Optional*, defaults to field machine name value.
* field machine name: the unique machine-readable name of the field. *Required*.
* help text: text describing the field and how it should be used. *Optional*, defaults to empty.
* field settings: a YAML-formatted array of machine-readable field settings. *Optional*, defaults vary by field type.
