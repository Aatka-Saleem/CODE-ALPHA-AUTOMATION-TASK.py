File Organizer Script

This script organizes files in a given directory by moving them into separate folders based on their file extensions.

How it works

1. The script prompts the user to enter a directory path.
2. It lists all files in the specified directory using os.listdir().
3. For each file, it extracts the file name and extension using os.path.splitext().
4. It checks if a folder with the same name as the file extension already exists in the directory.
5. If the folder exists, it moves the file into that folder using shutil.move().
6. If the folder does not exist, it creates a new folder with the same name as the file extension using os.makedirs() and then moves the file into that folder.

Code Explanation

- path = input("Enter path: "): Prompts the user to enter a directory path.
- files = os.listdir(path): Lists all files in the specified directory.
- for file in files: Loops through each file in the list.
- filename, extension = os.path.splitext(file): Extracts the file name and extension using os.path.splitext().
- extension = extension[1:]: Removes the dot (.) from the extension string.
- if os.path.exists(path + '/' + extension): Checks if a folder with the same name as the file extension already exists in the directory.
- shutil.move(path + '/' + file, path + '/' + extension + '/' + file): Moves the file into the existing folder.
- else: os.makedirs(path + '/' + extension): Creates a new folder with the same name as the file extension if it does not exist.
- shutil.move(path + '/' + file, path + '/' + extension + '/' + file): Moves the file into the newly created folder.
