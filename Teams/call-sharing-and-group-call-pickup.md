---
title: Freigeben von Anrufen und Gruppenanrufannahme
ms.author: serdars
author: SerdarSoysal
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: Anruffreigabe und Gruppenanrufabholung ermöglichen es Benutzern, eingehende Anrufe mit Kollegen zu teilen, damit Anrufe erfasst werden können, wenn der Benutzer nicht verfügbar ist.
ms.openlocfilehash: 1ec3c389bf2eb69f30e13ebbba6c7d5d1d5fe38c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102791"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Freigeben von Anrufen und Gruppenanrufannahme in Microsoft Teams

Mit den Anruffreigabe- und Gruppenanrufabholungsfunktionen von Microsoft Teams können Benutzer ihre eingehenden Anrufe mit Kollegen teilen, damit die Kollegen Anrufe entgegen nehmen können, die während der Benutzer nicht verfügbar sind.

Die Anrufanrufabholung für Gruppen ist für Empfänger weniger störend als andere Formen der Anruffreigabe (z. B. Anruf weiterleitung oder gleichzeitiges Klingeln), da Benutzer konfigurieren können, wie sie über einen eingehenden freigegebenen Anruf benachrichtigt werden möchten (über audio- und visuelle Benachrichtigung, nur visuell oder Banner in der Teams-App), und sie können entscheiden, ob sie ihn annehmen möchten.

Um Anrufe für andere Personen zu teilen, erstellt ein Benutzer eine Anrufgruppe und fügt die Benutzer hinzu, für die sie ihre Anrufe freigeben möchten. Anschließend wählen sie eine Einstellung für gleichzeitiges Klingeln oder Weiterleiten aus. Details finden Sie unter Anruf [weiterleitung und gleichzeitiges Anrufen in Teams.](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) Beachten Sie, dass mobile Geräte nur benachrichtigt werden, wenn sie für Banner und Klingelton festgelegt sind.

> [!IMPORTANT]
> Benutzer, der Besitzer der Anrufgruppe und Mitglieder der Anrufgruppe müssen sich im Bereitstellungsmodus nur in Teams befinden. Weitere Informationen zu den Bereitstellungsmodi von Teams finden Sie unter [Verstehen der Koexistenz](teams-and-skypeforbusiness-coexistence-and-interoperability.md) und Interoperabilität von Microsoft Teams und Skype for Business

## <a name="license-required"></a>Lizenz erforderlich

Die Benutzer müssen Enterprise-VoIP aktiviert sein, um die Anruffreigabe und die Gruppenanrufabholung einrichten und verwenden zu können. Weitere Details zum Lizenzierungsmodell finden Sie unter [Microsoft Teams-Dienstbeschreibung](/office365/servicedescriptions/teams-service-description).

## <a name="configure-group-call-pickup"></a>Konfigurieren der Gruppenanrufabholung

Zum Einrichten der Gruppenanrufabholung konfiguriert ein Benutzer zuerst eine Anrufgruppe (dies ist nicht mit einer Sicherheitsgruppe oder einer Microsoft 365-Gruppe identisch), und fügt dann die Benutzer hinzu, für die sie ihre Anrufe freigeben möchten. Anschließend wählen sie eine Einstellung für die gleichzeitige Anrufanruf- oder -weiterleitung aus. Weitere Informationen und schrittweise Verfahren finden Sie unter Anruf weiterleitung und gleichzeitiges Anrufen [in Teams.](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)

Die Einstellungen für die Erstellung von Anrufgruppen und Benachrichtigungen sind benutzergesteuerte Features. Administratoren müssen diese Features nicht für ihre Benutzer konfigurieren. Anrufgruppen können nicht aus Sicherheitsgruppen oder Microsoft 365-Gruppen erstellt werden. sie müssen in Teams erstellt werden.

Administratoren sollten Anrufgruppen über die **Einstellung TeamsCallingPolicy AllowCallGroups für** einen Benutzer aktivieren. Administratoren können dies auch über das Teams Admin-Portal aktivieren.  Darüber hinaus kann der konfigurierte Benutzer seine Anrufgruppen auch direkt über den Client konfigurieren. Administratoren oder Endbenutzer können die Konfiguration nicht gegenseitig blockieren, aber Teams Admin Portal und Teams-Client sollten diese Beziehung an beiden Stellen genau anzeigen. 

Wichtig: Wenn Administratoren Anrufgruppen für Benutzer deaktivieren (nachdem sie aktiviert und die Beziehungen zwischen Anrufgruppen konfiguriert wurden), müssen die Administratoren die Anrufgruppenbeziehungen für Benutzer im Teams Admin Center bereinigen, um ein falsches Anrufrouting zu vermeiden. 

## <a name="limitations"></a>Einschränkungen

Ein Mandant kann maximal 32.768 Anrufgruppen enthalten. Jede Anrufgruppe kann maximal 25 Benutzer haben. 

## <a name="more-information"></a>Weitere Informationen

[Anruf weiterleitung und gleichzeitiges Anrufen in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)