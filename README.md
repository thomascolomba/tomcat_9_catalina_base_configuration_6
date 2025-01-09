# tomcat_9_catalina_base_configuration_6

eso arranca el tomcat usando un CATALINA_BASE distinto de su valor per defecto.

vamos a intentar de usar el ant y ejecutar un par de target aqui.

Vamos a desplegar una webapp "hello" con el código fuente en ./source_code/
El controller está aquí : ./source_code/myapp/src/com/mycompany/mypackage

Está una instalación de ant allí : C:\apache\tomcat\catalina_bases\tomcat_9_catalina_base_configuration_6\apache-ant-1.10.15_modified
Con un archivo ./apache-ant-1.10.15_modified/lib/catalina-ant.jar añadido a la instalación per defecto de ant.

En ./source_code/myapp está el build.xml que compila/desplega/replega la aplicación a partir de su código fuente

./source_code/myapp/web/WEB-INF/web.xml tiene :
    <servlet-name>ControllerServlet</servlet-name>
    <servlet-class>com.mycompany.mypackage.ControllerServlet</servlet-class>
	y
	<servlet-name>ControllerServlet</servlet-name>
    <url-pattern>/ControllerServlet</url-pattern>


1) ant -> eso construye los .class
2).\callStartupBatWithThisFolderAsCatalinaBase_6.bat
3)ant install -> eso desplega los .class y los .jsp en el tomcat pre-arrancado
4)ir a http://localhost:8080/hello/mypage.jsp y http://localhost:8080/hello/ControllerServlet con el navegador para ver que está desplegada la aplicación.
  Se puede acceder a http://localhost:8080/hello/ControllerServlet para ver la respuesta de ControllerServlet.java y a http://localhost:8080/hello/mypage.jsp para ver el contenido de la jsp mypage.jsp
5) ant remove -> eso replega los .class y los .jsp del tomcat

