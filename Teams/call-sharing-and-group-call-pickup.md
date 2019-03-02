---
title: Freigeben von Anrufen und Gruppenanrufannahme in Microsoft Teams
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Rufen Sie die Freigabe, und Gruppe Anruf Pickup-kann Benutzer eingehende Anrufe mit Kollegen freigeben, sodass Anrufe erst erfasst werden können, wenn der Benutzer nicht verfügbar ist.
ms.openlocfilehash: df98dd4df064b23b687ddcc569e6c5a431137527
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "30351330"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Freigeben von Anrufen und Gruppenanrufannahme in Microsoft Teams

Der Anruf Freigabe und der Gruppe anrufen pickup Features von Microsoft-Teams können Benutzer freigeben, die ihre eingehenden mit Kollegen Anrufe, sodass die Kollegen Anrufe, die auftreten entgegennehmen können, wenn der Benutzer nicht verfügbar ist.

Gruppe Anruf Pickup-ist weniger störende an Empfänger als andere Arten von Anrufen (wie Anruf weiterleiten oder Gleichzeitiges Klingeln) freigeben, da Benutzer konfigurieren können, wie sie einen freigegebenen eingehenden Anruf (über eine Audio- und optische Benachrichtigung nur Visual benachrichtigt werden möchten oder in der app Teams Banner), und sie können entscheiden, ob annehmen des Anrufs.

Um Anrufe für andere Personen freigeben, ein Benutzer erstellt eine anrufgruppe und fügt die Benutzer, denen sie ihre Anrufe mit freigeben möchten. Klicken Sie dann wählen Sie ein Gleichzeitiges Klingeln oder Einstellung weiterleiten. Einzelheiten finden Sie in der [anrufweiterleitung und Gleichzeitiges Klingeln in Teams aufrufen](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .

> [!IMPORTANT]
> Benutzer, die Besitzer der Gruppe anrufen und Mitglieder der anrufgruppe muss in Teams nur Bereitstellungsmodus. Weitere Informationen zu Bereitstellungsmethoden Teams finden Sie unter [Grundlegendes zu Microsoft-Teams und Skype für Interoperabilität und Koexistenz Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Lizenz erforderlich

Benutzer müssen Enterprise-VoIP, die zum Einrichten und verwenden Anruf Freigabe und Anruf Pickup-gruppieren aktiviert sein. Weitere Details zur am Lizenzierungsmodell finden Sie unter [Office 365-Lizenzierung für Microsoft-Teams](office-365-licensing.md).

## <a name="configure-group-call-pickup"></a>Konfigurieren der Gruppe Anruf Pickup-

Zum Einrichten der Gruppe Anruf Pickup-ein Benutzer zuerst konfiguriert eine anrufgruppe (Dies ist nicht dasselbe wie eine Sicherheitsgruppe oder ein Office 365) und fügt dann die Benutzer, die sie ihre Anrufe mit freigeben möchten. Klicken Sie dann, wählen Sie ein Gleichzeitiges Klingeln oder forward Einstellung aufrufen. Weitere Informationen und schrittweise Verfahren finden Sie unter [anrufweiterleitung und Gleichzeitiges Klingeln in Teams aufrufen](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).

Rufen Sie die Gruppe erstellen und die Benachrichtigung, dass Voreinstellungen benutzergesteuerten Features sind. Administratoren müssen nicht diese Funktionen für die Benutzer zu konfigurieren. Anruf Gruppen können nicht von Sicherheitsgruppen oder Office 365-Gruppen erstellt werden. Sie müssen in Teams erstellt werden.

Administratoren sollten Anruf Gruppen über die **TeamsCallingPolicy AllowCallGroups** Einstellung für einen Benutzer aktivieren. Administratoren können nur gesteuert wird, ob dieser Benutzer Anruf Gruppen konfigurieren kann. Nachdem das Bit Admins "true" festgelegt ist nicht möglich, dass Benutzer aus konfigurieren, und fügen Sie dem Anruf GruppenBenutzer ihrer Wahl.

## <a name="limitations"></a>Einschränkungen

Ein Mandant kann bis zu 32.768 Anruf Gruppen enthalten. Es können maximal 5 Benutzer in den einzelnen Gruppen Anruf vorhanden sein. 

## <a name="more-information"></a>Weitere Informationen

[Die anrufweiterleitung und Gleichzeitiges Klingeln in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)