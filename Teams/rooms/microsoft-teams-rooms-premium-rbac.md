---
title: Rollenbasierte Zugriffssteuerung mit dem Dienst Microsoft Teams Room Premium
author: dstrome
ms.author: dstrome
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
description: Erfahren Sie mehr über rollenbasierte Zugriffssteuerung mit dem verwalteten Microsoft Teams-Räume Diensts.
f1keywords: ''
ms.openlocfilehash: c73ad1385a0654f3ef50dab46b803debe418b834b6497acfcb27f5a4de736f98
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301061"
---
# <a name="role-based-access-control-with-the-microsoft-teams-rooms-managed-service"></a>Rollenbasierte Zugriffssteuerung mit dem verwalteten Microsoft Teams-Räume Dienst

Rollenbasierte Zugriffssteuerung (Role-based Access Control, RBAC) im verwalteten Microsoft Teams-Räume hilft Ihnen bei der Verwaltung des Benutzerzugriffs auf Raumressourcendaten in Ihrer Organisation. Durch das Zuweisen von Rollen zu Ihren Dienstportalbenutzern können Sie einschränken, was diese sehen und ändern können. Jede Rolle verfügt über einen Satz von Berechtigungen, die bestimmen, welche Benutzer mit dieser Rolle innerhalb Ihrer Organisation darauf zugreifen und Änderungen daran ändern können.

Zum Erstellen, Bearbeiten oder Zuweisen von Rollen muss Ihr Konto über eine der folgenden Berechtigungen verfügen:

- Globaler Administrator über Azure Active Directory (Azure AD)
- Verwalteter Dienstadministrator über das Microsoft Teams-Räume verwalteten Dienstportals

## <a name="what-is-a-role"></a>Was ist eine Rolle?

Eine Rolle definiert den Satz der Berechtigungen, die Benutzern gewährt werden, die dieser Rolle zugewiesen sind. Derzeit verfügt der verwaltete Microsoft Teams-Räume über drei integrierte Rollen: **Administrator** für verwaltete Dienste, **Websiteleiter** und **Site Tech.** Sie umfassen einige häufige Szenarien für Benutzer in Ihrer Organisation, die möglicherweise mit der Verwaltung ihrer Räume involviert sind.

Um Rollen zu sehen, wechseln Sie im linken Navigationsbereich des Microsoft Teams-Räume-Portals für verwaltete Dienste zu Rollen **,** und wählen Sie dann eine der Rollen aus, um die Eigenschaften, Berechtigungen und Zuweisungen der Rolle zu sehen.  

- **Eigenschaften:** Name, Rollentyp und Beschreibung
- **Berechtigungen:** Listet Features und Berechtigungsebenen auf, auf die die Rolle Zugriff hat.
- **Zuordnungen:** Eine Liste von Rollenzuweisungen, die definieren, welche Benutzer über die konfigurierten Berechtigungen für den Bereich von Raumressourcenkonten verfügen. Eine Rolle kann mehrere Aufgaben haben, und ein Benutzer kann an mehreren Aufgaben arbeiten.

## <a name="built-in-roles"></a>Integrierte Rollen

Sie können integrierte Rollen Gruppen oder Benutzern ohne weitere Konfiguration zuweisen. Beachten Sie, dass Sie den Namen, die Beschreibung, den Typ oder die Berechtigungen einer integrierten Rolle nicht löschen oder bearbeiten können.

- **Administrator für verwaltete** Dienste: Hat Vollzugriff auf das Microsoft Teams Room Premium Service Portal.
- **Websiteleiter:** Organisiert Räume, hat Zugriff auf Berichte und kann Tickets verwalten. Registrierungsschlüssel können nicht zurückgesetzt oder Änderungen an der Dienstkonfiguration vorgenommen werden.  
- **Site Tech:** Verwaltet Tickets für bestimmte Räume. Verfügt nicht über die Berechtigungen zum Ändern des Diensts oder zum Organisieren von Räumen im Dienst.

In der folgenden Tabelle ist zusammengefasst, was die einzelnen Rollen tun können.

|Features |Berechtigung |Managed Service Administrator  |Websiteleiter  |Site Tech  |
|---------|---------|---------|---------|---------|
|Räume     |Anzeigen        |&#10004;           |&#10004;           |&#10004;  |
|    |Ändern         |&#10004;           |&#10004;           |&#10004; |
|    |Rücksetztaste         |&#10004;           |         ||
|    |Downloadschlüssel         |&#10004;           |&#10004;          |&#10004; |
|    |Registrierung aufenrolln         |&#10004;           |&#10004;           |&#10004; |
|Gruppenverwaltung   |Erstellen         |&#10004;           |           ||
|    |Anzeigen       |&#10004;          |&#10004;           ||
|    |Ändern         |&#10004;           |           ||
|Verwaltung von Update-Ringen    |Erstellen         |&#10004;           |           ||
|    |Anzeigen         |&#10004;           |           ||
|    |Ändern         |&#10004;           |           ||
|Berichte   |Anzeigen        |&#10004;           |&#10004;           ||
|Ticketverwaltung   |Kundenvorfall erstellen         |&#10004;           |&#10004;           |&#10004;  |
|    |Anzeigen         |&#10004;           |&#10004;           |&#10004;  |
|    |Aktualisieren         |&#10004;           |&#10004;           |&#10004;  |
|Microsoft Teams-Räume von verwalteten Diensteinstellungen    |Anzeigen         |&#10004;           |         ||
|    |Ändern        |&#10004;           |         ||
|Rollenverwaltung    |Anzeigen         |&#10004;           |         ||
|    |Ändern         |&#10004;           |         ||

## <a name="assign-a-role"></a>Zuweisen einer Rolle

Um Rollen zuweisen zu können, müssen Sie ein globaler Administrator oder ein Administrator für verwaltete Dienste sein.

1. Navigieren Sie im linken Navigationsbereich des Microsoft Teams-Räume Dienstportals zu **Einstellungen**  >  **Rollen**.

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="Screenshot der Access-Steuerelementseite mit Den Rollen":::

2. Wählen Sie die Rolle aus, die Sie zuweisen möchten.
3. Wählen Sie im Rollenbereich Aufgaben **hinzufügen**  >  **aus.**

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="Screenshot der Option "Hinzufügen" zum Hinzufügen einer Rolle":::

4. Geben Sie **auf der Seite Allgemeine** Einstellungen unter Aufgabeneigenschaften einen Namen für diese Aufgabe ein.  Die Beschreibung ist optional. Wählen Sie **Weiter aus.**
5. Geben Sie **auf** der  Seite Mitglieder im Feld Nach Benutzer oder Sicherheitsgruppe suchen den Namen eines Benutzers oder einer Sicherheitsgruppe in Ihrem Mandanten ein, dem Sie Berechtigungen erteilen möchten, und schließen Sie dann die Auswahl ab. Wählen Sie **Weiter aus.** 
6. Geben Sie **auf** der  Seite Bereich im Feld Nach Raum oder Raumgruppe suchen den Namen eines Raum oder einer Raumgruppe ein, den oder die der Benutzer verwalten darf. Wählen Sie **Weiter aus.**
7. Überprüfen Sie **auf der** Seite Fertig stellen die Details der Aufgabe. Wenn Sie mit der Konfiguration zufrieden sind, wählen Sie **Aufgabe hinzufügen aus.** Wenn Sie einen Abschnitt bearbeiten  möchten, verwenden Sie die Schaltfläche Zurück, oder wählen Sie den Schritt im linken Navigationsbereich aus.  

## <a name="related-topics"></a>Verwandte Themen

- [Microsoft Teams-Räume verwalteter Dienst](microsoft-teams-rooms-premium.md)
