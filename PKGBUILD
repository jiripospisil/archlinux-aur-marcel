# Maintainer: Jiri Pospisil <jiri@jpospisil.com>

pkgname=marcel
pkgver=0.27.0
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
b2sums=('20151094ca82f8adc87af31a582d1affc67cac223e74e1433748c9dbf06cbc9808e4e66d5506c990e9cb54810915ce069a0d2012df4f96c6c78abe159364ee0d')

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
