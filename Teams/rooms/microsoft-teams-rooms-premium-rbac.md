---
title: Rollenbasierte Zugriffssteuerung mit dem Microsoft Teams Room Premium-Dienst
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
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie mehr über die rollenbasierte Zugriffssteuerung mit dem Microsoft Teams-Räume verwalteten Dienst.
f1keywords: ''
ms.openlocfilehash: 0edce289a23116ed76bf984bfc72724295fc5a5a
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268360"
---
# <a name="role-based-access-control-with-the-microsoft-teams-rooms-managed-service"></a>Rollenbasierte Zugriffssteuerung mit dem Microsoft Teams-Räume verwalteten Dienst

Die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) im Microsoft Teams-Räume verwalteten Dienst hilft Ihnen beim Verwalten des Benutzerzugriffs auf Raumressourcendaten in Ihrer Organisation. Indem Sie Ihren Dienstportalbenutzern Rollen zuweisen, können Sie einschränken, was sie sehen und ändern können. Jede Rolle verfügt über eine Reihe von Berechtigungen, die bestimmen, auf welche Benutzer mit dieser Rolle innerhalb Ihrer Organisation zugegriffen und geändert werden kann.

Zum Erstellen, Bearbeiten oder Zuweisen von Rollen muss Ihr Konto über eine der folgenden Berechtigungen verfügen:

- Globaler Administrator über Azure Active Directory (Azure AD)
- Verwalteter Dienstadministrator über das Microsoft Teams-Räume-Portal für verwaltete Dienste

## <a name="what-is-a-role"></a>Was ist eine Rolle?

Eine Rolle definiert den Satz von Berechtigungen, die Benutzern gewährt werden, die dieser Rolle zugewiesen sind. Vorerst verfügt der Microsoft Teams-Räume verwaltete Dienst über drei integrierte Rollen: **Managed Service Administrator**, **Site Lead** und **Site Tech**. Sie behandeln einige häufige Szenarien für Benutzer in Ihrer Organisation, die möglicherweise an der Verwaltung Ihrer Räume beteiligt sind.

Um Rollen anzuzeigen, wechseln Sie im linken Navigationsbereich des Microsoft Teams-Räume verwalteten Dienstportals zu **"Rollen**", und wählen Sie dann eine der Rollen aus, um die Eigenschaften, Berechtigungen und Zuweisungen der Rolle anzuzeigen.  

- **Eigenschaften**: Name, Rollentyp und Beschreibung
- **Berechtigungen**: Listet Features und Berechtigungsstufen auf, auf die die Rolle Zugriff hat.
- **Zuweisungen**: Eine Liste der Rollenzuweisungen, die definieren, welche Benutzer über die konfigurierten Berechtigungen im Bereich von Raumressourcenkonten verfügen. Eine Rolle kann mehrere Aufgaben haben, und ein Benutzer kann sich an mehreren Aufgaben beteiligen.

## <a name="built-in-roles"></a>Integrierte Rollen

Sie können integrierten Rollen Gruppen oder Benutzern ohne weitere Konfiguration zuweisen. Denken Sie daran, dass Sie den Namen, die Beschreibung, den Typ oder die Berechtigungen einer integrierten Rolle nicht löschen oder bearbeiten können.

- **Verwalteter Dienstadministrator**: Hat Vollzugriff auf das Microsoft Teams Room Premium-Dienstportal.
- **Websiteleiter**: Organisiert Räume, hat Zugriff auf Berichte und kann Tickets verwalten. Der Registrierungsschlüssel kann nicht zurückgesetzt oder die Konfiguration des Diensts geändert werden.  
- **Site Tech**: Verwaltet Tickets für bestimmte Zimmer. Besitzt keine Berechtigungen zum Ändern des Diensts oder zum Organisieren von Räumen im Dienst.

In der folgenden Tabelle ist zusammengefasst, was die einzelnen Rollen leisten können.

|Features |Berechtigung |Verwalteter Dienstadministrator  |Websiteleiter  |Site Tech  |
|---------|---------|---------|---------|---------|
|Zimmer     |Anzeigen        |&#10004;           |&#10004;           |&#10004;  |
|    |Ändern         |&#10004;           |&#10004;           |&#10004; |
|    |Rücksetztaste         |&#10004;           |         ||
|    |Downloadschlüssel         |&#10004;           |&#10004;          |&#10004; |
|    |Registrierung aufheben         |&#10004;           |&#10004;           |&#10004; |
|Gruppenverwaltung   |Erstellen         |&#10004;           |           ||
|    |Anzeigen       |&#10004;          |&#10004;           ||
|    |Ändern         |&#10004;           |           ||
|Ringverwaltung aktualisieren    |Erstellen         |&#10004;           |           ||
|    |Anzeigen         |&#10004;           |           ||
|    |Ändern         |&#10004;           |           ||
|Berichte   |Anzeigen        |&#10004;           |&#10004;           ||
|Ticketverwaltung   |Erstellen eines Kundenvorfalls         |&#10004;           |&#10004;           |&#10004;  |
|    |Anzeigen         |&#10004;           |&#10004;           |&#10004;  |
|    |Aktualisieren         |&#10004;           |&#10004;           |&#10004;  |
|einstellungen für verwaltete Dienste Microsoft Teams-Räume    |Anzeigen         |&#10004;           |         ||
|    |Ändern        |&#10004;           |         ||
|Rollenverwaltung    |Anzeigen         |&#10004;           |         ||
|    |Ändern         |&#10004;           |         ||

## <a name="create-a-custom-role"></a>Erstellen einer benutzerdefinierten Rolle

Wenn die integrierten Rollen nicht den Anforderungen Ihrer Organisation entsprechen, können Sie eine Rolle erstellen und deren Berechtigungen nach Bedarf konfigurieren. Um eine Rolle zu erstellen, müssen Sie ein globaler Administrator oder Verwalteter Dienstadministrator sein. 

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams-Räume verwalteten Dienstportals zu **"Einstellungsrollen"** > .
2. Wählen Sie **"Rolle erstellen" aus**.
3. Geben Sie auf der Seite **"Allgemeine Einstellungen"** unter **"Rolleneigenschaften**" einen Namen für diese Rolle ein. Geben Sie unter **"Beschreibung**" Details zu dieser Rolle ein. Wählen Sie **"Weiter**" aus.
4. Wählen Sie auf der Seite **"Berechtigungen"** unter " **Rollenberechtigungen**" die Berechtigungen für diese Rolle aus, indem Sie die entsprechenden Kontrollkästchen aktivieren. Wählen Sie **"Weiter** " aus, um die erste Aufgabe für diese Rolle zu erstellen.
5. Geben Sie auf der Seite **"Zuordnungen** " unter " **Zuordnungseigenschaften**" einen Namen für diese Aufgabe ein. Die Beschreibung ist optional. Aktivieren Sie unter " **Benachrichtigungseinstellungen** " das Kontrollkästchen " **E-Mail-Benachrichtigungen** ", wenn Benutzer dieser Rolle E-Mail-Benachrichtigungen vom Dienst in Räumen im **Bereich** dieser Aufgabe erhalten sollen. Wählen Sie **"Weiter**" aus.
6. Geben Sie auf der Seite **"Mitglieder** " im Feld **"Nach Benutzer oder Sicherheitsgruppe suchen** " den Namen eines Benutzers oder einer Sicherheitsgruppe in Ihrem Mandanten ein, dem Sie Berechtigungen erteilen möchten, und schließen Sie dann die Auswahl ab. Wählen Sie **"Weiter**" aus. 
7. Geben Sie auf der Seite **"Bereich** " im Feld **"Raum oder Raumgruppe suchen** " den Namen eines Chatrooms oder einer Raumgruppe ein, die der Benutzer verwalten darf. Wählen Sie **"Weiter**" aus.
8. Überprüfen Sie auf der Seite **"Fertig stellen** " die Details der Rolle und Zuweisung. Wenn Sie mit der Konfiguration zufrieden sind, wählen Sie " **Neue Rolle hinzufügen" aus**. Wenn Sie einen Abschnitt bearbeiten möchten, verwenden Sie die Schaltfläche **"Vorherige** ", oder wählen Sie den Schritt im linken Navigationsbereich aus.  

## <a name="assign-a-role"></a>Zuweisen einer Rolle

Zum Zuweisen von Rollen müssen Sie ein globaler Administrator oder Verwalteter Dienstadministrator sein oder über eine Rolle mit Rollenverwaltungsberechtigungen verfügen.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams-Räume verwalteten Dienstportals zu **"Einstellungsrollen"** > .

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="Screenshot der Zugriffssteuerungsseite mit Rollen.":::

2. Wählen Sie die Rolle aus, die Sie zuweisen möchten.
3. Wählen Sie im Rollenbereich "Aufgaben **hinzufügen"** **aus** > .

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="Screenshot der Option &quot;Hinzufügen&quot; zum Hinzufügen einer Rolle.":::

4. Geben Sie auf der Seite **"Allgemeine Einstellungen"** unter " **Zuordnungseigenschaften**" einen Namen für diese Aufgabe ein. Die Beschreibung ist optional. Aktivieren Sie unter " **Benachrichtigungseinstellungen**" das Kontrollkästchen " **E-Mail-Benachrichtigungen** ", wenn Benutzer dieser Rolle E-Mail-Benachrichtigungen vom Dienst in Räumen im **Bereich** dieser Aufgabe erhalten sollen. Wählen Sie **"Weiter**" aus. 
5. Geben Sie auf der Seite **"Mitglieder** " im Feld **"Nach Benutzer oder Sicherheitsgruppe suchen** " den Namen eines Benutzers oder einer Sicherheitsgruppe in Ihrem Mandanten ein, dem Sie Berechtigungen erteilen möchten, und schließen Sie dann die Auswahl ab. Wählen Sie **"Weiter**" aus. 
6. Geben Sie auf der Seite **"Bereich** " im Feld **"Raum oder Raumgruppe suchen** " den Namen eines Chatrooms oder einer Raumgruppe ein, die der Benutzer verwalten darf. Wählen Sie **"Weiter**" aus.
7. Überprüfen Sie auf der Seite **"Fertig stellen** " die Details der Aufgabe. Wenn Sie mit der Konfiguration zufrieden sind, wählen Sie **"Zuweisung hinzufügen"** aus. Wenn Sie einen Abschnitt bearbeiten möchten, verwenden Sie die Schaltfläche **"Vorherige** ", oder wählen Sie den Schritt im linken Navigationsbereich aus.  

## <a name="related-topics"></a>Verwandte Themen

- [Microsoft Teams-Räume verwalteten Dienst](microsoft-teams-rooms-premium.md)
