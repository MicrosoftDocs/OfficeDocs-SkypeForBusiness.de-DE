---
title: Aufbewahrungsrichtlinien in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anach
description: Erhalten Sie Informationen zu Aufbewahrungsrichtlinien und wie sie in Teams verwaltet.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3c253569f642a8833d9bfad6677fe1a17624447
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640978"
---
# <a name="retention-policies-in-microsoft-teams"></a>Aufbewahrungsrichtlinien in Microsoft Teams

Teams Unterhaltungen sind beständigen und ewig standardmäßig beibehalten. Mit der Einführung von Aufbewahrungsrichtlinien können Administratoren Aufbewahrungsrichtlinien (Aufbewahrung und Löschung) in die Sicherheit & Compliance Center für Teams Chat und Channel-Nachrichten konfigurieren. Dadurch Organisationen, die Daten für die Kompatibilität (d. h., Beibehaltung der Richtlinie) für einen bestimmten Zeitraum beibehalten oder Beseitigen der Daten (d. h., Richtlinie löschen), wenn es eine Haftung nach einem bestimmten Zeitraum berücksichtigt wird. Aufbewahrungsrichtlinien Teams stellen Sie sicher, dass sie beim Löschen von Daten aus alle Speicherorte permanente Daten in der Teams Dienst entfernt wird. 

Verwenden Sie zum Verwalten von Teams Aufbewahrungsrichtlinien der Einstellungen und -Cmdlets in der Sicherheit in Office 365 Compliance Center unter **Daten Governance**& > **Aufbewahrung**.

Aufbewahrungsrichtlinien Teams unterstützen: 
    
- Permanentes: Teams Daten für eine angegebene Dauer beibehalten und nichts Unternehmen.
- Beibehaltung und dann löschen: Teams Daten für eine angegebene Dauer beibehalten, und klicken Sie dann löschen
- Löschen: Löschen von Teams Daten nach einer bestimmten Zeit

Aufbewahrungsrichtlinien Teams noch unterstützt nicht:

- Erweiterte Aufbewahrungsrichtlinien gelten nicht für Teams Chat und Teams Channel Nachricht Speicherorte
- Dauer von weniger als 30 Tagen

Administratoren können separate Aufbewahrungsrichtlinien für Teams private Chats (1:1 oder 1: n-Chats) und Teams Channel Nachrichten einrichten. In vielen Fällen sollten Organisationen private chatdaten als mehrere eine Haftung als Channel-Nachrichten, die in der Regel Weitere projektbezogenen Unterhaltungen sind. Richten Sie diese Richtlinien in der Sicherheit & Compliance Center, **Daten Governance** > **Aufbewahrung**. Schalten Sie **Teams channel Nachrichten** und **Teams chats** und definieren Sie dann die Aufbewahrungsrichtlinien für diesen Speicherorten (ebenfalls in der folgenden Abbildung dargestellt). 

Wenn Sie **Teams channel Nachrichten**aktivieren, können Sie Teams angeben, auf die diese Richtlinie angewendet wird. Beispielsweise für Teams X, Y und Z, der Administrator kann die Löschrichtlinien 1 Jahr (durch diese Teams einzeln auswählen) festgelegt, und Anwenden einer Richtlinie 3 Jahre Löschung auf den Rest der Teams. 

Das gleiche möglich für **Teams chats** , indem Sie bestimmte Benutzer auswählen und Anwenden von Aufbewahrungsrichtlinien eindeutig. 

![Diagramm des Workflows von Microsoft Teams-Daten zu Exchange und SharePoint](media/Retention-Policies.png)


> [!IMPORTANT]
> Die Teams Channel Nachricht Speicherorte und Teams Chats Speicherorte Adresse nur Teams Unterhaltungen in Exchange Online-Postfächer (Benutzer- und Postfächern) gespeichert. Die Nachrichten werden aus allen relevanten Speicherorte, nämlich die Postfächer, Gate und Chatdienst gelöscht. 
> 
> Verwenden Sie zum Verwalten von Aufbewahrungsrichtlinien für Teams Dateien, die in OneDrive für Unternehmen und SharePoint gespeichert sind, ihre Aufbewahrungsrichtlinien.

Konzipiert werden Löschrichtlinien für Teams Dateien über SharePoint Online und OneDrive for Business-Standorte konfiguriert. Daher ist es möglich, dass eine Richtlinie löschen konnte eine Datei in einer Nachricht Teams, Chat oder DDE-Kanal verwiesen wird, bevor diese Nachrichten gelöscht. In diesem Fall die Datei wird weiterhin in der Nachricht Teams angezeigt, aber wenn Sie die Datei klicken, erhalten Sie einen "Datei nicht gefunden"-Fehler (Dies kann auch ohne eine Richtlinie vorkommen, wenn ein Benutzer eine Datei manuell aus SharePoint Online oder OneDrive für Unternehmen löscht).

Ausführliche Informationen zur Konfiguration von Aufbewahrungsrichtlinien für Office 365 und das Lesen der [Übersicht über die Aufbewahrungsrichtlinien](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).
 
