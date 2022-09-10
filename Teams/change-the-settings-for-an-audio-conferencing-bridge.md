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
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: Ändern Sie die Einstellungen der Audiokonferenzbrücke, einschließlich Ein- und Ausgangsbenachrichtigungen, Wiedergeben von Namen oder Telefonnummern, Tönen und Auffordern von Anrufern, ihren Namen aufzuzeichnen.
ms.openlocfilehash: d9853826d9a93c5794017185f561b9d6a6cd1ffb
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641786"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Ändern der Einstellungen für eine Audiokonferenzbrücke

Wenn Sie Audiokonferenzen in Microsoft 365 oder Office 365 einrichten, erhalten Sie Telefonnummern für Ihre Benutzer von einer sogenannten Audiokonferenzbrücke. Eine Konferenzbrücke kann eine oder mehr Telefonnummern umfassen. Diese Telefonnummern werden verwendet, wenn Anrufer sich in eine Besprechung einwählen. Die Telefonnummer ist unten in der Teams-Besprechungseinladung enthalten.
  
Die Konferenzbrücke beantwortet einen Anruf und fordert den Anrufer mit Sprachansagen mithilfe einer automatischen Telefonzentrale für Besprechungen auf. Je nach Ihren Einstellungen kann sie dann Benachrichtigungen wiedergeben, Anrufer auffordern, ihren Namen aufzuzeichnen, und die PIN-Einstellungen steuern. PINs werden Besprechungsorganisatoren übergeben, damit sie eine Besprechung starten können, wenn sie keine Microsoft Teams-App verwenden.

  > [!IMPORTANT]
  > Eine PIN ist nur dann für den Besprechungsorganisator erforderlich, wenn ein Benutzer der Teams-App die Besprechung noch nicht gestartet hat. Wenn sich alle Teilnehmer in die Besprechung einwählen, benötigt der Besprechungsorganisator die PIN zum Starten der Besprechung.

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
    Weitere Informationen finden Sie [unter E-Mails, die automatisch an Benutzer gesendet werden, wenn sich ihre Audiokonferenzeinstellungen in Microsoft Teams ändern](emails-sent-to-users-when-their-settings-change-in-teams.md) .

6. Klicken Sie auf **Speichern**.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) nutzen.

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mit einem einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben erledigen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

  - [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [Beste Methoden zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))

- Windows PowerShell hat viele Vorteile in Bezug auf Geschwindigkeit, Einfachheit und Produktivität gegenüber der ausschließlichen Verwendung der Microsoft 365 Admin Center, z. B. wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

  - [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

  - [Installieren des Microsoft Teams PowerShell-Moduls](teams-powershell-install.md)
  
## <a name="related-topics"></a>Verwandte Themen

[Einrichten von Audiokonferenzen für Microsoft Teams](set-up-audio-conferencing-in-teams.md)
