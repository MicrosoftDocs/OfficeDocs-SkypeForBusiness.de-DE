---
title: Konfigurieren von ServiceNow für Teams-Räume
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: ronmart
ms.topic: article
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Informationen zum Konfigurieren von ServiceNow im Teams-Räume Premium-Portal
f1keywords: ''
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
ms.openlocfilehash: 920d31a350914115623a83f018815d8bebe94f6a
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272380"
---
# <a name="configure-servicenow-for-teams-rooms"></a>Konfigurieren von ServiceNow für Teams-Räume

In diesem Artikel werden die Voraussetzungen und Schritte zum Konfigurieren Ihrer ServiceNow-Umgebung im Teams-Räume Premium-Portal beschrieben.

## <a name="watch-microsoft-teams-rooms--managed-services-service-now-integration"></a>Watch: Microsoft Teams-Räume – Managed Services Service Now Integration

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4ZK4B]


### <a name="teams-rooms-prerequisites"></a>Teams-Räume Voraussetzungen

- Ihnen muss eine Dienstadministratorrolle zugewiesen sein. Weitere Informationen finden Sie unter [Rollenbasierte Zugriffssteuerung mit den Microsoft Teams-Räume Managed Services](microsoft-teams-rooms-premium-rbac.md).

### <a name="servicenow-prerequisites"></a>Voraussetzungen für ServiceNow

- Eine grundlegende Autorisierungsanmeldung oder eine [OAuth-Anmeldung](https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/security/concept/c_OAuthApplications.html) . Weitere Informationen finden Sie unter [Erstellen von Anmeldeinformationen](https://developer.servicenow.com/dev.do#!/learn/learning-plans/rome/servicenow_application_developer/app_store_learnv2_rest_rome_creating_credentials) in ServiceNow.
- Eine ServiceNow-Instanz und deren Instanzhostname und API-URI
- Eine Rolle von incident_manager oder höher
- Eine Softwareversion von ServiceNow, die die Tabellen-API unterstützt

## <a name="configure-your-environment"></a>Konfigurieren Ihrer Umgebung

Die Konfiguration Ihrer Umgebung ist hochgradig anpassbar und hängt von den Anforderungen Ihrer Organisation ab. Die folgenden Schritte führen Sie durch das Kopieren Ihrer vorhandenen Konfiguration in ServiceNow in das Teams-Räume Premium-Portal.

1. Öffnen Sie die ServiceNow-Instanz, die Sie kopieren möchten. Sie müssen darauf verweisen, wenn Sie das Konfigurationsformular im Teams-Räume Premium-Portal ausfüllen.
2. Wechseln Sie auf einer neuen Browserregisterkarte zum [Teams-Räume Premium-Portal](https://portal.rooms.microsoft.com/) und zu **"Einstellungen"**. Wählen Sie dann im linken Navigationsmenü **ServiceNow** aus, um das Konfigurationsformular zu öffnen.
3. Wählen Sie eine Authentifizierungsmethode aus, um sich anzumelden und Ihren ServiceNow-Instanzhost und API-URI einzugeben.
4. Alle erforderlichen Elemente in der Spalte "ServiceNow-Feld" des Abschnitts "Feldzuordnung" sollten vorgefüllt werden. Die folgende Tabelle enthält jedes ServiceNow-Feld und das entsprechende Microsoft Teams-Räume Feld. Schließen Sie die Aktion für jede Zeile des Feldzuordnungsabschnitts ab. Definitionen der einzelnen ServiceNow-Felder finden Sie unter [ServiceNow-Felddefinitionen](#servicenow-field-definitions).

| ServiceNow-Feld | Microsoft Teams-Räume Feld | Aktion |
| --- | --- | --- |
| short_description | Beschreibung des Vorfalls | Keine Aktion erforderlich. Das Teams-Räume Feld wird automatisch ausgefüllt. |
| Beschreibung | Erste Nachricht | Keine Aktion erforderlich. Das Teams-Räume Feld wird automatisch ausgefüllt. |
| assignment_group | Raumgruppe | Kopieren Sie den assignment_group Wert in Ihrer ServiceNow-Instanz, und fügen Sie ihn in das Feld "ServiceNow-Wert" im Konfigurationsformular ein. Wenn Sie mehrere assignment_group haben, wählen Sie " **Raumgruppe hinzufügen"** für jeden zusätzlichen benutzerdefinierten Wert aus. |
| Schweregrad | Ringe | Der Schweregrad ist ein benutzerdefinierter Wert in ServiceNow. Es ist das vierte Element in der zweiten Spalte Ihrer ServiceNow-Instanz. Kopieren Sie den Wert, und fügen Sie ihn in das Feld "ServiceNow-Wert" im Konfigurationsformular ein. Wenn Sie mehrere Schweregrade haben, wählen Sie " **Ring hinzufügen"** für jeden zusätzlichen benutzerdefinierten Wert aus. |
| Kommentare (optional) | Benutzerdefinierter Wert* | Wenn Sie dem Konfigurationsformular ein Kommentarfeld hinzufügen möchten, wählen Sie oben im Feldzuordnungsabschnitt " **Hinzufügen"** aus. Kopieren Sie den Kommentarwert in Ihrer ServiceNow-Instanz, und fügen Sie ihn in das Feld "ServiceNow" im Konfigurationsformular ein. Weisen Sie ihm ein Microsoft Teams-Raumfeld aus dem Dropdownmenü zu, und kopieren Sie den ServiceNow-Wert, und fügen Sie ihn ein. |
| Status (aufgelöst) | Benutzerdefinierter Wert* | Kopieren Sie den Auflösungszustand aus Ihrer ServiceNow-Instanz, und fügen Sie ihn in das Feld "ServiceNow-Wert" im Konfigurationsformular ein. |
| close_code | Benutzerdefinierter Wert* | Kopieren Sie auf der Registerkarte " **Lösungsinformationen** " Ihrer ServiceNow-Instanz den schließenden Code, und fügen Sie ihn in das Feld "ServiceNow-Wert" in das Konfigurationsformular ein. |

*Auswählen von benutzerdefinierten Werten im Dropdownmenü

>[!NOTE]
>Wenn Sie Ihre benutzerdefinierten Werte nicht finden können, wenden Sie sich an Ihren ServiceNow-Administrator.

Wenn Sie zusätzliche erforderliche Felder zum Abschnitt "Vorfall beheben" hinzufügen möchten, wählen Sie **"Hinzufügen"** aus.

## <a name="test-and-enable"></a>Testen und Aktivieren

Wählen Sie nach Abschluss des Konfigurationsformulars unten auf der Seite " **Testen** " aus. Tests sind erforderlich, um Ihre Konfiguration zu übermitteln.

Nachdem Ihr Test erfolgreich bestanden wurde, wählen Sie **"Absenden** " aus, um Ihre Änderungen zu speichern. Sobald Sie bereit sind, ServiceNow für Ihre Organisation zu aktivieren, setzen Sie die Umschaltfläche " **Möchten Sie ServiceNow aktivieren?** " auf " **Ein**".

## <a name="servicenow-field-definitions"></a>ServiceNow-Felddefinitionen

- **short_description**: Das Feld "Kurzbeschreibung" in ServiceNow ist ein kurzer alphanumerischer Wert mit 160 Zeichen, der eine Zusammenfassung des Vorfalls bereitstellt. Die Kurzbeschreibung entspricht der Vorfallbeschreibung im Teams-Räume Premium-Portal.

- **beschreibung**: Das Beschreibungsfeld in ServiceNow ist der erste Wert im Unterhaltungsverlauf eines ServiceNow-Vorfalls. Die Beschreibung entspricht der ersten Nachricht im Teams-Räume Premium-Portal.

- **assignment_group**: Das Zuordnungsgruppenfeld in ServiceNow wird verwendet, um Vorfälle zu organisieren. Zuordnungsgruppen entsprechen Raumgruppen im Teams-Räume Premium-Portal. Standardmäßig gibt es eine Raumgruppe, und es können weitere hinzugefügt werden. Sie entscheiden, wie viele Gruppen es gibt und wie Sie Ihre Vorfälle gruppieren. Beispielsweise können Sie Ihre Vorfälle nach Standort organisieren.

- **schweregrad**: Das Schweregradfeld in ServiceNow wird verwendet, um Vorfälle nach Priorität zu organisieren. Die Werte, die die Priorität festlegen, können angepasst werden. Der Schweregrad entspricht dem Feld "Ring" im Teams-Räume Premium-Portal. Um Ringe im Teams-Räume Premium-Portal anzupassen, wechseln Sie im linken Navigationsmenü zu **Aktualisierungen**. Wechseln Sie dann zur Registerkarte **"Ringe** ", und wählen Sie **"Ring hinzufügen"** aus.

- **Kommentare**: Kommentare ist ein optionales Feld in ServiceNow, das verwendet wird, um benutzerdefinierte erforderliche Felder aus Ihrer ServiceNow-Instanz in Ihre Teams-Räume Premium-Portalkonfiguration einzuschließen. Das Äquivalent von Kommentaren ist ein benutzerdefinierter Wert im Teams-Räume Premium-Portal.

- **state (resolved)**: Das Statusfeld (aufgelöst) in ServiceNow wird verwendet, um anzugeben, wie ein Vorfall behoben wurde, und ist erforderlich, um einen Vorfall zu schließen. Der Zustandswert (aufgelöst) kann angepasst werden. Das Äquivalent des Zustands (aufgelöst) ist ein benutzerdefinierter Wert im Teams-Räume Premium-Portal.

- **close_code**: Einem Vorfall muss ein enger Code zugewiesen werden, sobald er vollständig behoben ist. Dieser Wert kann in ServiceNow angepasst werden. Das Äquivalent von Close-Code ist ein benutzerdefinierter Wert im Teams-Räume Premium-Portal.
