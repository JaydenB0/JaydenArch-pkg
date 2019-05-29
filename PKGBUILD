# Maintainer: Jayden Bulexa <JaydenB0@pm.me>
pkgname=(jaydenarch-base jaydenarch-dev jaydenarch-power jaydenarch-laptop, jaydenarch-latex)
pkgver=2019
pkgrel=1
pkgdesc="Base system configuration for JaydenArch"
arch=('any')
url="https://github.com/JaydenB0/JaydenArch"
license=('MIT')
groups=(jaydenarch)

package_jaydenarch-base() {
	# Base Groups
	depends=(bash bzip2 coreutils cryptsetup device-mapper dhcpcd diffutils e2fsprogs file filesystem findutils gawk gcc-libs gettext glibc grep gzip inetutils iproute2 iputils jfsutils less licenses linux linux-firmware logrotate lvm2 man-db man-pages mdadm nano netctl pacman pciutils perl procps-ng psmisc reiserfsprogs s-nail sed shadow sysfsutils systemd-sysvcompat tar texinfo usbutils util-linux vi which xfsprogs wget)

	# Networking
	depends+=(networkmanager openssh netcat)

	# Shells
	depends+=(zsh)

	# Editor
	depends+=(neovim)

	# Multiplexor
	depends+=(tmux)
	
	# Filesystems
	depends+=(dosfstools)
	
	# Fonts
	depends+=(noto-fonts noto-fonts-cjk noto-fonts-emoji noto-fonts-extra ttf-dejavu xorg-fonts-misc)
	# Printing
	depends+=(cups)
	install="jaydenarch-base.install"
}

package_jaydenarch-dev() {	
	depends=(jaydenarch-base)
	# Dev Tools
	depends+=(autoconf automake binutils bison fakeroot flex gcc groff libtool m4 make patch pkgconf sed sudo systemd texinfo util-linux which)
}

package_jaydenarch-power() {
	depends=(cpupower powertop)
	install="jaydenarch-power.install"
}

package_jaydenarch-latex() {
	depends=('texlive-bin' 'texlive-htmlxml' $(pacman -Sgq texlive-most texlive-lang))
	install -d "$pkgdir"/opt
	cp -R ${srcdir}/install-tl-[0-9]*/ "$pkgdir"/opt/texlive-installer
}

package_jaydenarch-laptop(){
	# WM
	depends+=(i3-gaps)
	# Login Greeter
	depends+=(lightdm-webkit2-greeter)
	# Browser
	depends+=(firefox)

	# Xorg (Just install xorg group)
	depends+=(xorg-server xorg-xinit)	
	# Audio
	depends+=(alsa-utils alsa-firmware pulseaudio pulseaudio-alsa pulseaudio-bluetooth pavucontrol bluez bluez-utils)

	# Utility
	depends+=(redshift scrot feh)
	
	# Terminal
	depends+=(terminator compton)
}
