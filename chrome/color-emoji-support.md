# Color Emoji Support

On openSUSE Tumbleweed, install Noto Color Emoji font

    sudo zypper in noto-emoji-fonts noto-coloremoji-fonts

Create ~/.config/fontconfig/fonts.conf file with content:

    <?xml version='1.0' encoding='UTF-8'?>
    <!DOCTYPE fontconfig SYSTEM 'fonts.dtd'>
    <match>
    <test name="family">
    <string>sans-serif</string>
    </test>
    <edit name="family" mode="prepend" binding="strong">
    <string>Noto Color Emoji</string>
    </edit>
    <test name="family">
    <string>serif</string>
    </test>
    <edit name="family" mode="prepend" binding="strong">
    <string>Noto Color Emoji</string>
    </edit>
    <test name="family">
    <string>Apple Color Emoji</string>
    </test>
    <edit name="family" mode="prepend" binding="strong">
    <string>Noto Color Emoji</string>
    </edit>
    <dir>~/.fonts</dir>
    </match>

Then update font information cache by running

    fc-cache -f -v