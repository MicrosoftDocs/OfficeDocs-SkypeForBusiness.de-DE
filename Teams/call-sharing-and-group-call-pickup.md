---
title: Freigeben von Anrufen und Gruppenanrufannahme
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: Mit der Anruffreigabe und der Gruppenanrufannahme können Benutzer eingehende Anrufe mit Kollegen teilen, sodass Anrufe erfasst werden können, wenn der Benutzer nicht verfügbar ist.
ms.openlocfilehash: 70b1be389309d52b01852e575d08093ef7095a04
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789950"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Freigeben von Anrufen und Gruppenanrufannahme in Microsoft Teams

Mit den Funktionen zur Anruffreigabe und Gruppenanrufannahme von Microsoft Teams können Benutzer ihre eingehenden Anrufe mit Kollegen teilen, sodass die Kollegen Anrufe annehmen können, die auftreten, während der Benutzer nicht verfügbar ist.

Die Gruppenanrufannahme ist für Empfänger weniger störend als andere Formen der Anruffreigabe (z. B. Anrufweiterleitung oder gleichzeitiges Klingeln), da Benutzer konfigurieren können, wie sie über einen eingehenden freigegebenen Anruf benachrichtigt werden möchten (über Audio- und visuelle Benachrichtigungen, nur visuelle Elemente oder Banner in der Teams-App), und sie können entscheiden, ob sie ihn annehmen möchten.

Um Anrufe für andere Personen freizugeben, erstellt ein Benutzer eine Anrufgruppe und fügt die Benutzer hinzu, für die er seine Anrufe freigeben möchte. Anschließend wählen sie eine Einstellung für gleichzeitiges Klingeln oder Weiterleiten aus. Weitere Informationen finden Sie [unter Anrufweiterleitung und gleichzeitiges Anrufen in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) . Beachten Sie, dass mobile Geräte nur benachrichtigt werden, wenn sie für Banner und Klingelton festgelegt sind.

> [!IMPORTANT]
> Benutzer, der Besitzer der Anrufgruppe und Mitglieder der Anrufgruppe müssen sich im Bereitstellungsmodus "Nur Teams" befinden. Weitere Informationen zu Teams-Bereitstellungsmodi finden [Sie unter Grundlegendes zu Microsoft Teams und Skype for Business Koexistenz und Interoperabilität](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

## <a name="license-required"></a>Lizenz erforderlich

Benutzern muss eine Microsoft Teams Telefon Systemlizenz zugewiesen werden, um die Anruffreigabe und die Gruppenanrufannahme einzurichten und zu verwenden. Weitere Details zum Lizenzierungsmodell finden [Sie unter "So erhalten Sie das Telefonsystem"](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

## <a name="configure-group-call-pickup"></a>Konfigurieren der Gruppenanrufannahme

Um die Gruppenanrufannahme einzurichten, konfiguriert ein Benutzer zuerst eine Anrufgruppe (dies ist nicht mit einer Sicherheitsgruppe oder einer Microsoft 365-Gruppe identisch) und fügt dann die Benutzer hinzu, für die sie ihre Anrufe freigeben möchten. Anschließend wählen sie eine Einstellung für gleichzeitiges Anrufen oder Anrufweiterleitung aus. Weitere Informationen und schrittweise Verfahren finden Sie [unter Anrufweiterleitung und gleichzeitiges Anrufen in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).

Anrufgruppenerstellungs- und Benachrichtigungseinstellungen sind benutzergesteuerte Features. Administratoren müssen diese Features nicht für ihre Benutzer konfigurieren. Anrufgruppen können nicht aus Sicherheitsgruppen oder Microsoft 365-Gruppen erstellt werden. sie müssen in Teams erstellt werden.

Administratoren sollten Anrufgruppen über die Einstellung **"TeamsCallingPolicy AllowCallGroups** " für einen Benutzer aktivieren. Administratoren können dies auch über teams Admin Portal aktivieren.  Darüber hinaus kann der konfigurierte Benutzer seine Anrufgruppen auch direkt über den Client konfigurieren. Admin oder Endbenutzer können die Konfiguration nicht gegenseitig blockieren, aber Teams Admin Portal und Teams-Client sollten diese Beziehung an beiden Stellen genau anzeigen. 

Wichtig: Wenn Administratoren Anrufgruppen für Benutzer deaktivieren (nachdem sie aktiviert wurden und die Anrufgruppenbeziehungen konfiguriert sind), müssen die Administratoren die Anrufgruppenbeziehungen für Benutzer im Teams Admin Center bereinigen, um ein falsches Anrufrouting zu vermeiden. 

## <a name="limitations"></a>Einschränkungen

Jede konfigurierte Anrufgruppe kann maximal 25 Benutzer oder 32.768 Zeichen haben. 

## <a name="more-information"></a>Weitere Informationen

[Anrufweiterleitung und gleichzeitiges Anrufen in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
