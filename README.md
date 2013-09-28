# XWeb HTML5 client based on bootstrap

If you are using Maven you can simply add UI to  you application by adding (to web.xml):

<dependencies>
  ...
	<dependency>
		<groupId>ir.xweb</groupId>
		<artifactId>xweb-html5-bootstrap</artifactId>
		<version>0.7.0-SNAPSHOT</version>
		<type>war</type>
		<scope>runtime</scope>
	</dependency>
	...
<dependencies>


<build>
	<finalName>pdroid</finalName>
	...
	<plugins>
	   ...
		<plugin>
			<artifactId>maven-war-plugin</artifactId>
			<version>2.1.1</version>
			<configuration>
				<packagingExcludes>WEB-INF/web.xml</packagingExcludes>
				<overlays>
					<overlay>
						<groupId>ir.xweb</groupId>
						<artifactId>xweb-html5-bootstrap</artifactId>
						<type>war</type>
					</overlay>
				</overlays>
			</configuration>
		</plugin>
		....
	</plugins>
	...
</build>





Or you can simply download content and put in you webapp directory.
