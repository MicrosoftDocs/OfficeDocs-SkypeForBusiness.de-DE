---
title: 'Lync Server 2013: Konfigurieren der Verwendung von hochauflösenden Fotos'
description: 'Lync Server 2013: Konfigurieren der Verwendung von hochauflösenden Fotos'
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
ms.openlocfilehash: 48b0077fbfe2d525a7dac651ebd4c2a95892d3d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544171"
---
# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a>Konfigurieren der Verwendung von hochauflösenden Fotos in Microsoft lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-05_

Microsoft lync Server 2010 haben Benutzern die Möglichkeit geboten, Fotos Ihrer Kontakte anzuzeigen (und ihren eigenen Fotos für andere zur Verfügung zu stellen). In der Regel werden diese Fotos als Teil des thumbnailPhoto-Attributs des Benutzers in Active Directory gespeichert. Dies bringt eine strenge Beschränkung der Größe und Auflösung der Fotos mit sich: Das Attribut "thumbnailPhoto" kann lediglich Fotos einer Größe von maximal 48 x 48 Pixel aufnehmen.

In Microsoft lync Server 2013 können Fotos jedoch im Microsoft Exchange Server 2013 Postfach eines Benutzers gespeichert werden; Das ermöglicht Foto Größen von bis zu 648 Pixeln von 648 Pixel. Darüber hinaus können Exchange 2013 diese Fotos bei Bedarf automatisch für die Verwendung in unterschiedlichen Produkten anpassen. Normalerweise bedeutet dies drei verschiedene Foto Größen und-Auflösungen:

  - 48 x 48 Pixel - die für das Active Directory thumbnailPhoto-Attribut verwendete Größe. Wenn Sie ein Foto in Exchange 2013 hochladen, erstellt Exchange automatisch eine Pixel Version von 48 Pixel für 48 dieses Fotos und aktualisiert das thumbnailPhoto-Attribut des Benutzers. Beachten Sie jedoch, dass die umgekehrte nicht true ist: Wenn Sie das thumbnailPhoto-Attribut in Active Directory das Foto im Exchange 2013 Postfach des Benutzers nicht automatisch aktualisiert wird, manuell aktualisieren.

  - 96 Pixel um 96 Pixel, zur Verwendung in Microsoft Outlook 2013-Webanwendung, Microsoft Outlook 2013, Microsoft lync Web App und lync 2013.

  - 648 Pixel durch 648 Pixel für die Verwendung in lync 2013 und Microsoft lync Web App.

<div>


> [!NOTE]  
> Sofern Sie ausreichende Ressourcen besitzen, empfiehlt es sich, Fotos im Format 648 x 648 Pixel hochzuladen. Dies sorgt für eine maximale Auflösung und optimale Bildqualität in allen Office 2013-Anwendungen. Ein JPEG-Foto mit 648 x 648 Pixel und einer Tiefe von 24 Bit ergibt eine Datei mit einer Größe von rund 240 KB. Dies bedeutet, dass Sie für je vier Benutzerfotos rund ein MB Festplattenspeicher benötigen.



</div>

Hochauflösende Fotos, auf die mithilfe von Exchange Webdienste zugegriffen werden kann, können von Benutzern hochgeladen werden, die Outlook 2013-Webanwendung ausführt; Benutzer dürfen Ihr eigenes Foto nur aktualisieren. Administratoren können das Foto allerdings mit dem Exchange-Verwaltungsshell und einer Reihe von Windows PowerShell Befehlen, die dem folgenden ähneln, aktualisieren:

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

Der erste Befehl im vorherigen Beispiel verwendet das Get-Content-Cmdlet, um den Inhalt der Datei C: \\ FotosKenmyer.jpg zu lesen \\ und diese Daten in einer Variablen mit dem Namen "$Photo" zu speichern. Im zweiten Befehl wird das Exchange-Cmdlet Set-UserPhoto verwendet, um das Foto hochzuladen und das Foto an das Benutzerkonto von Ken Myers anzufügen.

<div>


> [!NOTE]  
> In diesem Beispiel wird der Active Directory-Anzeigename von Ken Myer als Benutzerkontoidentität verwendet. Sie können ein Benutzerkonto auch über andere IDs referenzieren, wie die SMTP-Adresse des Benutzers oder dessen Benutzerprinzipalnamen. Weitere Informationen finden Sie in der Dokumentation für das Set-UserPhoto-Cmdlet unter. <A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A>



</div>

Das Hochladen des Fotos entspricht keiner Zuweisung des Fotos zu Ken Myers Benutzerkonto. Das Hochladen des Fotos führt einfach nur dazu, dass eine Vorschau des Fotos auf der Seite der Outlook Web App-Optionen angezeigt wird. Damit das Foto dem Benutzerkonto zugewiesen wird, muss der Benutzer auf der Seite mit den Optionen auf **Speichern** klicken oder der Administrator muss den dritten Befehl des Beispiels ausführen. Dieser dritte Befehl benutzt den Save-Parameter, um das Foto dem Benutzerkonto von Ken Myer zuzuweisen:

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

Um zu überprüfen, ob das neue Foto dem Benutzerkonto zugewiesen wurde, kann Ken Myers sich bei lync 2013 anmelden, **Optionen**auswählen und dann **mein Bild**auswählen. Das neu hochgeladene Foto sollte dann als Kens persönliches Foto angezeigt werden. Alternativ können Administratoren die Fotos aller Benutzer prüfen, indem sie den Internet Explorer starten und zu einer URL der folgenden Art navigieren:

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

Wenn der Administrator das Foto mit Internet Explorer anzeigen kann, der Benutzer aber sein Foto nicht in lync 2013 anzeigen kann, deutet dies normalerweise auf ein Verbindungsproblem mit Exchange Webdienste oder dem Exchange-AutoErmittlungsdienst hin.

Beachten Sie auch, dass keine zusätzliche Konfiguration erforderlich ist, um dieses Foto in lync 2013 zur Verfügung zu stellen. Stattdessen ist das Foto sofort verfügbar, nachdem es hochgeladen wurde und das Set-UserPhoto-Cmdlet ausgeführt wurde.

</div>

<span> </span>

</div>

</div>

</div>

