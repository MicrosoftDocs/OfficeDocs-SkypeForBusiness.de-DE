---
title: 'Lync Server 2013: Erstellen einer Ansage'
TOCTitle: Erstellen einer Ansage
ms:assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412783(v=OCS.15)
ms:contentKeyID: 49295005
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen einer Ansage in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Zum Erstellen einer neuen Ansage müssen Sie die folgenden Schritte ausführen:

1.  Für Audioansagen zeichnen Sie die Audiodatei mithilfe Ihrer bevorzugten Anwendung zur Audioaufzeichnung auf.

2.  Führen Sie für Audioansagen das Cmdlet **Import-CsAnnouncementFile** aus, um den Inhalt der Audiodatei in den Dateispeicher zu importieren.

3.  Führen Sie das Cmdlet **New-CsAnnouncement** aus, um die Ansage zu erstellen und zu benennen. Diesen Schritt führen Sie aus, um Ankündigungen zu erstellen, die Audioansagen, eine Text-zu-Sprache-Ansage (Text-to-Speech, TTS) oder keine Ansage enthalten.
    

    > [!TIP]
    > Möglicherweise möchten Sie eine Ankündigung erstellen (wenn Sie z.&nbsp;B. Anrufe an ein bestimmtes Ziel durchstellen möchten, ohne eine Nachricht wiederzugeben.



4.  Weisen Sie die neue Ansage einem Nummernbereich in der Tabelle nicht zugewiesener Nummern zu.

In diesem Thema wird beschrieben, wie Ansagen importiert und erstellt werden. Ausführliche Informationen zur Zuweisung von Ansagen in der Tabelle nicht zugewiesener Nummern finden Sie unter [Konfigurieren der Tabelle nicht zugewiesener Nummern in Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).

## So erstellen Sie eine neue Ansage

1.  Erstellen Sie die Audiodatei für Audioansagen.

2.  Melden Sie sich auf dem Computer, auf dem die Lync Server-Verwaltungsshell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten an, wie beschrieben unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

3.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

4.  Führen Sie für Audioansagen folgenden Befehl aus:
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  Führen Sie folgenden Befehl aus:
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    Zum Durchstellen von Anrufen an die Voicemail geben Sie "SIPAddress" im Format "sip:Benutzername@Domänenname;opaque=app:voicemail" ein (Beispiel: sip:bob@contoso.com;opaque=app:voicemail). Zum Durchstellen von Anrufen an eine Telefonnummer geben Sie "SIPAddress" im Format "sip:Nummer@Domänenname;user=phone" ein (Beispiel: sip:+ 14255550121@contoso.com;user=phone).
    
    Beispiel für die Festlegung einer Audioansage:
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    Beispiel für die Festlegung einer TTS-Ansage:
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    Ausführlichere Informationen zu diesen Cmdlets und eine Liste der Sprachcodes zur Verwendung im Parameter **TextToSpeechPrompt** finden Sie unter [New-CsAnnouncement](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAnnouncement).

## Siehe auch

#### Weitere Ressourcen

[Import-CsAnnouncementFile](https://docs.microsoft.com/en-us/powershell/module/skype/Import-CsAnnouncementFile)  
[New-CsAnnouncement](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAnnouncement)  
[Konfigurieren der Tabelle nicht zugewiesener Nummern in Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md)

