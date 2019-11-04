1. lépés: Az Apache2 webszerver és MariaDB adatbázis telepítése
  
        apt-get install -y apache2 mariadb-server mariadb-client php libapache2-mod-php php-mysql
  
2. lépés: PHP működésének ellenőrzése
  
      a. Készítsünk egy info.php fájlt a /var/www/html mappába:
        
        nano /var/www/html/info.php
      
      b. A következő PHP kódot helyezzük el benne, majd mentsük el:
      
        <?php
            phpinfo();
        ?>
      
      c. Indítsuk újra az Apache2 szervert a következő parancsok egyikével:
      
        service apache2 restart
        VAGY
        /etc/init.d/apache2 restart
        VAGY
        systemctl restart apache2
        VAGY
        service apache2 reload
      
      d. A böngészőből ellenőrizzük az info.php fájl elérését:
        
        http://localhost/info.php
        
      e. Amennyiben működik, biztonság okokból töröljük a fájlt a következő paranccsal:
      
        rm -f /var/www/html/info.php

3. lépés: phpMyAdmin telepítése

      a. A következő paranccsal kezdeményezzük:
      
        apt-get install phpmyadmin php-mcrypt
        
      b. A következőben válasszuk ki az apache2 webszerver, majd a dbconfig-common beállításainak az elvégzését.
      
      c. Állítsuk be a phpMyAdmin belépéséhez használandó jelszót, majd erősítsük meg.

4. lépés: phpMyAdmin elérése

        http://localhost/phpmyadmin
        
      TIPP: Amennyiben nem töltődik be a felület, a következő parancsot futtassuk a következő parancsot:
        
        ln -s /usr/share/phpmyadmin /var/www/html/phpmyadmin
        
