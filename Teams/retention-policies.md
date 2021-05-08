---
title: Aufbewahrungsrichtlinien für Microsoft Teams Verwalten
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Mithilfe von Aufbewahrungsrichtlinien für Microsoft Teams Nachrichten, die Ihre Organisation erfüllen muss, um interne Richtlinien, brancheninterne Vorschriften oder gesetzliche Vorschriften einzuhalten, und zum Löschen von Nachrichten, die als Haftungsausschluss betrachtet werden oder keinen juristischen geschäftlichen Wert haben.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ec6b257f91c7e5003a4a69079e37b20b5f338528
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617757"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>Aufbewahrungsrichtlinien für Microsoft Teams Verwalten

> [!NOTE]
> Wenn Sie in Teams eine Meldung sehen, dass Ihre Chats oder Nachrichten durch eine Aufbewahrungsrichtlinie gelöscht wurden, lesen Sie [Teams-Nachrichten zu Aufbewahrungsrichtlinien](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).
> 
> Die Informationen auf dieser Seite richten sich an IT-Administratoren, die diese Aufbewahrungsrichtlinien verwalten.

Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen von Microsoft 365 helfen Ihnen, die Informationen in Ihrer Organisation effektiver zu verwalten. Sie können Aufbewahrungseinstellungen konfigurieren, um Daten zu speichern, die zur Einhaltung der internen Richtlinien, brancheninternen Vorschriften oder gesetzlichen Vorschriften Ihrer Organisation erforderlich sind. Sie können die Aufbewahrungseinstellungen auch so konfigurieren, dass Daten gelöscht werden, die als Belastung angesehen werden, die Sie nicht mehr aufbewahren müssen oder die keinen rechtlichen oder geschäftlichen Wert haben.

Teams unterstützt Aufbewahrungsrichtlinien für Chat- und Kanal-Nachrichten, so dass Sie als Administrator proaktiv entscheiden können, ob Sie diese Daten aufbewahren, löschen oder für einen bestimmten Zeitraum aufbewahren und dann löschen möchten. Der Anfang des Aufbewahrungszeitraums für diese Aktionen basiert immer auf dem Erstellen einer Nachricht. Sie können eine Aufbewahrungsrichtlinie für Teams auf Ihre gesamte Organisation oder bestimmte Benutzer und Teams anwenden. Aufbewahrungsbezeichnungen werden für Teams nicht unterstützt.

Weitere Informationen zu Aufbewahrungslösungen in Microsoft 365 finden Sie unter [Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen.](/microsoft-365/compliance/retention)

Benutzer, die einer Aufbewahrungsrichtlinie für Teams unterliegen, müssen über eine entsprechende Lizenz verfügen, z. B. Office 365 E3 oder Office 365 A3. Weitere Lizenzierungsoptionen für diese Aufbewahrungsrichtlinien finden Sie im Abschnitt ["Informations-Governance"](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) Microsoft 365 Richtlinien zur Lizenzierung von & [Compliance.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) Weitere Informationen zur Lizenzierung für lizenzen für Teams Sie unter [Microsoft Teams Dienstbeschreibung](/office365/servicedescriptions/teams-service-description).

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a>Unterstützung Teams Aufbewahrungsrichtlinien für Aufbewahrungs- und Löschaktionen

Wenn Sie eine Aufbewahrungsrichtlinie Teams, um Chats oder Kanalnachrichten zu behalten, können Benutzer ihre Nachrichten in ihrer App weiterhin bearbeiten Teams löschen. Obwohl Die Benutzer ihre bereits bearbeiteten oder gelöschten Nachrichten in Teams nicht mehr sehen können, werden die Daten dieser Nachrichten an einem sicheren Ort gespeichert, der für eDiscovery-Suchen durch Complianceadministratoren vorgesehen ist. Das endgültige Löschen dieser Daten geschieht nicht vor dem Ende des konfigurierten Aufbewahrungszeitraums, wenn eine andere Aufbewahrungsrichtlinie für die Aufbewahrung dieser Daten konfiguriert ist oder die Daten einem [eDiscovery-Speicher](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds)unterliegen.

Wenn eine Aufbewahrungsrichtlinie zum Löschen von Chats und Kanalnachrichten konfiguriert ist, sind diese Nachrichten für das automatische Löschen berechtigt. Wenn die Meldungen weiterhin in der Teams-App angezeigt werden, werden sie dort nicht mehr angezeigt, und die Benutzer werden informiert, dass diese Nachrichten von einer Aufbewahrungsrichtlinie [gelöscht wurden.](#end-user-experience) Wenn die Nachrichten zuvor einer Aufbewahrungsaktion unterliegen und von Benutzern bearbeitet oder gelöscht wurden, werden diese Nachrichten jetzt aus dem sicheren Speicherort gelöscht und bei eDiscovery-Suchen nicht mehr zurückgegeben.

Ausführliche Informationen dazu, wie diese Richtlinien je nach Richtlinienkonfiguration und Benutzeraktionen funktionieren und welche Nachrichtendaten für Teams-Aufbewahrungsrichtlinien einbezogen und ausgeschlossen werden, finden Sie unter Informationen zur Aufbewahrung für [Microsoft Teams.](/microsoft-365/compliance/retention-policies-teams) Auf dieser Seite wird auch erläutert, warum es beim Löschen von Nachrichten durch Aufbewahrungsrichtlinien manchmal zu Verzögerungen kommen kann. Beispielsweise können Nachrichten benutzern in der Teams-App bis zu sieben Tage nach dem in der Aufbewahrungsrichtlinie konfigurierten Ablaufzeitraum angezeigt werden.

Wenn Sie mehrere Aufbewahrungsrichtlinien für Teams mit unterschiedlichen Aufbewahrungseinstellungen einrichten, klären die Grundsätze der Aufbewahrung alle Konflikte. Beispiel:

- Wenn es einen Konflikt zwischen der Aufbewahrung oder dem Löschen desselben Inhalts gibt, werden die Inhalte immer am sicheren Ort aufbewahrt, sodass sie für Complianceadministratoren mit eDiscovery durchsucht werden können.
    
    Dieses Prinzip gilt auch für Nachrichten, die aus juristischen oder juristischen Gründen unter eDiscovery-Halte halte ich.

- Wenn es einen Konflikt bei der Aufbewahrungsdauer für dieselben Inhalte gibt, werden diese über den längsten Aufbewahrungszeitraum an einem sicheren Ort aufbewahrt.

Diese beiden Grundsätze der Aufbewahrung adressieren die meisten Konflikte, die entstehen können, wenn Sie mehrere Aufbewahrungsrichtlinien für Teams haben. Weitere Informationen finden Sie unter [Die Grundsätze der Aufbewahrung oder was hat Vorrang?](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Wann sind die Aufbewahrungsrichtlinien für Teams zu verwenden

In vielen Fällen betrachten Organisationen private Chat-Daten als eine größere Belastung als Kanalnachrichten, bei denen es sich in der Regel eher um projektbezogene Gespräche handelt.

Sie können separate Aufbewahrungsrichtlinien für private Chats (1:1- oder 1:Viele-Chats) und Kanalnachrichten einrichten. Sie können auch eindeutige Richtlinien konfigurieren, die für bestimmte Benutzer oder Teams in Ihrer Organisation gelten. Bei Teams-Chats können Sie auswählen, für welche Benutzer die Richtlinie gilt. Bei Teams-Kanalnachrichten können Sie auswählen, für welche Teams die Richtlinie gilt.

So können Sie beispielsweise für Kanalnachrichten eine Aufbewahrungsrichtlinie auf bestimmte Teams in Ihrer Organisation anwenden, und diese Richtlinie wird nach einem Jahr mit einer Löschaktion konfiguriert. Wenden Sie dann eine weitere Aufbewahrungsrichtlinie auf alle anderen Teams an, und diese Richtlinie wird nach 3 Jahren mit einer Löschaktion konfiguriert.

## <a name="create-and-manage-retention-policies-for-teams"></a>Aufbewahrungsrichtlinien für Teams erstellen und verwalten

Verwenden Sie zum Erstellen oder Bearbeiten einer Aufbewahrungsrichtlinie für Chats und Teams Kanalnachrichten die Anweisungen aus Aufbewahrungsrichtlinie für [Teams Speicherorte.](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)

Diese Seite bietet zusätzliche Informationen zum Erstellen und Verwalten von Aufbewahrungsrichtlinien für andere Workloads in Microsoft 365. Sie könnten zum Beispiel auch eine Aufbewahrungsrichtlinie für Microsoft 365 Groups erstellen, um Dateien aufzubewahren und zu löschen, auf die in Teams zugegriffen wird und die in OneDrive oder SharePoint gespeichert sind.  

## <a name="end-user-experience"></a>Endbenutzererfahrung

Bei privaten Chats (1:1-Chats) oder Gruppenchats sehen Benutzer, dass Chats, die älter sind als die Konfiguration der Aufbewahrungsrichtlinie, gelöscht werden. Zudem wird eine automatisch generierte Nachricht mit dem Hinweis "Wir haben ältere Nachrichten aufgrund der Aufbewahrungsrichtlinie Ihrer Organisation gelöscht" über den noch nicht gelöschten Nachrichten angezeigt. Beispiel:

:::image type="content" source="media/retention-policies-image1.png" alt-text="Benutzer in Teams informiert, dass Chatnachrichten aufgrund einer Richtlinie von Teams gelöscht werden":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Benutzer in Teams erklären, dass Nachrichten aufgrund einer Aufbewahrungsrichtlinie von Teams gelöscht werden":::

Bei Kanalnachrichten sehen Benutzer (Mitglieder des Kanals), dass die gelöschten Nachrichten nach dem Ablaufen der Nachrichten aus der Ansicht verschwinden. Wenn die gelöschte Nachricht eine übergeordnete Nachricht einer Thread-Unterhaltung war, dann wird anstelle der übergeordneten Nachricht die Meldung "Diese Nachricht wurde aufgrund einer Richtlinie zur Aufbewahrung gelöscht" angezeigt. Beispiel:

:::image type="content" source="media/retention-policies-image3.png" alt-text="Screenshot des Kanals vor der Speicherung":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="Screenshot des Kanals nach der Speicherung":::

> [!NOTE]
> Die angezeigten Nachrichten, die Benutzer aufgrund von gelöschten Nachrichten sehen, sind derzeit nicht konfigurierbar.

Die Links in diesen angezeigten Nachrichten führen zu [Teams-Nachrichten über Aufbewahrungsrichtlinien](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b). Diese Dokumentation für Endbenutzer hilft bei der Beantwortung allgemeiner Fragen, warum Nachrichten gelöscht wurden. Stellen Sie jedoch sicher, dass Sie im Rahmen der Bereitstellung Ihrer Aufbewahrungsrichtlinie den Benutzern und Ihrem Helpdesk die Auswirkungen der konfigurierten Einstellungen mitteilen.

## <a name="related-topics"></a>Verwandte Themen

- [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](/microsoft-365/compliance/get-started-with-retention)
- [Informationen zur Aufbewahrung für Microsoft Teams](/microsoft-365/compliance/retention-policies-teams)
- [Erstellen und Konfigurieren von Aufbewahrungsrichtlinien](/microsoft-365/compliance/create-retention-policies)
