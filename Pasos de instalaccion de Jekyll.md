
**Paso 1: actualiza tu sistema** 
Recomendamos actualizar los paquetes de su sistema antes de instalar nuevo software. 

**sudo apt update -y**

**sudo apt-get install ruby-full build-essential zlib1g-dev**


**Paso 2: instale Ruby y Bundler** 
Jekyll está basado en Ruby, por lo que primero debes instalar Ruby. También recomendamos utilizar Bundler para gestionar las dependencias de Ruby. 

Instale Ruby y otras dependencias necesarias. 

**sudo apt install ruby-full build-essential zlib1g-dev** 


Configure RubyGems (sistema de administración de paquetes Ruby) para instalar gemas (paquetes Ruby) en su directorio de inicio. Esto ayuda a evitar problemas de permisos. 

**echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc echo 'export GEM\_HOME="$HOME/gems"' >> ~/.bashrc echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc source ~/.bashrc** 


Instalé Bundler, una herramienta para gestionar las dependencias de Ruby. 

paquete de instalación de gemas 

**Paso 3: instala Jekyll** 
Una vez instalados Ruby y Bundler, puede instalar Jekyll usando RubyGems. 

gem install jekyll bundler


Esto instalará Jekyll y sus dependencias en su sistema. 


**Paso 4: verificar la instalación** 
Para asegurarse de que Jekyll esté instalado correctamente, verifique la versión. 

**jekyll -v** 

Si la versión de Jekyll se muestra en el resultado, la instalación fue exitosa. 

![1](/Jekyl-v.png)

**Paso 5: Creación del repositorio local**

Conectamos el repositorio local con nuestra cuenta de github.

**mkdir myblog** 

**cd myblog** 

**git init** 

**git remote add origin https://github.com/tu\_cuenta\_github/myblog.git**

Después conectamos la rama gh-pages para poder posteriormente poder publicar el sitio web.

**git checkout -b gh-pages**

**Paso 6: crea un nuevo proyecto en Jekyll** 
Para comenzar a usar Jekyll, cree un nuevo sitio usando el siguiente comando: 

**jekyll new myblog**


Este comando genera la estructura de archivos básica para su sitio Jekyll. 








**Paso 7: inicie el servidor de desarrollo Jekyll** 
Accede a tu nuevo directorio de proyectos. 

cd (donde quieras ir) 


Inicie el servidor de desarrollo Jekyll de la siguiente manera: 

**bundle exec jekyll serve - -host 10.0.22.2XX (si jekyll se encuentra en una máquina virtual. Utiliza como IP la de tu máquina virtual)**

` `Navegación: **http:// 10.0.22.2XX:4000/myblog** à Para ver la página 


Esto iniciará su servidor local (generalmente http://localhost:4000) y le permitirá ver el sitio que está desarrollando.

**Paso 8: Publicación del sitio web**

Ingresar a configuraciones (settings) del repositorio (rueda dentada) y elegir la opción páginas (pages) de la barra lateral izquierda y automáticamente se genera un dominio. 

Para comprobar su funcionamiento se puede hace click en Visitar sitio (visit site): <https://tu_cuenta_github.github.io/myblog/>











**Paso 9: Configurar las gemas** 

Cogemos la página donde están ubicadas las gemas para proceder después a su instalación.

**source “https://rubygems.org”**

Posteriormente procederemos a su instalación/actualización para que las gemas estén operativas.

**gem "github-pages", group: :jekyll\_plugins** 

**group :jekyll\_plugins do** 

**gem “jekyll-feed”, “~> 0,12”** 

**end**

![2](/informacion.png)

**Paso 10: Probamos el sitio localmente**

Hay que ejecutar este comando para conectar el Jekyll con nuestra ip.

**bundle exec jekyll serve - -host 10.0.22.2XX** 

(si jekiyll se encuentra en una máquina virtual. Utiliza la IP de tu máquina virtual.)** 

Navegación: **http:// 10.0.22.2XX:4000/myblog**

**Paso 11: Modificar los archivos para subirlos al repositorio local**

Lo primero abrimos el index.md para poder editarlo, una vez dentro de el nos dirigimos al directorio raíz y modificamos el titulo, descripción, etc… .

Una vez acabado los cambios los subimos a la cuenta de github con:

**git add .** 

**git commit -m "Actualizamos contenido jekyll"**

` `**git push origin gh-pages**  

Nota: Recuerda que podrás acceder al sitio a través de la siguiente URL: https:**//tu\_cuenta\_github.github.io/myblog/**

URL de los posts (pagina): https://unairpgg.github.io/myblog/
