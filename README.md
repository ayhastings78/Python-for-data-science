Annotation Analysis and Organization Script

This script analyzes and organizes satellite annotation files stored in a specified directory. It validates the file naming convention, performs statistical analysis, and creates a structured folder hierarchy for easy access.

Features

	1.	Analyze Annotations:
	•	Counts total and valid files based on the naming convention.
	•	Groups annotations by date, month, and year.
	•	Identifies the busiest month (most annotations).
	•	Sorts annotation files from the most recent to the oldest.
	•	Provides statistics for:
	•	Unique satellites and their usage counts.
	•	Unique regions covered.
	2.	Organize Files by Month:
	•	Automatically creates subfolders for each month (YYYYMM format).
	•	Moves annotation files into the respective subfolders.

	The script assumes the annotation files follow this naming convention:
	{DATE}_{TIME}_SN{SATELLITE_NUMBER}_QUICKVIEW_VISUAL_{VERSION}_{UNIQUE_REGION}.txt

	ie : 20240102_185527_SN27_QUICKVIEW_VISUAL_1_1_10_SATL-2KM-11N_740_3850.txt

	DATE: YYYYMMDD format (e.g., 20240102).
	•	TIME: HHMMSS format (e.g., 185527).
	•	SATELLITE_NUMBER: Integer ID of the satellite (e.g., 27).
	•	VERSION: Pipeline version (e.g., 1_1_10).
	•	UNIQUE_REGION: A string describing the region (e.g., SATL-2KM-11N_740_3850).

	Requirements

	•	Python 3.7 or higher
	•	Libraries:
	•	os
	•	re
	•	collections

	sage

	1.	Set Up the Folder Path:
Update the folder_path variable in the script to the directory containing your annotation files.
folder_path = "/path/to/your/annotations"

	2.	Run the Script:
Execute the Python script to analyze and organize the annotation files.
	3.	Output:
The script provides:
	•	A summary of analysis results in the console.
	•	A reorganized folder structure with subfolders for each month.

	Output Example

Analysis Results:
{
  "total_files": 206,
  "valid_files": 194,
  "annotations_by_month": {
    "202401": 27,
    "202402": 45,
    "202403": 17,
    "202404": 25,
    "202405": 28,
    "202406": 52
  },
  "busiest_month": ["202406", 52],
  "sorted_files": [
    "20240623_193704_SN27_QUICKVIEW_VISUAL_1_7_0_SATL-2KM-11N_566_3734.txt",
    "20240623_215120_SN29_QUICKVIEW_VISUAL_1_7_0_SATL-2KM-10N_596_4134.txt"
  ],
  "unique_satellites": 9,
  "annotations_per_satellite": {
    "27": 29,
    "24": 26,
    "26": 37
  },
  "most_recent_satellite": 27,
  "unique_regions": 87
}

Organized Folder Structure:
annotations/
├── 202401/
│   ├── 20240102_185527_SN27_QUICKVIEW_VISUAL_1_1_10_SATL-2KM-11N_740_3850.txt
│   └── ...
├── 202402/
│   ├── ...
├── 202403/
│   ├── ...

Customization

	•	Update the file_name_pattern to modify the naming convention.
	•	Modify the folder organization logic as per your needs.

	Troubleshooting

	•	Incomplete Input Errors: Ensure there are no syntax errors (missing brackets, incorrect indentation).
	•	Folder Not Found: Verify that the folder_path exists and is accessible.
	•	Invalid Files: Check that the files in the directory match the expected naming convention.