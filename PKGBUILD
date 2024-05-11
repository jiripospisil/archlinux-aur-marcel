# Maintainer: Jiri Pospisil <jiri@jpospisil.com>

pkgname=marcel
pkgver=0.25.0
pkgrel=1
pkgdesc='A modern shell'
url='https://github.com/geophile/marcel'
source=("https://github.com/geophile/marcel/archive/refs/tags/v$pkgver.tar.gz")
arch=('any')
depends=('python' 'python-dill' 'python-psutil')
makedepends=(
  'python-build'
  'python-installer'
  'python-wheel'
  'python-setuptools'
)
license=('GPL-3.0-only')
b2sums=('fc3ce2083f74c50a84454da8a4eb18520de6d9a1cc18a1ef8c3425c0c5c0f9f18b8e64ca014d9e21fc880a97d455778d84a0e46bd937298f39fac17160953db5')

prepare() {
  cd marcel-"$pkgver"
  rm -rf 'test'
}

build() {
  cd marcel-"$pkgver"
  python -m build --wheel --no-isolation
}

package() {
  cd marcel-"$pkgver"
  python -m installer --destdir="$pkgdir" dist/*.whl
}
