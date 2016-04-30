Заменя всички info.jpg с icons/info.jpg:

    $ sed -i 's:info\.jpg:icons/info\.jpg:g' path/to/file.php

Трие всички редове, отговарящи на регулярния израз:

    $ sed -i '/Invalid user/d' /var/log/messages

Трие файлове, които не са за commit

    $ git status -s | awk '{print $2} ' | xargs rm

How to **rsync** Drupal files

    $ rsync -avz user@host:/path/to/drupal/sites/default/files sites/default
    $ rsync -avz user@host:/path/to/drupal/sites/default/files/ sites/default/files

How to use **find**

    $ find /home/user -type f -exec sed -i 's/ugly/beautiful/g' {} \;
    $ find . -type d -user fileowner -exec chmod 0755 {} \;
    $ find . -type f -name 'settings.php' | xargs sed -i 's/oldpass/newpass/'
    $ chmod -R g+rwX sites/default/files/

mysqldump

    $ mysqldump -uroot -ppasswd -hlocalhost ttins --opt --allow-keywords --flush-logs --hex-blob --master-data --quote-names | bzip2 -c > dbname_$(date +%Y-%m-%d-%H%M%S).sql.bz2

Terminal shortcuts
- Ctrl-A - moves the cursor to the beginning of the command line
- Ctrl-E - moves the cursor to the end of the command line
- Ctrl-W - deletes the word immediately before the cursor
- Ctrl-K - deletes everything immediately after the cursor
- Ctrl-Y - undo a deletion
- To get out of broken SSH session press: Enter, then ~ and finally .

SSHFS

    $ sshfs martin@192.168.3.48:/home/martin /mnt/martin
    $ fusermount -u /mnt/martin

vi - replace 'default' with 'drupal' from line 48 to
the end of the file. For the whole file, replace :48,$ with :%:

    :48,$s/default/drupal/gc

ISO CD burning

    $ wget -c "ftp://some.org/file[0-9].iso"
    $ mkisofs -V label_name -r dir | gzip > image.iso.gz
    $ cdrecord -v dev=/dev/cdrom blank=fast

Show all passwords

    javascript:(function(){var s,F,j,f,i; s = ""; F = document.forms; for(j=0; j<F.length; ++j) { f = F[j]; for (i=0; i<f.length; ++i) { if (f[i].type.toLowerCase() == "password") s += f[i].value + "\n"; } } if (s) alert("Passwords in forms on this page:\n\n" + s); else alert("There are no passwords in forms on this page.");})();

iptables

    $ for i in `cat ban.u.list`; do iptables -I INPUT -s $i -j DROP; done

GPS

    $ gpsbabel -t -r -w -i gdb -f "Eho_zimno.gdb" -o kml -F "Eho_zimno.kml"

Presentation mode

    $ xrandr --output VGA1 --right-of LVDS1 # or --below
