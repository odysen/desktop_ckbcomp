# Maintainer: Stella Benware (enterthevoidx86@gmail.com)

pkgname=ckbcomp
pkgver=1.233
pkgrel=1
pkgdesc="Compile a XKB keyboard description to a keymap suitable for loadkeys or kbdcontrol"
arch=(any)
url="http://anonscm.debian.org/cgit/d-i/console-setup.git/"
license=('GPL2')
depends=('perl')
source=("http://ftp.debian.org/debian/pool/main/c/console-setup/console-setup_${pkgver}.tar.xz")
sha512sums=(SKIP)
conflicts=(ckbcomp-bin)

package() {
    if [[ -d "${srcdir}/console-setup" ]]
    then
        cd console-setup
    elif [[ -d "${srcdir}/console-setup-${pkgver}" ]]
    then 
        cd console-setup-${pkgver} 
    elif [[ -d "${srcdir}/work" ]]
    then
        cd work
    else
	echo "Source directory not found.".
	exit 1
    fi


    if [[ ${?} != 0 ]]
    then
        cd console-setup-${pkgver}
    fi

    install -d ${pkgdir}/usr/bin/
    install -m755 Keyboard/ckbcomp ${pkgdir}/usr/bin/
}
