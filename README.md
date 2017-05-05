# vCowFS_G5

ทำการดาวน์โหลด meson

    $ git clone git://github.com/mesonbuild/meson.git
    
ทำการดาวน์โหลดและติดตั้ง python

    $ python get-pip.py 
    $ pip install requests
    
ทำการติดตั้ง meson

    $ python3 setup.py install
    $ pip3 install meson

ทำการดาวน์โหลดและติดตั้ง ninja 

    $ git clone git://github.com/ninja-build/ninja.git && cd ninja
    $ git checkout release
    $ cat README
    $ ./configure.py --bootstrap

ทำการดาวน์โหลด libfuse และสร้าง directory เพื่อ run meson จาก

    $ git clone git://github.com/libfuse/libfuse.git
    $ mkdir build
    $ cd build
    $ meson ..
    
ทำการ config ดังต่อไปนี้

    $ mesonconf # list options
    $ mesonconf  -D disable-mtab=true # set an option

ในการสร้าง, ทดสอบและติดตั้ง libfuse จะต้องใช้ ninja ดังนี้

    $ ninja
    $ sudo python3 -m pytest test/
    $ sudo ninja install

การรันเพื่่อทดสอบ py.test จะต้องใช้ Python module ดังนี้

    $ sudo chown root:root util/fusermount3
    $ sudo chmod 4755 util/fusermount3
    $ python3 -m pytest test/
