# Maintainer: Mathieu Pasquet <mathieui@mathieui.net>

pkgname=python-sleekxmpp-poezio
pkgver=20120824
pkgrel=2
pkgdesc="A XMPP library written for Python 3.x (with 2.6 compatibility) - Poezio branch"
arch=(any)
url="http://github.com/fritzy/SleekXMPP"
license=('MIT')
depends=('python')
makedepends=('git')
conflicts=('python-sleekxmpp' 'python-sleekxmpp-devel')
provides=('python-sleekxmpp' 'python-sleekxmpp-devel')
optdepends=('python-dnspython: SRV records and Gmail')

_gitroot="git://github.com/louiz/SleekXMPP.git"
_gitname="sleekxmpp"

build() {
  cd "$srcdir"
  msg "Connecting to GIT server...."

  if [ -d $_gitname ] ; then
    cd $_gitname && git pull origin
    msg "The local files are updated."
  else
    git clone $_gitroot $_gitname
  fi

  msg "GIT checkout done or server timeout"

  cd "$srcdir/$_gitname"

  python setup.py install --root=$pkgdir/ --optimize=1
}
