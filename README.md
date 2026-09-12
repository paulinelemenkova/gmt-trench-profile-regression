# GMT Trend Regression KKT — Trench Profile Regression Modelling Scripts

GMT (Generic Mapping Tools) shell scripts for statistical trend modelling of bathymetric trench-profile data. Stacked cross-section depth profiles of the Kuril-Kamchatka Trench are fitted with a sequence of regression models by weighted least squares, comparing polynomial orders and mixed polynomial-plus-Fourier models, with residual diagnostics. The scripts have been used to generate figures in the author's marine-geomorphological publications.

## What the scripts do

- fit successive regression models to the stacked profile with trend1d: linear (y = a + b*x), quadratic (y = a + b*x + c*x^2), and mixed polynomial + Fourier (adding cosine/sine terms)
- plot each fitted model over the data (psxy)
- plot the residuals of the highest-order model as a diagnostic panel
- plot the median stacked profile with error bars and an envelope, annotated with tectonic features (Pacific Plate, trench, Kuril chain)
- label the model equations and add a subtitle describing the weighted-least-squares polynomial / Fourier fitting (pstext)
- add the GMT logo (logo) and clean up temporary files (rm)
- export to raster (psconvert) at high resolution

Separate scripts model the northern and southern trench segments.

## Data source

Stacked cross-section bathymetric profiles of the Kuril-Kamchatka Trench (see the companion cross-section profiling scripts), input as GMT table files (stack2.txt, env2.txt).

## Files

- GMT-24-script-trend-north.sh: regression models, northern segment
- GMT-24-script-trend-south.sh: regression models, southern segment
- GMT-trend.sh: base trend-fitting workflow

## Requirements

- GMT 6.x (Generic Mapping Tools): https://www.generic-mapping-tools.org
- A POSIX shell (bash)
- The stacked profile / envelope table(s) available locally

## Usage

Place the required profile tables in the working directory, then run:

    bash GMT-24-script-trend-north.sh

The script writes a PostScript file and converts it to a raster image (JPG/PNG) via psconvert.

## Author and citation

Polina Lemenkova
ORCID: https://orcid.org/0000-0002-5759-1089

These scripts support figures in the author's marine-geomorphological papers; please cite the specific article a given figure appears in. The full publication list is available via the ORCID record above.

## License

See the LICENSE file in this repository.
