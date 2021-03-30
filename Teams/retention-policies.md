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
description: Verwenden Sie Aufbewahrungsrichtlinien für Microsoft Teams, um Nachrichten zu behalten, die erforderlich sind, um interne Richtlinien, Branchenbestimmungen oder gesetzliche Anforderungen zu erfüllen, und um Nachrichten zu löschen, die als Haftung gelten oder keinen rechtlichen Geschäftswert haben.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 748106de5ed7e2f0147a182716ca8bce1571b82f
ms.sourcegitcommit: 6505dd1fb891ab27fcc9f36423fda67aae6fcfd7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418813"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>Aufbewahrungsrichtlinien für Microsoft Teams Verwalten

> [!NOTE]
> Wenn Sie in Teams eine Meldung sehen, dass Ihre Chats oder Nachrichten durch eine Aufbewahrungsrichtlinie gelöscht wurden, lesen Sie [Teams-Nachrichten zu Aufbewahrungsrichtlinien](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).
> 
> Die Informationen auf dieser Seite richten sich an IT-Administratoren, die diese Aufbewahrungsrichtlinien verwalten.

Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen von Microsoft 365 helfen Ihnen, die Informationen in Ihrer Organisation effektiver zu verwalten. Sie können Aufbewahrungseinstellungen konfigurieren, um Daten zu speichern, die erforderlich sind, um die internen Richtlinien, Branchenbestimmungen oder gesetzlichen Anforderungen Ihrer Organisation zu erfüllen. Sie können die Aufbewahrungseinstellungen auch so konfigurieren, dass Daten gelöscht werden, die als Belastung angesehen werden, die Sie nicht mehr aufbewahren müssen oder die keinen rechtlichen oder geschäftlichen Wert haben.

Teams unterstützt Aufbewahrungsrichtlinien für Chat- und Kanal-Nachrichten, so dass Sie als Administrator proaktiv entscheiden können, ob Sie diese Daten aufbewahren, löschen oder für einen bestimmten Zeitraum aufbewahren und dann löschen möchten. Der Start des Aufbewahrungszeitraums für diese Aktionen basiert immer darauf, wann eine Nachricht erstellt wird. Sie können eine Aufbewahrungsrichtlinie für Teams auf Ihre gesamte Organisation oder bestimmte Benutzer und Teams anwenden. Aufbewahrungsbezeichnungen werden für Teams nicht unterstützt.

Weitere Informationen zur Aufbewahrung und wie Sie Aufbewahrungseinstellungen mithilfe von Aufbewahrungsrichtlinien oder Aufbewahrungsbezeichnungen für andere Workloads in Microsoft 365 anwenden können, finden Sie unter [Mehr zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](/microsoft-365/compliance/retention).

Die Mindestlizenzierungsanforderung für Aufbewahrungsrichtlinien für Teams ist Microsoft 365 E3. Weitere Informationen zur Lizenzierung finden Sie in der [Microsoft Teams-Dienstbeschreibung](/office365/servicedescriptions/teams-service-description).

## <a name="how-teams-retentiondeletion-policies-work"></a>So funktionieren Aufbewahrungs-/Löschungsrichtlinien in Teams

Teams-Chat-Nachrichten werden an zwei Orten gespeichert. Primäre Kopie wird in Azure gespeichert, eine sekundäre Kopie, die für Compliancerichtlinien verwendet wird, wird in einem ausgeblendeten Ordner im Exchange-Onlinepostfach jedes im Chat enthaltenen Benutzers gespeichert, und Nachrichten des Teams-Kanals werden in einem ähnlichen ausgeblendeten Ordner im Gruppenpostfach für das Team gespeichert. Wenn eine Richtlinie zum Löschen von Chatnachrichten auf einen Benutzer oder ein Team angewendet wird, wird die sekundäre Kopie zuerst gelöscht, gefolgt von der primären Kopie. Die eDiscovery- oder Teams-Suche basiert auf Nachrichten, die in einer sekundären Kopie gespeichert sind. Nachrichten können daher nicht gefunden werden, wenn die sekundäre Kopie gelöscht wird. 

Wenn eine **Aufbewahrungsrichtlinie** für Chatnachrichten auf einen Benutzer oder ein Team angewendet wird und die Nachrichten gelöscht werden (entweder aufgrund einer anderen Löschrichtlinie oder durch den Benutzer selbst), wird die primäre Kopie gelöscht, daher wird die Nachricht für den Teams-Client ausgeblendet, aber die sekundäre Kopie wird automatisch in einen ausgeblendeten Ordner namens "Löschspeicher" verschoben, der sich als Unterordner im **Ordner** "Wiederherstellbare Elemente" von Exchange befindet. Solange diese Nachrichten nicht dauerhaft aus dem Ordner "SubstrateHolds" gelöscht werden, bleiben sie für eDiscovery-Tools durchsuchbar.

Ausführliche Informationen darüber, was in Aufbewahrungsrichtlinien für Teams enthalten ist und was nicht, und wie diese Richtlinien je nach Richtlinienkonfiguration funktionieren, finden Sie unter [Mehr zur Aufbewahrung für Microsoft Teams](/microsoft-365/compliance/retention-policies-teams).

> [!NOTE]
> Diese Seite erklärt, warum es manchmal zu Verzögerungen kommen kann, wenn Aufbewahrungsrichtlinien Nachrichten löschen. Beispielsweise können Nachrichten bis zu 7 Tage nach dem Ablauf, den Sie in der Richtlinie für die Aufbewahrung konfiguriert haben, sichtbar sein.

Wenn Sie mehrere Aufbewahrungsrichtlinien für Teams mit unterschiedlichen Aufbewahrungseinstellungen einrichten, klären die Grundsätze der Aufbewahrung alle Konflikte. Beispiel:
- Wenn es einen Konflikt zwischen dem Beibehalten oder Löschen desselben Inhalts gibt, wird der Inhalt immer beibehalten.
- Wenn es einen Konflikt darüber gibt, wie lange derselbe Inhalt aufbewahrt werden soll, wird er für die längste Aufbewahrungszeit aufbewahrt.

Diese beiden Grundsätze der Aufbewahrung adressieren die meisten Konflikte, die entstehen können, wenn Sie mehrere Aufbewahrungsrichtlinien für Teams haben. Weitere Informationen finden Sie unter [Die Grundsätze der Aufbewahrung oder was hat Vorrang?](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Wann sind die Aufbewahrungsrichtlinien für Teams zu verwenden

In vielen Fällen betrachten Organisationen private Chat-Daten als eine größere Belastung als Kanalnachrichten, bei denen es sich in der Regel eher um projektbezogene Gespräche handelt.

Sie können separate Aufbewahrungsrichtlinien für private Chats (1:1- oder 1:Viele-Chats) und Kanalnachrichten einrichten. Sie können auch eindeutige Richtlinien konfigurieren, die für bestimmte Benutzer oder Teams in Ihrer Organisation gelten. Bei Teams-Chats können Sie auswählen, für welche Benutzer die Richtlinie gilt. Bei Teams-Kanalnachrichten können Sie auswählen, für welche Teams die Richtlinie gilt.

So können Sie beispielsweise für Kanalnachrichten eine einjährige Löschrichtlinie auf bestimmte Teams in Ihrer Organisation und eine Löschrichtlinie von drei Jahren auf alle anderen Teams anwenden.

## <a name="create-and-manage-retention-policies-for-teams"></a>Aufbewahrungsrichtlinien für Teams erstellen und verwalten

Um eine Richtlinie zur Aufbewahrung von Chats und Kanal-Nachrichten in Teams zu erstellen, verwenden Sie die Anweisungen unter [Aufbewahrungsrichtlinie für Teams-Standorte](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations).

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
