# Maintainer: archtux <antonio.arias99999 at gmail.com>

pkgname=deadbeef-plugin-jack
pkgver=20111126
pkgrel=1
pkgdesc="JACK output plugin for DeaDBeeF."
url="http://gitorious.org/deadbeef-sm-plugins/jack"
arch=('i686' 'x86_64')
license='MIT'
depends=('deadbeef' 'jack2')
makedepends=('git')

 
_gitname=jack
_gitroot=git://gitorious.org/deadbeef-sm-plugins/jack.git
 
build() {
  cd $srcdir
  msg "Connecting to GIT server...."
  rm  -rf $srcdir/$_gitname-build
 
  if [ -d $_gitname ]; then
   cd $_gitname
   git pull
    else
   git clone $_gitroot
     fi

  msg "GIT checkout done or server timeout"
  msg "Starting make..."
 
  cd $srcdir/${_gitname}
  
  make
  install -Dm644 jack.so $pkgdir/usr/lib/deadbeef/jack.so
}