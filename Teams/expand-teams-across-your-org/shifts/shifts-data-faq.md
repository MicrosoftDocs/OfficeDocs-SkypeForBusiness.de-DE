---
title: Häufig gestellte Fragen (FAQ) zum Verschieben von Daten
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
description: Hier erhalten Sie Antworten auf häufig gestellte Fragen zu Schichtendaten, z. B. wo Schichten gespeichert werden, Datenaufbewahrung, Abruf und Verschlüsselung.
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
ms.openlocfilehash: 3f26413aa746b37474e7035e313fc8ffff2fb93c
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2022
ms.locfileid: "63039953"
---
# <a name="shifts-data-faq"></a>Häufig gestellte Fragen (FAQ) zum Verschieben von Daten

In diesem Artikel werden häufig gestellte Fragen zu Schichtendaten behandelt, z. B. wo Schichten gespeichert werden, Datenaufbewahrung, Abruf und Verschlüsselung.

## <a name="where-is-shifts-data-stored"></a>Wo werden Verschiebedaten gespeichert?

Verschiebt Daten werden in einem von drei Regionen (Geos) gespeichert: Asien-Pazifik (APAC), Der Europäischen Union (EU) oder den Vereinigten Staaten. Jeder Geospeicher speichert Daten in mindestens zwei Azure-Rechenzentrumsregionen für Hochverfügbarkeit (High Availability, HA) und Notfallwiederherstellung (Disaster Recovery, DR). Heute nutzen die Geodaten der VEREINIGTEn Staaten und Nordamerika Rechenzentren in Nord-Mittel- und Süd-Mittel-USA. Weitere Informationen finden Sie unter [Wo Microsoft 365 kundendaten gespeichert sind](/microsoft-365/enterprise/o365-data-locations).

Derzeit bietet Shifts Datenspeicherung in Australien, Kanada, Frankreich, Japan und Großbritannien an. Wir arbeiten an einer Erweiterung der Unterstützung für weitere Standorte.

## <a name="can-i-choose-where-shifts-data-is-stored"></a>Kann ich auswählen, wo Schichten gespeichert werden?

Bei der ersten Einrichtung Teams Sie ein Land oder eine Region auswählen, das bzw. die auf Abonnementebene festgelegt ist. Shifts berücksichtigt diese Auswahl und verwendet das in Teams festgelegte Gebiet, wenn diese Region unterstützt wird. Wenn wir uns in dieser Region noch nicht befinden, speichern wir Daten in einer von uns unterstützten Umgebung. In Zukunft planen wir die Migration vorhandener Daten, die in einer nahe gelegenen Region gespeichert sind, in die Region, die in der Region bereitgestellt Teams.

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>Kann ich in Schichten auf die persönlichen Daten eines Benutzers zugreifen und diese exportieren oder löschen?

Schichten sind DSGVO-konform (DSGVO-konform).Eine formelle Anfrage einer Person (die als "Betroffenen von Daten" bezeichnet wird) eine Aktion für ihre persönlichen Daten zu ergreifen, wird als Datensubjektanforderung (Data Subject Request, DSR) bezeichnet. Sie können personenbezogene Daten in Schichten als Reaktion auf eine DSR suchen und darauf reagieren.

Sie können das eDiscovery-Tool für die Inhaltssuche in Microsoft 365 Compliance Center verwenden, um Nach Zeitplan- und Uhrzeitdaten zu suchen Excel. Bei allen anderen Schichten-Daten können Sie Screenshots der Daten erstellen.

Weitere Informationen finden Sie unter [Office 365 von Datensubjektanforderungen für die DSGVO undGPA](/microsoft-365/compliance/gdpr-dsr-office365).

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>Was geschieht mit Schichten von Daten, wenn ich Schichten für meine Organisation deschalte?

Durch das Deaktivieren von Schichten in Ihrer Organisation *werden keine* Daten gelöscht. Wenn Sie Schichten deaktivieren und dann später Schichten aktivieren, sind Ihre Schichtdaten weiterhin verfügbar.

Wenn Sie Ihren Mandanten löschen, werden alle Schichtdaten nach Ende des Aufbewahrungszeitraums gelöscht.

Es gibt keine Option, nur Schichtendaten zu löschen. Wenn Sie ein Team in einer Teams löschen, werden die diesem Team zugeordneten Daten von Schichten nach Ablauf des Aufbewahrungszeitraums gelöscht. Weitere Informationen finden Sie unter [Aufbewahrung, Löschung und Löschung von Daten in Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>Kann ich einen Schichtplan wiederherstellen, der gelöscht wurde?

Sie können einen gelöschten Zeitplan wiederherstellen, wenn die Microsoft 365, die den Zeitplan Teams, wiederhergestellt wird.

Standardmäßig wird eine gelöschte Microsoft 365 30 Tage aufbewahrt. Dieser 30-Tage-Zeitraum wird als "weiches Löschen" bezeichnet, da Sie die Gruppe trotzdem wiederherstellen können. Weitere Informationen finden Sie unter [Wiederherstellen einer gelöschten Microsoft 365 Gruppe](/microsoft-365/admin/create-groups/restore-deleted-group?view=o365-worldwide&tabs=admin-center).

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>Kann ich benutzerdefinierte Aufbewahrungsrichtlinien für Schichtendaten verwenden?

Derzeit werden benutzerdefinierte Aufbewahrungsrichtlinien von Schichten nicht unterstützt.

Weitere Informationen zu Aufbewahrungsrichtlinien in Teams finden Sie unter Informationen zur [](/microsoft-365/compliance/retention-policies-teams) Aufbewahrung für Teams und Verwalten von [Aufbewahrungsrichtlinien für Teams](../../retention-policies.md).

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>Kann ich Schichtendaten für einen Benutzer abrufen, dessen Lizenz widerrufen wurde?

Heute bieten wir keine Möglichkeit zum Abrufen von Daten für einen Benutzer, dessen Lizenz widerrufen wurde. Auf diese Funktion arbeiten wir hin.

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>Welche Art der Verschlüsselung verwendet Schichten für ruhende Und-Daten bei der Übertragung?

Verschiebt ruhede Daten werden von Azure Cosmos DB und Azure-Storage. Weitere Informationen finden Sie unter [Azure-Datenverschlüsselung ruhen lassen sich](/azure/security/fundamentals/encryption-atrest) und [Datenverschlüsselung in Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest).

Schichten folgen Microsoft 365 Richtlinien für die Verschlüsselung von Daten bei der Übertragung. Weitere Informationen finden Sie unter [Verschlüsselung für Daten bei der Übertragung](/compliance/assurance/assurance-encryption-in-transit).

Verlagerungen der Verschlüsselung ruher Daten und der übertragenen Daten werden jährlich von der SOC2-Complianceprüfung überprüft.

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>Kann ich auf unveränderliche Kopien von Schichtendaten zugreifen?

Es werden keine unveränderlichen Kopien von Schichtendaten gespeichert. Beispielsweise kann ein Vorgesetzter Änderungen an einem Zeitplan vornehmen, z. B. Notizen hinzufügen, Schichtzeiten ändern, Vorgänge zuweisen und so weiter.

## <a name="can-shifts-data-be-edited"></a>Können Schichtdaten bearbeitet werden?

Es gibt bestimmte Aspekte von Schichten, die nicht geändert werden können, und bestimmte Aspekte, die geändert werden können. So können beispielsweise Schichtdetails wie Notizen und Farben auf ähnliche Weise bearbeitet werden wie in der Schichten-App. Schichtanforderungen können nur bearbeitet werden, wenn die Anforderung bearbeitet wird.

Wenn Sie sehen möchten, welche Felder geändert wurden, können Sie Microsoft 365 Überwachungsprotokoll nach Schichten-Ereignissen durchsuchen. Weitere Informationen zu den Ereignissen, die für Schichtenaktivitäten im Überwachungsprotokoll des Microsoft 365 protokolliert werden, finden Sie unter Schichten [in Teams Aktivitäten](../../audit-log-events.md#shifts-in-teams-activities).

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>Meine Organisation verwendet für die Planung ein Personalverwaltungssystem. Können wir Schichten integrieren und auf die Daten zugreifen?

Schichten Graph-APIs können Sie Schichtendaten in WFM-Systeme (Externe Mitarbeiterverwaltung) integrieren. Weitere Informationen finden Sie unter [Schichten Graph-APIs](/graph/api/resources/shift).

Darüber hinaus bieten wir verwaltete Schichten-Connectors und Open-Source-Connectors für Schichten an. Mit diesen Connectors können Sie Ihr WFM-System direkt in Schichten integrieren. Weitere Informationen zu Schichten-Connectors und unterstützten WFM-Systemen finden Sie unter [Schichten-Connectors](shifts-connectors.md).

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>Können Daten von Schichten nach einem bestimmten Zeitraum dauerhaft gelöscht werden?

Heute löschen wir Ihre Schichtendaten überhaupt nicht. Mithilfe [von Graph-APIs](/graph/api/resources/shift) ist es möglich, eine App mit Power Apps zu [](/powerapps/maker/) erstellen, um Daten für einen bestimmten Zeitraum zu speichern. Dies wird jedoch systemeigene nicht unterstützt.

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>Können Verschiebedaten in einer Mandanten-zu-Mandant-Migration verschoben werden?

Verschiebt Daten können auf bestimmte Anforderung von einem Mandanten zu einem anderen migriert werden. Beachten Sie, dass die Migration von Mandanten zu Mandanten nicht ohne Unterstützung unterstützt wird, aber als Kundenanforderung ausgelöst werden kann.

## <a name="related-articles"></a>Verwandte Artikel

- [Schichten für Teams](../shifts-for-teams-landing-page.md)
- [Verwalten der Schichten-App](manage-the-shifts-app-for-your-organization-in-teams.md)
