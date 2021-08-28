---
title: Ändern der Einstellungen für eine Audiokonferenzbrücke
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: Ändern Sie die Einstellungen der Audiokonferenzbrücke, einschließlich Eingangs- und Ausgangsbenachrichtigungen, Wiedergabe von Namen oder Telefonnummern, Töne und Aufforderungsanrufer, um ihren Namen zu notieren.
ms.openlocfilehash: 434142eb0e7d8cd4759eec180e903eaecad47525
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58607852"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Ändern der Einstellungen für eine Audiokonferenzbrücke

Wenn Sie Audiokonferenzen in Microsoft 365 oder Office 365 einrichten, erhalten Sie von der so genannten Audiokonferenzbrücke Telefonnummern für Ihre Benutzer. Eine Konferenzbrücke kann eine oder mehrere Telefonnummern umfassen. Diese Telefonnummern werden verwendet, wenn Anrufer sich in eine Besprechung einwählen. Die Telefonnummer ist am Ende der Skype for Business- oder Microsoft Teams-Besprechungseinladung zu finden.
  
Die Konferenzbrücke nimmt den Anruf an und gibt Sprachanweisungen einer automatischen Telefonzentrale aus. Je nach Ihren Einstellungen kann sie dann Benachrichtigungen wiedergeben, Anrufer auffordern, ihren Namen aufzuzeichnen, und die PIN-Einstellungen steuern. Besprechungsorganisatoren erhalten PINs, damit sie eine Besprechung starten können, wenn sie keine Skype for Business- oder Microsoft Teams-App verwenden.

  > [!IMPORTANT]
  > Der Besprechungsorganisator benötigt nur dann eine PIN, wenn die Besprechung nicht bereits von einem Benutzer einer Skype for Business- oder Microsoft Teams-App gestartet wurde. Wenn sich alle Teilnehmer in die Besprechung einwählen, benötigt der Besprechungsorganisator die PIN zum Starten der Besprechung. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Symbol, das das Microsoft Teams-Logo zeigt](media/teams-logo-30x30.png) Verwenden des Microsoft Teams Admin Centers

1. Navigieren Sie in der linken Navigationsleiste zu **Konferenzbrücken**  >  **für Besprechungen.** 

2. Klicken Sie oben auf der **Seite Konferenzbrücken** auf **Einstellungen für Brücke.** 

3. Wählen Sie **im Bereich Einstellungen der** Brücke: 
   - **Benachrichtigungen über Besprechungs- und -abgänge** Wenn Sie dies deaktivieren, werden Benutzer, die bereits an der Besprechung teilgetreten sind, nicht benachrichtigt, wenn jemand der Besprechung beitritt oder diese verlässt.
    
     Wenn Sie Benachrichtigungen über den Zugang **zur Besprechung und das** Beenden der Besprechung aktivieren, können Sie die folgenden Optionen auswählen:
    
   - **Names or phone numbers** (Namen oder Telefonnummern): Wenn sich Benutzer in eine Besprechung einwählen und teilnehmen, wird ihre Telefonnummer wiedergegeben.
    
   - **Tones** (Töne): Wenn sich Benutzer in eine Besprechung einwählen und teilnehmen, wird ein Ton wiedergegeben.
      
   - **Bitten Sie Anrufer, ihren Namen vor der Teilnahme an der Besprechung aufzeichnen zu können.** Wenn Sie dies deaktivieren, werden Anrufer nicht aufgefordert, ihren Namen einzuschalten, bevor sie an einer Besprechung teilnehmen.

4. Wenn Sie die PIN-Länge für Besprechungen festlegen möchten, wählen Sie in der Liste **PIN-Länge** die Anzahl der Ziffern für die PIN aus.

5. Um anzugeben, ob E-Mails an Ihre Benutzer gesendet werden sollen, aktivieren oder deaktivieren Sie Automatisch E-Mails an Benutzer senden, wenn sich **deren Audiokonferenzkonfiguration ändert.**
    Weitere Informationen finden Sie unter E-Mails, die automatisch an Benutzer gesendet werden, wenn sich ihre [Audiokonferenzeinstellungen in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) ändern, oder E-Mails, die an Benutzer gesendet werden, wenn sich ihre Einstellungen in Skype for Business [Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) ändern.
 
6. Klicken Sie auf **Speichern**. 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) nutzen.
    
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie ihre Microsoft 365 oder Office 365 über einen einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell hat gegenüber der ausschließlichen Verwendung der Microsoft 365 Admin Center viele Vorteile in der Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen: 
    
  - [Einführung in Windows PowerShell und Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>Verwandte Themen

[Einrichten von Audiokonferenzen für Microsoft Teams](set-up-audio-conferencing-in-teams.md)

[Einrichten von Audiokonferenzen für Skype for Business Online](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)