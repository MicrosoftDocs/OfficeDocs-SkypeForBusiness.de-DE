---
title: 'Lync Server 2013: Erstellen einer Ansage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create an announcement
ms:assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412783(v=OCS.15)
ms:contentKeyID: 48185005
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec4384457ae0121893f0413d674368877e5396f4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-an-announcement-in-lync-server-2013"></a>Erstellen einer Ansage in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Zum Erstellen einer neuen Ansage müssen Sie die folgenden Schritte ausführen:

1.  Für Audioansagen zeichnen Sie die Audiodatei mithilfe Ihrer bevorzugten audiorecording-Anwendung auf.

2.  Führen Sie für Audioansagen das Cmdlet **Import-CsAnnouncementFile** aus, um den Inhalt der Audiodatei in Dateispeicher zu importieren.

3.  Führen Sie das Cmdlet **New-CsAnnouncement** aus, um die Ansage zu erstellen und zu benennen. Führen Sie diesen Schritt aus, um Ankündigungen mit einer Eingabeaufforderung, einer TTS-Ansage (Text-to-Speech) oder keine Eingabeaufforderung zu erstellen.
    
    <div>
    

    > [!TIP]  
    > Möglicherweise möchten Sie eine Ansage ohne Eingabeaufforderung erstellen (beispielsweise, wenn Sie Anrufe an ein bestimmtes Ziel übertragen möchten, ohne eine Nachricht wiedergeben zu müssen).

    
    </div>

4.  Weisen Sie die neue Ansage einem Nummernbereich in der Tabelle nicht zugewiesener Nummern zu.

In diesem Thema wird das Importieren und Erstellen von Ankündigungen beschrieben. Ausführliche Informationen zum Zuweisen von Ankündigungen in der Tabelle nicht zugewiesene Nummern finden Sie unter [Konfigurieren der Tabelle nicht zugewiesene Nummern in lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).

<div>

## <a name="to-create-a-new-announcement"></a>So erstellen Sie eine neue Ansage

1.  Erstellen Sie für Audioansagen die Audiodatei.

2.  Melden Sie sich an dem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.

3.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

4.  Führen Sie für Audioansagen Folgendes aus:
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  Ausführen
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    Geben Sie SIPAddress im Format SIP: username@Domainname; Opaque = App: Voicemail ein (beispielsweise SIP: Bob@contoso. com; Opaque = App: Voicemail), um Anrufe an Voicemail weiterzuleiten. Geben Sie zum Übertragen von Anrufen an eine Telefonnummer SIPAddress im Format SIP: Number@Domainname; User = Phone ein (beispielsweise SIP: + 14255550121@contoso. com; User = Phone).
    
    Beispielsweise zum Angeben einer Audioansage:
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    Geben Sie beispielsweise eine TTS-Eingabeaufforderung an:
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    Weitere Details zu diesen Cmdlets und eine Liste der Sprachcodes, die im Parameter **TextToSpeechPrompt** verwendet werden sollen, finden Sie unter [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Import-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[Konfigurieren der Tabelle nicht zugewiesener Nummern in lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

