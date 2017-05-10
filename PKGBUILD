# Maintainer: Wendell Smith <wendell.smith at gmail.com>
pkgname=facetimehd
pkgver=0.1
pkgrel=1
pkgdesc="Adds the facetimehd module"
arch=('x86_64')
url="https://github.com/patjak/bcwc_pcie"
license=('GPL')
depends=('dkms')
source=(dkms.conf fthd_buffer.c fthd_buffer.h fthd_ddr.c fthd_ddr.h
    fthd_debugfs.c fthd_debugfs.h fthd_drv.c fthd_drv.h fthd_hw.c fthd_hw.h
    fthd_isp.c fthd_isp.h fthd_reg.h fthd_ringbuf.c fthd_ringbuf.h fthd_v4l2.c
    fthd_v4l2.h Makefile)
md5sums=('bcafb91c48b68ece00d2d75720e6ff96'
         '38c497f2031bb7ffc67b645a2b4d2535'
         'db515c284566a9bf4fa70c1eb0e11561'
         'd796447970049fe0892abfdfdec8ea93'
         'c51f4ece8ba7bab0a6ebab0f3bcaae5b'
         '55069f86ef0025015d1179977aefeb1e'
         'e38b14e6002b7f49aa579e2154420da0'
         '6337ddabac2fd33832cb0f614beef6da'
         '8e0cbca4a6caafd1ab95ec42bc1f4b67'
         '99ba931f8d6e14a1015d1e26d69f77ab'
         '6d063d4b3dc3574c0222cf8fffe4ca4a'
         '3a0dbdada3c067500f42aca5bbeb2c7a'
         'fe50b955f91d41453945f201242dd626'
         '1ea6e9a7903e28777cf56254a6bc42c9'
         '18c5db8ff3ee72b663d1d6df0a15803a'
         '3bfe39bdb1e322f677025645d690ca30'
         'dbc8e27a7429be3796f840d8efce18c9'
         '8f44ef99ce4eca1ee7318a40a8df3a82'
         'f7b817682580f3b47394fc92ba202af1')

build() {
    echo "makepkg: make modules"
	make -C "/usr/lib/modules/`uname -r`/build" M="${srcdir}" modules
}

package() {
    make -C "/usr/lib/modules/`uname -r`/build" M="${srcdir}" INSTALL_MOD_PATH="${pkgdir}/usr" modules_install
}
