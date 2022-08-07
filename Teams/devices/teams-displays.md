---
title: Microsoft Teams-Displays
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
- Teams_ITAdmin_Devices
search.appverid: MET150
ms.localizationpriority: medium
description: Dieser Artikel enthält eine Übersicht über und Features, die von Microsoft Teams-Displays unterstützt werden.
ms.openlocfilehash: 18b8219a3eef391170c7321ae994d79f1b73f016
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268770"
---
# <a name="microsoft-teams-displays"></a>Microsoft Teams-Displays

Microsoft Teams-Displays sind eine Kategorie von all-in-one dedizierten Teams-Geräten, die über einen Umgebungs-Touchscreen und eine freihändige Umgebung verfügen, die von Cortana unterstützt wird. Dieser Artikel enthält eine Übersicht über Teams-Anzeigen und kann Ihnen bei der Planung, Bereitstellung und Verwaltung von Teams-Anzeigen in Ihrer Organisation helfen.

Teams-Displays bringen Ihren bevorzugten Teams-Features&ndash;Chat, Besprechungen, Anrufe, Kalender und Dateien&ndash;auf einem einzigen Gerät zusammen. Bei Teams-Displays können Benutzer ein Mikrofon, eine Kamera und Lautsprecher (oder ein Bluetooth-Headset) für eine zuverlässige Anruf- und Besprechungserfahrung verwenden. Teams-Displays können in die Windows-PCs der Benutzer integriert werden, um eine Begleiterfahrung zu bieten, die eine nahtlose geräteübergreifende Interaktion ermöglicht.

Weitere Informationen finden Sie in den [Displays "Erste Schritte mit Teams"](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6).

## <a name="features-supported-by-teams-displays"></a>Von Teams unterstützte Features werden angezeigt

Zusätzlich zu den [von Teams-Telefonen unterstützten Features](phones-for-teams.md#features-supported-by-teams-phones) sind die folgenden Features nur für Teams-Displays verfügbar:

- **Dedizierte Anzeigen für Teams** Benutzer können auf alle zentralen Teams-Features zugreifen, einschließlich Chat, Besprechungen, Anrufe, Teams und Kanäle, Dateien und mehr.
- **Umgebungsumgebung** Benutzer können mit immer aktivierten und auf einen Blick sichtbaren Displays ganz einfach über ihre Arbeit auf dem Laufenden bleiben, um wichtige Aktivitäten und Benachrichtigungen zu sehen, ohne auf ihrem primären Arbeitsgerät kontextabhängig zu wechseln. Benutzer können Teams-Anzeigen auch personalisieren, indem sie den Hintergrund über Einstellungen anpassen.
- **Freisprechen mit Cortana** Benutzer können mithilfe ihrer Stimme mit Teams-Displays interagieren, um mühelos an Besprechungen teilzunehmen und an Besprechungen teilzunehmen, Antworten auf einen Teams-Chat zu diktieren, zu überprüfen, was sich im Kalender befindet und vieles mehr.
- **Hinterlassen einer Notiz auf dem Sperrbildschirm** Gäste können Audio-, Video- und Textnotizen hinterlassen, und Benutzer können die von Gästen hinterlassenen Notizen überprüfen und sehen, wer angehalten wird.  

## <a name="required-licenses"></a>Erforderliche Lizenzen

Teams-Lizenzen können als Teil von [Microsoft 365- und Office 365-Abonnements](/office365/servicedescriptions/teams-service-description) erworben werden. Weitere Informationen zu den erforderlichen Lizenzen für die Verwendung von Teams-Displays finden Sie unter [Sprach- und Videoanrufe mit Microsoft Teams](https://products.office.com/microsoft-teams/voice-calling).

Weitere Informationen zum Abrufen von Teams finden Sie Gewusst wie [Zugriff auf Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>Bereitstellen von Teams-Anzeigen mithilfe von Intune

Weitere Informationen zum Bereitstellen von Teams-Displays mithilfe von Intune finden Sie unter [Bereitstellen von Teams-Telefonen und Teams-Displays](phones-displays-deploy.md).

## <a name="manage-teams-displays-in-your-organization"></a>Verwalten von Teams-Anzeigen in Ihrer Organisation

Um Ihre Teams-Anzeigegeräte zu verwalten, wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **den Teams-Anzeigen**. Von hier aus können Sie das Gerätekonfigurationsprofil ändern, Updates verwalten, Geräte neu starten, Gerätetags hinzufügen und entfernen und vieles mehr. Weitere Informationen finden [Sie unter Verwalten Ihrer Geräte in Teams](device-management.md).

## <a name="set-up-hot-desking-on-teams-displays"></a>Einrichten von "Hot Desking" auf Teams-Displays

Hot Desking ermöglicht es Personen in Ihrer Organisation, temporäre Arbeitsbereiche im Voraus über Teams und Outlook oder vom Gerät selbst zu reservieren. Wenn hot desking aktiviert ist, werden Benutzer, die sich bei Teams anmelden, mit ihren Microsoft 365-Anmeldeinformationen angezeigt, um auf ihre Besprechungen, Chats und Dateien zuzugreifen. Wenn sie sich abmelden, werden alle ihre persönlichen Informationen vom Gerät entfernt.

Um zu beginnen, müssen Sie Microsoft Teams-Räume Standard Lizenzen erwerben und Ressourcenkonten für jede Teams-Anzeige erstellen. Siehe [Erstellen von Ressourcenkonten für Räume und freigegebene Teams-Geräte](../rooms/with-office-365.md) zum Erstellen von Ressourcenkonten.

Nachdem Sie Ressourcenkonten erstellt haben, können Sie eine Richtlinie erstellen und zuweisen, um hot desking zu aktivieren. Weitere Informationen finden Sie unter [New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) .

> [!IMPORTANT]
> Da Teams-Displays mit hot desking von mehreren Personen in freigegebenen Arbeitsbereichen verwendet werden, können sich Regeln für bedingten Zugriff und andere Identitätskonfigurationen in Ihrer Umgebung, z. B. die mehrstufige Authentifizierung, auf diese Geräte auswirken und Anmeldeprobleme verursachen. Anleitungen zum Sichern freigegebener Geräte finden Sie unter ["Bewährte Methoden für die Authentifizierung" für freigegebene Android-Geräte von Teams](authentication-best-practices-for-android-devices.md).

## <a name="upgrade-teams-phones-to-teams-displays"></a>Aktualisieren von Teams-Telefonen auf Teams-Displays

Teams-Displays sind die Weiterentwicklung von Teams-Telefonen. Sie können Teams-Telefone in Ihrer Organisation über das Microsoft Teams Admin Center auf Teams-Displays aktualisieren. Diese Option ist nur für Telefone verfügbar, die ein Upgrade auf Teams-Displays unterstützen. Weitere Informationen finden Sie unter ["Aktualisieren von Teams-Telefonen auf Teams-Displays](upgrade-phones-to-displays.md)".

## <a name="see-also"></a>Siehe auch

[Einführung in Microsoft Teams-Displays](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams Marketplace](https://office.com/teamsdevices)

[Telefone für Teams](phones-for-teams.md)

[FÜR Microsoft Teams zertifizierte IP-Telefone](teams-ip-phones.md)

[Aktualisieren von IP-Telefonen auf Teams-Displays](upgrade-phones-to-displays.md)

[Cortana-Sprachunterstützung in Teams](../cortana-in-teams.md)