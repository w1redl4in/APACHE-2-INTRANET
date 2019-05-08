# APACHE2 Download
    sudo su
    apt install apache2
    
# Criacao de pasta/pagina
    cd /var/www/html/
    mkdir SUAPASTA
    cd SUAPASTA 
    nano index.html
    
## Edicao basica de html
    <html>
      <head>
        <title>teste</title>
      </head>
      <body>
        <h1>teste</h1>
      </body>
    </html>

# Configuracao APACHE2
    cd /etc/apache2/sites-available/
    cp 000-default.conf NOMEDOSEUSITE.conf
    nano NOMEDOSEUSITE.conf
    
## Configuracao do arquivo
    <VirtualHost *:80>
          ServerName nomedoseusite
          ServerAdmin root@nomedasuamaquina
          DocumentRoot /var/www/html/SUAPASTA
          ErrorLog ${APACHE_LOG_DIR}/error.log
          CustomLog ${APACHE_LOG_DIR}/acess.log combined
    </VirtualHost>
    
 
 # Subindo pagina
    a2ensite nomedoseusite.conf
    systemctl reload apache2
 
 # Editando tabela hosts no C1
        sudo su
        nano /etc/hosts
        
        
        
        192.168.100.11      nomedoseusite
