---
title: Verwalten von Aufbewahrungsrichtlinien für Microsoft Teams
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Verwenden Sie Aufbewahrungsrichtlinien für Microsoft Teams, um Nachrichten zu behalten, die erforderlich sind, um interne Richtlinien, Branchenbestimmungen oder gesetzliche Anforderungen zu erfüllen, und um Nachrichten zu löschen, die als Haftung gelten oder keinen juristischen Geschäftlichen Wert haben.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 66af968b066b1fa385674d828985606f05bd3d07
ms.sourcegitcommit: b0753baa55841a2c6c5dc006dcdd117704af3b42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2021
ms.locfileid: "50401309"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>Verwalten von Aufbewahrungsrichtlinien für Microsoft Teams

> [!NOTE]
> Wenn in Teams eine Meldung angezeigt wird, dass Ihre Chats oder Nachrichten durch eine Aufbewahrungsrichtlinie gelöscht wurden, lesen Sie [Teams-Nachrichten zu Aufbewahrungsrichtlinien.](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)
> 
> Die Informationen auf dieser Seite sind für IT-Administratoren vorgesehen, die diese Aufbewahrungsrichtlinien verwalten.

Aufbewahrungsrichtlinien und Aufbewahrungsbeschriftungen von Microsoft 365 helfen Ihnen, die Informationen in Ihrer Organisation effektiver zu verwalten. Sie können Aufbewahrungseinstellungen konfigurieren, um Daten zu speichern, die erforderlich sind, um den internen Richtlinien, Branchenbestimmungen oder gesetzlichen Anforderungen Ihrer Organisation zu entsprechen. Sie können aufbewahrungseinstellungen auch so konfigurieren, dass Daten gelöscht werden, die als Haftung betrachtet werden, die Sie nicht mehr behalten müssen oder die keinen rechtlichen oder geschäftlichen Wert haben.

Teams unterstützt Aufbewahrungsrichtlinien für Chat- und Kanalnachrichten, sodass Sie als Administrator proaktiv entscheiden können, ob Diese Daten beibehalten, gelöscht oder für einen bestimmten Zeitraum beibehalten und dann gelöscht werden sollen. Sie können eine Aufbewahrungsrichtlinie für Teams auf Ihre gesamte Organisation oder bestimmte Benutzer und Teams anwenden. Aufbewahrungsbeschriftungen werden für Teams nicht unterstützt.

Weitere Informationen zur Aufbewahrung und zum Anwenden von Aufbewahrungseinstellungen mithilfe von Aufbewahrungsrichtlinien oder Aufbewahrungsbeschriftungen für andere Workloads in Microsoft 365 finden Sie unter Informationen zu Aufbewahrungsrichtlinien und [Aufbewahrungsbeschriftungen.](https://docs.microsoft.com/microsoft-365/compliance/retention)

Die Mindestlizenzanforderung für Aufbewahrungsrichtlinien für Teams ist Microsoft 365 E3. Weitere Informationen zur Lizenzierung finden Sie unter [Microsoft Teams-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

## <a name="how-teams-retention-policies-work"></a>Funktionsweise der Aufbewahrungsrichtlinien von Teams

Teams-Chatnachrichten werden in einem ausgeblendeten Ordner im Postfach jedes Benutzers gespeichert, der im Chat enthalten ist, und Teams-Kanalnachrichten werden in einem ähnlichen ausgeblendeten Ordner im Gruppenpostfach für das Team gespeichert. Wenn Sie Nachrichten beibehalten möchten, die einer Aufbewahrungsrichtlinie unterliegen, wird eine Kopie des Inhalts automatisch im  Ordner "Wiederherstellbare Elemente" in einem ausgeblendeten Ordner namens **"Unterordner" mit** dem Namen "Speicherinhalte" aufbewahrt. Solange diese Nachrichten nicht dauerhaft aus dem Ordner "Benachrichtigungen" gelöscht werden, bleiben sie mit eDiscovery-Tools durchsucht.

Ausführliche Informationen dazu, was für Microsoft Teams-Aufbewahrungsrichtlinien enthalten und ausgeschlossen ist und wie diese Richtlinien je nach Ihrer Richtlinienkonfiguration funktionieren, finden Sie unter Informationen zur Aufbewahrung [für Microsoft Teams.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

> [!NOTE]
> Auf dieser Seite wird erläutert, warum beim Löschen von Nachrichten durch Aufbewahrungsrichtlinien manchmal Verzögerungen angezeigt werden. Beispielsweise können Nachrichten bis zu 7 Tage nach dem Ablaufzeitraum angezeigt werden, den Sie in der Aufbewahrungsrichtlinie konfiguriert haben.

Wenn Sie mehrere Teams-Aufbewahrungsrichtlinien mit unterschiedlichen Aufbewahrungseinstellungen einrichten, lösen die Grundsätze der Aufbewahrung alle Konflikte. Beispiel:
- Wenn es einen Konflikt zwischen dem Beibehalten oder Löschen desselben Inhalts gibt, wird der Inhalt immer beibehalten.
- Wenn bei der Aufbewahrung desselben Inhalts ein Konflikt besteht, wird er für den längsten Aufbewahrungszeitraum beibehalten.

Diese beiden Grundsätze der Aufbewahrung lösen die meisten Konflikte, die auftreten können, wenn Sie über mehrere Aufbewahrungsrichtlinien für Teams verfügen. Weitere Informationen finden Sie unter Die Grundsätze der Aufbewahrung oder was [hat Vorrang?](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Wann sind die Aufbewahrungsrichtlinien für Teams zu verwenden

In vielen Fällen betrachten Organisationen private Chat-Daten als eine größere Belastung als Kanalnachrichten, bei denen es sich in der Regel eher um projektbezogene Gespräche handelt.

Sie können separate Aufbewahrungsrichtlinien für private Chats (1:1- oder 1:Viele-Chats) und Kanalnachrichten einrichten. Sie können auch eindeutige Richtlinien konfigurieren, die für bestimmte Benutzer oder Teams in Ihrer Organisation gelten. Bei Teams-Chats können Sie auswählen, für welche Benutzer die Richtlinie gilt. Bei Teams-Kanalnachrichten können Sie auswählen, für welche Teams die Richtlinie gilt.

So können Sie beispielsweise für Kanalnachrichten eine einjährige Löschrichtlinie auf bestimmte Teams in Ihrer Organisation und eine Löschrichtlinie von drei Jahren auf alle anderen Teams anwenden.

## <a name="create-and-manage-retention-policies-for-teams"></a>Erstellen und Verwalten von Aufbewahrungsrichtlinien für Teams

Zum Erstellen einer Aufbewahrungsrichtlinie für Teams-Chats und Kanalnachrichten verwenden Sie die Anweisungen aus [Aufbewahrungsrichtlinie für Teams-Speicherorte.](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)

Diese Seite enthält zusätzliche Informationen zum Erstellen und Verwalten von Aufbewahrungsrichtlinien für andere Workloads in Microsoft 365. Sie können beispielsweise auch eine Aufbewahrungsrichtlinie für Microsoft 365-Gruppen erstellen, um Dateien zu speichern und zu löschen, auf die in Teams zugegriffen wird und die in OneDrive oder SharePoint gespeichert sind.  

## <a name="end-user-experience"></a>Endbenutzererfahrung

Bei privaten Chats (1:1-Chats) oder Gruppenchats sehen Die Benutzer, dass Chats, die älter als die Aufbewahrungsrichtlinienkonfiguration sind, gelöscht werden, und eine automatisch generierte Meldung mit der Meldung "Wir haben ältere Nachrichten aufgrund der Aufbewahrungsrichtlinie Ihrer Organisation gelöscht" wird über noch nicht gestartete Nachrichten angezeigt. Beispiel:

:::image type="content" source="media/retention-policies-image1.png" alt-text="Benutzer informiert in Teams, dass Chatnachrichten aufgrund einer Teams-Aufbewahrungsrichtlinie gelöscht werden":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Benutzer in Teams, die Nachrichten erläutern, werden als Ergebnis einer Teams-Aufbewahrungsrichtlinie gelöscht":::

Bei Kanalnachrichten werden den Benutzern (Kanalmitgliedern) die gelöschten Nachrichten nach Ablauf der Nachrichten nicht mehr angezeigt. Wenn die gelöschte Nachricht eine übergeordnete Nachricht einer Unterhaltung im Thread war, wird statt der übergeordneten Nachricht die Meldung "Diese Nachricht wurde aufgrund einer Aufbewahrungsrichtlinie gelöscht" angezeigt. Beispiel:

:::image type="content" source="media/retention-policies-image3.png" alt-text="Screenshot des Kanals vor der Aufbewahrung":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="Screenshot des Kanals nach der Aufbewahrung":::

> [!NOTE]
> Die angezeigten Nachrichten, die Benutzer als Ergebnis gelöschter Nachrichten sehen, können derzeit nicht konfiguriert werden.

Die Links in diesen angezeigten Nachrichten wechseln zu [Teams-Nachrichten zu Aufbewahrungsrichtlinien.](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b) Diese Dokumentation für Endbenutzer hilft Ihnen, grundlegende Fragen zu beantworten, warum ihre Nachrichten gelöscht wurden. Stellen Sie im Rahmen ihrer Aufbewahrungsrichtlinienbereitstellung jedoch sicher, dass Sie den Benutzern und Ihrem Helpdesk die Auswirkungen Ihrer konfigurierten Einstellungen vermitteln.

## <a name="related-topics"></a>Verwandte Themen

- [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbeschriftungen](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-retention)
- [Informationen zur Aufbewahrung von Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)
- [Erstellen und Konfigurieren von Aufbewahrungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies)