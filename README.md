# CertGen
 Certificate generator utility to personalise blank template.

This is a PWA utility which creates electronic certificates as follows:

a) 'Select template:' - A file picker to select an input PDF document. This will always be a single page A4 portrait document.

b) 'Select font:' 'Size:'- picker/drop list to choose from the system installed fonts & sizes.

c) 'Select offset:' x[nnn] y[nnn] - Specifies a position in the PDF in points (1/72").

d) 'Enter names:' - A means of entering a list of names, each as a single string, eg "John Smith".

e) A 'Generate' button which, when pressed, takes each name in turn and overlays it on the input certificate with the chosen font and size, horizontally and vertically centred about the selected X,Y position. It then saves a new certificate using the associated name, eg "John Smith.pdf", in the selected directory, or the Downloads folder, depending on permissions.

During generation there is an indication of progress, before a "Done - n certificates generated" message is displayed.

There is a service worker, sw.js:
This caches the core app files and the pdf-lib.min.js script from the CDN.
If the user is offline, the cached copy will be used.
If the app is updated later, just bump CACHE_NAME (eg v3) to force a refresh.

Open the webpage in Chrome (Android).
Add to Home Screen → CertGen installs like an app.
After the first load, it will run completely offline (including PDF generation).

Note, if changing the hard-coded default X,Y coordinates, they appear in 2 places, in the HTML and JS in gen_Btn:addEventListener().

