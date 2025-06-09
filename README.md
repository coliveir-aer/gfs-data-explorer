# **GFS Data Explorer**

A simple, single-page web application to discover, filter, and download Global Forecast System (GFS) data from the NOAA Big Data Program archive on AWS S3. This tool is designed to provide an intuitive interface for accessing GFS GRIB2 files without needing to manually construct S3 paths or parse file listings.

## **Features**

* **Intuitive Filtering:** Filter GFS data by Date, Model Run Cycle (00Z, 06Z, 12Z, 18Z), Product Category (resolution and parameter sets), and specific Forecast Hours.  
* **Direct S3 Querying:** Constructs and executes direct queries against the public noaa-gfs-bdp-pds S3 bucket.  
* **Results Display:** Displays a clean, filterable list of matching GRIB2 files with their forecast hour, size, and full filename.  
* **Direct Downloads:** Select one or more files from the results list to download them directly from AWS S3 to your local machine.  
* **Transparent Path Generation:** Shows the generated S3 path used for the query, which is useful for debugging or for use in other scripts and tools.

## **How to Use**

This project is a self-contained index.html file with no external dependencies beyond Tailwind CSS and Google Fonts, which are loaded via a CDN.

1. Download: Download the index.html file from this repository.  
2. Open: Open the index.html file in any modern web browser (e.g., Chrome, Firefox, Safari, Edge).  
3. Query:  
   * Select your desired Date, Cycle, Product Category, and Forecast Hour(s).  
   * Click the "Query GFS Data" button.  
4. Download:  
   * Once the results appear, use the checkboxes to select the files you need.  
   * Click the "Download Selected" button.

## **Technical Details**

* Frontend: Built with plain HTML, CSS, and JavaScript.  
* Styling: Uses [Tailwind CSS](https://tailwindcss.com/) for rapid UI development, loaded via CDN.  
* Fonts: Uses the [Inter](https://fonts.google.com/specimen/Inter) font family from Google Fonts.  
* Data Interaction: Interacts directly with the AWS S3 REST API (ListObjectsV2) to query for files. It includes a fallback mechanism using a CORS proxy (api.allorigins.win) to ensure functionality in more restrictive browser environments.

## **Data Source**

This tool accesses data from the NOAA Global Forecast System (GFS) on the AWS Open Data Registry.

* Data Registry Link: [https://registry.opendata.aws/noaa-gfs-bdp-pds/](https://registry.opendata.aws/noaa-gfs-bdp-pds/)  
* Data Citation: When using data retrieved with this tool, please cite the source appropriately: *NOAA Global Forecast System (GFS) was accessed from the AWS Open Data Registry.*

## **Contributing**

Contributions, issues, and feature requests are welcome\! Feel free to check the [issues page](https://github.com/coliveir-aer/gfs-data-explorer/issues) to see if you can help out.
