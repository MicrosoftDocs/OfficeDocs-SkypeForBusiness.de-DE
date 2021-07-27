---
title: Verwalten des Benutzerzugriffs auf Education Insights
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Verwalten Sie den Benutzerzugriff auf Education Insights in Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7980b062d864b7354a329ce5743b0209d9a54e2a
ms.sourcegitcommit: e3bc5418025780207b05766cd817ef01c014a809
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2021
ms.locfileid: "53565701"
---
# <a name="manage-user-access-to-education-insights"></a>Verwalten des Benutzerzugriffs auf Education Insights

Dieses Dokument enthält die erforderlichen Schritte zum Verwalten des Benutzerzugriffs auf [Education Insights in Microsoft Teams](class-insights.md).

Sie müssen Berechtigungen erteilen an leitende akademische Beauftragte, Abteilungsleiter, Bezirksleiter, Schuldirektoren, Schulleiter, Beratungslehrer, Fachleiter, Programmleiter, Sozialarbeiter sowie Psychologen. Dozenten werden *automatisch* Berechtigungen erteilt, wenn sie ein Klassenteam besitzen.

Um Insights auf Organisationsebene bereitzustellen, müssen Sie [Daten vom Studenteninformationssystem (SIS) importieren](education-insights-sis-data-sync.md), damit Insights die hierarchische Struktur des Bildungssystems richtig zugeordnet ist.

> [!NOTE]
> Nur der Globale Administrator kann den Benutzerzugriff auf Insights verwalten.

> [!TIP]
> Wir empfehlen Ihnen, Insights für alle Ihre Bildungsleiter zu aktivieren, damit sie die Daten zum Verständnis der einzelnen Schulen zur Verfügung haben und in der Lage sind, Probleme schnell zu erkennen und ihre Dozenten zu unterstützen. Selbst wenn Sie ein Pilotprojekt ausführen, kann es dennoch hilfreich sein, die Einblicke für alle Bildungsleiter aktiviert zu lassen, die Kommunikation aber nur auf die Pilotgruppe von Benutzern auszurichten.



## <a name="manange-permissions"></a>Berechtigungen verwalten

* Öffnen Sie die Insights-App, klicken Sie auf **Einstellungen**, und wählen Sie **Benutzerberechtigungen** aus.

:::image type="content" source="media/insights-user-permissions.png" alt-text="Einstellungen":::

> [!NOTE]
> Wenn Sie eine Berechtigung für eine Organisationsebene bereitstellen, kann der Benutzer alle darunter liegenden Organisationseinheiten sehen. Geben Sie die Berechtigung nur denjenigen Bildungsleitern, die sie benötigen.
> 
> Erteilen Sie Berechtigungen nur an die Schulleiter, die sie benötigen und nur für die Organisationseinheiten, für die sie verantwortlich sind. Wenn Sie nicht sicher sind, ob für eine bestimmte Organisation eine Benutzerberechtigung erforderlich ist, wenden Sie sich an die Fachleute für den Datenschutz in Ihrer Bildungseinrichtung, z. B. Mitarbeiter im Rechts- oder Personalwesen.

## <a name="role-based-permissions"></a>Rollenbasierte Berechtigungen

Wenn Sie das [SDS V2.1-Dateiformat](/schooldatasync/sds-v2.1-csv-file-format) oder das [SDS V2-Dateiformat](/schooldatasync/sds-v2-csv-file-format)verwenden, können Sie alle Rollen und die gesamte Hierarchie der Schulen innerhalb des Bildungssystems importieren. Mit dieser vollständigen Zuordnung können Sie Rollen Berechtigungen zuweisen. 

> [!NOTE]
> Wenn einem Benutzer eine Rolle zugewiesen wird, erhält er automatisch die richtigen Berechtigungen, um die für ihn relevanten Daten zu sehen.

* Klicken Sie bei Bedarf auf die Registerkarte **rollenbasierte Berechtigungen**.

  Sie sehen eine Liste der Rollen in Ihrer Bildungsorganisation, die Ebene in dieser Hierarchie für jede Rolle, wie vielen Benutzer diese Rolle zugewiesen ist, und die Berechtigungsstufe der Rolle. 
  
  :::image type="content" source="media/insights-role-based-permissions.png" alt-text="Rollenbasierte Berechtigungen":::
  
  Wenn eine Rolle auf mehr als einer Organisationsebene vorhanden ist, wird diese Rolle mehrmals angezeigt, einmal für jede Ebene. Im Screenshot haben wir Prinzipale sowohl auf Schul- als auch auf Bezirksebene, sodass es zwei Zeilen für „Prinzipal“ gibt.
  
* Klicken Sie für jede Rolle auf das Stiftsymbol, um die Berechtigungsstufe auszuwählen. Der Standard ist, dass die Rolle keine Berechtigung zum Anzeigen von Insights hat.
* Wählen Sie die Berechtigungsstufe aus – **Daten für ihre Organisation anzeigen** oder **Keine**.
* Klicken Sie auf **Änderungen speichern**.

  Diese Berechtigungsstufe wird jetzt automatisch jedem neuen Benutzer mit dieser Rolle und Organisationsebene zugewiesen. Der Benutzer sieht die Daten für alle Organisationseinheiten auf seiner Hierarchieebene und darunter.
  
  Wenn ein Benutzer in der Liste angezeigt wird, der eine differenziertere Berechtigungsstufe benötigt, passen Sie diese in „Individuelle Berechtigungen“ an.
  
  Wenn ein Benutzer nicht mehr einer Rolle angehört, wird seine Berechtigung für diese Rolle automatisch widerrufen (obwohl er möglicherweise noch über individuelle Berechtigungen verfügt).


## <a name="individual-permissions"></a>Individuelle Berechtigungen

Verwenden Sie individuelle Berechtigungen, um die Berechtigung für einen Benutzer anzupassen, oder um jedem Benutzer Berechtigungen zuzuweisen, wenn Sie nicht SDS V2 zum Importieren von SIS-Daten für die Organisation verwendet haben.

* Klicken Sie auf die Registerkarte **Individuelle Berechtigungen**.
  
  Sie sehen die Benutzer in Ihrer Bildungsorganisation, denen eine individuelle Berechtigung erteilt wurden. 
  
  :::image type="content" source="media/insights-individual-permissions.png" alt-text="Individuelle Berechtigungen":::
  
### <a name="grant-individual-permission-to-a-user"></a>Erteilen individueller Berechtigungen für einen Benutzer
* Klicken Sie oben links auf dem Bildschirm auf **Erteilen individueller Berechtigungen**.
* Geben Sie den Benutzernamen oder die E-Mail-Adresse jedes Benutzers ein.
* Wählen Sie eine Berechtigungsstufe aus:
  * **Alle** bedeutet, dass der Benutzer alle Organisationseinheiten auf allen Ebenen sieht. Dies wird sehr selten verwendet.
  * **Bestimmte Organisation** bedeutet, dass der Benutzer die ausgewählte Organisationseinheit und alle darunter liegenden Organisationseinheiten sieht. Beginnen Sie mit der Eingabe, und wählen Sie die Organisationseinheit aus der Liste aus.
* Klicken Sie auf **Berechtigung gewähren**, um zu speichern.

### <a name="change-the-individual-permission-of-a-user"></a>Ändern der individuellen Berechtigung eines Benutzers
* Klicken Sie für den jeweiligen Benutzer auf das Stiftsymbol, um die individuelle Berechtigungsstufe auszuwählen.
* Wählen Sie die Berechtigungsstufe aus:
  * **Alle** bedeutet, dass der Benutzer alle Organisationseinheiten auf allen Ebenen sieht. Dies wird sehr selten verwendet.
  * **Bestimmte Organisation** bedeutet, dass der Benutzer die ausgewählte Organisationseinheit und alle darunter liegenden Organisationseinheiten sieht. Beginnen Sie mit der Eingabe, und wählen Sie die Organisationseinheit aus der Liste aus.
  * **Keine** bedeutet, dass der Benutzer nur die Organisationseinheiten sieht, die automatisch durch seine Rolle zugewiesen werden (sofern vorhanden).
* Klicken Sie auf **Änderungen speichern**, um zu speichern.
