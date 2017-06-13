_commit=b13a35db2cef474925b385eef8291ea21ec7fb36
pkgname=audacious-plugins
pkgver=3.8.2
pkgrel=1
pkgdesc="Plugins for Audacious"
arch=('x86_64')
url="http://audacious-media-player.org/"
license=('BSD' 'GPL')

depends=('audacious' 'qt5-multimedia' 'glib2' 'python2' 'alsa-lib' 'pulseaudio' 'jack' 'lame' 'libvorbis' 'flac'
         'mpg123' 'faad2' 'ffmpeg' 'libmodplug' 'fluidsynth' 'libcdio-paranoia' 'wavpack'
         'dbus-glib' 'libnotify' 'curl' 'libmtp' 'neon' 'libmms' 'libcue')


optdepends=('alsa-lib: Advanced Linux Sound Arch. output'
            'pulseaudio: PulseAudio output'
            'jack: Jack Audio Connection Kit output'
            'lame: FileWriter MP3 output'
            'libvorbis: Vorbis input, FileWriter Vorbis output'
            'flac: FLAC input, FileWriter FLAC output'

            'mpg123: MP3 input'
            'faad2: AAC input'
            'ffmpeg: ffaudio input'
            'libmodplug: modplug input'
            'fluidsynth: MIDI FluidSynth backend input'
            'libcdio-paranoia: CD Digital Audio input'
            'wavpack: WavPack input'

            'dbus-glib: Gnome Shortcuts Plugin'
            'libnotify: libnotify OSD'
            'curl: AudioScrobbler Client'
            'libmtp: Upload to MTP device'

            'neon: neon-based http transport'
            'libmms: libmms-based mms transport'
            'libcue: CUE playlist format'

            'qt5-multimedia: qtaudio support')
            
source=(https://github.com/audacious-media-player/audacious-plugins/archive/${_commit}.zip)
md5sums=('06ff85ae07b1fba723f4b4a8e6d9f4a9')

build() {
  cd "$srcdir/$pkgname-$_commit"

./autogen.sh 
  ./configure \
    --prefix=/usr \
    --enable-amidiplug \
    --enable-qt \
    --disable-gtk 
  make
}

package() {
  cd "$srcdir/$pkgname-$_commit"
  make DESTDIR="$pkgdir" install
  install -Dm644 COPYING "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
