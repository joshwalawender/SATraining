# Starlists

Starlists are just text files containing the observers targets for the night.  The files are read by the OA's instance of MAGIQ and can be used to slew the telescope to the selected target and fill in other parameters as needed such as rotator position, non-sidereal tracking rates, offset star information (see [target acquisition](../target_acquisition/)), etc.

The files need to follow a specific format (see the [starlist page](https://www2.keck.hawaii.edu/realpublic/observing/starlist.html) for details).

If observers have manually created their starlist file or have used a starlist generator such as the one for MOSFIRE, they then need to move the file to a location where the OAs can find it easily.  Traditionally, this is in `/kroot/starlists/(observer or PI name)`, so each observer has a directory which they put their starlists in every time they use Keck.  The "(observer or PI name)" is a free form name which each individual chooses, so there is no set pattern to them though many follow the pattern of `[first initial][last name]` (e.g. `jwalawender`, `jlyke`).

## Web based starlist tool

The observer login page has a web based starlist tool where users can generate their starlists.  If done this way, there is no need to copy the file over manually as the tool will place it in `/kroot/starlists/web/(name)` where "(name)" is the first initial plus last name of the observer who uploaded it (e.g. for observer Jane Doe, the directory will be `/kroot/starlists/web/jdoe`). 
