# sc1-data-format
Format for the byte arrays sent from firmware to software within the solar car and from the solar car to the engineering dashboard. The format also contains additional information about each piece of data that is collected from the solar car, as detailed below.

## Format
The following information is listed within the format for each piece of data being collected from the solar car:
* <b>Name</b> - A name to identify each piece of data.
* <b>Number of bytes</b> - The number of bytes that each piece of data takes up within the byte arrays mentioned above. This value depends on the data type (see next point).
* <b>Data type</b> - The data type that each piece of data should be interpreted as. This is used for consistency when constructing and unpacking the byte arrays.
* <b>Units</b> - The units of each piece of data, if applicable (empty string if not applicable).
* <b>Nominal minimum</b> - The nominal minimum value for each piece of data, expressed as a number and assumed to be in the same units as previously listed. The value of a given piece of data should not fall below this value during normal operation.
  * The default value, when the nominal minimum value for a piece of data is not yet known, is 0.
* <b>Nominal maximum</b> - The nominal maximum value for each piece of data, expressed as a number and assumed to be in the same units as previously listed. The value of a given piece of data should not exceed this value during normal operation.
  * The default value, when the nominal maximum value for a piece of data is not yet known, is 100.
* <b>Category/Subsystem</b> - Indicates the category or electrical subsystem that each piece of data belongs to. This value is currently only used for categorizing data when selecting what will be shown in the graphs in the engineering dashboard.
  * Ideally, each piece of data would belong to a specific electrical subsystem. However, sometimes it makes more sense to categorize certain pieces of data, like data from sensors that aren't necessarily collecting data about a specific subsystem, differently.

For each piece of data, the information described above will be listed as follows:

&emsp;"name": [\<<i>number of bytes</i>\>, "data_type", "units", \<<i>nominal minimum</i>\>, \<<i>nominal maximum</i>\>, "Category/Subsystem"]
