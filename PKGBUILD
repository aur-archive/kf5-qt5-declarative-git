# Contributor: Andrea Scarpino <andrea@archlinux.org>

pkgname=kf5-qt5-declarative-git
pkgver=v5.1.0.beta1.89.g7e73dc0
pkgrel=1
pkgdesc="A cross-platform application and UI framework (QtQml, QtQuick)"
arch=('i686' 'x86_64')
url="http://qt-project.org/"
license=('GPL3' 'LGPL')
depends=('kf5-qt5-jsbackend-git' 'kf5-qt5-xmlpatterns-git')
makedepends=('git')
provides=('kf5-qt5-declarative')
options=('!libtool')
source=(git://gitorious.org/qt/qtdeclarative.git)
md5sums=('SKIP')

pkgver() {
  cd qtdeclarative
  git describe --always | sed 's|-|.|g'
}

prepare() {
  cd qtdeclarative
  git checkout dev
}

build() {
  export QT_SELECT=kf5

  cd qtdeclarative
  qtchooser -run-tool=qmake
  make
}

package() {
  cd qtdeclarative
  make INSTALL_ROOT="${pkgdir}" install
}
