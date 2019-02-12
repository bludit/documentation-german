# Installation
<!-- Position: 3 -->

Bludit ist in wenigen Schtitten installiert:

1. Lade die neueste Version von Bludit von der [offiziellen Website](https://www.bludit.com/de/) herunter.
2. Entpacke das ZIP-Archiv.
3. Lade den Inhalt des ZIP-Archivs in das Verzeichnis auf deinem Server, in dem du Bludit installieren möchtest. Das kann im Hauptverzeichnis sein (root) oder in einem Unterverzeichnis wie beispielsweise `/bludit`.
4. Rufe im Browser die Domain mit der Installation auf. Befindet sie im Hauptverzeichnis `https://meinedomain.ch`, wenn sie sich in einem Unterverzeichnis befindet beispielsweise `https://meinedomain.ch/bludit`.
5. Der Bludit-Installer führt dich darauf durch die Einrichtung der Website.

---

<h2 id="iis-internet-information-services">IIS (Internet Information Services)</h2>

Für die Installation mit IIS (Internet Information Services, früher: Internet Information Server) von Microsoft muss die Datei .htaccess angepasst werden.

Beispielsweise:

```
<rules> 
   <rule name="Rule1" stopProcessing="true">
      <match url="^(.*)$" ignoreCase="false" />
         <conditions>
            <add input="{REQUEST_FILENAME}" matchType="IsFile" ignoreCase="false" negate="true" />
            <add input="{REQUEST_FILENAME}" matchType="IsDirectory" ignoreCase="false" negate="true" />
            <add input="{URL}" pattern="^/favicon.ico$" ignoreCase="false" negate="true" />
         </conditions>
      <action type="Rewrite" url="index.php?q={R:1}" appendQueryString="true" />
   </rule>
</rules>
```

---

<div class="note">
<div class="title">Zeitzone</div>
Bludit versucht deine Zeitzone automatisch zu ermitteln. Es empfiehlt sich aber, die Einstellung der Zeitzone nach der Installation   im Administrationsbereich unter <strong>Einstellungen</strong> > <strong>Sprache/Zeitzone</strong> > <strong>Zeitzone</strong> zu überprüfen.
</div>

<div class="note">
<div class="title">Files auf den Server laden</div>
Um die Dateien auf den Server zu laden, kannst du einen FTP- oder SFTP-Client oder WebFTP verwenden. Weitere Informationen dazu findest du beispielsweise auf der Website <em>Planet Bludit</em> unter <a href="https://planet-bludit.ch/installation/file-transfer-ftp-und-sftp" target="_blank">File Transfer (FTP und SFTP)</a>.
</div>
