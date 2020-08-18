---
title: Rollenbasierte Zugriffssteuerung mit dem Microsoft Teams Room Premium-Dienst
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informieren Sie sich über die rollenbasierte Zugriffssteuerung mit dem verwalteten Microsoft Teams rooms-Dienst.
f1keywords: ''
ms.openlocfilehash: ec8bb770f1dd843c569a98dd909c87ef3ca14dd0
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788783"
---
# <a name="role-based-access-control-with-the-microsoft-teams-rooms-managed-service"></a>Rollenbasierte Zugriffssteuerung mit dem Microsoft Teams rooms Managed Service

Rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) im Microsoft Teams rooms Managed Service hilft Ihnen, den Zugriff von Benutzern auf Raum Ressourcendaten in Ihrer Organisation zu verwalten. Indem Sie Ihren Dienstportal Benutzern Rollen zuweisen, können Sie einschränken, was Sie sehen und ändern können. Jede Rolle verfügt über eine Reihe von Berechtigungen, die bestimmen, welche Benutzer mit dieser Rolle in Ihrer Organisation darauf zugreifen und diese ändern können.

Zum Erstellen, bearbeiten oder Zuweisen von Rollen muss Ihr Konto über eine der folgenden Berechtigungen verfügen:

- Globaler Administrator durch Azure Active Directory (Azure AD)
- Managed Service-Administrator über das Microsoft Teams rooms Managed Service Portal

## <a name="what-is-a-role"></a>Was ist eine Rolle?

Eine Rolle definiert den Satz von Berechtigungen, die Benutzern zugewiesen wurden, die dieser Rolle zugewiesen sind. Im Moment verfügt der Managed Service für Microsoft Teams rooms über drei integrierte Rollen: **Managed Service Administrator**, **Website Lead**und Site- **Tech**. Sie decken einige häufige Szenarien für Benutzer in Ihrer Organisation ab, die möglicherweise an der Verwaltung ihrer Räume beteiligt sind.

Wenn Sie Rollen anzeigen möchten, wechseln Sie in der linken Navigationsleiste des Microsoft Teams Room Managed Service Portals zu **Rollen**, und wählen Sie dann eine der Rollen aus, um die Eigenschaften, Berechtigungen und Aufgaben der Rolle anzuzeigen.  

- **Eigenschaften**: Name, Rollentyp und Beschreibung
- **Berechtigungen**: Listet die Features und die Berechtigungsstufe auf, auf die die Rolle zugreifen kann.
- **Aufgaben**: eine Liste von Rollenzuweisungen, die definieren, welche Benutzer über die konfigurierten Berechtigungen für den Bereich der Raum Ressourcenkonten verfügen. Eine Rolle kann mehrere Zuordnungen aufweisen, und ein Benutzer kann mehrere Aufgaben haben.

## <a name="built-in-roles"></a>Integrierte Rollen

Sie können Gruppen oder Benutzern integrierte Rollen ohne weitere Konfiguration zuweisen. Beachten Sie, dass Sie den Namen, die Beschreibung, den Typ oder die Berechtigungen einer integrierten Rolle nicht löschen oder bearbeiten können.

- **Managed Service Administrator**: bietet vollständigen Zugriff auf das Microsoft Teams Room Premium-Service Portal.
- **Website Lead**: organisiert Räume, hat Zugriff auf Berichte und kann Tickets verwalten. Der Registrierungsschlüssel kann nicht zurückgesetzt oder Änderungen an der Konfiguration des Diensts vorgenommen werden.  
- **Website-Technologie**: verwaltet Tickets für bestimmte Räume. Verfügt nicht über die Berechtigungen zum Ändern des Diensts oder zum Organisieren von Räumen im Dienst.

In der folgenden Tabelle wird zusammengefasst, was jede Rolle tun kann.

|Features |Berechtigungs |Managed Service-Administrator  |Website Lead  |Website-Tech  |
|---------|---------|---------|---------|---------|
|Chatrooms     |Ansicht        |&#10004;           |&#10004;           |&#10004;  |
|    |Ändern         |&#10004;           |&#10004;           |&#10004; |
|    |Reset-Taste         |&#10004;           |         ||
|    |Download-Taste         |&#10004;           |&#10004;          |&#10004; |
|    |Registrierung         |&#10004;           |&#10004;           |&#10004; |
|Gruppenverwaltung   |Erstellen         |&#10004;           |&#10004;           ||
|    |Ansicht       |&#10004;          |&#10004;           ||
|    |Ändern         |&#10004;           |&#10004;           ||
|Aktualisieren der Ring Verwaltung    |Erstellen         |&#10004;           |&#10004;           ||
|    |Ansicht         |&#10004;           |&#10004;           ||
|    |Ändern         |&#10004;           |&#10004;           ||
|Berichte   |Ansicht        |&#10004;           |&#10004;           ||
|Ticket Verwaltung   |Kunden Vorfall erstellen         |&#10004;           |&#10004;           |&#10004;  |
|    |Ansicht         |&#10004;           |&#10004;           |&#10004;  |
|    |Aktualisieren         |&#10004;           |&#10004;           |&#10004;  |
|Microsoft Teams rooms-Einstellungen für verwaltete Dienste    |Ansicht         |&#10004;           |         ||
|    |Ändern        |&#10004;           |         ||
|Rollenverwaltung    |Ansicht         |&#10004;           |         ||
|    |Ändern         |&#10004;           |         ||

## <a name="assign-a-role"></a>Zuweisen einer Rolle

Wenn Sie Rollen zuweisen möchten, müssen Sie ein globaler Administrator oder ein verwalteter Dienstadministrator sein.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams rooms Managed Service Portals zu **Rollen**.

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="Screenshot der Seite "Zugriffssteuerung" mit Rollen":::

2. Wählen Sie die Rolle aus, die Sie zuweisen möchten.
3. Wählen Sie im Rollenbereich **Aufgaben**  >  **Hinzufügen**aus.

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="Screenshot der Option "hinzufügen" zum Hinzufügen einer Rolle":::

4. Geben Sie auf der Seite **Allgemeine Einstellungen** unter **Zuordnungseigenschaften**einen Namen für diese Aufgabe ein. Die Beschreibung ist optional. Wählen Sie **weiter aus.**
5. Geben Sie auf der Seite **Mitglieder** im Feld **nach Benutzer oder Sicherheitsgruppe suchen** den Namen eines Benutzers oder einer Sicherheitsgruppe in Ihrem Mandanten ein, dem Sie Berechtigungen erteilen möchten, und füllen Sie dann die Auswahl aus. Wählen Sie **weiter**aus. 
6. Geben Sie auf der Seite " **Bereich** " im Feld **nach Raum oder Raum suchen** den Namen einer Raum-oder Raumgruppe ein, die dem Benutzer verwaltet werden darf. Wählen Sie **weiter**aus.
7. Überprüfen Sie auf der Seite **Fertig stellen** die Details der Aufgabe. Wenn Sie mit der Konfiguration zufrieden sind, wählen Sie **Aufgabe hinzufügen**aus. Wenn Sie einen Abschnitt bearbeiten möchten, verwenden Sie die Schaltfläche **zurück** , oder wählen Sie den Schritt in der linken Navigationsleiste aus.  

## <a name="related-topics"></a>Verwandte Themen

- [Microsoft Teams rooms, verwalteter Dienst](microsoft-teams-rooms-premium.md)
