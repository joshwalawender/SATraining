# Focus

There are several different focus procedures at Keck.  Some are internal to the instrument and some are internal focus inside the instruments.  This page does not attempt to be comprehensive, only to give a flavor of the different strategies.

## Telescope Focus

Telescope focus (i.e. moving the piston of the secondary mirror to focus the telescope on to the instrument's image plane) is typically performed by to OA.  There are two standard ways of doing this.  First, using MIRA, which adjusts the tip and tilt of the individual primary mirror segments to separate the images from each segment.  If this is done with two tilts (in and out), then an extrapolation to the correct focus position can be calculated and the corresponding secondary piston adjustment sent.  In addition, the positions of the segment images can be used to adjust the tip and tilt of the secondary to zero out coma.

As a general rule of thumb, MIRA is typically done on the first night with any instrument after it has been put on the telescope.  This is done in order to set the secondary tilts.

After that, we may do focus using either autofoc (see below) or do more MIRA.  Some observers prefer MIRA for whatever reason, this is fine, but it does take a bit longer to do than autofoc.  In addition, some instruments should always do MIRA as the first choice.  MOSFIRE is one example because there is no slit viewing camera to do autofoc on.

## Autofoc

Autofoc is a process that can be run via MAGIQ using the guider cameras.  It does a more traditional method of finding focus in which it moves the secondary and measures image quality (FWHM).  It then fits a parabola to the values and determines the position of best focus.  Because this runs on a guider, it must be parfocalized to the instrument.  If the guider is a slit viewing camera, this is done (otherwise the slit itself would appear blurry in the guide image).  For guiders which are looking off axis (such as with MOSFIRE) this is not ensured at the same level, so an autofoc using those guiders is less desirable.

## Instrument Internal Focus

Several instruments (e.g. LRIS, ESI, KCWI) require an internal focusing process be done periodically.  In the case of LRIS, this is done every day.  The goal of these processes are to focus the internal optics on to the plane where the telescope will be focussed later during the night.  This is typically done by monitoring the width of spectral lines formed by an arc lamp and stepping through focus positions and choosing the best position by fitting a parabola to the resulting plot of FWHM vs. position.

For some instruments (notably LRIS) there may be multiple internal focal planes.  For LRIS, the long slit focal plane is slightly different than the MOS mask and imaging focal planes, so there are two different modes to perform the internal focus for.
