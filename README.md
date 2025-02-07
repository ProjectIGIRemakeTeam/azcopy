# Azure File Upload UI Tool

This tool allows users to upload files to Azure Storage from a Windows environment using the `azcopy.exe` command-line tool.

![AzCopy Tool](https://github.com/ProjectIGIRemakeTeam/azcopy/blob/main/azcopy.png)


## Features
- **Drag and Drop / Open Folder**: Allows users to easily select a folder.
- **Enter SAS Token URL**: Enter a Shared Access Signature (SAS) token URL with the appropriate read/write permissions.
- **Upload**: Upload files/folders to Azure Storage via `azcopy.exe`.
- **Clone Windows**: Create a snapshot of your Windows as .vhd or .vhdx via `disk2vhd.exe`.

## RELEASE v1.0
https://github.com/ProjectIGIRemakeTeam/azcopy/releases/tag/azcopy

## Requirements
- **azcopy.exe**: The tool requires `azcopy.exe`, which is included in the provided package.  
  - If you don't have it, you can download it from the [Microsoft Azure website](https://learn.microsoft.com/en-us/azure/storage/common/storage-use-azcopy-v10).
- **Windows Operating System**

## Instructions

1. **Drag and Drop / Open Folder**  
   - Drag a folder or use the "Open Folder" button to select the folder you want to upload.

2. **Enter SAS Token URL**  
   - Obtain your SAS Token URL from Azure Portal. The URL should look like:  
     `https://your_storage_account.blob.core.windows.net/your_container?your_SAS_token_here`
   - Ensure that you grant the necessary read/write permissions for your SAS token.

3. **Click Upload**  
   - Once you have selected the folder and entered the SAS Token URL, click the "Upload" button to start the upload process.

4. **Clone Windows**  
   - Once you created the .vhd or .vhdx format, just repeat the steps above to upload snapshot.


## How it Works

When you click "Upload", the tool opens `cmd.exe` and executes the following command:

```bash
azcopy.exe copy "your_folder_path" "SAS_TOKEN_URL" --recursive=true
