# Maintainer: artist for Sonic-DE

pkgname=sonic-system-info
pkgver=6.6.4
_dirver=$(echo $pkgver | cut -d. -f1-3)
pkgrel=1
pkgdesc='Display information about your computer''s hardware on the Sonic desktop'
arch=(x86_64)
url='https://github.com/Sonic-DE/sonic-system-info'
license=(LGPL-2.0-or-later)
depends=(aha
         clinfo
         dmidecode
         gcc-libs
         glibc
         glu
         iproute2 # ip
         kauth
         kcmutils
         kconfig
         kcoreaddons
         kdeclarative
         ki18n
         kio
         kirigami
         kservice
         libdisplay-info
         libdrm
         libpulse # pactl
         libusb
         lm_sensors
         mesa-utils
         qt6-base
         qt6-declarative
         sh
         solid
         systemsettings
         vulkan-tools
         xorg-xdpyinfo)
makedepends=(extra-cmake-modules
             fwupd
             kdoctools
             vulkan-headers)
optdepends=('fwupd: firmware security module'
            'plasma-disks: SMART devices health monitor')
groups=(sonicde)
conflicts=(kinfocenter)
provides=(kinfocenter)
source=("${url}/archive/refs/tags/${pkgver}.tar.gz")

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF \
    -DCMAKE_INSTALL_LIBEXECDIR=lib
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}

sha256sums=('6b924706d75a11314c883051fe09edc24615a8b52cb23cd38d35608fb26753cb')
