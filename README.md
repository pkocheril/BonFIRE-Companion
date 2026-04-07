# BonFIRE Companion App
Companion application for quick data visualization and spectrum generation. Continuously a work-in-progress. No guarantees of accuracy, completeness, or functionality.

Written in HTML.


## Highlights and main functions
* Fast and lightweight
* No installation required (runs in a web browser, even offline)
* Automated file matching (CH1, CH2, Tlist, and XYZT info files)
* Built-in visualization of time-delay profiles, with optional region-of-interest inspection and comparison plotting with "retaining"
* Automatic IR spectrum generation from an entire folder of data files


## Usage
Simply double-click the ```.html``` file and the app will launch in your default web browser.

### Data loading
To load data, either press the "+Load" button at the top left or drag and drop files into the box at the top left. For default BonFIRE, you should drag in all of the files for given measurement (CH1.raw, CH2.raw, Tlist.txt, and XYZT.txt). Loaded files can be cleared by pressing the "X" button, just to the right of the "+Load" button.

Upon loading, the CH2 image and time-delay profile should populate the middle panes of the app. The uploaded files are visible on the left side, appearing as a list of files with indicators marking which input file types (CH2, CH1, T, and XYZ) were correctly identified and grouped together. On the right side, various key parameters from the loaded file are shown for reference. The frequency can be manually overridden by typing in the "Frequency Override" box, if needed.

*To swap between different files, simply click on the file you want to visualize and that will be loaded into the middle panes.* The CH1 data can be visualized by clicking "CH1 - PMT" just below the file input box. Slightly below that, you can find a drop-down menu to decide how the files are sorted (by default, sorted by measurement time, recorded in the XYZT file).

### Data inspection
In the image view, the scrubber at the top left allows you to select the frame that you're visualizing. You can also draw a box on the image to select a region-of-interest (ROI) for further analysis.

In the time trace view, the drop-down options at the top-left allow you to choose between visualizing the profile across all pixels or only for a selected ROI. You can also change the x-axis to plot delay stage position or index, and change the y-axis to plot on log-scale.

To compare time traces, you can press the "Retain" button at the top right of that pane, then select a different ROI in your image and compare the two. Make sure you're using the ROI average instead of averaging all pixels to make this comparison. The live plot will update with the ROI, but the 'retained' plot stays put until you clear it ("Clear all").

### Sweep analysis
To analyze BonFIRE sweeps, you can drag an entire folder containing a series of BonFIRE measurement files (CH1.raw, CH2.raw, Tlist, and XYZT) into the "Drop files or folder" input window. Upon receiving a folder *(not currently working on Windows)*, the app should default to spectrum analysis, where the data are combined into a single graph of BonFIRE intensity vs IR frequency *(currently only IR frequency - other independent variables planned in the future!)*. Alternatively, you can drag and drop multiple files in, then switch to the "Spectrum" tab and press "Build from all datasets" to generate a spectrum from all loaded files.

If you select the "Files" tab on the left, you can see the individual files that comprise the spectrum and click on a file to view that individual image stack and time trace. You can then click on different files to switch between them.

If you select the "Spectrum" tab on the left, you'll then see the condensed list of frequencies and their calculated BonFIRE intensities (max minus min). At the bottom of the list, you'll see buttons to re-initialize the spectrum plot ("Plot") and toggle normalization by the IR power ("Norm IR"), as well as clearing out the loaded spectrum ("Clear").

Lastly, the "Mode" toggle at the top-right of the time trace pane allows you to switch between examining time traces and spectral profiles. You can then scrub through a series of BonFIRE images, using the scrubber at the top-left of the image pane. Ideally, this should retain the same functionality as the time trace ROI comparison, where spectra can be compared in different ROIs - however, there are multiple known bugs with this feature.

### Exporting
Export options are found at the bottom-right of the app. Generally, PNGs and CSVs are supported for the processed data. For the time traces, the "CSV" and "PNG" buttons at the top right of the pane also allow you to export the current plot directly.

There is a known bug with the "App PNG" export not properly capturing the side panes. If you want this information, a simple screenshot is likely more effective.

### A note on general utility
The [MATLAB-based BonFIRE Processing Code](https://github.com/pkocheril/BonFIRE-Processing-Code) is recommended for all final analyses. This app is meant as a companion to be used during experiments, where speed is prioritized over accuracy.

# How to cite
If you found any of these functions useful, please cite this code as:

1. PA Kocheril, RE Leighton, N Naji, D Lee, H Wang, J Du, and L Wei*. Towards accurate predictions of bond-selective fluorescence spectra. DOI: 10.48550/arXiv.2601.11902
