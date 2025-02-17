# FOREST ARMY - libcurl Installation Guide

## Description
This guide provides instructions on how to install and set up the `libcurl-impersonate-chrome.so.4` library on Termux for the Airdrop Projects.

## Installation & Setup

1. **Download the Library:**
   - Download the appropriate version of `libcurl-impersonate-chrome.so.4` for your system using `wget`:
     ```bash
     wget https://github.com/lwthiker/curl-impersonate/releases/download/v0.6.1/libcurl-impersonate-v0.6.1.aarch64-linux-gnu.tar.gz
     ```

2. **Extract the Files:**
   - Extract the `.tar.gz` file using:
     ```bash
     tar -xvzf libcurl-impersonate-v0.6.1.aarch64-linux-gnu.tar.gz
     ```

3. **Move the Library:**
   - Move the extracted `libcurl-impersonate-chrome.so.4` to the correct directory:
     ```bash
     mv libcurl-impersonate-chrome.so.4 /data/data/com.termux/files/usr/lib/
     ```

4. **Update Library Path:**
   - Set the `LD_LIBRARY_PATH` to include the directory where the library is located:
     ```bash
     export LD_LIBRARY_PATH=/data/data/com.termux/files/usr/lib:$LD_LIBRARY_PATH
     ```

5. **Preload the Library:**
   - Preload the library to ensure it's used by applications:
     ```bash
     export LD_PRELOAD=/data/data/com.termux/files/usr/lib/libcurl-impersonate-chrome.so.4
     ```

6. **Verify the Setup:**
   - Run the following to check if the library is linked correctly:
     ```bash
     ldd /data/data/com.termux/files/usr/lib/python3.12/site-packages/curl_cffi/_wrapper.abi3.so
     ```

## Troubleshooting
- Ensure that the `libcurl-impersonate-chrome.so.4` library is present in `/data/data/com.termux/files/usr/lib/`.
- If the library is not detected, verify that the `LD_LIBRARY_PATH` is set correctly.

## License
This installation guide is part of the Midas Project. The project is licensed under the MIT License.
