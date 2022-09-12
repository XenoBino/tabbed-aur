pkgname="xenobino-tabbed-git"
pkgver="0.6"
pkgrel="1"
pkgdesc="Suckless's tabbed, patched to my liking"
arch=("x86_64")
depends=("glibc" "libx11" "libxft" "libxrender" "fontconfig")
url="https://github.com/XenoBino/tabbed"
license=("MIT")

prepare() {
	if [ -d tabbed ]; then rm -rf tabbed; fi
	git clone --depth 1 https://github.com/XenoBino/tabbed
}

build() {
	pushd tabbed &> /dev/null
	make
	popd &> /dev/null
}

package() {
	strip "${srcdir}/tabbed/tabbed"
	strip "${srcdir}/tabbed/xembed"
	mkdir -p "${pkgdir}/usr/bin"
	#mkdir -p "${pkgdir}/usr/share/applications"
	mkdir -p "${pkgdir}/usr/share/man/man1"
	cp "${srcdir}/tabbed/tabbed" "${pkgdir}/usr/bin/tabbed"
	cp "${srcdir}/tabbed/xembed" "${pkgdir}/usr/bin/xembed"
	cp "${srcdir}/tabbed/tabbed.1"  "${pkgdir}/usr/share/man/man1/tabbed.1"
	cp "${srcdir}/tabbed/xembed.1"  "${pkgdir}/usr/share/man/man1/xembed.1"
	#cp "${srcdir}/tabbed/tabbed.desktop" "${pkgdir}/usr/share/applications/tabbed.desktop"
	chmod +x "${pkgdir}/usr/bin/tabbed"
	chmod +x "${pkgdir}/usr/bin/xembed"
}
