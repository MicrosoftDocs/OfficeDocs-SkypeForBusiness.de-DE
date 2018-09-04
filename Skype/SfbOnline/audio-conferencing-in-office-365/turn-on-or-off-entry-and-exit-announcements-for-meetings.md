---
title: Ein- und Ausschalten von Ein- und Ausstiegsankündigungen für Besprechungen in Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Erfahren Sie, wie Sie Ein- und Ausstiegsankündigungen in einer Skype for Business Online-Besprechung mit dem Skype for Business Admin Center ein- und ausschalten können. '
ms.openlocfilehash: 874624c3d7cfb184f4206f61cf2a91a67eb2e2cd
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779035"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>Ein- und Ausschalten von Ein- und Ausstiegsankündigungen für Besprechungen in Skype for Business Online

> [!Note]
> Informationen zu Ein- und Ausstiegsankündigungen in Microsoft Teams finden Sie unter [Ein- und Ausstiegsankündigungen für Besprechungen in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).

Wenn Sie Audiokonferenzen in Office 365 einrichten, erhalten Sie eine Audiokonferenzbrücke. Eine Konferenzbrücke kann eine oder mehrere Telefonnummern enthalten, mit denen Personen eine Skype for Business-Besprechung anrufen. 
  
Die Konferenzbrücke beantwortet einen Anruf für einen Benutzer, der mit einem Telefon in eine Besprechung einwählt. Die Konferenzbrücke antwortet dem Anrufer mit Sprachansagen einer automatischen Telefonzentrale und kann dann, abhängig von Ihren Einstellungen, Benachrichtigungen abspielen, Anrufer auffordern, ihren Namen aufzuzeichnen und die PIN-Sicherheit einrichten. Einem Organisator von Skype for Business-Besprechungen wird eine PIN zugewiesen, die es ihm ermöglicht, eine Besprechung zu starten, wenn er die Besprechung nicht mit der Skype for Business-Anwendung starten kann. Sie können jedoch festlegen, dass eine PIN nicht erforderlich ist, um eine Besprechung zu starten.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Festlegen von Optionen für die Besprechungsteilnahme
    
1. in der linken Navigation des **Skype for Business Admin Center**, wechseln Sie zu **Audiokonferenz** > **Microsoft Bridge-Einstellungen**.
    
2. Unter **Besprechungsteilnahme erfahren** wählen oder löschen Sie **Aktivieren von Benachrichtigungen zum Ein- und Ausstieg bei Besprechungen**. Diese Option ist standardmäßig aktiviert. Wenn Sie das Kontrollkästchen deaktivieren, werden Benutzer, die bereits an der Besprechung teilnehmen, nicht benachrichtigt, wenn ein Teilnehmer der Besprechung beitritt oder diese verlässt.
    
3. Unter **Einstieg/Ausstieg-Ansagetyp** wählen Sie **Namen oder Telefonnummern** oder **Töne**.
    
4. Aktivieren oder deaktivieren Sie **Anrufer bitten, ihren Namen aufzuzeichnen, bevor sie dem Meeting beitreten**.
    
5. Nachdem Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) nutzen.
    
-  In Bezug auf Windows PowerShell dreht sich bei Skype for Business Online alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Optimale Möglichkeiten zur Verwaltung von Office 365 mit Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet viele Vorteile in Bezug auf Geschwindigkeit, Einfachheit und Produktivität gegenüber der ausschließlichen Verwendung des Office 365 Admin Center, beispielsweise wenn Sie Einstellungen für viele Benutzer gleichzeitig ändern. Erfahren Sie mehr über diese Vorteile in den folgenden Themen: 
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>Verwandte Themen

[Allgemeine Fragen zur Audiokonferenz](/MicrosoftTeams/audio-conferencing-common-questions)
