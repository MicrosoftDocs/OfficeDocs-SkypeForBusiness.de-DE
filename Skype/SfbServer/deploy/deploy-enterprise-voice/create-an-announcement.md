---
title: Erstellen oder Löschen einer Ansage in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: Erstellen oder löschen Sie Ansagen für die Ankündigungsanwendung in Skype for Business Server Enterprise-VoIP. Dies wirkt sich auf die Art und Weise aus, wie Anrufe an nicht zugewiesene Nummern verarbeitet werden.
ms.openlocfilehash: 9f2b4fcda8e98d4b939b6b443da875dbe153546c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824905"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a>Erstellen oder Löschen einer Ansage in Skype for Business Server

Erstellen oder löschen Sie Ansagen für die Ankündigungsanwendung in Skype for Business Server Enterprise-VoIP. Dies wirkt sich auf die Art und Weise aus, wie Anrufe an nicht zugewiesene Nummern verarbeitet werden.

Beim Konfigurieren von Ansagen konfigurieren Sie, wie Anrufe an nicht zugewiesene Nummern verarbeitet werden sollen. Sie können eine Eingabeaufforderung wiedergeben, bei der es sich um eine Audiodatei oder eine Text-zu-Sprache-Datei (Text-to-Speech, TTS) oder einfach um eine Übergabe des Anrufs an ein angegebenes Ziel ohne Wiedergabe einer Ansforderung geht.

Sie müssen Ankündigungen erstellen, bevor Sie die Tabelle nicht zugewiesener Nummern definieren. Sie müssen diesen Schritt für alle Ansagen ausführen, die eine Audioansage, eine TTS-Ansage oder keine Ansage verwenden.

In diesem Thema wird das Importieren und Erstellen von Ansagen beschrieben. Weitere Informationen zum Zuweisen von Ansagen in der Tabelle nicht zugewiesener Nummern finden Sie unter "Konfigurieren der Tabelle nicht [zugewiesener Nummern".](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx)

## <a name="create-a-new-announcement-for-unassigned-numbers"></a>Erstellen einer neuen Ansage für nicht zugewiesene Nummern

Zum Erstellen einer neuen Ankündigung müssen Sie die folgenden Schritte ausführen:

1. Für Audioaufforderungen zeichnen Sie die Audiodatei mithilfe Ihrer bevorzugten Audioaufzeichnungsanwendung auf.

2. Führen Sie für Audioansagen das **Cmdlet "Import-CsAnnouncementFile"** aus, um den Inhalt der Audiodatei in den Dateispeicher zu importieren.

3. Führen Sie **das Cmdlet "New-CsAnnouncement"** aus, um die Ansage zu erstellen und zu benennen. Führen Sie diesen Schritt aus, um Ansagen mit einer Audioansage, einer Text-zu-Sprache-Ansage (Text-to-Speech, TTS) oder ohne Ansage zu erstellen.

    > [!TIP]
    > Möglicherweise möchten Sie eine Ansage ohne Ansage erstellen (z. B. wenn Sie Anrufe an ein bestimmtes Ziel übertragen möchten, ohne eine Nachricht wieder zu wiedergeben).

4. Weisen Sie die neue Ansage einem Nummernbereich in der Tabelle nicht zugewiesener Nummern zu.

### <a name="to-create-a-new-announcement"></a>So erstellen Sie eine neue Ansage

1. Erstellen Sie für Audioaufforderungen die Audiodatei.

2. Melden Sie sich bei dem Computer, auf dem Skype for Business Server Management Shell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten an, wie unter "Berechtigungen zum Delegieren des **Setups" beschrieben.**

3. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**

4. Führen Sie für Audioaufforderungen:

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. Führen Sie dies aus:

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    Geben Sie zum Übertragen von Anrufen an Voicemail "SIPAddress" im Format "sip:username@domainname;opaque=app:voicemail" ein (z. B. "sip:bob@contoso.com;opaque=app:voicemail"). Geben Sie zum Übertragen von Anrufen an eine Telefonnummer "SIPAddress" im Format "sip:number@domainname;user=phone" ein (z. B. "sip:+ 14255550121@contoso.com;user=phone").

    So geben Sie beispielsweise eine Audioaufforderung an:

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    So geben Sie beispielsweise eine TTS-Eingabeaufforderung an:

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   Weitere Informationen zu diesen Cmdlets und eine Liste der im Parameter **"TextToSpeechPrompt"** zu verwendenden Sprachcodes finden Sie unter [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).

## <a name="delete-an-announcement-for-unassigned-numbers"></a>Löschen einer Ansage für nicht zugewiesene Nummern

### <a name="to-delete-an-announcement"></a>So löschen Sie eine Ankündigung

1. Melden Sie sich bei dem Computer, auf dem Skype for Business Server Management Shell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten an, wie unter "Berechtigungen zum Delegieren des **Setups" beschrieben.**

2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**

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
    > Weitere Informationen zu weiteren Optionen finden Sie unter ["Get-CsAnnouncement"](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) und ["Remove-CsAnnouncement".](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

## <a name="see-also"></a>Weitere Informationen

[Erstellen oder Löschen einer Ansage in Skype for Business Server](create-an-announcement.md)

[Import-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

