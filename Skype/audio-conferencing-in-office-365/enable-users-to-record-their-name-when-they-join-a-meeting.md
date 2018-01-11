---
title: Aktivieren von Benutzern, ihren Namen aufzuzeichnen, wenn sie an eine Besprechung teilnehmen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Informationen Sie zum Aktivieren oder deaktivieren, ob die Benutzer ihre Namen beim Beitritt zu einer Besprechung festhalten können "
ms.openlocfilehash: f07bb24530e7b59ab6f54dfe2cd4eadf91def20c
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting"></a>Aktivieren von Benutzern, ihren Namen aufzuzeichnen, wenn sie an eine Besprechung teilnehmen

Wenn Sie Audiokonferenzen in Office 365 einrichten, erhalten Sie Telefonnummern und was eine audiokonferenzbrücke aufgerufen wird. Eine Konferenzbrücke kann eine oder mehrere Telefonnummern enthalten, die ein dedizierter oder gemeinsam genutzter Telefonnummer werden können.
  
Die Konferenzbrücke beantwortet einen Anruf für einen Benutzer, die in einer Besprechung mit einem Telefon einwählt. Bitten Sie die Konferenzbrücke den Anrufer mit Ansagen aus eine automatische Telefonzentrale beantwortet, und klicken Sie dann je nach ihrer Einstellungen kann wiedergeben Benachrichtigungen, Anrufer tragen Sie ihren Namen, und richten Sie die PIN-Sicherheit für Besprechungsorganisatoren. PINs auf gewährt Besprechungsorganisatoren um eine Besprechung starten können. Jedoch können Sie es einrichten, damit eine PIN erforderlich ist, um eine Besprechung zu starten.
  
## <a name="set-whether-callers-should-record-their-name"></a>Festlegen Sie, ob Anrufer ihren Namen aufzeichnen müssen sollten

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Microsoft Bridge-Einstellungen**.
    
4. Unter **Teilnahme an einer Besprechung auftreten**finden Sie unter das Kontrollkästchen **Besprechungseintrag aktivieren, und beenden Sie Benachrichtigungen aktiviert werden**.
    
  - **Ausgewählt** Anrufer werden aufgefordert, ihren Namen aufzeichnen müssen, bevor sie an einer Besprechung teilnehmen. Diese Option ist standardmäßig ausgewählt.
    
  - **Deaktiviert** Anrufer werden nicht aufgefordert, ihren Namen aufzeichnen müssen, bevor sie an einer Besprechung teilnehmen.
    
5. Nachdem Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit sparen oder dies automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) verwenden.
    
-  Windows PowerShell ist alles über das Verwalten von Benutzern und welche Benutzer tätigen dürfen. Mit Windows PowerShell können Sie eine zentrale Verwaltung Ihrer täglichen Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen, die mit Office 365 verwalten. Siehe folgende Themen, um Windows PowerShell zu verwenden:
    
  - [Warum müssen Sie mithilfe von Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell hat viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität über nur über das Office 365 Administrationscenter, beispielsweise wenn Sie ändert sich die Einstellung für viele Benutzer gleichzeitig durchführen. Informationen Sie zu dieser Vorteile in den folgenden Themen: 
    
  - [Eine Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>Verwandte Themen

[Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams](set-up-audio-conferencing.md)

