
    Verify the following are installed:
        PHP 4.3+
        GD Image Processing Library
            This library is usually installed by default.
            If you plan on disabling image uploads to use TinyIB as a text board only, this library is not required.
    CD to the directory you wish to install TinyIB.
    Run the command:
        git clone git://github.com/tslocum/TinyIB.git ./
    Copy settings.default.php to settings.php
    Configure settings.php
        To allow WebM upload:
            Ensure your web host is running Linux.
            Install mediainfo and ffmpegthumbnailer. On Ubuntu, run sudo apt-get install mediainfo ffmpegthumbnailer.
        To require moderation before displaying posts:
            Ensure your TINYIB_DBMODE is set to mysql, mysqli, or pdo.
            Set TINYIB_REQMOD to files to require moderation for posts with files attached.
            Set TINYIB_REQMOD to all to require moderation for all posts.
            Moderate posts by visiting the management panel.
        When setting TINYIB_DBMODE to pdo, note that PDO mode has been tested on MySQL databases only. Theoretically it will work with any applicable driver, but this is not guaranteed. If you use an alternative driver, please report back regarding how it works.
        To use ImageMagick instead of GD when creating thumbnails:
            Install ImageMagick and ensure that the convert command is available.
            Set TINYIB_THUMBNAIL to imagemagick.
            Note: GIF files will have animated thumbnails, which will often have large file sizes.
        To remove the play icon from .SWF and .WebM thumbnails, delete or rename video_overlay.png
    CHMOD write permissions to these directories:
        ./ (the directory containing TinyIB)
        ./src/
        ./thumb/
        ./res/
        ./inc/flatfile/ (only if you use the flatfile database mode)
    Navigate your browser to imgboard.php and the following will take place:
        The database structure will be created.
        Directories will be verified to be writable.
        The file index.html will be created containing the new image board.
