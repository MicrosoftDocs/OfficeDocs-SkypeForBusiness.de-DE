---
title: Erstellen oder Löschen einer Ankündigung in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: Erstellen oder Löschen von Ankündigungen für die Ankündigungsanwendung in Skype for Business Server Enterprise-VoIP. Dies wirkt sich darauf aus, wie Anrufe an nicht zugewiesene Nummern verarbeitet werden.
ms.openlocfilehash: 3a5fdbcb5f9c4e72790f35f73cef791868634ce9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765923"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a>Erstellen oder Löschen einer Ankündigung in Skype for Business Server

Erstellen oder Löschen von Ankündigungen für die Ankündigungsanwendung in Skype for Business Server Enterprise-VoIP. Dies wirkt sich darauf aus, wie Anrufe an nicht zugewiesene Nummern verarbeitet werden.

Wenn Sie Ankündigungen konfigurieren, konfigurieren Sie tatsächlich, wie Anrufe an nicht zugewiesene Nummern verarbeitet werden sollen. Sie können eine Eingabeaufforderung wiedergeben, bei der es sich um eine Audiodatei oder eine TTS-Datei (Text-to-Speech) handeln kann, oder Sie können den Anruf einfach an ein angegebenes Ziel übertragen, ohne eine Eingabeaufforderung wiederzugeben.

Sie müssen Ankündigungen erstellen, bevor Sie die Tabelle nicht zugewiesener Nummern definieren. Sie müssen diesen Schritt für alle Ankündigungen ausführen, die eine Audioaufforderung, eine TTS-Eingabeaufforderung oder keine Eingabeaufforderung verwenden.

In diesem Thema wird beschrieben, wie Ankündigungen importiert und erstellt werden. Ausführliche Informationen zum Zuweisen von Ankündigungen in der Tabelle nicht zugewiesener Nummern finden Sie unter [Configure the Unassigned Number Table](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-unassigned-number-table).

## <a name="create-a-new-announcement-for-unassigned-numbers"></a>Erstellen einer neuen Ankündigung für nicht zugewiesene Nummern

Um eine neue Ankündigung zu erstellen, müssen Sie die folgenden Schritte ausführen:

1. Notieren Sie die Audiodatei für Audioansagen mit ihrer bevorzugten Audioaufzeichnungsanwendung.

2. Führen Sie für Audioansagen das Cmdlet **"Import-CsAnnouncementFile"** aus, um den Inhalt der Audiodatei in file Store zu importieren.

3. Führen Sie das Cmdlet **New-CsAnnouncement** aus, um die Ankündigung zu erstellen und zu benennen. Führen Sie diesen Schritt aus, um Ankündigungen mit einer Audioaufforderung, einer TTS-Eingabeaufforderung (Text-to-Speech) oder keiner Eingabeaufforderung zu erstellen.

    > [!TIP]
    > Sie können eine Ansage ohne Aufforderung erstellen (z. B. wenn Sie Anrufe an ein bestimmtes Ziel übertragen möchten, ohne eine Nachricht wiederzugeben).

4. Weisen Sie die neue Ankündigung einem Nummernbereich in der Tabelle nicht zugewiesener Nummern zu.

### <a name="to-create-a-new-announcement"></a>So erstellen Sie eine neue Ankündigung

1. Erstellen Sie für Audioansagen die Audiodatei.

2. Melden Sie sich bei dem Computer an, auf dem Skype for Business Server Verwaltungsshell als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten installiert ist, wie unter **"Stellvertretungs-Setupberechtigungen"** beschrieben.

3. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell.**

4. Führen Sie für Audioansagen Folgendes aus:

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. Führen Sie  aus.

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    Geben Sie für die Übertragung von Anrufen an Voicemail SIPAddress im Format "sip:username@domainname;opaque=app:voicemail" ein (z. B. "sip:bob@contoso.com;opaque=app:voicemail"). Wenn Sie Anrufe an eine Telefonnummer weiterleiten möchten, geben Sie SIPAddress im Format "sip:number@domainname;user=phone" ein (z. B. sip:+ 14255550121@contoso.com;user=phone).

    So geben Sie z. B. eine Audioaufforderung an:

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    So geben Sie z. B. eine TTS-Eingabeaufforderung an:

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   Weitere Informationen zu diesen Cmdlets und eine Liste der Sprachcodes, die im **TextToSpeechPrompt-Parameter** verwendet werden sollen, finden Sie unter [New-CsAnnouncement.](/powershell/module/skype/new-csannouncement?view=skype-ps)

## <a name="delete-an-announcement-for-unassigned-numbers"></a>Löschen einer Ansage für nicht zugewiesene Nummern

### <a name="to-delete-an-announcement"></a>So löschen Sie eine Ankündigung

1. Melden Sie sich bei dem Computer an, auf dem Skype for Business Server Verwaltungsshell als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten installiert ist, wie unter **"Stellvertretungs-Setupberechtigungen"** beschrieben.

2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell.**

3. Listen Sie alle Ankündigungen in Ihrer Organisation auf. Führen Sie an der Eingabeaufforderung Folgendes aus:

   ```powershell
   Get-CsAnnouncement
   ```

4. Suchen Sie in der Ergebnisliste nach der zu löschenden Ankündigung, und kopieren Sie die GUID. Führen Sie an der Eingabeaufforderung dann Folgendes aus:

   ```powershell
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    Beispiel:

   ```powershell
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > Ausführliche Informationen zu weiteren Optionen finden Sie unter ["Get-CsAnnouncement"](/powershell/module/skype/get-csannouncement?view=skype-ps) und ["Remove-CsAnnouncement".](/powershell/module/skype/remove-csannouncement?view=skype-ps)

## <a name="see-also"></a>Weitere Informationen

[Erstellen oder Löschen einer Ankündigung in Skype for Business Server](create-an-announcement.md)

[Import-CsAnnouncementFile](/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[New-CsAnnouncement](/powershell/module/skype/new-csannouncement?view=skype-ps)

[Remove-CsAnnouncement](/powershell/module/skype/remove-csannouncement?view=skype-ps)

[Get-CsAnnouncement](/powershell/module/skype/get-csannouncement?view=skype-ps)