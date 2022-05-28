---
title: Microsoft Teams wird angezeigt
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
ms.localizationpriority: medium
description: Dieser Artikel enthält eine Übersicht über und Features, die von Microsoft Teams-Displays unterstützt werden.
ms.openlocfilehash: 4b724370ff348f41b8d4c4406a218e1dd1ba0709
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2022
ms.locfileid: "65760867"
---
# <a name="microsoft-teams-displays"></a>Microsoft Teams wird angezeigt

Microsoft Teams displays are a category of all-in-one dedicated Teams devices that feature an ambient touchscreen and a hands-free experience powered by Cortana. Dieser Artikel enthält eine Übersicht über Teams Anzeigen und kann Ihnen bei der Planung, Bereitstellung und Verwaltung Teams Anzeigen in Ihrer Organisation helfen.

Teams-Displays bringen Ihre bevorzugten Teams Features&ndash;Chat, Besprechungen, Anrufe, Kalender und Dateien&ndash;auf einem einzigen Gerät zusammen. Mit Teams-Displays können Benutzer ein Mikrofon, eine Kamera und Lautsprecher (oder Bluetooth Headset) für eine zuverlässige Anruf- und Besprechungserfahrung verwenden. Teams-Displays können in die Windows PCs der Benutzer integriert werden, um eine Begleiterfahrung zu bieten, die eine nahtlose geräteübergreifende Interaktion ermöglicht.

Weitere Informationen finden Sie [in Erste Schritte mit Teams Anzeigen](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6).

## <a name="features-supported-by-teams-displays"></a>Von Teams-Displays unterstützte Features

Zusätzlich zu den [von Teams Smartphones unterstützten Features](phones-for-teams.md#features-supported-by-teams-phones) sind die folgenden Features für Teams Displays eindeutig:

- **Dedizierte Displays für Teams** Benutzer können auf alle Kernfunktionen Teams zugreifen, einschließlich Chat, Besprechungen, Anrufe, Teams und Kanäle, Dateien und mehr.
- **Umgebungsumgebung** Benutzer können mit immer aktivierten und auf einen Blick sichtbaren Displays ganz einfach über ihre Arbeit auf dem Laufenden bleiben, um wichtige Aktivitäten und Benachrichtigungen zu sehen, ohne auf ihrem primären Arbeitsgerät kontextabhängig zu wechseln. Benutzer können auch Teams Anzeigen personalisieren, indem sie den Hintergrund über Einstellungen anpassen.
- **Freisprechen mit Cortana** Benutzer können mit Teams Anzeigen mithilfe ihrer Stimme interagieren, um mühelos an Besprechungen teilzunehmen und an Besprechungen teilzunehmen, Antworten auf einen Teams Chat zu diktieren, zu überprüfen, was sich im Kalender befindet und vieles mehr.
- **Hinterlassen einer Notiz auf dem Sperrbildschirm** Gäste können Audio-, Video- und Textnotizen hinterlassen, und Benutzer können die von Gästen hinterlassenen Notizen überprüfen und sehen, wer angehalten wird.  

## <a name="required-licenses"></a>Erforderliche Lizenzen

Teams Lizenzen können im Rahmen von [Microsoft 365- und Office 365-Abonnements](/office365/servicedescriptions/teams-service-description) erworben werden. Weitere Informationen zu den erforderlichen Lizenzen für die Verwendung Teams Anzeigen finden Sie unter [Sprach- und Videoanrufe mit Microsoft Teams](https://products.office.com/microsoft-teams/voice-calling).

Weitere Informationen zum Abrufen von Teams finden Sie Gewusst wie [Zugriff auf Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>Bereitstellen Teams Anzeigen mithilfe von Intune

Weitere Informationen zum Bereitstellen Teams Anzeigen mithilfe von Intune finden [Sie unter Bereitstellen Teams Smartphones und Teams Displays](phones-displays-deploy.md).

## <a name="manage-teams-displays-in-your-organization"></a>Verwalten Teams Anzeigen in Ihrer Organisation

Um Ihre Teams Anzeigegeräte zu verwalten, wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **Teams Anzeigen**. Von hier aus können Sie das Gerätekonfigurationsprofil ändern, Updates verwalten, Geräte neu starten, Gerätetags hinzufügen und entfernen und vieles mehr. Weitere Informationen finden Sie unter [Verwalten Ihrer Geräte in Teams](device-management.md).

## <a name="set-up-hot-desking-on-teams-displays"></a>Einrichten von Hot-Desking auf Teams Anzeigen

Mit hot desking können Personen in Ihrer Organisation temporäre Arbeitsbereiche im Voraus über Teams und Outlook oder vom Gerät selbst reservieren. Wenn hot desking aktiviert ist, melden sich Benutzer bei Teams wird mit ihren Microsoft 365 Anmeldeinformationen angezeigt, um auf ihre Besprechungen, Chats und Dateien zuzugreifen. Wenn sie sich abmelden, werden alle ihre persönlichen Informationen vom Gerät entfernt.

Um zu beginnen, müssen Sie Microsoft Teams-Räume Standard Lizenzen erwerben und Ressourcenkonten für jede Teams Anzeigen erstellen. Siehe [Erstellen von Ressourcenkonten für Räume und freigegebene Teams Geräten](../rooms/with-office-365.md) zum Erstellen von Ressourcenkonten.

Nachdem Sie Ressourcenkonten erstellt haben, können Sie eine Richtlinie erstellen und zuweisen, um hot desking zu aktivieren. Weitere Informationen finden Sie unter [New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) .

> [!IMPORTANT]
> Da Teams mit hot desking in freigegebenen Arbeitsbereichen von mehreren Personen verwendet werden, können Regeln für bedingten Zugriff und andere Identitätskonfigurationen in Ihrer Umgebung, z. B. die mehrstufige Authentifizierung, sich auf diese Geräte auswirken und Anmeldeprobleme verursachen. Anleitungen zum Sichern freigegebener Geräte finden Sie unter ["Bewährte Methoden für die Authentifizierung" für freigegebene Teams Android Geräte](authentication-best-practices-for-android-devices.md).

## <a name="upgrade-teams-phones-to-teams-displays"></a>Aktualisieren Teams Smartphones auf Teams Anzeigen

Teams displays is the evolution of Teams phones. Sie können Teams Smartphones in Ihrer Organisation mithilfe des Microsoft Teams Admin Centers auf Teams Anzeigen aktualisieren. Diese Option ist nur für Smartphones verfügbar, die ein Upgrade auf Teams Anzeigen unterstützen. Weitere Informationen finden Sie [unter Upgrade Teams Smartphones auf Teams Anzeigen](upgrade-phones-to-displays.md).

## <a name="see-also"></a>Siehe auch

[Einführung in Microsoft Teams Displays](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams Marketplace](https://office.com/teamsdevices)

[Telefone für Teams](phones-for-teams.md)

[IP-Telefone, die für Microsoft Teams zertifiziert sind](teams-ip-phones.md)

[Aktualisieren von IP-Telefonen auf Teams Anzeigen](upgrade-phones-to-displays.md)

[Cortana Sprachunterstützung in Teams](../cortana-in-teams.md)