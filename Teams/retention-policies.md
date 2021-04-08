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
description: Verwenden Sie Aufbewahrungsrichtlinien für Microsoft Teams, um Nachrichten zu behalten, die Ihre Organisation benötigt, um interne Richtlinien, Branchenbestimmungen oder gesetzliche Anforderungen zu erfüllen, und um Nachrichten zu löschen, die als Haftung gelten oder keinen rechtlichen Geschäftlichen Wert haben.
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

Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen von Microsoft 365 helfen Ihnen, die Informationen in Ihrer Organisation effektiver zu verwalten. Sie können Aufbewahrungseinstellungen konfigurieren, um Daten zu speichern, die erforderlich sind, um die internen Richtlinien, Branchenbestimmungen oder gesetzlichen Anforderungen Ihrer Organisation zu erfüllen. Sie können die Aufbewahrungseinstellungen auch so konfigurieren, dass Daten gelöscht werden, die als Belastung angesehen werden, die Sie nicht mehr aufbewahren müssen oder die keinen rechtlichen oder geschäftlichen Wert haben.

Teams unterstützt Aufbewahrungsrichtlinien für Chat- und Kanal-Nachrichten, so dass Sie als Administrator proaktiv entscheiden können, ob Sie diese Daten aufbewahren, löschen oder für einen bestimmten Zeitraum aufbewahren und dann löschen möchten. Der Start des Aufbewahrungszeitraums für diese Aktionen basiert immer darauf, wann eine Nachricht erstellt wird. Sie können eine Aufbewahrungsrichtlinie für Teams auf Ihre gesamte Organisation oder bestimmte Benutzer und Teams anwenden. Aufbewahrungsbezeichnungen werden für Teams nicht unterstützt.

Weitere Informationen zu Aufbewahrungslösungen in Microsoft 365 finden Sie unter Informationen zu Aufbewahrungsrichtlinien [und Aufbewahrungsbeschriftungen.](/microsoft-365/compliance/retention)

Benutzer, die einer Aufbewahrungsrichtlinie für Teams unterliegen, müssen über eine entsprechende Lizenz verfügen, z. B. Office 365 E3 oder Office 365 A3. Weitere Lizenzierungsoptionen für diese Aufbewahrungsrichtlinien finden Sie im Abschnitt [Information Governance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) aus Microsoft 365-Lizenzierungsleitfäden für Sicherheit [und & Compliance.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) Weitere Informationen zur Lizenzierung für Teams finden Sie unter [Microsoft Teams-Dienstbeschreibung](/office365/servicedescriptions/teams-service-description).

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a>Unterstützung von Aufbewahrungs- und Löschaktionen durch Teams-Aufbewahrungsrichtlinien

Wenn Sie eine Teams-Aufbewahrungsrichtlinie zum Beibehalten von Chats oder Kanalnachrichten konfigurieren, können Benutzer ihre Nachrichten in ihrer Teams-App weiterhin bearbeiten und löschen. Obwohl die Benutzer ihre vorab bearbeiteten oder gelöschten Nachrichten in Teams nicht mehr sehen, werden die Daten aus diesen Nachrichten an einem sicheren Speicherort gespeichert, der für eDiscovery-Suchen durch Complianceadministratoren entwickelt wurde. Das endgültige Löschen dieser Daten geschieht nicht vor dem Ende des konfigurierten Aufbewahrungszeitraums oder wenn eine andere Aufbewahrungsrichtlinie für die Aufbewahrung dieser Daten konfiguriert ist oder ein [eDiscovery-Speicher unterliegt.](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds)

Wenn eine Aufbewahrungsrichtlinie zum Löschen von Chats und Kanalnachrichten konfiguriert ist, können diese Nachrichten automatisch gelöscht werden. Wenn die Nachrichten weiterhin in der Teams-App angezeigt werden, werden sie dort ausgeblendet, und die Benutzer werden darüber informiert, dass diese Nachrichten von einer [Aufbewahrungsrichtlinie gelöscht wurden.](#end-user-experience) Wenn die Nachrichten zuvor einer Aufbewahrungsaktion unterliegen und von Benutzern bearbeitet oder gelöscht wurden, werden diese Nachrichten jetzt aus dem sicheren Speicherort gelöscht und nicht mehr in eDiscovery-Suchen zurückgegeben.

Ausführliche Informationen zur Funktionsweise dieser Richtlinien je nach Richtlinienkonfiguration und Benutzeraktionen sowie zu den Nachrichtendaten, die für Microsoft Teams-Aufbewahrungsrichtlinien eingeschlossen und ausgeschlossen werden, finden Sie unter Informationen zur Aufbewahrung für [Microsoft Teams.](/microsoft-365/compliance/retention-policies-teams) Auf dieser Seite wird auch erläutert, warum es manchmal zu Verzögerungen beim Löschen von Nachrichten durch Aufbewahrungsrichtlinien kommen kann. Beispielsweise können Nachrichten für Benutzer in der Teams-App bis zu 7 Tage nach dem Ablaufzeitraum angezeigt werden, den Sie in der Aufbewahrungsrichtlinie konfiguriert haben.

Wenn Sie mehrere Aufbewahrungsrichtlinien für Teams mit unterschiedlichen Aufbewahrungseinstellungen einrichten, klären die Grundsätze der Aufbewahrung alle Konflikte. Beispiel:

- Wenn es einen Konflikt zwischen dem Beibehalten oder Löschen desselben Inhalts gibt, wird der Inhalt immer am sicheren Speicherort aufbewahrt, sodass er mit eDiscovery für Complianceadministratoren durchsucht werden kann.
    
    Dieses Prinzip gilt auch für Nachrichten, die aus rechtlichen oder ermittlungstaktischen Gründen unter eDiscovery-Halteschutz stehen.

- Wenn bei der Aufbewahrung desselben Inhalts ein Konflikt besteht, wird er für den längsten Aufbewahrungszeitraum am gesicherten Speicherort aufbewahrt.

Diese beiden Grundsätze der Aufbewahrung adressieren die meisten Konflikte, die entstehen können, wenn Sie mehrere Aufbewahrungsrichtlinien für Teams haben. Weitere Informationen finden Sie unter [Die Grundsätze der Aufbewahrung oder was hat Vorrang?](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Wann sind die Aufbewahrungsrichtlinien für Teams zu verwenden

In vielen Fällen betrachten Organisationen private Chat-Daten als eine größere Belastung als Kanalnachrichten, bei denen es sich in der Regel eher um projektbezogene Gespräche handelt.

Sie können separate Aufbewahrungsrichtlinien für private Chats (1:1- oder 1:Viele-Chats) und Kanalnachrichten einrichten. Sie können auch eindeutige Richtlinien konfigurieren, die für bestimmte Benutzer oder Teams in Ihrer Organisation gelten. Bei Teams-Chats können Sie auswählen, für welche Benutzer die Richtlinie gilt. Bei Teams-Kanalnachrichten können Sie auswählen, für welche Teams die Richtlinie gilt.

Für Kanalnachrichten können Sie beispielsweise eine Aufbewahrungsrichtlinie auf bestimmte Teams in Ihrer Organisation anwenden, und diese Richtlinie ist nach einem Jahr mit einer Löschaktion konfiguriert. Wenden Sie dann eine weitere Aufbewahrungsrichtlinie auf alle anderen Teams an, und diese Richtlinie ist nach drei Jahren mit einer Löschaktion konfiguriert.

## <a name="create-and-manage-retention-policies-for-teams"></a>Aufbewahrungsrichtlinien für Teams erstellen und verwalten

Zum Erstellen oder Bearbeiten einer Aufbewahrungsrichtlinie für Teams-Chats und Kanalnachrichten verwenden Sie die Anweisungen aus [aufbewahrungsrichtlinie für Teams-Speicherorte.](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)

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
