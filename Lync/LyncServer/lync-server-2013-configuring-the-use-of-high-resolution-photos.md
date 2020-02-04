---
title: 'Lync Server 2013: Konfigurieren der Verwendung von Fotos mit hoher Auflösung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the use of high-resolution photos in Lync Server 2013
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49733753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cb82c047491a43f2a8682d3a6688f67e76af730
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a>Konfigurieren der Verwendung von Fotos mit hoher Auflösung in Microsoft lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-05_

Microsoft lync Server 2010 bot Benutzern die Möglichkeit, Fotos Ihrer Kontakte anzuzeigen (und ihre eigenen Fotos anderen Personen zur Verfügung zu stellen). Diese Fotos wurden in der Regel als Teil des thumbnailPhoto-Attributs des Benutzers in Active Directory gespeichert. Dadurch wurde die Größe und Auflösung der Fotos schwerwiegend eingeschränkt: das thumbnailPhoto-Attribut kann nur ein Foto mit einer maximalen Größe von 48 Pixeln von 48 Pixeln enthalten.

In Microsoft lync Server 2013 können Fotos jedoch im Microsoft Exchange Server 2013-Postfach eines Benutzers gespeichert werden. Damit können Foto Größen von bis zu 648 Pixeln von 648 Pixeln verwendet werden. Darüber hinaus kann Exchange 2013 die Größe dieser Fotos für die Verwendung in unterschiedlichen Produkten nach Bedarf automatisch ändern. Das bedeutet in der Regel drei verschiedene Foto Größen und-Auflösungen:

  - 48 Pixel um 48 Pixel, die für das Active Directory-thumbnailPhoto-Attribut verwendete Größe. Wenn Sie ein Foto in Exchange 2013 hochladen, erstellt Exchange automatisch eine 48 Pixel-Version des Fotos mit 48 Pixeln und aktualisiert das thumbnailPhoto-Attribut des Benutzers. Beachten Sie jedoch, dass umgekehrt nicht wahr ist: Wenn Sie das thumbnailPhoto-Attribut in Active Directory manuell aktualisieren, wird das Foto im Exchange 2013-Postfach des Benutzers nicht automatisch aktualisiert.

  - 96 Pixel von 96 Pixeln für die Verwendung in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft lync Web App und lync 2013.

  - 648 Pixel von 648 Pixeln für die Verwendung in lync 2013 und Microsoft lync Web App.

<div>


> [!NOTE]  
> Wenn Sie über die Ressourcen verfügen, sollten Sie 648x648-Fotos hochladen. Dies bietet die maximale Auflösung und optimale Bildqualität in den Office 2013-Anwendungen. Jedes JPEG-Foto mit einer Größe von 648x648 und einer Tiefe von 24 Bits führt zu einer Dateigröße von ungefähr 240 KB. Das bedeutet, dass Sie für alle 4 Benutzer Fotos ungefähr 1 Megabyte Speicherplatz benötigen.



</div>

Fotos mit hoher Auflösung, auf die über Exchange-Webdienste zugegriffen wird, können von Benutzern hochgeladen werden, die Outlook 2013 Web App ausführen. Benutzer dürfen nur Ihr eigenes Foto aktualisieren. Administratoren können das Foto allerdings mit der Exchange-Verwaltungsshell und einer Reihe von Windows PowerShell-Befehlen aktualisieren, die dem folgenden ähneln:

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

Der erste Befehl im vorherigen Beispiel verwendet das Cmdlet "Get-Content", um den Inhalt der Datei C:\\Fotos\\kenmyer. jpg zu lesen und diese Daten in einer Variablen mit dem Namen $Photo zu speichern. Im zweiten Befehl wird das Exchange-Cmdlet Satz-UserPhoto verwendet, um das Foto hochzuladen und dieses Foto an das Benutzerkonto von Ken Myers anzufügen.

<div>


> [!NOTE]  
> In diesem Beispiel wird der Active Directory-Anzeigename von Ken Myer als Benutzerkontoidentität verwendet. Sie können ein Benutzerkonto auch über andere IDs wie die SMTP-Adresse des Benutzers oder dessen Benutzerprinzipalnamen referenzieren. Weitere Informationen finden Sie in <A href="http://go.microsoft.com/fwlink/p/?linkid=268536">http://go.microsoft.com/fwlink/p/?LinkId=268536</A> der Dokumentation für das Cmdlet "Satz-UserPhoto".



</div>

Das Hochladen des Fotos entspricht keiner Zuweisung des Fotos zu Ken Myers Benutzerkonto. Durch das Hochladen wird einfach eine Vorschau dieses Fotos auf der Seite der Outlook Web App-Optionen angezeigt. Damit dieses Foto dem Benutzerkonto zugewiesen wird, muss der Benutzer auf der Seite mit den Optionen auf **Speichern** klicken oder der Administrator muss den dritten Befehl des Beispiels ausführen. Dieser dritte Befehl weist das Foto mithilfe des Parameters „Save“ dem Benutzerkonto von Ken Myer zu:

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

Um zu überprüfen, ob das neue Foto dem Benutzerkonto zugewiesen wurde, kann Ken Myers sich bei lync 2013 anmelden, **Optionen**auswählen und dann **mein Bild**auswählen. Das neu hochgeladene Foto sollte dann als Kens persönliches Foto angezeigt werden. Alternativ können Administratoren die Fotos aller Benutzer prüfen, indem sie den Internet Explorer starten und zu einer URL der folgenden Art navigieren:

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

Wenn der Administrator das Foto mit Internet Explorer anzeigen kann, der Benutzer aber sein Foto in lync 2013 nicht anzeigen kann, weist dies in der Regel auf ein Verbindungsproblem mit Exchange-Webdiensten oder dem Exchange-AutoErmittlungsdienst hin.

Beachten Sie auch, dass keine zusätzliche Konfiguration erforderlich ist, um dieses Foto in lync 2013 zur Verfügung zu stellen. Stattdessen ist das Foto unmittelbar verfügbar, nachdem es hochgeladen und das Cmdlet „Set-UserPhoto“ ausgeführt wurde.

</div>

<span> </span>

</div>

</div>

</div>

