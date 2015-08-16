pkgname=matchsubtitles
pkgver=20110827
pkgrel=3
pkgdesc="Rename subtitles (.srt files) to match the given video files."
url="https://code.google.com/p/winebottle-cli"
arch=('any')
license=('GPL3')
depends=('bash')
makedepends=('git')

_gitroot="https://code.google.com/p/winebottle-cli/"
_gitname="winebottle-cli"

build() {
    cd $srcdir

    msg "Connecting to GIT server..."
    if [[ -d $_gitname ]]; then
        cd $_gitname && git pull origin
        msg "The local files are updated."
    else
        git clone $_gitroot $_gitname
    fi
    msg "GIT checkout done or server timeout."
}

package() {
    mkdir -p $pkgdir/usr/bin/
    cp $srcdir/$_gitname/scripts/matchsubtitles $pkgdir/usr/bin/
    chmod 755 $pkgdir/usr/bin/matchsubtitles
}
