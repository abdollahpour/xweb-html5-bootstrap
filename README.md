# XWeb HTML5 client based on bootstrap

If you are using Maven you can simply add UI to  you application by adding (to web.xml):

```xml
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
```

Or you can simply download content and put in you webapp directory.

And you can also need at some configuration to xweb.xml file. Ex:
```xml
<xweb version='1.0'>
	<property key='default.user'>admin@pdroid.org</property>
		<!-- data/ directory in your application server startup path -->
		<property key='default.dir.store'>${xweb.base}/data</property>
	</properties>

	<module>
		<name>rewrite</name>
		<author>Hamed Abdollahpour</author>
		<class>ir.xweb.module.RewriteModule</class>
		<properties>
			<property key="/wiki/(.*)" value="/wiki.html" />
		</properties>
	</module>
	
	<module>
		<name>wiki</name>
		<author>Hamed Abdollahpour</author>
		<class>ir.xweb.module.WikiModule</class>
		<validators>
			<!-- TODO: restrict illegal value to cheat system -->
			<validator param="get" regex=".*?" />
			<validator param="html" regex=".*?" />
			<validator param="put" regex=".*?" />
		</validators>
		<roles>
			<role definite="true" param="" eval="true" value="admin" />
			<role param="get,html" eval="true" value=".*?" />
		</roles>
		<properties>
			<!-- You need to put all the wiki content into the /wiki directory of you webapp -->
			<property key='dir.wiki'>${xweb.root}/wiki</property>
			<!-- You need to put all the wiki content into the /wiki directory of you webapp -->
			<property key='dir.cache'>${default.dir.store}/temp</property>
		</properties>
	</module>
	
</xweb>
```
