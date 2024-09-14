# install-imagick-on-live-server
Install Imagick extenssion manually on server if you don't have Sudo access

# Install Imagick extenssion manually on server if you don't have Sudo access


**1. Go to Terminal and run these commands each line have a seprate command.**

    cd ~
    wget https://download.imagemagick.org/ImageMagick/download/ImageMagick.tar.gz
    tar xvzf ImageMagick.tar.gz
    cd ImageMagick-*
    ./configure --prefix=$HOME/imagemagick
    make
    make install
    export PATH=$HOME/imagemagick/bin:$PATH

**2. After installing .user.ini is Supported, create a file with name .user.ini**

    nano /path/to/your/laravel/project/.user.ini

**3. Add the Extension to the .user.ini** 
(ImageMagick-7.1.1-38 folder name can be changed):

    extension=/home/yourusername/ImageMagick-7.1.1-38/lib/imagick.so

**4. Open or create the .htaccess file:**

    nano .htaccess

**5. Add the following lines in .htaccess file to load the imagick.so extension:**

    # Load Imagick extension
    SetEnv PHPRC /path/to/your/laravel/project/.user.ini

**6. Its Completed, Now Confirm and Verify, let's create a phpinfo.php File**

    nano /path/to/your/laravel/project/public/phpinfo.php

**7. Add the Following code**

    <?php phpinfo(); ?>

# Go ahead => Open to http://yourdomain.com/phpinfo.php and find Imagick extenssion is enable

