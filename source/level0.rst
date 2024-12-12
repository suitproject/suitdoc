Level 0 Processing
=================

Level-0 data is available to download from ISRO's data center, ISSDC. SUIT-POC pings the ISSDC server every 10 minutes and checks for new data dumps.
The data is bundled as tar balls of one hour. Each tar ball should come with a trg file, which contains the checksum and file size of the tar ball.
The ``checkDownload.sh`` script does a file size matching and then does the download. If both files are not present, then they are added to a waiting queue.
Whenever both the files are available, the download is triggered.


Binary To FITS conversion
-------------------------
When the download of a tar ball is completed, ``extract.sh`` file will trigger the unzip process and push to the ``binary.queue``.
Each tar ball is includes image and header file for each image for a duration of roughly one hour.

Adding Headers
-------------

Auxillary file Processing
----------------
