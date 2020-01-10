---
title: Erstellen oder Löschen einer Ankündigung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: Sie können Ankündigungen für Ankündigungs Anwendungen in Skype for Business Server Enterprise-VoIP erstellen oder löschen. Dies wirkt sich auf den Umgang mit Anrufen an nicht zugewiesene Nummern aus.
ms.openlocfilehash: 50a55908e238dfc1e3ce3d9979d554c7115576a2
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001195"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a>Erstellen oder Löschen einer Ankündigung in Skype for Business Server

Sie können Ankündigungen für Ankündigungs Anwendungen in Skype for Business Server Enterprise-VoIP erstellen oder löschen. Dies wirkt sich auf den Umgang mit Anrufen an nicht zugewiesene Nummern aus.

Bei der Konfiguration von Ansagen wird tatsächlich konfiguriert, wie Anrufe an nicht zugewiesene Nummern verarbeitet werden sollen. Sie können eine Ansage wiedergeben, bei der es sich um eine Audiodatei oder eine TTS-Datei (Text-to-Speech, Text-zu-Sprache) handeln kann, oder Sie können den Anruf einfach an ein angegebenes Ziel durchstellen, ohne eine Ansage abzuspielen.

Sie müssen Ansagen erstellen, bevor Sie die Tabelle nicht zugewiesener Nummern definieren. Diesen Schritt führen Sie für alle Ansagen aus, die eine Audioansage, eine TTS-Ansage oder keine Ansage enthalten.

In diesem Abschnitt wird beschrieben, wie Ansagen importiert und erstellt werden. Ausführliche Informationen zur Zuweisung von Ansagen in der Tabelle nicht zugewiesener Nummern finden Sie unter [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).

## <a name="create-a-new-announcement-for-unassigned-numbers"></a>Erstellen einer neuen Ansage für nicht zugewiesene Nummern

Zum Erstellen einer neuen Ansage müssen Sie die folgenden Schritte ausführen:

1. Für Audioansagen zeichnen Sie die Audiodatei mithilfe Ihrer bevorzugten Anwendung zur Audioaufzeichnung auf.

2. Führen Sie für Audioansagen das Cmdlet **Import-CsAnnouncementFile** aus, um den Inhalt der Audiodatei in den Dateispeicher zu importieren.

3. Führen Sie das Cmdlet **New-CsAnnouncement** aus, um die Ansage zu erstellen und zu benennen. Diesen Schritt führen Sie aus, um Ansagen zu erstellen, die Audioansagen, eine Text-zu-Sprache-Ansage (Text-to-Speech, TTS) oder keine Ansage enthalten.

    > [!TIP]
    > Möglicherweise möchten Sie eine Ansage erstellen (wenn Sie z. B. Anrufe an ein bestimmtes Ziel durchstellen möchten, ohne eine Nachricht wiederzugeben.

4. Weisen Sie die neue Ansage einem Nummernbereich in der Tabelle nicht zugewiesener Nummern zu.

### <a name="to-create-a-new-announcement"></a>So erstellen Sie eine neue Ansage

1. Erstellen Sie die Audiodatei für Audioansagen.

2. Melden Sie sich bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter **Delegieren von Setup Berechtigungen**beschrieben.

3. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

4. Führen Sie für Audioansagen folgenden Befehl aus:

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. Führen Sie folgenden Befehl aus:

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    Zum Durchstellen von Anrufen an die Voicemail geben Sie „SIPAddress“ im Format „sip:Benutzername@Domänenname;opaque=app:voicemail“ ein (Beispiel: sip:bob@contoso.com;opaque=app:voicemail). Zum Durchstellen von Anrufen an eine Telefonnummer geben Sie „SIPAddress“ im Format „sip:Nummer@Domänenname;user=phone“ ein (Beispiel: sip:+ 14255550121@contoso.com;user=phone).

    Beispiel für die Festlegung einer Audioansage:

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    Beispiel für die Festlegung einer TTS-Ansage:

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   Ausführliche Informationen zu diesen Cmdlets sowie eine Liste der Sprachcodes, die im **TextToSpeechPrompt** -Parameter verwendet werden können, finden Sie unter [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).

## <a name="delete-an-announcement-for-unassigned-numbers"></a>Löschen einer Ansage für nicht zugewiesene Nummern

### <a name="to-delete-an-announcement"></a>So löschen Sie eine Ansage

1. Melden Sie sich bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter **Delegieren von Setup Berechtigungen**beschrieben.

2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

3. Listen Sie alle Ansagen in Ihrer Organisation auf. Führen Sie an der Eingabeaufforderung Folgendes aus:

   ```powershell
   Get-CsAnnouncement
   ```

4. Suchen Sie in der Ergebnisliste nach der zu löschenden Ansage und kopieren Sie die GUID. Führen Sie an der Eingabeaufforderung dann Folgendes aus:

   ```powershell
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    Beispiel:

   ```powershell
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > Ausführliche Informationen zu weiteren Optionen finden Sie unter [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) und [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).

## <a name="see-also"></a>Siehe auch

[Erstellen oder Löschen einer Ankündigung in Skype for Business Server](create-an-announcement.md)

[Import-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[Neu – CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

