---
title: Häufig gestellte Fragen zu Schichten von Daten
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Erhalten Sie Antworten auf häufig gestellte Fragen zu Shifts-Daten, einschließlich der Speicherorte von Shifts-Daten, der Datenaufbewahrung, des Abrufs und der Verschlüsselung.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d4fc6e36c0c78bdf86e1384fe6269f292f20deb7
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922826"
---
# <a name="shifts-data-faq"></a>Häufig gestellte Fragen zu Schichten von Daten

Dieser Artikel befasst sich mit häufig gestellten Fragen zu Schichtdaten, einschließlich des Speicherorts von Schichtdaten, der Datenaufbewahrung, des Abrufs und der Verschlüsselung.

## <a name="where-is-shifts-data-stored"></a>Wo werden Shifts-Daten gespeichert?

Schichtdaten werden in einer von drei Regionen (Geos) gespeichert: Asien-Pazifik (APAC), Europäische Union (EU) oder USA. Jede Geo speichert Daten in mindestens zwei Azure-Rechenzentrumsregionen für hohe Verfügbarkeit (Ha) und Notfallwiederherstellung (Disaster Recovery, DR). Heute verwendet die USA/Nordamerika-Geo Rechenzentren in North Central und South Central USA. Weitere Informationen finden Sie [unter "Wo ist Microsoft 365 gespeicherte Kundendaten](/microsoft-365/enterprise/o365-data-locations)."

Derzeit bietet Shifts Datenresidenz in Australien, Kanada, Frankreich, Japan und dem Vereinigten Königreich. Wir arbeiten aktiv daran, den Support auf weitere Standorte auszuweiten.

## <a name="can-i-choose-where-shifts-data-is-stored"></a>Kann ich auswählen, wo Schichtendaten gespeichert werden?

Wenn Sie Teams zum ersten Mal einrichten, wählen Sie ein Land oder eine Region aus, das auf Abonnementebene festgelegt ist. Schichten berücksichtigt diese Auswahl und verwendet das Gebietsschema und die Region, die in Teams festgelegt sind, wenn wir diese Region unterstützen. Wenn wir uns noch nicht in dieser Region befinden, speichern wir Daten in einer nahe gelegenen Region, die wir unterstützen. In Zukunft planen wir, vorhandene Daten, wenn sie in einer nahe gelegenen Region gespeichert sind, in die Region zu migrieren, die in Teams bereitgestellt wird.

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>Kann ich in Schichten auf die personenbezogenen Daten eines Benutzers zugreifen und diese exportieren oder löschen?

Schichten sind mit der Datenschutz-Grundverordnung (DSGVO) kompatibel.Ein formelles Ersuchen einer Person (als betroffene Person bezeichnet), maßnahmen gegen ihre personenbezogenen Daten zu ergreifen, wird als Antrag einer betroffenen Person (Data Subject Request, DSR) bezeichnet. Sie können personenbezogene Daten in Schichten als Reaktion auf einen Antrag einer betroffenen Person suchen und darauf reagieren.

Sie können das eDiscovery-Tool für die Inhaltssuche im Microsoft Purview-Complianceportal verwenden, um nach Zeitplan- und Zeituhrdaten zu suchen und diese in Excel zu exportieren. Für alle anderen Schichtdaten können Sie Screenshots der Daten erstellen.

Weitere Informationen finden Sie [unter Office 365 Anträge betroffener Personen für die DSGVO und das CCPA](/microsoft-365/compliance/gdpr-dsr-office365).

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>Was geschieht mit Schichtendaten, wenn ich Schichten für meine Organisation deaktiviere?

Durch das Deaktivieren von Schichten in Ihrer Organisation *werden keine* Daten gelöscht. Wenn Sie Schichten deaktivieren und dann später Schichten aktivieren, sind Ihre Schichtdaten weiterhin verfügbar.

Wenn Sie Ihren Mandanten löschen, werden alle Schichtendaten nach Ablauf des Aufbewahrungszeitraums gelöscht.

Es gibt keine Möglichkeit, nur Schichtendaten zu löschen. Wenn Sie ein Team in Teams löschen, werden Schichtplandaten, die diesem Team zugeordnet sind, nach Ablauf des Aufbewahrungszeitraums gelöscht. Weitere Informationen finden Sie [unter Datenaufbewahrung, -löschung und -vernichtung in Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>Kann ich einen gelöschten Schichtplan wiederherstellen?

Sie können einen gelöschten Zeitplan wiederherstellen, wenn die Microsoft 365 Gruppe, die ihn unterstützt (oder das Team in Teams) wiederhergestellt wird.

Standardmäßig wird eine gelöschte Microsoft 365 Gruppe 30 Tage lang aufbewahrt. Dieser 30-Tage-Zeitraum wird als "vorläufiges Löschen" bezeichnet, da Sie die Gruppe dennoch wiederherstellen können. Weitere Informationen finden [Sie unter Wiederherstellen einer gelöschten Microsoft 365 Gruppe](/microsoft-365/admin/create-groups/restore-deleted-group?view=o365-worldwide&tabs=admin-center).

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>Kann ich benutzerdefinierte Aufbewahrungsrichtlinien für Schichtdaten verwenden?

Derzeit unterstützt Schichten keine benutzerdefinierten Aufbewahrungsrichtlinien.

Weitere Informationen zu Aufbewahrungsrichtlinien in Teams finden [Sie unter "Informationen zur Aufbewahrung für Teams](/microsoft-365/compliance/retention-policies-teams) und [Verwalten von Aufbewahrungsrichtlinien für Teams](../../retention-policies.md)".

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>Kann ich Schichtdaten für einen Benutzer abrufen, dessen Lizenz widerrufen wurde?

Heute bieten wir nicht die Möglichkeit, Daten für einen Benutzer abzurufen, dessen Lizenz widerrufen wurde. Auf diese Funktion arbeiten wir hin.

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>Welche Art von Verschlüsselung verwendet Schichten für Ruhe- und Übertragungsdaten?

Schichtendaten werden im Ruhezustand von Azure Cosmos DB und Azure Storage verschlüsselt. Weitere Informationen finden Sie [unter Azure-Datenverschlüsselung im Ruhezustand](/azure/security/fundamentals/encryption-atrest) und [Datenverschlüsselung in Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest).

Schichten folgen Microsoft 365 Richtlinien für die Verschlüsselung von Daten während der Übertragung. Weitere Informationen finden Sie [unter Verschlüsselung für Daten während der Übertragung](/compliance/assurance/assurance-encryption-in-transit).

Verschiebungen bei der Verschlüsselung ruher und während der Übertragung von Daten werden jährlich durch die SOC2-Complianceüberwachung überprüft.

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>Kann ich auf unveränderliche Kopien von Shifts-Daten zugreifen?

Unveränderliche Kopien von Shifts-Daten werden nicht gespeichert. Beispielsweise kann ein Vorgesetzter Änderungen an einem Zeitplan vornehmen, z. B. Notizen hinzufügen, Schichtzeiten ändern, Aufgaben zuweisen usw.

## <a name="can-shifts-data-be-edited"></a>Können Schichtdaten bearbeitet werden?

Es gibt bestimmte Aspekte von Schichten, die nicht geändert werden können, und bestimmte Aspekte, die geändert werden können. So können beispielsweise Schichtdetails wie Notizen und Farben ähnlich wie in der Schichten-App bearbeitet werden. Schichtanforderungen können nur bearbeitet werden, wenn die Anforderung zurückgezogen wird.

Um zu sehen, welche Felder geändert wurden, können Sie im Microsoft 365 Überwachungsprotokoll nach Shifts-Ereignissen suchen. Weitere Informationen zu den Ereignissen, die für Schichtenaktivitäten im Microsoft 365 Überwachungsprotokoll protokolliert werden, finden Sie [unter Schichten in Teams Aktivitäten](../../audit-log-events.md#shifts-in-teams-activities).

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>Meine Organisation verwendet ein Mitarbeiterverwaltungssystem für die Planung. Können wir Schichtendaten integrieren und darauf zugreifen?

Mit Schichten Graph APIs können Sie Schichtdaten in WFM-Systeme (External Workforce Management) integrieren. Weitere Informationen finden Sie unter [Schichten Graph APIs](/graph/api/resources/shift).

Wir bieten auch verwaltete Schichten-Connectors und Open-Source-Schichten-Connectors an. Mit diesen Connectors können Sie Ihr WFM-System direkt in Schichten integrieren. Weitere Informationen zu Shifts-Connectors und unterstützten WFM-Systemen finden Sie unter [Shifts Connectors](shifts-connectors.md).

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>Können Schichtdaten nach einem bestimmten Zeitraum dauerhaft gelöscht werden?

Heute löschen wir Ihre Shifts-Daten überhaupt nicht. Mithilfe von [Shifts Graph-APIs](/graph/api/resources/shift) ist es möglich, [eine App mit Power Apps zu erstellen](/powerapps/maker/), um Daten für einen bestimmten Zeitraum aufzubewahren. Dies wird jedoch nicht nativ unterstützt.

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>Können Schichtdaten in einer Mandanten-zu-Mandant-Migration verschoben werden?

Schichtdaten können auf bestimmte Anforderungen von einem Mandanten zu einem anderen migriert werden. Denken Sie daran, dass die Migration von Mandanten zu Mandant nicht standardmäßig unterstützt wird, sondern als Kundenanfrage ausgelöst werden kann.

## <a name="related-articles"></a>Verwandte Artikel

- [Schichten für Teams](../shifts-for-teams-landing-page.md)
- [Verwalten der Schichten-App](manage-the-shifts-app-for-your-organization-in-teams.md)
