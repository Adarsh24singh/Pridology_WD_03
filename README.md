# Pridology_WD_03


import zipfile
import os

# Paths to uploaded files
zip_paths = [
    "/mnt/data/bank.zip",
    "/mnt/data/bank-additional.zip"
]

# Extract both zip files
extracted_paths = []
for zip_path in zip_paths:
    with zipfile.ZipFile(zip_path, 'r') as zip_ref:
        extract_path = zip_path.replace('.zip', '')
        zip_ref.extractall(extract_path)
        extracted_paths.append(extract_path)

# List the extracted files
extracted_files = {}
for path in extracted_paths:
    extracted_files[path] = os.listdir(path)

extracted_files
