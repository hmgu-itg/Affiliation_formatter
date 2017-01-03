# Affiliation formatter

A tool to create formatted author and affiliation list for publications based on excel table.   

### usage:

`./Affiliation_formatter.py -i input.xlsx -o output.html`

## System equirements:

python3/pandas above version 0.16

## Input requirements:

In the excel table one line represents one author of the publication and all of the affiliated institutions are listed in that line. The columns will be identifed by their names, so the order of the columns is not important. The affiliation columns can be repeated as many times as necessary. 

Required <b>name fields</b> in the input xlsx file:
* "First Name",
* "Middle Name" (Only initials, without spaces),
* "Last Name"

<b>Affiliation fields</b>:
* "Institute/Department/University",
* "City/State",
* "Post/Zip code",
* "Country"

The affiliation fields can be repeated as many times as necessary. Order of the columns are not considered. Other fields in the xlsx table will not be considered. As of v.1.1 field names are case insensitive! For a properly formatted example see <b>test_author_list.xlsx</b>.

## Output formats:

The script creates a formatted html file that can be read by any wordprocessors and save in the desired format. If one person has multiple affiliations their numbers will be listed in an ascending order. The numbers are assigned to affiliations in the order of apperance. 

Author names: [First name] [Middle name initials]. [Last name]^[affiliation_number(s)]</br>
Affiliation list: [affiliation_number]. [Institute/Department/University], [City/State] [Post/Zip Code], [Country]
