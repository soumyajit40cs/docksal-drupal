## docksal setup instruction for windows
1. install ubuntu wsl(18.04 or latest TLS) for windows
2. install docker desktop for Windows
3. Go to the docker desktop settings page. update "Resources". select the checkbox for "Enable integration with my default WSL distro" and select ubuntu version that you installed on step one. goto "general" and check "Expose daemon on tcp://localhost:2375 without TLS"
4. log in to your Ubuntu through the command prompt using your user name/passsword
5. install apache into the ubuntu
6. install docksal into the ubuntu using this command "DOCKER_NATIVE=1 bash <(curl -fsSL https://get.docksal.io)"
7. during docksal install time if you noticed curl error for raw.githubusercontent.com. then you have to update your Windows system host file. just goto c:\Windows\System32\Drivers\etc\hosts and add this line 185.199.108.133 raw.githubusercontent.com
8. once docksal install is complete then you can run your Drupal project using docksal. either you can create new project using composer the run the project or you can use old codebase project using docksal
9. once you run fin system start & fin p start then you can access the project through the URL. for example /var/www/html/drupal --> drupal.docksal.site is the url for your project
10. if you are unable to access the Drupal project through the url then you have to update some configurations.
11. run those command fin config set --global DOCKSAL_DNS_DOMAIN=docksal.site
fin config set --global DOCKSAL_VHOST_PROXY_IP=127.0.0.1
fin system reset vhost-proxy
12. hostname -I you can get the local host IP. update the host file again like add ip_address drupal.docksal.site. then you can access the app using this URL
13. apache/ip related error then run sudo service apache2 stop and run fin command.
   
