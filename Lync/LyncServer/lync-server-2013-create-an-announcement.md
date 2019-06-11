---
title: 'Lync Server 2013: Erstellen einer Ankündigung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create an announcement
ms:assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412783(v=OCS.15)
ms:contentKeyID: 48185005
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b80210787a8261d122fa7508807ab995279c7d0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-an-announcement-in-lync-server-2013"></a>Erstellen einer Ankündigung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Zum Erstellen einer neuen Ansage müssen Sie die folgenden Schritte ausführen:

1.  Für Audioansagen zeichnen Sie die Audiodatei mithilfe Ihrer bevorzugten Anwendung zur Audioaufzeichnung auf.

2.  Führen Sie für Audioansagen das Cmdlet **Import-CsAnnouncementFile** aus, um den Inhalt der Audiodatei in den Dateispeicher zu importieren.

3.  Führen Sie das Cmdlet **New-CsAnnouncement** aus, um die Ansage zu erstellen und zu benennen. Diesen Schritt führen Sie aus, um Ansagen zu erstellen, die Audioansagen, eine Text-zu-Sprache-Ansage (Text-to-Speech, TTS) oder keine Ansage enthalten.
    
    <div>
    

    > [!TIP]  
    > Möglicherweise möchten Sie eine Ansage erstellen (wenn Sie z. B. Anrufe an ein bestimmtes Ziel durchstellen möchten, ohne eine Nachricht wiederzugeben.

    
    </div>

4.  Weisen Sie die neue Ansage einem Nummernbereich in der Tabelle nicht zugewiesener Nummern zu.

In diesem Abschnitt wird beschrieben, wie Ansagen importiert und erstellt werden. Details zum Zuweisen von Ankündigungen in der Tabelle "nicht zugewiesene Nummern" finden Sie unter [Konfigurieren der Tabelle "nicht zugewiesene Nummern" in lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).

<div>

## <a name="to-create-a-new-announcement"></a>So erstellen Sie eine neue Ansage

1.  Erstellen Sie die Audiodatei für Audioansagen.

2.  Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter Delegieren von [Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.

3.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

4.  Führen Sie für Audioansagen folgenden Befehl aus:
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  Führen Sie folgenden Befehl aus:
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    Zum Durchstellen von Anrufen an die Voicemail geben Sie „SIPAddress“ im Format „sip:Benutzername@Domänenname;opaque=app:voicemail“ ein (Beispiel: sip:bob@contoso.com;opaque=app:voicemail). Zum Durchstellen von Anrufen an eine Telefonnummer geben Sie „SIPAddress“ im Format „sip:Nummer@Domänenname;user=phone“ ein (Beispiel: sip:+ 14255550121@contoso.com;user=phone).
    
    Beispiel für die Festlegung einer Audioansage:
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    Beispiel für die Festlegung einer TTS-Ansage:
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    Ausführliche Informationen zu diesen Cmdlets sowie eine Liste der Sprachcodes, die im **TextToSpeechPrompt** -Parameter verwendet werden können, finden Sie unter [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Import-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[Neu – CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[Konfigurieren der Tabelle nicht zugewiesener Nummern in Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

