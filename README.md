# Digital-Investigation
A repository for the digital forensic analysis of network recordings, utilising tools such as HxD (hex editor), base64.  This experiment illustrates the process of extracting, decoding, and analysing files (including executables, documents, and images) from network traffic that has been captured using tools such as Wireshark.
<h1>Repository Structure</h1>
  <ul>
  <li>`captures/` - Raw network capture data (e.g., exported from Wireshark as .txt or .pcap).</li>
  <li>` analysis/` - Documentation and findings from the investigation.</li>
  <li>`images/` - Recovered files (e.g., images, documents) from the capture.</li>
  <li>`tools/` - Instructions for using base64 and other utilities.</li>
  </ul>
<h1>🛠 Tools Used</h1>
    <ul>
    <li>Wireshark: For capturing and exporting network traffic.</li>
    <li>HxD: For hex-level analysis and extraction of file data.</li>
    <li>base64: For decoding encoded data found in network streams.</li>
    </ul>
<h2>🚦 Investigation Workflow</h2>

## 1. Capture Network Traffic
   - Use Wireshark to capture network activity and export the relevant packets (e.g., HTTP file transfers).
<img src="">
   - Identify files, right click> follow> TCP stream,
<img src="">

   - Save the TCP stream or HTTP object as a `.txt` file in the `captures/` folder.

### 2. **Hex Analysis with HxD**
   - Open the exported data in HxD.
   - Identify file signatures (e.g., PNG: `89 50 4E 47`, JPG: `FF D8 FF`, PDF: `%PDF`, ZIP: `50 4B 03 04`).
<img src="">
<img src="">
<img src="">
<img src="">

   - Select from the file signature to the end of the file (e.g., PNG ends with `49 45 4E 44 AE 42 60 82`).
   - Copy and save as a new binary file (e.g., `extracted_BNS02.png` in the `images/` folder).

### 3. **Base64 Decoding (if needed)**
   - If you find base64-encoded data in the capture, copy it to a `.txt` file.
     - **Online:**  
       - Go to [https://www.base64decode.org/](https://www.base64decode.org/)
       - Paste the base64 string and download the decoded file.
