pkgname="xenobino-tabbed-git"
pkgver="0.6"
pkgrel="2"
pkgdesc="Suckless's tabbed, patched to my liking"
arch=("x86_64")
depends=("glibc" "libx11" "libxft" "libxrender" "fontconfig")
url="https://github.com/XenoBino/tabbed"
license=("MIT")

prepare() {
	if [ -d xenobino-tabbed-git ]; then rm -rf xenobino-tabbed-git; fi
	git clone --depth 1 https://github.com/XenoBino/tabbed xenobino-tabbed-git
}

build() {
	pushd xenobino-tabbed-git &> /dev/null
	make
	popd &> /dev/null
}

package() {
	# DESTDIR: Install to ${pkgdir} for packaging
	# PREFIX: Use /usr instead of /usr/local
	pushd xenobino-tabbed-git &> /dev/null
	make DESTDIR="${pkgdir}" PREFIX="/usr" install
	popd &> /dev/null
}
