# LPIC-2

Es gibt itneraktive und nicht-interaktive, sowie Login und NoLogin-Shells.

eine neue Shell ist entweder eine pts Shell, wenn diese von
einem Terminalemulator in der GUI geöffnet wird, oder eine tty Shell, wenn diese von einer
Systemkonsole ausgeführt wird.

tty steht für “teletypewriter”, pts für “pseudo terminal slave”. Für weitere
Informationen: man tty und man pts.

**bash -l oder bash --login**
ruft eine Shell mit Login auf.

**bash -i**
ruft eine interaktive Shell auf.

**bash --noprofile**
ignoriert bei Shells mit Login sowohl die systemweite Startdatei /etc/profile als auch die
Startdateien auf Benutzerebene ~/.bash_profile, ~/.bash_login und ~/.profile.

**bash --norc**
ignoriert bei interaktiven Shells sowohl die systemweite Startdatei /etc/bash.bashrc als
auch die Startdatei auf Benutzerebene ~/.bashrc.

**bash --rcfile <file>**
übernimmt <file> als Startdatei bei interaktiven Shells und ignoriert die systemweite
/etc/bash.bashrc und die benutzerspezifische ~/.bashrc.
