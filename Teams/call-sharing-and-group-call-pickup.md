---
title: Freigeben von Anrufen und Gruppenanrufannahme in Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
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
description: Mit der Anruf Freigabe und der Gruppenanruf-Pickup können Benutzer eingehende Anrufe an Kollegen weiterleiten, damit Anrufe aufgenommen werden können, wenn der Benutzer nicht verfügbar ist.
ms.openlocfilehash: c3a47c892940762807a86d6690fa59520f137960
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824553"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Freigeben von Anrufen und Gruppenanrufannahme in Microsoft Teams

Mit den Funktionen für Anruf Freigabe und Gruppenanruf-Abholung von Microsoft Teams können Benutzer Ihre eingehenden Anrufe an Kollegen weitergeben, damit die Kollegen Anrufe entgegennehmen können, die eintreten, während der Benutzer nicht verfügbar ist.

Die Gruppenanruf Abholung ist weniger störend für die Empfänger als andere Formen der Anruf Freigabe (wie Anrufweiterleitung oder gleichzeitiges Klingeln), da Benutzer konfigurieren können, wie Sie über einen eingehenden freigegebenen Anruf benachrichtigt werden möchten (über Audio-und visuelle Benachrichtigung, nur visuell, oder Banner in der Teams-APP), und Sie können entscheiden, ob Sie Sie beantworten möchten.

Um Anrufe mit anderen zu teilen, erstellt ein Benutzer eine anrufgruppe und fügt die Benutzer hinzu, deren Anrufe Sie freigeben möchten. Dann wählen Sie eine gleichzeitige Ring-oder Forward-Einstellung aus. Weitere Informationen finden Sie unter [Anrufweiterleitung und gleichzeitiges anrufen in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .

> [!IMPORTANT]
> Benutzer, der Besitzer der anrufgruppe und Mitglieder der anrufgruppe müssen sich nur im Bereitstellungsmodus von Teams befinden. Weitere Informationen zu den Bereitstellungsmodi für Teams finden Sie Untergrund [Legendes zu Microsoft Teams und Skype for Business-Koexistenz und-Interoperabilität](teams-and-skypeforbusiness-coexistence-and-interoperability.md) .

## <a name="license-required"></a>Lizenz erforderlich

Für Benutzer muss Enterprise-VoIP aktiviert sein, um die Anruf Freigabe und die Gruppenanruf Abholung einzurichten und zu verwenden. Weitere Informationen zum Lizenzierungsmodell finden Sie unter [Office 365-Lizenzierung für Microsoft Teams](office-365-licensing.md).

## <a name="configure-group-call-pickup"></a>Konfigurieren der Gruppenanruf Abholung

Um die Gruppenanruf Abholung einzurichten, konfiguriert ein Benutzer zuerst eine anrufgruppe (Dies ist nicht dasselbe wie eine Sicherheitsgruppe oder eine Office 365-Gruppe) und fügt dann die Benutzer hinzu, für die Sie Ihre Anrufe freigeben möchten. Dann wählen Sie eine gleichzeitige Klingel-oder Anruf Weiterleitungseinstellung. Weitere Informationen und schrittweise Anleitungen finden Sie unter [Anrufweiterleitung und gleichzeitiges anrufen in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).

Anrufgruppen Erstellung und Benachrichtigungseinstellungen sind benutzergesteuerte Funktionen. Administratoren müssen diese Features nicht für Ihre Benutzer konfigurieren. Anrufgruppen können nicht aus Sicherheitsgruppen oder Office 365-Gruppen erstellt werden. Sie müssen in Teams erstellt werden.

Administratoren sollten Anrufgruppen über die TeamsCallingPolicy- **AllowCallGroups** -Einstellung für einen Benutzer aktivieren. Administratoren können dies auch über das Team-Administratorportal aktivieren.  Darüber hinaus kann der konfigurierte Benutzer seine Anrufgruppen auch direkt über den Client konfigurieren. Administratoren oder Endbenutzer können die Konfiguration nicht voneinander blockieren, aber Teams-Administratorportal und Teams-Client sollten diese Beziehung an beiden Stellen genau anzeigen. 

Wichtig: Wenn Administratoren Anrufgruppen für Benutzer deaktivieren (nachdem Sie aktiviert wurde und die Anrufgruppen Beziehungen konfiguriert sind), müssen die Administratoren die Anrufgruppen Beziehungen für Benutzer im Team Admin Center bereinigen, um ein fehlerhaftes Anrufrouting zu vermeiden. 

## <a name="limitations"></a>Einschränkungen

Ein Mandant kann maximal 32.768 Anrufgruppen enthalten. In jeder anrufgruppe können maximal 25 Benutzer vorhanden sein. 

## <a name="more-information"></a>Weitere Informationen

[Anrufweiterleitung und gleichzeitiges Klingeln in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
