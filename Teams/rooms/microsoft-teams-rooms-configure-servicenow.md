---
title: Konfigurieren von ServiceNow für Teams-Räume
author: cazawideh
ms.author: czawideh
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Informationen zum Konfigurieren von ServiceNow im Teams-Räume Premium Portal
f1keywords: ''
ms.openlocfilehash: a7e1313321c5e556be814d7aa0bd0b80ae9bcb35
ms.sourcegitcommit: 69a5d4994ef75b9c16efa99554fb7f2ee1ccf52a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2021
ms.locfileid: "58973227"
---
# <a name="configure-servicenow-for-teams-rooms"></a>Konfigurieren von ServiceNow für Teams-Räume

In diesem Artikel werden die Voraussetzungen und Schritte zum Konfigurieren Ihrer ServiceNow-Umgebung im Teams-Räume Premium beschrieben.

## <a name="before-you-begin"></a>Bevor Sie beginnen

### <a name="teams-rooms-prerequisites"></a>Teams-Räume Voraussetzungen

- Ihnen muss eine Dienstadministratorrolle zugewiesen sein. Weitere Informationen finden Sie unter [Rollenbasierte Zugriffssteuerung mit dem Microsoft Teams-Räume Verwaltete Dienste.](microsoft-teams-rooms-premium-rbac.md)

### <a name="servicenow-prerequisites"></a>ServiceNow-Voraussetzungen

- Eine Standardautorisierungs-Anmeldung oder eine OAuth-Anmeldung. Weitere Informationen finden Sie unter [Erstellen von Anmeldeinformationen](https://developer.servicenow.com/dev.do#!/learn/learning-plans/rome/servicenow_application_developer/app_store_learnv2_rest_rome_creating_credentials) in ServiceNow.
- Eine ServiceNow-Instanz und deren Instanzhostname und API-URI
- Eine Rolle incident_manager oder höher
- Eine Softwareversion von ServiceNow, die Tabellen-API unterstützt

## <a name="set-up-servicenow-configuration-to-teams-rooms"></a>Einrichten der ServiceNow-Konfiguration für Teams-Räume

Die Konfiguration Ihrer Umgebung ist in hohem Maße anpassbar und hängt von den Anforderungen Ihrer Organisation ab. In den folgenden Schritten wird das Kopieren Ihrer vorhandenen Konfiguration in ServiceNow in das Teams-Räume Premium schritt.

1. Öffnen Sie die ServiceNow-Instanz, die Sie kopieren möchten. Sie müssen darauf verweisen, wenn Sie das Konfigurationsformular im Teams-Räume Premium ausfüllen.
2. Wechseln Sie auf einer neuen Browserregisterkarte zum portal [Teams-Räume Premium,](https://portal.rooms.microsoft.com/) und wechseln Sie **zu Einstellungen.** Wählen Sie dann **im linken Navigationsmenü ServiceNow** aus, um das Konfigurationsformular zu öffnen.
3. Wählen Sie eine Authentifizierungsmethode aus, um sich anmelden und Ihren ServiceNow-Instanzhost und API-URI ein eingeben.
4. Alle erforderlichen Elemente in der Spalte "ServiceNow Field" des Abschnitts "Feldzuordnung" sollten vorab ausgefüllt werden. Die folgende Tabelle enthält jedes "ServiceNow"-Feld und das entsprechende Microsoft Teams-Räume Feld. Führen Sie die Aktion für jede Zeile des Abschnitts Feldzuordnung aus. Definitionen der einzelnen "ServiceNow"-Felds finden Sie unter [ServiceNow-Felddefinitionen.](#servicenow-field-definitions)

| **ServiceNow-Feld** | **Microsoft Teams-Räume** | **Aktion** |
| --- | --- | --- |
| short_description | Vorfallbeschreibung | Keine Aktion erforderlich. Das Teams-Räume Feld wird automatisch ausgefüllt. |
| Beschreibung | Erste Nachricht | Keine Aktion erforderlich. Das Teams-Räume Feld wird automatisch ausgefüllt. |
| assignment_group | Gruppe "Raum" | Kopieren Sie assignment_group Wert in Ihrer ServiceNow-Instanz, und fügen Sie ihn in das Feld "ServiceNow"-Wert im Konfigurationsformular ein. Wenn Sie mehrere Gruppen assignment_group, wählen Sie **Raumgruppe** hinzufügen für jeden zusätzlichen benutzerdefinierten Wert aus. |
| Schweregrad | Ringe | Der Schweregrad ist ein benutzerdefinierter Wert in ServiceNow. Dies ist das vierte Element in der zweiten Spalte ihrer ServiceNow-Instanz. Kopieren Sie den Wert, und fügen Sie ihn in das Wertfeld ServiceNow im Konfigurationsformular ein. Wenn Sie mehrere Schweregrade haben, wählen Sie für jeden zusätzlichen benutzerdefinierten Wert **Ring** hinzufügen aus. |
| Kommentare (optional) | Benutzerdefinierter Wert* | Wenn Sie dem Konfigurationsformular ein  Kommentarfeld hinzufügen möchten, wählen Sie oben im Abschnitt feldzuordnung die Option Hinzufügen aus. Kopieren Sie den Kommentarwert in Ihrer ServiceNow-Instanz, und fügen Sie ihn in das Feld "ServiceNow" im Konfigurationsformular ein. Weisen Sie ihr Microsoft Teams Feld "Raum" aus dem Dropdownmenü zu, und kopieren Sie den Wert "ServiceNow", und fügen Sie ihn ein. |
| Zustand (aufgelöst) | Benutzerdefinierter Wert* | Kopieren Sie den Auflösungszustand aus Ihrer ServiceNow-Instanz, und fügen Sie ihn in das Wertfeld ServiceNow im Konfigurationsformular ein. |
| close_code | Benutzerdefinierter Wert* | Kopieren Sie **auf der Registerkarte** Auflösungsinformationen Ihrer ServiceNow-Instanz den Code, und fügen Sie ihn in das Feld "ServiceNow"-Wert in das Konfigurationsformular ein. |

*Wählen Sie benutzerdefinierte Werte aus dem Dropdownmenü aus.

>[!NOTE]
>Wenn Sie Ihre benutzerdefinierten Werte nicht finden können, wenden Sie sich an Ihren ServiceNow-Administrator.

Wenn Sie dem Abschnitt Vorfall zusätzliche Pflichtfelder hinzufügen möchten, wählen Sie **Hinzufügen aus.**

## <a name="test-and-enable-your-servicenow-configuration"></a>Testen und Aktivieren der ServiceNow-Konfiguration

Nachdem Sie das Konfigurationsformular abgeschlossen haben, wählen **Sie unten** auf der Seite Test aus. Zum Übermitteln der Konfiguration sind Tests erforderlich.

Nachdem der Test erfolgreich abgeschlossen wurde, wählen Sie **Absenden aus,** um Ihre Änderungen zu speichern. Sobald Sie bereit sind, ServiceNow für Ihre Organisation zu aktivieren, schalten Sie den Schalter Möchten Sie **ServiceNow? aktivieren?** auf **Ein.**

## <a name="servicenow-field-definitions"></a>ServiceNow-Felddefinitionen

- **short_description:** Das Kurzbeschreibungsfeld in ServiceNow ist ein kurzer alphanumerischer Wert aus 160 Zeichen, der eine Zusammenfassung des Vorfalls bietet. Die Kurzbeschreibung entspricht der Vorfallbeschreibung im Teams-Räume Premium Portal.

- **description**: Das Beschreibungsfeld in ServiceNow ist der erste Wert im Unterhaltungsverlauf eines ServiceNow-Vorfalls. Die Beschreibung entspricht der Nachricht "First" im Teams-Räume Premium Portal.

- **assignment_group:** Das Zuordnungsgruppesfeld in ServiceNow wird zum Organisieren von Vorfällen verwendet. Aufgabengruppen sind äquivalent zu Raumgruppen im Teams-Räume Premium Portal. Standardmäßig gibt es eine Raumgruppe, und weitere können hinzugefügt werden. Sie entscheiden, wie viele Gruppen es gibt und wie Sie Ihre Vorfälle gruppieren. Beispielsweise können Sie Ihre Vorfälle nach Ort organisieren.

- **Schweregrad:** Das Schweregradfeld in "ServiceNow" wird verwendet, um Vorfälle nach Priorität zu organisieren. Die Werte, die Priorität bestimmen, können angepasst werden. Der Schweregrad entspricht dem Feld "Ring" im Teams-Räume Premium Portal. Um Ringe im Teams-Räume Premium anzupassen, wechseln Sie **im** linken Navigationsmenü zu Updates. Wechseln Sie dann zur Registerkarte **Ringe,** und wählen Sie **Ring hinzufügen aus.**

- **Comments:** Comments ist ein optionales Feld in ServiceNow, das verwendet wird, um benutzerdefinierte erforderliche Felder aus Ihrer ServiceNow-Instanz in Ihre Teams-Räume Premium-Portalkonfiguration zu verwenden. Das Äquivalent zu Kommentaren ist ein benutzerdefinierter Wert im Teams-Räume Premium Portal.

- **State (aufgelöst):** Das Feld "Status" (aufgelöst) in "ServiceNow" wird verwendet, um zu bestimmen, wie ein Vorfall gelöst wurde, und ist erforderlich, um einen Vorfall zu schließen. Der Statuswert (aufgelöst) kann angepasst werden. Das Äquivalent zu Zustand (aufgelöst) ist ein benutzerdefinierter Wert im Teams-Räume Premium Portal.

- **close_code:** Nach der vollständigen Lösung muss einem Vorfall ein Code zum Schließen zugewiesen werden. Dieser Wert kann in ServiceNow angepasst werden. Das Äquivalent zu Close Code ist ein benutzerdefinierter Wert im Teams-Räume Premium Portal.
