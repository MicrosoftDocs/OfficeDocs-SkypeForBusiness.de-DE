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
description: Verwenden Sie Aufbewahrungsrichtlinien für Microsoft Teams, um Nachrichten aufzubewahren, die Ihre Organisation zur Einhaltung interner Richtlinien, Branchenvorschriften oder rechtlicher Anforderungen benötigt, und um Nachrichten zu löschen, die als Belastung angesehen werden oder keinen rechtlichen Geschäftswert haben.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f1dbd1d7c586c989484fa71b1e0b0e3d1fb47550
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727404"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>Aufbewahrungsrichtlinien für Microsoft Teams Verwalten

> [!NOTE]
> Wenn Sie in Teams eine Meldung sehen, dass Ihre Chats oder Nachrichten durch eine Aufbewahrungsrichtlinie gelöscht wurden, lesen Sie [Teams-Nachrichten zu Aufbewahrungsrichtlinien](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).
> 
> Die Informationen auf dieser Seite richten sich an IT-Administratoren, die diese Aufbewahrungsrichtlinien verwalten.

Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen von Microsoft 365 helfen Ihnen, die Informationen in Ihrer Organisation effektiver zu verwalten. Sie können Aufbewahrungseinstellungen konfigurieren, um Daten aufzubewahren, die benötigt werden, um die internen Richtlinien Ihres Unternehmens, Branchenvorschriften oder gesetzliche Anforderungen zu erfüllen. Sie können die Aufbewahrungseinstellungen auch so konfigurieren, dass Daten gelöscht werden, die als Belastung angesehen werden, die Sie nicht mehr aufbewahren müssen oder die keinen rechtlichen oder geschäftlichen Wert haben.

Teams unterstützt Aufbewahrungsrichtlinien für Chat- und Kanal-Nachrichten, so dass Sie als Administrator proaktiv entscheiden können, ob Sie diese Daten aufbewahren, löschen oder für einen bestimmten Zeitraum aufbewahren und dann löschen möchten. Der Beginn des Aufbewahrungszeitraums für diese Aktionen basiert immer darauf, wann eine Nachricht erstellt wird. Sie können eine Aufbewahrungsrichtlinie für Teams auf Ihre gesamte Organisation oder bestimmte Benutzer und Teams anwenden. Aufbewahrungsbezeichnungen werden für Teams nicht unterstützt.

Weitere Informationen zu Aufbewahrungslösungen in Microsoft 365 finden Sie unter [Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](/microsoft-365/compliance/retention).

Benutzer, die einer Aufbewahrungsrichtlinie für Teams unterliegen, müssen über eine entsprechende Lizenz verfügen, z. B. Office 365 E3 oder Office 365 A3. Weitere Lizenzierungsoptionen für diese Aufbewahrungsrichtlinien finden Sie im Abschnitt [Information Governance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) aus [Microsoft 365-Lizenzierungsanleitung für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance). Weitere Informationen zur Lizenzierung für Teams finden Sie in der [Microsoft Teams-Dienstbeschreibung](/office365/servicedescriptions/teams-service-description).

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a>Unterstützung von Aufbewahrungs- und Löschaktionen durch Teams-Aufbewahrungsrichtlinien

Wenn Sie eine Teams-Aufbewahrungsrichtlinie zum Aufbewahren von Chat- oder Kanalnachrichten konfigurieren, können Benutzer ihre Nachrichten weiterhin in ihrer Teams-App bearbeiten und löschen. Obwohl Benutzer ihre zuvor bearbeiteten oder gelöschten Nachrichten nicht mehr in Teams sehen, werden Daten aus diesen Nachrichten an einem sicheren Speicherort gespeichert, der für eDiscovery-Suchvorgänge durch Complianceadministratoren konzipiert ist. Das endgültige Löschen dieser Daten erfolgt nicht vor dem Ende des konfigurierten Aufbewahrungszeitraums, wenn eine andere Aufbewahrungsrichtlinie für die Aufbewahrung dieser Daten konfiguriert ist oder einer [eDiscovery-Aufbewahrung](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds) unterliegt.

Wenn eine Aufbewahrungsrichtlinie zum Löschen von Chat- und Kanalnachrichten konfiguriert ist, können diese Nachrichten automatisch gelöscht werden. Wenn die Nachrichten weiterhin in der Teams-App angezeigt werden, werden sie von dort ausgeblendet, und [Benutzer werden darüber informiert, dass diese Nachrichten durch eine Aufbewahrungsrichtlinie](#end-user-experience) gelöscht wurden. Wenn die Nachrichten zuvor einer Aufbewahrungsaktion unterzogen wurden und von Benutzern bearbeitet oder gelöscht wurden, werden diese Nachrichten jetzt vom gesicherten Speicherort gelöscht und nicht mehr in eDiscovery-Suchvorgängen zurückgegeben.

Ausführliche Informationen darüber, wie diese Richtlinien in Abhängigkeit von der Richtlinienkonfiguration und den Benutzeraktionen funktionieren und welche Nachrichtendaten für die Teams-Aufbewahrungsrichtlinien ein- und ausgeschlossen werden, finden Sie unter [Mehr zur Aufbewahrung für Microsoft Teams](/microsoft-365/compliance/retention-policies-teams). Diese Seite also erklärt, warum es manchmal zu Verzögerungen kommen kann, wenn Aufbewahrungsrichtlinien Nachrichten löschen. Beispielsweise können Nachrichten bis zu 7 Tage nach dem Ablauf, den Sie in der Aufbewahrungsrichtlinie konfiguriert haben, für Benutzer in der Teams-App sichtbar sein.

Wenn Sie mehrere Aufbewahrungsrichtlinien für Teams mit unterschiedlichen Aufbewahrungseinstellungen einrichten, klären die Grundsätze der Aufbewahrung alle Konflikte. Zum Beispiel:

- Wenn es einen Konflikt zwischen dem Aufbewahren oder Löschen desselben Inhalts gibt, wird der Inhalt immer am gesicherten Speicherort aufbewahrt, sodass er mit eDiscovery für Complianceadministratoren durchsuchbar bleibt.
    
    Dieses Prinzip gilt auch für Nachrichten, die sich aus rechtlichen oder untersuchungsrechtlichen Gründen in eDiscovery-Archiven befinden.

- Wenn es einen Konflikt darüber gibt, wie lange derselbe Inhalt am gesicherten Speicherort aufbewahrt werden soll, wird er für die längste Aufbewahrungszeit aufbewahrt.

Diese beiden Grundsätze der Aufbewahrung adressieren die meisten Konflikte, die entstehen können, wenn Sie mehrere Aufbewahrungsrichtlinien für Teams haben. Weitere Informationen finden Sie unter [Die Grundsätze der Aufbewahrung oder was hat Vorrang?](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Wann sind die Aufbewahrungsrichtlinien für Teams zu verwenden

In vielen Fällen betrachten Organisationen private Chat-Daten als eine größere Belastung als Kanalnachrichten, bei denen es sich in der Regel eher um projektbezogene Gespräche handelt.

Sie können eine einzelne Aufbewahrungsrichtlinie sehr effizient für alle nachrichten Teams konfigurieren. Zur Feinsteuerung können Sie aber auch:

- Es gibt separate Aufbewahrungsrichtlinien für private Chats (1:1- oder 1:n-Chats), Nachrichten von Standardkanälen oder Nachrichten von privaten Kanälen.

- Wenden Sie die Richtlinien nur auf bestimmte Benutzer oder Teams in Ihrer Organisation an. Für Teams Chats und privaten Kanälen können Sie auswählen, für welche Benutzer die Richtlinie gilt. Bei Teams-Kanalnachrichten können Sie auswählen, für welche Teams die Richtlinie gilt.

Beispiel für Standardkanalnachrichten: Erstellen Sie eine Aufbewahrungsrichtlinie für bestimmte Teams in Ihrer Organisation, und konfigurieren Sie diese Richtlinie nach einem Jahr mit einer Löschaktion. Erstellen Sie dann eine weitere Aufbewahrungsrichtlinie für Standardkanalnachrichten für alle anderen Teams, und konfigurieren Sie diese Richtlinie mit einer Löschaktion nach 3 Jahren.

## <a name="create-and-manage-retention-policies-for-teams"></a>Aufbewahrungsrichtlinien für Teams erstellen und verwalten

Verwenden Sie zum Erstellen oder Bearbeiten einer Aufbewahrungsrichtlinie für Teams-Nachrichten die Anweisungen aus Aufbewahrungsrichtlinie für Teams [Speicherorte.](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)

Diese Seite bietet zusätzliche Informationen zum Erstellen und Verwalten von Aufbewahrungsrichtlinien für andere Workloads in Microsoft 365. Sie könnten zum Beispiel auch eine Aufbewahrungsrichtlinie für Microsoft 365 Groups erstellen, um Dateien aufzubewahren und zu löschen, auf die in Teams zugegriffen wird und die in OneDrive oder SharePoint gespeichert sind.  

## <a name="end-user-experience"></a>Endbenutzererfahrung

Bei privaten Chats (1:1-Chats) oder Gruppenchats sehen Benutzer, dass Chats, die älter sind als die Konfiguration der Aufbewahrungsrichtlinie, gelöscht werden. Zudem wird eine automatisch generierte Nachricht mit dem Hinweis "Wir haben ältere Nachrichten aufgrund der Aufbewahrungsrichtlinie Ihrer Organisation gelöscht" über den noch nicht gelöschten Nachrichten angezeigt. Zum Beispiel:

:::image type="content" source="media/retention-policies-image1.png" alt-text="Der Benutzer wurde in Teams darüber informiert, dass Chatnachrichten aufgrund einer Aufbewahrungsrichtlinie Teams werden.":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Der Benutzer Teams, der erläutert, dass Nachrichten als Ergebnis einer Aufbewahrungsrichtlinie Teams werden.":::

Bei Kanalnachrichten sehen Benutzer (Mitglieder des Kanals), dass die gelöschten Nachrichten nach dem Ablaufen der Nachrichten aus der Ansicht verschwinden. Wenn die gelöschte Nachricht eine übergeordnete Nachricht einer Thread-Unterhaltung war, dann wird anstelle der übergeordneten Nachricht die Meldung "Diese Nachricht wurde aufgrund einer Richtlinie zur Aufbewahrung gelöscht" angezeigt. Beispiel:

:::image type="content" source="media/retention-policies-image3.png" alt-text="Screenshot des Kanals vor der Aufbewahrung.":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="Screenshot des Kanals nach der Aufbewahrung.":::

> [!NOTE]
> Die angezeigten Nachrichten, die Benutzer aufgrund von gelöschten Nachrichten sehen, sind derzeit nicht konfigurierbar.

Die Links in diesen angezeigten Nachrichten führen zu [Teams-Nachrichten über Aufbewahrungsrichtlinien](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b). Diese Dokumentation für Endbenutzer hilft bei der Beantwortung allgemeiner Fragen, warum Nachrichten gelöscht wurden. Stellen Sie jedoch sicher, dass Sie im Rahmen der Bereitstellung Ihrer Aufbewahrungsrichtlinie den Benutzern und Ihrem Helpdesk die Auswirkungen der konfigurierten Einstellungen mitteilen.

## <a name="related-topics"></a>Verwandte Themen

- [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](/microsoft-365/compliance/get-started-with-retention)
- [Informationen zur Aufbewahrung für Microsoft Teams](/microsoft-365/compliance/retention-policies-teams)
- [Erstellen und Konfigurieren von Aufbewahrungsrichtlinien](/microsoft-365/compliance/create-retention-policies)
