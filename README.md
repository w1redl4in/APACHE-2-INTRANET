# Instalação 
    sudo su
    apt install apache2 
    
# Criação de "domínios"
    cd /var/www/html/
    mkdir SUAPASTA
    cd SUAPASTA 
    nano index.html
    
## Modelo básico de html
    <html>
      <head>
        <title>teste</title>
      </head>
      <body>
        <h1>teste</h1>
      </body>
    </html>

# Configuração do site/apache 
    cd /etc/apache2/sites-available/
    nano NOMEDOSEUSITE.conf
   
    <VirtualHost *:80>
          ServerName nomedoseusite
          ServerAdmin root@nomedasuamaquina
          DocumentRoot /var/www/html/SUAPASTA
          ErrorLog ${APACHE_LOG_DIR}/error.log
          CustomLog ${APACHE_LOG_DIR}/acess.log combined
    </VirtualHost>
    
 
 # Subindo a página
    cd /etc/apache2/sites-available/
    a2ensite nomedoseusite.conf
    systemctl reload apache2
 
 # "DNS" (na máquina Cliente)
        sudo su
        nano /etc/hosts
        
        
        
        192.168.100.11      nomedoseusite
