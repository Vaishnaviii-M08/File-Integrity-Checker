
# File Integrity Checker

A Python script to monitor the integrity of files in a specified directory using SHA-256 hashes. The script scans the directory, calculates the hash values of files, and compares them with previously saved hashes to detect changes such as file creation, modification, and deletion.

## Features
- **File Hashing**: Uses SHA-256 to calculate the hash of each file.
- **File Monitoring**: Monitors a directory for file changes (creation, modification, deletion).
- **Integrity Checking**: Compares current file hashes with previously stored ones to detect file changes.
- **JSON Storage**: Saves and loads file hashes in a JSON file to track file integrity across script runs.

## Requirements
- Python 3.x
- `os` and `hashlib` modules (These are standard Python libraries and should come pre-installed.)

## Installation
1. Clone this repository:
    ```bash
    git clone https://github.com/Vaishnaviii-M08/file-integrity-checker.git
    cd file-integrity-checker
    ```

2. Ensure that you have Python 3.x installed on your system. If not, download and install Python from [python.org](https://www.python.org/downloads/).

## Usage
1. Run the script:
    ```bash
    python file_integrity_checker.py
    ```

2. The script will prompt you to input the directory to monitor. You can also specify the file name for storing the hashes (default is `file_hashes.json`).

3. The script will continuously monitor the directory for file changes (created, modified, or deleted) at regular intervals (default is 10 seconds). The detected changes will be printed to the console, and the hash file will be updated.

### Example Output:
When you run the script, you might see output like this:
```
Created files:
  - ./my_files/new_file.txt

Modified files:
  - ./my_files/changed_file.txt

Deleted files:
  - ./my_files/old_file.txt
```

If no changes are detected:
```
No changes detected.
```

## How It Works
- The script first calculates the SHA-256 hash of all files in the monitored directory and saves the hashes to a JSON file (`file_hashes.json`).
- On subsequent runs, it recalculates the hashes and compares them with the saved hashes:
  - If a new file is created, it is detected as a "created" file.
  - If a file's hash differs from the saved one, it is marked as "modified."
  - If a file no longer exists in the directory, it is detected as a "deleted" file.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```
