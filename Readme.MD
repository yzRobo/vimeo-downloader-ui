# Universal Video Downloader

A self-hosted, incredibly simple, and powerful web interface for downloading video and audio from YouTube, Vimeo, Twitter, and 1000+ other websites.

With its latest update, the application is now a **fully portable, double-click-to-run executable** for Windows. No installation or command-line knowledge required.

## What's New in Version 3.0

This is a complete overhaul focused on ease of use and portability:

*   **One-Click Start:** No more scripts or commands. Just double-click `UniversalVideoDownloader.exe` to run the application.
*   **Automatic Browser Launch:** Your default web browser will automatically open to the downloader interface seconds after you start the app.
*   **Smart & Robust:** The server automatically finds an open port if the default is in use and provides clear, user-friendly error messages.
*   **Cleaner Distribution:** The entire application is contained in a single folder. Just the `.exe`, a `bin` folder for its tools, and a `downloads` folder.
*   **Fully Portable:** Keep the folder on your desktop or a USB drive. As long as the `exe`, `bin`, and `downloads` folders are kept together, it just works.

## Key Features

*   **Multi-Platform Support:** Download from:
    *   **YouTube** - Videos, playlists, shorts
    *   **Vimeo** - Public and private/embedded videos
    *   **Twitter/X**, **Instagram**, **TikTok**, **Threads**, and more.
*   **User-Friendly Interface:**
    *   **Multi-URL Paste:** Paste a list of URLs, and the app creates input fields for you.
    *   **Private/Public Toggle:** Easily switch modes for public videos or domain-protected private videos.
    *   **Platform Indicators:** Instantly see which site each URL is from.
*   **Advanced Download Formats:** For each batch, choose to download:
    *   Video + Audio (Standard `.mp4`)
    *   Video Only (`.mp4` with a `_No_Audio` suffix)
    *   Audio Only as `.mp3` (Re-encoded for compatibility)
    *   Audio Only as `.m4a` (Copied directly for speed)
*   **Batch Organization:**
    *   Group downloads into sections that run one after another.
    *   Apply custom filename prefixes (e.g., `01.1_`, `01.2_`, then `02.1_`) for perfect course organization.
*   **Process Control & Real-Time Progress:**
    *   **Cancel Button:** Stop the entire download queue at any time.
    *   Live progress bars, download speed, file size, and detailed logs are displayed right in your browser.

## Getting Started (The Easy Way)

1.  Go to the [**Releases Page**](https://github.com/yzRobo/universal-video-downloader/releases).
2.  Under the latest release, download the `Universal-Video-Downloader-vX.X.X.zip` file.
3.  Unzip the folder to a location of your choice (e.g., your Desktop).
4.  Open the unzipped folder and double-click **`UniversalVideoDownloader.exe`**.

That's it! A console window will appear, and your default web browser will open to `http://localhost:3000` automatically.

### First Time Running

*   **Windows Security:** Windows Defender SmartScreen might show a warning because the app is not code-signed. This is normal. Click "**More info**" and then "**Run anyway**".
*   **Firewall:** Your firewall may ask for permission for the app to access the network. Click "**Allow access**". This is required for it to function as a local server.

### Important Notes
*   The console window that opens is the server. **To stop the application, simply close this window.**
*   Keep all files (`UniversalVideoDownloader.exe`, `bin/`, `downloads/`) in the same folder. Do not delete or move the `bin` folder, as it contains required tools.
*   All your downloaded files will be saved in the `downloads` folder.

## How to Use the Interface

1.  **Add Video URLs:**
    *   Paste any supported video URL into the input field. The platform will be automatically detected.
    *   To paste multiple URLs, copy a list (one per line) and paste it into a URL field. The app will create new rows for you.
2.  **Configure Download Options:**
    *   Choose your desired format (Video+Audio, Video Only, etc.).
    *   Set filename prefixes for organization.
3.  **Start Downloads:**
    *   Click "Start All Downloads".
    *   Monitor progress with real-time stats and cancel anytime if needed.

### Advanced: Downloading Private/Embedded Videos

Some videos (especially from Vimeo) are embedded on private sites.
1.  In the relevant section, toggle the download type to **"Private"**.
2.  Enter the website URL where the video is embedded (e.g., `https://courses.example.com`). This tells the downloader where to "pretend" it's coming from.

## For Developers: Building from Source

If you want to modify the code and build the executable yourself:

1.  **Prerequisites:** You must have [Node.js](https://nodejs.org/) (v18 or later) installed.
2.  **Clone the Repository:**
    ```bash
    git clone https://github.com/yzRobo/universal-video-downloader.git
    cd universal-video-downloader
    ```
3.  **Install Dependencies:** This will also download `yt-dlp` and `ffmpeg` into the `bin` directory.
    ```bash
    npm install
    ```
4.  **Run in Development Mode:**
    ```bash
    npm start
    ```
5.  **Build the Executable:** This will create a `dist` folder containing the portable application.
    ```bash
    npm run build
    ```

## Troubleshooting

*   **Application closes immediately:** Make sure the `bin` folder with `yt-dlp.exe` and `ffmpeg.exe` is in the same directory as `UniversalVideoDownloader.exe`. If they are missing, try running `npm install` (if you're a developer) or re-downloading the release ZIP.
*   **Antivirus/Firewall issues:** If the app is blocked, try temporarily disabling your antivirus or adding an exception for `UniversalVideoDownloader.exe` and the `bin` folder.
*   **Downloads fail:** Check that the URL is correct. For private videos, ensure you are using "Private" mode with the correct referer domain.
*   **"Could not find an available port":** The app tries to use port 3000 and up. If this error occurs, another application is using all the ports it's trying. Close other development servers or applications and try again.

## Supported Sites

This tool supports over 1,000 websites via `yt-dlp`. For a complete list, visit the [yt-dlp supported sites page](https://github.com/yt-dlp/yt-dlp/blob/master/supportedsites.md).

## License

This project is licensed under the MIT License.
