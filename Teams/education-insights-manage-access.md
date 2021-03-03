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
ms.openlocfilehash: 32bd773975ff6b67d28ab765ffa7c932e978af7d
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145935"
---
# <a name="manage-user-access-to-education-insights"></a>Verwalten des Benutzerzugriffs auf Education Insights

Dieses Dokument enthält die erforderlichen Schritte zum Verwalten des Benutzerzugriffs auf [Education Insights in Microsoft Teams](class-insights.md).

Sie müssen Berechtigungen erteilen an leitende akademische Beauftragte, Abteilungsleiter, Bezirksleiter, Schuldirektoren, Schulleiter, Beratungslehrer, Fachleiter, Programmleiter, Sozialarbeiter sowie Psychologen. Dozenten werden *automatisch* Berechtigungen erteilt, wenn sie ein Klassenteam besitzen.

Um Insights auf Organisationsebene bereitzustellen, müssen Sie [Daten vom Studenteninformationssystem (SIS) importieren](education-insights-sis-data-sync.md), damit Insights die hierarchische Struktur des Bildungssystems richtig zugeordnet ist.

> [!NOTE]
> Nur der Globale Administrator kann den Benutzerzugriff auf Insights verwalten.

> [!TIP]
> Wir empfehlen Ihnen, Insights für alle Ihre Bildungsleiter zu aktivieren, damit sie die Daten zum Verständnis der einzelnen Schulen zur Verfügung haben und in der Lage sind, Probleme schnell zu erkennen und ihre Dozenten zu unterstützen. Selbst wenn Sie ein Pilotprojekt ausführen, kann es dennoch hilfreich sein, die Einblicke für alle Bildungsleiter aktiviert zu lassen, die Kommunikation aber nur auf die Pilotgruppe von Benutzern auszurichten.



## <a name="grant-permissions"></a>Erteilen von Berechtigungen

* Öffnen Sie die Insights-App, klicken Sie auf **Einstellungen**, und wählen Sie **Benutzerberechtigungen** aus.

:::image type="content" source="media/insights-user-permissions.png" alt-text="Einstellungen":::

* Wählen Sie **Benutzer hinzufügen** aus.
* Geben Sie den Benutzernamen oder die E-Mail-Adresse jedes Benutzers ein.
* Wählen Sie eine Berechtigungsstufe aus:
  * Der **Zugriff auf alle Organisationseinheiten** bedeutet, dass der Benutzer alle Organisationseinheiten auf allen Ebenen sieht.
  * Der **Zugriff auf bestimmte Schulen** bedeutet, dass der Benutzer die ausgewählten Schulen sieht. Beginnen Sie mit der Eingabe, und wählen Sie die Schule/Hochschule aus der Liste aus. Sie können mehrere Schulen gleichzeitig hinzufügen.
* Klicken Sie auf **Neue Benutzer hinzufügen**.

:::image type="content" source="media/insights-add-users.png" alt-text="Erteilen von Berechtigungen":::

> [!NOTE]
> Erteilen Sie Berechtigungen nur an die Schulleiter, die sie benötigen und nur für die Organisationseinheiten, für die sie verantwortlich sind. Wenn Sie nicht sicher sind, ob für eine bestimmte Organisation eine Benutzerberechtigung erforderlich ist, wenden Sie sich an die Fachleute für den Datenschutz in Ihrer Bildungseinrichtung, z. B. Mitarbeiter im Rechts- oder Personalwesen.

## <a name="edit-permissions"></a>Berechtigungen bearbeiten 
* Wählen Sie einen bestimmten Benutzer und dann **Berechtigungen bearbeiten**.
* Aktualisieren Sie die Liste der Berechtigungsstufen oder Schulen und klicken Sie auf **Berechtigungen aktualisieren**.

:::image type="content" source="media/insights-edit-users.png" alt-text="Berechtigungen bearbeiten":::

## <a name="remove-permissions"></a>Berechtigungen entfernen
* Wählen Sie die Benutzer aus, die Sie entfernen möchten, und wählen Sie dann **Benutzer entfernen** aus.
* Diese Benutzer haben keinen Zugriff mehr auf Insights auf Organisationsebene, können aber weiterhin auf Insights auf Klassenebene zugreifen, wenn sie ein Klassenteam besitzen.

:::image type="content" source="media/insights-remove-users.png" alt-text="Berechtigungen entfernen":::
