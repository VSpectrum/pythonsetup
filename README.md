# pythonsetup
How I went about creating my python 2.7.11 virtualenv on debian/ubuntu/linux mint

1. Get a set of dependencies!:

sudo apt-get install -y \
autotools-dev      \
blt-dev            \
build-essential    \
bzip2              \
dpkg-dev           \
g++-multilib       \
gcc-multilib       \
libbluetooth-dev   \
libbz2-dev         \
libexpat1-dev      \
libffi-dev         \
libffi6            \
libffi6-dbg        \
libgdbm-dev        \
libgpm2            \
libjpeg62-dev      \
libncursesw5-dev   \
libreadline-dev    \
libreadline-gplv2-dev  \
libsqlite3-dev     \
libssl-dev         \
libtinfo-dev       \
libxml2-dev        \
libxslt-dev        \
mime-support       \
net-tools          \
netbase            \
python-crypto      \
python-dev         \
python-imaging     \
python-mox3        \
python-pil         \
python-ply         \
python-setuptools  \
quilt              \
tk-dev             \
zlib1g-dev



2. Make some folders for organization. Get Python 2.7.11 sources zip. Unpack in a directory and start building it:

mkdir ~/python-src
mkdir ~/.localpython
cd ~/python-src

wget https://www.python.org/ftp/python/2.7.11/Python-2.7.11.tgz
tar -zxvf Python-2.7.11.tar.gz
cd Python-2.7.11

make clean
./configure --prefix=/home/<username>/.localpython
make
make install



3. Get virtualenv and unpack and install it for the newly installed version of python:

cd ~python-src
wget https://pypi.python.org/packages/source/v/virtualenv/virtualenv-15.0.0.tar.gz#md5=d9652f8d154546926939066e596af83c
tar -zxvf virtualenv-1.5.2.tar.gz
cd virtualenv-15.0.0/
~/.localpython/bin/python setup.py install



4. Make some virtualenvs!:

~/.localpython/bin/virtualenv nameofenv --python=/home/<user>/.localpython/bin/python2.7
~/.localpython/bin/virtualenv py2.7.11 --python=/home/<user>/.localpython/bin/python2.7
~/.localpython/bin/virtualenv godmode --python=/home/<user>/.localpython/bin/python2.7



5. Finale:
source ~/godmode/bin/activate
