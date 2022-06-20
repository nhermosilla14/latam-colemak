## latam-colemak
### Latin American Spanish Colemak keyboard layout

### THIS WORK IS INSPIRED, BUT IN NO WAY ENDORSED BY DREYMAR. IT'S ALSO NOT BEING DEVELOPED ANYMORE.

#### Update!! Added console keymap (thanks to Jorge "Jorgicio" Pizarro)

This aims to provide a «good enough» implementation of the latam Colemak keyboard layout designed by DreymaR (for more info, check http://forum.colemak.com/viewtopic.php?id=1607). It is completely functional in X11, while the terminal version is currently WIP.

Another version, slightly different (but not made by DreymaR), is provided too, with the sole modification of keeping WASD as in QWERTY, to avoid troubles while gaming.

#Important features:
- The layout is near nearly identical to this:

![](https://dl.dropboxusercontent.com/u/14504410/Keyboards/dreymar/doc/locale/Cmk-eD-latam-ksym_Xm.png)

The colemak-gaming version looks similar, but WASD remains untouched from QWERTY and the R is between T and H.

- The layout file is based on the latam-dvorak file (https://github.com/flobosg/latam-dvorak), so it also contains that layout.


#Installation

# X.org

First of all, do a backup of the following files:

/usr/share/X11/xkb/rules/evdev.lst

/usr/share/X11/xkb/rules/evdev.xml

/usr/share/X11/xkb/symbols/latam

Then, replace the latam file in your system with the custom one provided here.

After that, open as root the first file listed and, under the '! variant' list, add these lines:

	colemak          latam: Spanish (Latin American, Colemak)
	colemak-gaming   latam: Spanish (Latin American, Colemak for gaming)

Save it and open as root the second file, look for the latam layout and edit to add these:

```    <layout>
      <configItem>
        <name>latam</name>
		          
        <shortDescription>es</shortDescription>
  ...
      </configItem>
      <variantList>
        <variant>
          <configItem>
            <name>colemak</name>
            <description>Spanish (Latin American, Colemak)</description>
	  </configItem>
        </variant>
        <variant>
          <configItem>
            <name>colemak-gaming</name>
            <description>Spanish (Latin American, Colemak for gaming)</description>
	  </configItem>
        </variant>
  ...
  
  </variantList>
    </layout>
```

Then you can try it using:

$ setxkbmap latam colemak

# TTY

To install the terminal version, copy both *.map.gz files to /usr/share/kbd/keymaps/i386/colemak/, and run this on the TTY:


$ loadkeys colemak-la

or

$ loadkeys colemak-la-gaming


If everything works fine, open /etc/vconsole.conf and edit it:


KEYMAP=colemak-la
...


Please report if you find any issue!
