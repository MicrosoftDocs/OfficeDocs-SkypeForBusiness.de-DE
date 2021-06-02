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
description: Anruffreigabe und Gruppenanrufabrufabruf ermöglichen es Benutzern, eingehende Anrufe mit Kollegen zu teilen, sodass Anrufe erfasst werden können, wenn der Benutzer nicht verfügbar ist.
ms.openlocfilehash: 98094ff0b4b5d7b037915273b2c2730d42517c22
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717836"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Freigeben von Anrufen und Gruppenanrufannahme in Microsoft Teams

Mit den Anruffreigabefunktionen und der Anrufabruffunktionen von Microsoft Teams können Benutzer ihre eingehenden Anrufe mit Kollegen teilen, sodass die Kollegen Anrufe entgegen nehmen können, die während der Benutzer verfügbar sind.

Das Abholen von Gruppenanrufen ist für Empfänger weniger störend als andere Formen der Anruffreigabe (wie Anruf weiterleitung oder gleichzeitiges Klingeln), da Benutzer konfigurieren können, wie sie über einen eingehenden freigegebenen Anruf benachrichtigt werden möchten (über Audio und visuelle Benachrichtigung, nur per visueller Darstellung oder über ein Banner in der Teams-App), und sie können entscheiden, ob sie den Anruf annehmen möchten.

Um Anrufe für andere Personen zu teilen, erstellt ein Benutzer eine Anrufgruppe und fügt die Benutzer hinzu, für die er ihre Anrufe freigeben möchte. Anschließend wählen sie eine Einstellung für gleichzeitiges Klingeln oder Weiterleiten aus. Weitere [Informationen finden Sie unter](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) Anruf weiterleitung und Teams in der Anrufkonferenz. Beachten Sie, dass mobile Geräte nur benachrichtigt werden, wenn sie für Banner und Klingelton festgelegt sind.

> [!IMPORTANT]
> Benutzer, der Besitzer der Anrufgruppe und Mitglieder der Anrufgruppe müssen sich im Teams Bereitstellungsmodus befinden. Weitere Details zu Teams Bereitstellungsmodi finden Sie unter Verstehen Microsoft Teams und Skype for Business [Koexistenz und Interoperabilität](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Lizenz erforderlich

Benutzern muss eine Lizenz Microsoft Teams Telefonsystem zugewiesen sein, um Anruffreigaben und das Abholen von Gruppenanrufen einrichten und verwenden zu können. Weitere Details zum Lizenzierungsmodell finden Sie unter Dies ist das, was [Sie mit dem Telefonsystem.](https://docs.microsoft.com/MicrosoftTeams/here-s-what-you-get-with-phone-system)

## <a name="configure-group-call-pickup"></a>Konfigurieren der Gruppenanrufabrufabrufe

Um das Abholen von Gruppenanrufen zu einrichten, konfiguriert ein Benutzer zuerst eine Anrufgruppe (dies ist nicht dasselbe wie eine Sicherheitsgruppe oder eine Microsoft 365-Gruppe), und fügt dann die Benutzer hinzu, für die sie ihre Anrufe freigeben möchten. Anschließend wählen sie eine Einstellung für gleichzeitiges Anrufen oder Anruf weiterleiten aus. Weitere Informationen und schrittweise Anleitungen finden Sie unter [Anruf weiterleitung und gleichzeitiges](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)Anrufen in Teams.

Die Erstellung von Anrufgruppen und Benachrichtigungseinstellungen sind benutzergesteuerte Features. Administratoren müssen diese Features für ihre Benutzer nicht konfigurieren. Anrufgruppen können nicht aus Sicherheitsgruppen oder Gruppen Microsoft 365 werden. sie müssen in der Teams.

Administratoren sollten Anrufgruppen über die **TeamsCallingPolicy AllowCallGroups-Einstellung** für einen Benutzer aktivieren. Administratoren können dies auch über das Teams aktivieren.  Darüber hinaus kann der konfigurierte Benutzer auch seine Anrufgruppen direkt über den Client konfigurieren. Administratoren oder Endbenutzer können die Konfiguration nicht voneinander blockieren, aber Teams-Verwaltungsportal und Teams-Client sollten diese Beziehung an beiden Stellen genau anzeigen. 

Wichtig: Wenn Administratoren Anrufgruppen für Benutzer deaktivieren (nachdem sie aktiviert und die Beziehungen zwischen Anrufgruppen konfiguriert wurden), müssen die Administratoren die Anrufgruppenbeziehungen für Benutzer im Teams Admin Center bereinigen, um falsche Anrufrouting zu vermeiden. 

## <a name="limitations"></a>Einschränkungen

Jede konfigurierte Anrufgruppe kann maximal 25 Benutzer oder 32.768 Zeichen umfassen. 

## <a name="more-information"></a>Weitere Informationen

[Anruf weiterleitung und gleichzeitiges Anrufen in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
