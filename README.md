
# Webtrees Custom Module: ⚶ Shared Places

This [webtrees](https://www.webtrees.net/) custom module supports shared places as level 0 GEDCOM objects, on the basis of the Gedcom 5.5EL extension. It hooks into an extended 'Facts and Events' tab, enhancing places with data obtained from the respective shared place.
The project’s website is [cissee.de](https://cissee.de).

## Contents

* [Features](#features)
* [Gedcom 5.5EL](#gedcom)
* [Download](#download)
* [Installation](#installation)
* [License](#license)

### Features<a name="features"/>

* Shared places are handled as level 0 _LOC records, containing coordinates, notes, and media objects.
* Shared places may be edited and viewed via an additional top-level menu.
* On the (extended) facts and events tab, shared place data is displayed in addition to regular place data.
* All shared place data is fully included in the gedcom exported by webtrees (and may also be imported from other sources supporting _LOC records), on the basis of the Gedcom 5.5EL extension.
* Geodata is provided to other modules (e.g. for use in maps).

![SharedPlaces2](SharedPlaces2.png)

### Gedcom 5.5EL<a name="gedcom"/>

The Gedcom 5.5EL extension is described [here](http://wiki-en.genealogy.net/Gedcom_5.5EL). For _LOC records, we additionally allow fields from [this specification](http://wiki-en.genealogy.net/GEDCOM/PLAC-Tag#Agreements_for_PLAC), thus we end up with the following structure:

~~~~
0 @<XREF:_LOC>@ _LOC
1 NAME <PLACE_NAME> {1:M}
2 DATE <DATE_VALUE> {0:1}
2 _NAMC <PLACE_NAME_ADDITION> {0:1}
2 ABBR <ABBREVIATION_OF_NAME> {0:M}
3 TYPE <TYPE_OF_ABBREVIATION> {0:1}
2 LANG <LANGUAGE_ID> {0:1}
2 <<SOURCE_CITATION>> {0:M}
1 TYPE <TYPE_OF_LOCATION> {0:M}
2 DATE <DATE_VALUE> {0:1}
2 <<SOURCE_CITATION>> {0:M}
1 _FPOST <FOKO_POSTCODE> {0:M}
2 DATE <DATE_VALUE> {0:1}
1 _POST <POSTAL_CODE> {0:M}
2 DATE <DATE_VALUE> {0:1}
2 <<SOURCE_CITATION>> {0:M}
1 _GOV <GOV_IDENTIFIER> {0:1}
1 _FSTAE <FOKO_TERRITORY_IDENTIFIER> {0:1}
1 _FCTRY <FOKO_STATE_IDENTIFIER> {0:1}
1 MAP {0:1}
2 LATI <PLACE_LATITUDE> {1:1}
2 LONG <PLACE_LONGITUDE> {1:1}
1 _MAIDENHEAD <MAIDENHEAD_LOCATOR> {0:1}
1 EVEN [<EVENT_DESCRIPTOR>|<NULL>] {0:M}
2 <<EVENT_DETAIL>> {0:1}
1 _LOC @<XREF:_LOC>@ 0:M
2 TYPE <HIERARCHICAL_RELATIONSHIP> {1:1}
2 DATE <DATE_VALUE> {0:1}
2 <<SOURCE_CITATION>> {0:M}
1 _DMGD <DEMOGRAPHICAL_DATA> {0:M}
2 DATE <DATE_VALUE> {0:1}
2 <<SOURCE_CITATION>> {0:M}
2 TYPE <TYPE_OF_DEMOGRAPICAL_DATA> 1:1
1 _AIDN <ADMINISTRATIVE_IDENTIFIER> {0:M}
2 DATE <DATE_VALUE> {0:1}
2 <<SOURCE_CITATION>> {0:M}
2 TYPE <TYPE_OF_ADMINISTRATIVE_IDENTIFIER> {1:1}
1 <<MULTIMEDIA_LINK>> {0:M}
1 <<NOTE_STRUCTURE>> {0:M}
1 <<SOURCE_CITATION>> {0:M}
1 <<CHANGE_DATE>> {0:1}
~~~~

Note that currently only selected parts of this structure are displayed and supported by the editor.

### Download<a name="download"/>

* Current version: 1.7.9.6
* Based on and tested with webtrees 1.7.9, may also work with older 1.7.x versions.
* Requires the Hooks module ('hooks_repackaged', or the original Hooks module via webtrees-geneajaubart). Requires the 'personal_facts_with_hooks' module.
* Download the zipped module, including all required dependencies, [here](https://cissee.de/vesta.latest.zip).
* Support, suggestions, feature requests: <ric@richard-cissee.de>
* Issues also via <https://github.com/ric2016/shared_places/issues>

### Installation<a name="installation"/>

* Unzip the files and copy them to the modules_v3 folder of your webtrees installation. All required modules are included in the zip file. It's safe to overwrite the respective directories if they already exist (they are bundled with other custom modules as well), as long as other custom models using these dependencies are also upgraded to their respective latest versions.
* Enable the extended 'Facts and Events' module via Control Panel -> Modules -> Module Administration -> Facts and Events.
* Enable the main module via Control Panel -> Modules -> Module Administration -> Shared Places. After that, you may configure some options.
* Enable the Hooks module via Control Panel -> Modules -> Module Administration -> Hooks. Make sure all hooks are selected (in the preferences of the Hooks module).				
* Configure the visibility of the old and the extended 'Facts and Events' tab via Control Panel -> Modules -> Tabs (they both appear as 'Facts and Events' here - usually, you'll want to use only one of them. You may just disable the old 'Facts and Events' module altogether).

### License<a name="license"/>

* **shared_places: a webtrees custom module**
* Copyright (C) 2017 to 2018 Richard Cissée
* Derived from **webtrees** - Copyright (C) 2010 to 2016  webtrees development team.
* Derived from **webtrees-geneajaubart** - Copyright (C) 2009 to 2016  Jonathan Jaubart.

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <http://www.gnu.org/licenses/>.
