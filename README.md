# Demo: Tabletop or flat file to Datatables Table

## About
Use either [Tabletop.js](http://builtbybalance.com/Tabletop/) and a Google Spreadsheet to feed data to the [DataTables](http://datatables.net/) jQuery plugin, or use a flat JSON file. Some additional configuration options are available.

This is an enhanced version of 	a demo by [Chris Essig](https://twitter.com/CourierEssig) &amp; [Chris Keller](https://twitter.com/ChrisLKeller) made possible thanks to the Open Source work of [Built By Balance](http://builtbybalance.com) &amp; [Allan Jardine](https://github.com/DataTables).

* [Demo Page](http://projects.chrislkeller.com/demos/datafeed_to_datatables)
* [Repo](https://github.com/chrislkeller/datafeed_to_datatables)
* [ReadMe](https://github.com/chrislkeller/datafeed_to_datatables#readme)

## Setup

* Create a container to house the table.
		
		<div id="demo"></div>

* If planning to use a Google spreadsheet as the data source, follow the [Tabletop.js instructions](http://builtbybalance.com/Tabletop/#tabletop-instructions) for setting up the spreadsheet and publishing it.

* Add your spreadsheet ID as a value to the spreadsheetKey key in the defaultTableOptions.

	    // add if dataSource is tabletop
	    spreadsheetKey: '0An8W63YKWOsxdE1aSVBMV2RBaWphdWFqT3VQOU1xeHc',

* If planning to use a flat json file, I prefer to:
	* Set the file up in a Google Spreadsheet.
	* Expo the file as a csv.
	* Use this [csv to json Python script](https://gist.github.com/chrislkeller/4700210#file-csv-to-json-py) to set up the file format.

* Setup the columns you wish to display in the table by editing/adding strings to the the defaultTableOptions columnHeaders array. This will set the value for both the mDataProp and sTitle.

		columnHeaders: ['Day', 'Time', 'Place'],

## Options

The following configuration options are available:

* ```dataSource```:  Specifies source of data for the table, either **'tabletop'** or **'flatfile'**.
  * Data type: string
  * Default value: ```tabletop```

* ```spreadsheetKey```:  Add the key from your Google spreadsheet if the dataSource is set to tabletop.
  * Data type: string
  * Default value: ```0An8W63YKWOsxdE1aSVBMV2RBaWphdWFqT3VQOU1xeHc```

* ```jsonFile```:  Add the path to a flat json file if the dataSource is set to flatfile.
  * Data type: string
  * Default value: ```static-files/data/nicar_sessions_sked.json```
  * Flat file format used for this demo:

		{"objects": [{"description": "", "title": "Breaking local stories with economic data (Sponsored by Donald W. Reynolds National Center for Business Journalism)", "place": "Regency North", "time": "2 p.m. - 5 p.m.", "speaker": "Paul Overberg, Jeannine Aversa, Thomas Dail", "day": "Wednesday"}]}

* ```tableElementContainer```:  The div id in which the table will be displayed.
  * Data type: string
  * Default value: ```#demo```

* ```tableType```:  The type of table to render, either **'standard'** or **'drilldown'**. Drilldown adds [drill-down rows](http://www.datatables.net/blog/Drill-down_rows) that contain more information.
  * Data type: string
  * Default value: ```drilldown```

* ```columnHeaders```:  Table headers you want to appear from the the spreadsheet or data file.
  * Data type: array
  * Default value: ```columnHeaders: ['Day', 'Time', 'Place']```

* ```tableSorting```:  The table sorting method, The first value is the zero-indexed column to sort on. The second value can be 'asc' or 'desc'.
  * Data type: array
  * Default value: ```[[ 3, "asc" ]]```* ```displayLength```:  Seems as though it needs to at least be set to a minimum of 10 needed to alter the per page select menu.
  * Data type: integer
  * Default value: ```15```

## Links & Resources

* [Tabletop.js](http://builtbybalance.com/Tabletop/)
* [Data Tables](http://datatables.net/index)