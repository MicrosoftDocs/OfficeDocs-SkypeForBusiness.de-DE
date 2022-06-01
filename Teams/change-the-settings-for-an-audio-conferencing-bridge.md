---
title: Ändern der Einstellungen für eine Audiokonferenzbrücke
ms.author: heidip
author: MicrosoftHeidi
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
description: Ändern Sie die Einstellungen der Audiokonferenzbrücke, einschließlich Ein- und Ausgangsbenachrichtigungen, Wiedergeben von Namen oder Telefonnummern, Tönen und Auffordern von Anrufern, ihren Namen aufzuzeichnen.
ms.openlocfilehash: 48925c30d9ac42c76b6f00d8416d767c6e0ab14d
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823044"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Ändern der Einstellungen für eine Audiokonferenzbrücke

Wenn Sie Audiokonferenz in Microsoft 365 oder Office 365 einrichten, erhalten Sie Telefonnummern für Ihre Benutzer von einer sogenannten Audiokonferenzbrücke. Eine Konferenzbrücke kann eine oder mehr Telefonnummern umfassen. Diese Telefonnummern werden verwendet, wenn Anrufer sich in eine Besprechung einwählen. Die Telefonnummer ist am Ende der Skype for Business- oder Microsoft Teams-Besprechungseinladung zu finden.
  
Die Konferenzbrücke nimmt den Anruf an und gibt Sprachanweisungen einer automatischen Telefonzentrale aus. Je nach Ihren Einstellungen kann sie dann Benachrichtigungen wiedergeben, Anrufer auffordern, ihren Namen aufzuzeichnen, und die PIN-Einstellungen steuern. Besprechungsorganisatoren erhalten PINs, damit sie eine Besprechung starten können, wenn sie keine Skype for Business- oder Microsoft Teams-App verwenden.

  > [!IMPORTANT]
  > Der Besprechungsorganisator benötigt nur dann eine PIN, wenn die Besprechung nicht bereits von einem Benutzer einer Skype for Business- oder Microsoft Teams-App gestartet wurde. Wenn sich alle Teilnehmer in die Besprechung einwählen, benötigt der Besprechungsorganisator die PIN zum Starten der Besprechung.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Navigieren Sie im linken Navigationsbereich zu **den Brücken der Besprechungskonferenz** > .

2. Klicken Sie oben auf der Seite " **Konferenzbrücken** " auf " **Brückeneinstellungen"**.

3. Wählen Sie im **Einstellungsbereich "Brücke** " Folgendes aus:
   - **Benachrichtigungen zum Ein- und Beenden von Besprechungen** Wenn Sie dies deaktivieren, werden Benutzer, die bereits an der Besprechung teilgenommen haben, nicht benachrichtigt, wenn jemand die Besprechung ein- oder verlässt.

     Wenn Sie **Benachrichtigungen über Besprechungs- und Besprechungseintritte** aktivieren, können Sie die folgenden Optionen auswählen:

   - **Names or phone numbers** (Namen oder Telefonnummern): Wenn sich Benutzer in eine Besprechung einwählen und teilnehmen, wird ihre Telefonnummer wiedergegeben.

   - **Tones** (Töne): Wenn sich Benutzer in eine Besprechung einwählen und teilnehmen, wird ein Ton wiedergegeben.

   - **Bitten Sie Anrufer, ihren Namen aufzuzeichnen, bevor sie an der Besprechung teilnehmen.** Wenn Sie dies deaktivieren, werden Anrufer nicht aufgefordert, ihren Namen aufzuzeichnen, bevor sie an einer Besprechung teilnehmen.

4. Um die PIN-Länge für Besprechungen festzulegen, wählen Sie in der Pinlängenliste die gewünschte Anzahl von Ziffern für die **PIN** aus.

5. Um anzugeben, ob E-Mails an Ihre Benutzer gesendet werden sollen, aktivieren oder deaktivieren Sie **das automatische Senden von E-Mails an Benutzer, wenn sich die Konfiguration für Audiokonferenzen ändert**.
    Weitere Informationen finden Sie [unter "Automatisch an Benutzer gesendete E-Mails", wenn sich ihre Audiokonferenz Einstellungen in Microsoft Teams ändern](emails-sent-to-users-when-their-settings-change-in-teams.md), oder [E-Mails, die an Benutzer gesendet werden, wenn sich ihre Einstellungen in Skype for Business Online ändern](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change).

6. Klicken Sie auf **Speichern**.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) nutzen.

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mithilfe eines einzigen Administrationspunkts verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben erledigen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

  - [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [Beste Methoden zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))

- Windows PowerShell hat viele Vorteile in Bezug auf Geschwindigkeit, Einfachheit und Produktivität gegenüber der ausschließlichen Verwendung der Microsoft 365 Admin Center, z. B. wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

  - [Einführung in Windows PowerShell und Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Verwenden von Windows PowerShell zum Ausführen häufiger Skype for Business Online-Verwaltungsaufgaben](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) heruntergeladen werden.
  
## <a name="related-topics"></a>Verwandte Themen

[Einrichten von Audiokonferenzen für Microsoft Teams](set-up-audio-conferencing-in-teams.md)

[Einrichten von Audiokonferenz für Skype for Business Online](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
