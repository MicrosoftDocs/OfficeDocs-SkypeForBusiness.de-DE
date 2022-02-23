---
title: Microsoft Teams anzeigen
ms.author: czawideh
author: cazawideh
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
description: Dieser Artikel bietet eine Übersicht über die von der Microsoft Teams unterstützten Features.
ms.openlocfilehash: 8c8004edd12042ca27e77e545f23b8770f8d1899
ms.sourcegitcommit: e9b0a274fdfee3d5bc8211cb099155546b281fe0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2022
ms.locfileid: "62926328"
---
# <a name="microsoft-teams-displays"></a>Microsoft Teams anzeigen

Microsoft Teams-Displays sind eine Kategorie von all-in-one-dedizierten Teams-Geräten, die über einen Umgebungs-Touchscreen und eine freisprechnde Besprechung verfügen, auf der die Geräte Cortana. Dieser Artikel bietet eine Übersicht über Teams anzeigen und kann Ihnen beim Planen, Bereitstellen und Verwalten Teams Anzeigen in Ihrer Organisation helfen.

Teams zeigt Ihre bevorzugten&ndash; Funktionen Teams chats, Besprechungen, Anrufe,&ndash; Kalender und Dateien auf einem einzigen Gerät zusammen. Bei Teams können Benutzer ein Mikrofon, eine Kamera und Lautsprecher (oder Bluetooth Headset) verwenden, um zuverlässige Anrufe und Besprechungen zu ermöglichen. Teams-Displays sind in die App Windows-PCs integriert, um eine Begleiterfahrung zu bieten, die eine nahtlose geräteübergreifende Interaktion ermöglicht.

Weitere Informationen finden Sie unter [Erste Schritte mit Teams Anzeigen](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6).

## <a name="features-supported-by-teams-displays"></a>Von Bildschirmen unterstützte Teams

Zusätzlich zu den von [Ihren Smartphones unterstützten Teams](phones-for-teams.md#features-supported-by-teams-phones) sind die folgenden Features für alle Teams eindeutig:

- **Dedizierte Displays für Teams** Benutzer können auf alle grundlegenden Teams-Features zugreifen, einschließlich Chats, Besprechungen, Anrufen, Teams und Kanälen, Dateien und mehr.
- **Umgebungserlebnis** Benutzer können mit ständig sichtbaren und über einen Blick sichtbaren Anzeigen ganz einfach den Überblick über ihre Arbeit behalten, um wichtige Aktivitäten und Benachrichtigungen anzuzeigen, ohne auf ihrem primären Arbeitsgerät kontextwechseln zu müssen. Benutzer können auch Ihre Teams durch Anpassen des Hintergrunds über Einstellungen personalisieren.
- Freisprechen mit **Cortana** Benutzer können mit Teams-Anzeigen interagieren und dabei ihre Stimme verwenden, um mühelos an Besprechungen teilzunehmen und zu präsentieren, Antworten in einen Teams-Chat diktieren, zu überprüfen, was sich im Kalender befinden und vieles mehr.
- **Hinterlassen einer Notiz auf dem Sperrbildschirm** Gäste können auswählen, ob sie Audio-, Video- und Textnotizen hinterlassen, und Benutzer können die Notizen überprüfen, die von Gästen hinterlassen wurden, und sehen, wer sie gestoppt hat.  

## <a name="required-licenses"></a>Erforderliche Lizenzen

Teams-Lizenzen können im Rahmen von Abonnements Microsoft 365 [Office 365 werden](/office365/servicedescriptions/teams-service-description). Weitere Informationen zu den erforderlichen Lizenzen für die Verwendung von Teams Anzeigen finden Sie unter Sprach- und [Videoanrufe mit Microsoft Teams](https://products.office.com/microsoft-teams/voice-calling).

Weitere Informationen dazu, wie Sie Teams erhalten, finden Sie unter Wie [kann ich auf meine Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>Bereitstellen von Teams mithilfe von Intune

Weitere Informationen zum Bereitstellen von Teams mit Intune finden Sie unter Bereitstellen von Teams [und Teams Anzeigen](phones-displays-deploy.md).

## <a name="manage-teams-displays-in-your-organization"></a>Verwalten Teams anzeigen in Ihrer Organisation

Um Ihre Teams zu verwalten, wechseln Sie in der linken Navigationsleiste Microsoft Teams Admin Center **zu Teams Anzeigen**. Hier können Sie das Gerätekonfigurationsprofil ändern, Updates verwalten, Geräte neu starten, Gerätetags hinzufügen und entfernen und vieles mehr. Weitere Informationen finden Sie unter [Verwalten ihrer Geräte in Teams](device-management.md).

## <a name="set-up-hot-desking-on-teams-displays"></a>Einrichten von "Hot-King" auf Teams Bildschirmen

Mit "Hot-King" können Personen in Ihrer Organisation temporäre Arbeitsbereiche im Voraus über Teams und Outlook oder vom Gerät selbst reservieren. Wenn "Hot-King" aktiviert ist, melden sich Benutzer mit ihren Teams-Anmeldeinformationen Microsoft 365 an, um auf ihre Besprechungen, Chats und Dateien zu zugreifen. Wenn sich die Person abmeldet, werden alle persönlichen Informationen vom Gerät entfernt.

Um zu beginnen, müssen Sie ressourcenlizenzen Microsoft Teams-Räume Standard erwerben und Ressourcenkonten für jeden einzelnen Teams erstellen. Informationen [zum Erstellen von Microsoft Teams-Räume mit Office 365](../rooms/with-office-365.md) finden Sie unter Bereitstellen von Ressourcenkonten.

Nachdem Sie Ressourcenkonten erstellt haben, können Sie eine Richtlinie erstellen und zuweisen, um "Hot-King" zu aktivieren. Weitere [Informationen finden Sie unter New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) .

> [!IMPORTANT]
> Da Teams-Bildschirme mit Hot-King von mehreren Personen in freigegebenen Arbeitsbereichen verwendet werden, können Sich Regeln für bedingten Zugriff und andere Identitätskonfigurationen in Ihrer Umgebung, z. B. mehrstufige Authentifizierung, auf diese Geräte auswirken und Anmeldeprobleme verursachen. Anleitungen zum Sichern freigegebener Geräte finden Sie unter Bewährte Methoden für die [Authentifizierung für freigegebene Teams Android-Geräte](authentication-best-practices-for-android-devices.md).

## <a name="upgrade-teams-phones-to-teams-displays"></a>Aktualisieren von Teams auf Teams Bildschirme

Teams Anzeigen ist die Weiterentwicklung Teams Smartphones. Sie können für Teams in Ihrer Organisation ein upgraden, Teams mithilfe des Microsoft Teams Admin Centers angezeigt werden. Diese Option ist nur für Telefone verfügbar, die ein Upgrade auf Teams unterstützen. Weitere Informationen finden Sie unter [Aktualisieren Teams auf Teams Bildschirme](upgrade-phones-to-displays.md).

## <a name="see-also"></a>Mehr dazu

[Einführung Microsoft Teams Bildschirme](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams Marketplace](https://office.com/teamsdevices)

[Telefone für Teams](phones-for-teams.md)

[Ip Phones certified for Microsoft Teams](teams-ip-phones.md)

[Aktualisieren von IP-Telefonen auf Teams Bildschirme](upgrade-phones-to-displays.md)

[Cortana Sprachunterstützung in Teams](../cortana-in-teams.md)