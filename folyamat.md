1. lépés: Az Apache2 webszerver, MariaDB adatbázis és a phpMyAdmin felület telepítése
  
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
        /etc/init.d/apache2 restart
        systemctl restart apache2
        service apache2 reload
      
      d. A böngészőből ellenőrizzük az info.php fájl elérését:
        
        http://localhost/info.php
