# Serveur web linux

**Methode :**

-  Installez le service apache2 (nom du paquet : apache2)
- Accédez au répertoire racine web d’Apache /var/www/html/
- Modfier le index.html
-  http://votre_IP/index.html

**Plusieur Site WEB**

· Créez un dossier /var/www/cyberprotect/ sur votre serveur.
. Déplacez le SITEWEB dans /var/www/cyberprotect/
· Assurez-vous que les fichiers dans /var/www/cyberprotect ont les bonnes permissions pour être ac-
cessibles par Apache :
chown -R www-data:www-data /var/www/cyberprotect
chmod -R 755 /var/www/cyberprotect
· Copiez le fichier /etc/apache2/sites-available/000-default.conf dans /etc/apache2/sites-avai-
lable/cyberprotect.conf.
· Modifiez la ligne DocumentRoot /var/www/html en indiquant le chemin d'accès vers votre site.
Il reste à désactiver l'ancien site et à activer le nouveau.
· Désactivez le site web par défaut d'Apache 2 :
a2dissite 000-default.conf
· Activez votre site web :
a2ensite cyberprotect.conf
· Activez les modifications en rechargeant le service apache2.
· Rechargez la page dans le navigateur de votre machine hôte (ou accédez à http://votre_IP/in-
dex.html). Le site web de la société CyberProtect

**Journalisation**

Le service apache2 enregistre ses logs dans le répertoire /var/log/apache2/. Les lignes ci-dessous, entrées
dans le fichier de configuration du site, ont permis de spécifier un fichier différent pour les logs d'accès et
les logs d'erreur :
ErrorLog ${APACHE_LOG_DIR}/error.site-perso.log
CustomLog ${APACHE_LOG_DIR}/access.site-perso.log combined

**jamais utiliser nano et utiliser tail**
