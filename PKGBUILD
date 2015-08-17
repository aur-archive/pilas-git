# Maintainer: Diego Mascialino <diego@gcoop.coop>
# Contributor: Nicolas Echániz <nicoechaniz@altermundi.net> 

pkgname=pilas-git
pkgver=20130701
pkgrel=1
pkgdesc="Un motor para hacer videojuegos de manera sencilla en Python.  An engine to make games in an easy way with Python."
arch=('any')
depends=('python2' 'setuptools' 'pybox2d-svn' 'python2-pyqt')
makedepends=('mercurial')
conflicts=('pilas-hg')
license=('LGPL')
url="http://www.pilas-engine.com.ar"

build() {
    cd ${srcdir}
    if [ -d pilas/.git ]; then
        (cd pilas && git pull)
    else
        git clone git://github.com/hugoruscitti/pilas.git
    fi

    cd pilas
    git submodule update --init
    python2 setup.py build
}

package() {
    cd ${srcdir}
    cd pilas
    python2 setup.py install --root="$pkgdir"
}

md5sums=()
