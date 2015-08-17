pkgname=weboob-stable-git
pkgrel=1
pkgver=20120206
pkgdesc="Weboob (Web Out Of Browsers) provides several applications to interact with a lot of websites. Stable branch."
url="http://weboob.org"
license=('GPL3')
arch=('i686' 'x86_64')
depends=('python2' 'python-dateutil' 'python-mechanize' 'pyxdg' 'python2-elementtidy' 'python-html2text' 'python2-yaml' 'python-lxml' 'python-html5lib' 'python-clientform' 'python2-feedparser' 'python-gdata' 'python-nose' 'python2-prettytable' 'python-mako' 'python-routes' 'python2-webob' 'python-imaging' 'pygtk' 'python2-qt' 'pywebkitgtk' 'python-pysqlite' 'python-simplejson' 'mimms')
makedepends=('git' 'setuptools')
conflicts=('weboob')
provides=('weboob')

_gitroot="git://git.symlink.me/pub/romain/weboob-stable.git"
_gitname=weboob-stable

build() {
	cd $srcdir
	msg "Connecting to GIT server...."

	if [ -d $srcdir/$_gitname ] ; then
		cd $_gitname && git pull origin
		msg "The local files are updated."
		cd ../
	else
		git clone $_gitroot
	fi

	msg "GIT checkout done or server timeout"

	rm -rf build
	git clone $_gitname build
	cd build

	python2 setup.py install --root=$pkgdir
} 
