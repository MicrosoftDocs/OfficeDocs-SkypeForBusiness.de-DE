---
title: Konfigurieren der Verwendung von hoch auflösenden Fotos in Microsoft Lync Server 2013
TOCTitle: Konfigurieren der Verwendung von hoch auflösenden Fotos in Microsoft Lync Server 2013
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49890854
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der Verwendung von hoch auflösenden Fotos in Microsoft Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Microsoft Lync Server 2010 bietet Benutzern die Möglichkeit, Fotos ihrer Kontakte anzuzeigen (und für andere eigene Fotos zur Verfügung zu stellen). In der Regel werden diese Fotos als Teil des thumbnailPhoto-Attributs des Benutzers in Active Directory gespeichert. Dies bringt eine strenge Beschränkung der Größe und Auflösung der Fotos mit sich: Das Attribut "thumbnailPhoto" kann lediglich Fotos einer Größe von maximal 48 x 48 Pixel aufnehmen.

In Microsoft Lync Server 2013 können Fotos jedoch im Microsoft Exchange Server 2013-Postfach des Benutzers gespeichert werden. Dieses erlaubt Fotogrößen bis zu 648 x 648 Pixel. Darüber hinaus kann Exchange 2013 die Größe dieser Fotos automatisch für die Verwendung in verschiedenen Produkten anpassen. Dies führt meist zu drei verschiedenen Fotogrößen und -auflösungen:

  - 48 x 48 Pixel - die für das Active Directory thumbnailPhoto-Attribut verwendete Größe. Wenn Sie ein Foto in Exchange 2013 hochladen, erstellt Exchange automatisch eine Version mit 48 x 48 Pixel des Fotos und aktualisiert damit das thumbnailPhoto-Attribut des Benutzers. Beachten Sie jedoch, dass dies umgekehrt nicht der Fall ist: Wenn Sie das thumbnailPhoto-Attribut in Active Directory manuell aktualisieren, wird das Foto im Exchange 2013-Postfach des Benutzers nicht automatisch aktualisiert.

  - 96 x 96 Pixel, für die Verwendung in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App und Lync 2013.

  - 648 x 648 Pixel für die Verwendung in Lync 2013 und Microsoft Lync Web App.


> [!NOTE]
> Sofern Sie ausreichende Ressourcen besitzen, empfiehlt es sich, Fotos im Format 648 x 648 Pixel hochzuladen. Dies sorgt für eine maximale Auflösung und optimale Bildqualität in allen Office 2013-Anwendungen. Ein JPEG-Foto mit 648 x 648 Pixel und einer Tiefe von 24 Bit ergibt eine Datei mit einer Größe von rund 240 KB. Dies bedeutet, dass Sie für je vier Benutzerfotos rund ein MB Festplattenspeicher benötigen.



Hochauflösende Fotos, auf die mit den Exchange-Webdiensten zugegriffen wird, können durch Benutzer der Outlook 2013 Web App hochgeladen werden. Benutzer können ausschließlich ihre eigenen Fotos aktualisieren. Administratoren können jedoch mit der Exchange-Verwaltungsshell und verschiedenen Windows PowerShell-Befehlen die Fotos aller Benutzer aktualisieren. Beispiel:

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

Im ersten Befehl des obigen Beispiels wird das Get-Content-Cmdlet verwendet, um die Inhalte der Datei "C:\\Photos\\Kenmyer.jpg" zu lesen und diese Daten in einer Variablen namens "$photo" zu speichern. Im zweiten Befehl wird das Exchange-Cmdlet "Set-UserPhoto" genutzt, um das Foto hochzuladen und mit dem Benutzerkonto von Ken Myer zu verbinden.


> [!NOTE]
> In diesem Beispiel wird der Active Directory-Anzeigename von Ken Myer als Benutzerkontoidentität verwendet. Sie können ein Benutzerkonto auch über andere IDs referenzieren, wie die SMTP-Adresse des Benutzers oder dessen Benutzerprinzipalnamen. Weitere Informationen finden Sie in der Dokumentation zum Set-UserPhoto-Cmdlet unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=268536%26clcid=0x407">http://go.microsoft.com/fwlink/?linkid=268536&amp;clcid=0x407</A>



Das Hochladen des Fotos entspricht keiner Zuweisung des Fotos zu Ken Myers Benutzerkonto. Das Hochladen des Fotos führt einfach nur dazu, dass eine Vorschau des Fotos auf der Seite der Outlook Web App-Optionen angezeigt wird. Damit das Foto dem Benutzerkonto zugewiesen wird, muss der Benutzer auf der Seite mit den Optionen auf **Speichern** klicken oder der Administrator muss den dritten Befehl des Beispiels ausführen. Dieser dritte Befehl benutzt den Save-Parameter, um das Foto dem Benutzerkonto von Ken Myer zuzuweisen:

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

Um zu prüfen, ob das neue Foto dem Benutzerkonto zugewiesen wurde, kann sich Ken Myer in Lync 2013 anmelden, die **Optionen** auswählen und dann **Mein Bild** auswählen. Das neu hochgeladene Foto sollte dann als Kens persönliches Foto angezeigt werden. Alternativ können Administratoren die Fotos aller Benutzer prüfen, indem sie den Internet Explorer starten und zu einer URL der folgenden Art navigieren:

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

Wenn der Administrator das Foto im Internet Explorer sehen kann, der Benutzer sein Foto in Lync 2013 aber nicht sieht, deutet dies meist auf ein Verbindungsproblem mit den Exchange-Webdiensten oder mit dem Exchange-AutoErmittlungsdienst hin.

Beachten Sie auch, dass keine zusätzliche Konfiguration erforderlich ist, um dieses Foto in Lync 2013 zur Verfügung zu stellen. Stattdessen ist das Foto unmittelbar verfügbar, nachdem es hochgeladen und das Cmdlet Set-UserPhoto ausgeführt wurde.

