# Changelog

Each beta's section lists what changed since the beta before it; a cycle's first beta
lists everything since the latest stable release. What has shipped stable is tracked in
the [main repo's changelog](https://github.com/jpweytjens/barberfish/blob/master/CHANGELOG.md).

## 4.0.0-beta3

Grade colors:
- The Barberfish palette, the default, now colors descents: three teal-to-slate bands at -2, -6 and -10, mirroring the climb side
- Its flat band is now a green-grey that stands apart from the map, instead of a light grey that read as a road edge
- The new colors apply everywhere grades are colored: the Grade field, the HUD grade column, the elevation profile, and the grade map

Emphasis:
- The band count pickers are replaced by handles on a to-scale palette bar: each handle is the grade where color starts, climbs and descents set separately, the end of the bar is off
- The Grade Map card carries the same bar, showing the profile's handles when Tuning is Sync and its own climb handle when Independent

Grade map (beta):
- Descents and flat road are now painted along with the climbs, chevrons included, each in its own band color
- Simplification follows the zoom: the line coarsens as you zoom out and the detail returns as you zoom in
- The card's preview now shows an up-and-over pass

Config screen:
- The Global section is split into Palettes and Time, and the sections are reordered

Fixes:
- Dead-flat road at exactly 0% is colored again when Emphasis is off, instead of leaving black gaps in the profile and grey ones on the map

## 4.0.0-beta2

Grade map (beta):
- The Map Overlay card is now called Grade Map, and the Climbing section describes it that way. The rename starts the card from its defaults again, so set it up once more if you changed it in beta1
- Chevrons follow the map's own rhythm: they are spaced along the whole route instead of restarting inside each climb, they slide off a bend rather than vanishing on it, and they stay pinned to the road while you pinch, so the overlay no longer rearranges itself at every zoom step
- Chevrons no longer blink on a rebuild. Only the ones that actually changed are redrawn, instead of hiding all of them and showing them again
- Standing still no longer rebuilds the chevrons, where GPS jitter used to be enough to trigger it

Grade:
- The HUD grade column has the same whole number, one decimal and % sign choices as the Grade field, set on the column itself

Fixes:
- A route ridden in reverse now draws the grade map's climb colors and chevrons, and shows saved POIs on the elevation profile, where you meet them rather than mirrored to the far end of the route
- The position dot on the elevation profile and on Overview no longer sits half outside the field at the very start and end of a route

## 4.0.0-beta1

New data fields:
- Distance, the ride odometer
- Distance Remaining to the destination
- Ascent Remaining, the climbing left to the destination
- Descent Remaining to the destination
- Ride Remaining, the distance and climbing left stacked in one field
- Overview, a plain elevation profile of the whole route with a dot for where you are
- Distance and the remaining fields also selectable as HUD slots
- The standalone elevation sparkline is now called Profile

Data Field Design:
- Barberfish fields now match Karoo's Data Icons and Label Size settings. Karoo doesn't share those choices with extensions, so mirror them once in the new Data Field Design config section.

Config previews:
- Field previews now play one simulated ride: power, heart rate, cadence, and grade rise and fall together, elapsed time is moving plus paused, and dawn and dusk track sunrise and sunset
- Similar fields preview different values: average speed Total reads below Moving, last lap trails the current lap

Colors:
- Threshold text colors now adjust per theme like the zone palettes: red and green read clearly at night, the range warning orange in daylight
- A one-sided min or max range in text mode no longer fades from white in light mode, where it was invisible

New defaults, saved settings stay as they are:
- Speed starts at instant rather than 3s smoothing
- Power Zone and HR Zone start with one decimal

Map overlay (beta):
- While navigating a route, climbs are drawn over the route line in the same grade colors as the elevation profile, with chevrons along the way
- The new Map Overlay card under Climbing toggles the overlay, the colored lines, and the chevrons
- Beta means less riding than the rest of 4.0; if the map misbehaves, turn it off and report what you saw

Grade:
- Shows a whole number or one decimal, with or without the % sign

Profile and Overview:
- Hide the header to give the elevation trace the whole cell

Placeholders and icons:
- The generic Not available is gone; fields now say why data is missing, like the native ones: No sensor for an unpaired sensor, No route and Off route on route fields, Needs 30s power data on NP
- Time field icons stay plain until the ride starts, then turn green, matching the native Ride Time field
- The green icon tint now uses Karoo's darker shade in light mode

Fixes:
- Global POIs now show on the elevation profile, not just the POIs that are part of the route. Thanks to Theolean for the report.
- The Profile field no longer goes blank when the HUD sparkline is set to Climbs or Off. Thanks to Jamie Bishop for the report.
- POI dots on the elevation profile are now solid instead of slightly see-through
- Grade in fill mode keeps its color while holding the last value, instead of dropping to grey text
- The held-grey grade reading is now readable in light mode, not only dark
- Searching and other placeholder text now sits at the same height as in the native fields, instead of slightly low
