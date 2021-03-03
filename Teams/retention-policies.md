---
title: Aufbewahrungsrichtlinien in Microsoft Teams
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Verwenden Sie Aufbewahrungsrichtlinien für Microsoft Teams, um Nachrichten zu behalten, die zur Einhaltung interner Richtlinien, brancheninterner Vorschriften oder gesetzlicher Anforderungen erforderlich sind, und um Nachrichten zu löschen, die als Haftung angesehen werden oder keinen juristischen geschäftlichen Wert haben.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aba9858466b43693603aa4a1cd396748d2c83d6e
ms.sourcegitcommit: def4b475b785a7b963f499cf9a1044e842ff66a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2021
ms.locfileid: "49786827"
---
# <a name="retention-policies-in-microsoft-teams"></a>Aufbewahrungsrichtlinien in Microsoft Teams

Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen von Microsoft 365 helfen Ihnen, die Informationen in Ihrer Organisation effektiver zu verwalten. Sie können Aufbewahrungseinstellungen konfigurieren, um Daten zu speichern, die zur Einhaltung der internen Richtlinien, Branchenbestimmungen oder gesetzlichen Anforderungen Ihrer Organisation erforderlich sind. Sie können auch Aufbewahrungseinstellungen konfigurieren, um Daten zu löschen, die als Haftung betrachtet werden, die Sie nicht mehr behalten müssen oder die keinen juristischen oder geschäftlichen Wert haben.

Teams unterstützt Aufbewahrungsrichtlinien für Chat- und Kanalnachrichten, sodass Sie als Administrator proaktiv entscheiden können, ob diese Daten für einen bestimmten Zeitraum beibehalten, gelöscht oder für einen bestimmten Zeitraum gelöscht werden sollen. Sie können eine Aufbewahrungsrichtlinie für Teams auf Ihre gesamte Organisation oder bestimmte Benutzer und Teams anwenden. Aufbewahrungsbezeichnungen werden für Teams nicht unterstützt.

Weitere Informationen zur Aufbewahrung und dazu, wie Sie Aufbewahrungseinstellungen mithilfe von Aufbewahrungsrichtlinien oder Aufbewahrungsbezeichnungen für andere Workloads in Microsoft 365 anwenden können, finden Sie unter "Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbeschriftungen". [](https://docs.microsoft.com/microsoft-365/compliance/retention)

Die Mindestlizenzanforderung für Aufbewahrungsrichtlinien für Teams ist Microsoft 365 E3. Weitere Informationen zur Lizenzierung finden Sie in der [Beschreibung des Microsoft Teams-Diensts.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="how-teams-retention-policies-work"></a>Funktionsweise der Aufbewahrungsrichtlinien von Teams

Teams-Chatnachrichten werden in einem verborgenen Ordner im Postfach jedes benutzers gespeichert, der in den Chat einbezogen ist, und Teamkanalnachrichten werden in einem ähnlichen verborgenen Ordner im Gruppenpostfach für das Team gespeichert. Zum Beibehalten von Nachrichten, die einer Aufbewahrungsrichtlinie unterliegen, wird eine Kopie des Inhalts automatisch in einem verborgenen Ordner namens **"Holds"** als Unterordner im Ordner "Wiederherstellbare Elemente" von Exchange gespeichert.  Bis diese Nachrichten dauerhaft aus dem Ordner "Holds" gelöscht werden, können sie weiterhin von eDiscovery-Tools durchsucht werden.

Ausführliche Informationen dazu, was in Microsoft Teams-Aufbewahrungsrichtlinien einbezogen und ausgeschlossen wird und wie diese Richtlinien je nach Ihrer Richtlinienkonfiguration funktionieren, finden Sie unter "Informationen zur Aufbewahrung [für Microsoft Teams".](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

> [!NOTE]
> Auf dieser Seite wird erläutert, warum manchmal Verzögerungen beim Löschen von Nachrichten durch Aufbewahrungsrichtlinien angezeigt werden. Beispielsweise können Nachrichten bis zu sieben Tage nach dem Ablaufzeitraum angezeigt werden, den Sie in der Aufbewahrungsrichtlinie konfiguriert haben.

Wenn Sie mehrere Aufbewahrungsrichtlinien für Teams mit unterschiedlichen Aufbewahrungseinstellungen einrichten, lösen die Grundsätze der Aufbewahrung alle Konflikte. Beispiel:
- Wenn es einen Konflikt zwischen der Aufbewahrung oder dem Löschen desselben Inhalts gibt, bleiben die Inhalte immer erhalten.
- Wenn es einen Konflikt bei der Aufbewahrungsdauer für dieselben Inhalte gibt, werden diese über den längsten Aufbewahrungszeitraum aufbewahrt.

Diese beiden Grundsätze der Aufbewahrung adressieren die meisten Konflikte, die entstehen können, wenn Sie über mehrere Aufbewahrungsrichtlinien für Teams verfügen. Weitere Informationen finden Sie jedoch unter den Grundsätzen der Aufbewahrung oder was [Vorrang hat?](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Wann sind die Aufbewahrungsrichtlinien für Teams zu verwenden

In vielen Fällen betrachten Organisationen private Chat-Daten als eine größere Belastung als Kanalnachrichten, bei denen es sich in der Regel eher um projektbezogene Gespräche handelt.

Sie können separate Aufbewahrungsrichtlinien für private Chats (1:1- oder 1:Viele-Chats) und Kanalnachrichten einrichten. Sie können auch eindeutige Richtlinien konfigurieren, die für bestimmte Benutzer oder Teams in Ihrer Organisation gelten. Bei Teams-Chats können Sie auswählen, für welche Benutzer die Richtlinie gilt. Bei Teams-Kanalnachrichten können Sie auswählen, für welche Teams die Richtlinie gilt.

So können Sie beispielsweise für Kanalnachrichten eine einjährige Löschrichtlinie auf bestimmte Teams in Ihrer Organisation und eine Löschrichtlinie von drei Jahren auf alle anderen Teams anwenden.

## <a name="create-and-manage-retention-policies-for-teams"></a>Erstellen und Verwalten von Aufbewahrungsrichtlinien für Teams

Verwenden Sie zum Erstellen einer Aufbewahrungsrichtlinie für Chats und Kanalnachrichten in Teams die Anweisungen aus der [Aufbewahrungsrichtlinie für Teams-Speicherorte.](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)

Diese Seite enthält zusätzliche Informationen zum Erstellen und Verwalten von Aufbewahrungsrichtlinien für andere Workloads in Microsoft 365. Sie können beispielsweise auch eine Aufbewahrungsrichtlinie für Microsoft 365-Gruppen erstellen, um Dateien, auf die in Teams zugegriffen wird und die in OneDrive oder SharePoint gespeichert sind, zu speichern und zu löschen.  

## <a name="end-user-experience"></a>Endbenutzererfahrung

Bei privaten Chats (1:1-Chats) oder Gruppenchats werden Endbenutzern angezeigt, dass Chats, die älter als die Konfiguration der Aufbewahrungsrichtlinien sind, gelöscht werden, und eine Steuerelementmeldung mit der Meldung "Wir haben ältere Nachrichten aufgrund der Aufbewahrungsrichtlinie Ihrer Organisation gelöscht" wird über noch nicht gespeicherten Nachrichten angezeigt.

:::image type="content" source="media/retention-policies-image1.png" alt-text="Benutzer informiert in Teams, dass Chatnachrichten aufgrund einer Aufbewahrungsrichtlinie von Teams gelöscht werden":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Benutzer in Teams, der erläutert, dass Nachrichten als Ergebnis einer Aufbewahrungsrichtlinie für Teams gelöscht werden":::

Bei Kanalnachrichten wird Endbenutzern (Kanalmitgliedern) angezeigt, dass die gelöschten Nachrichten nach Ablauf der Nachrichten nicht mehr angezeigt werden. Wenn die gelöschte Nachricht eine übergeordnete Nachricht eines Unterhaltungsthreads war, wird statt der übergeordneten Nachricht die Meldung "Diese Nachricht wurde aufgrund einer Aufbewahrungsrichtlinie gelöscht" angezeigt.

:::image type="content" source="media/retention-policies-image3.png" alt-text="Screenshot des Kanals vor der Aufbewahrung":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="Screenshot des Kanals nach der Aufbewahrung":::

> [!NOTE]
> Die angezeigten Nachrichten, die Endbenutzer als Ergebnis gelöschter Nachrichten sehen, können derzeit nicht konfiguriert werden.


## <a name="related-topics"></a>Verwandte Themen

- [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-retention)
- [Informationen zur Aufbewahrung für Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)
- [Erstellen und Konfigurieren von Aufbewahrungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies)