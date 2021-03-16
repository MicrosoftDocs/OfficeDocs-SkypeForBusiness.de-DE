---
title: Verfügbarkeit der App "Genehmigungen" in Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Erfahren Sie mehr über die Verfügbarkeit der Anwendung "Genehmigungen" in Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f916b4e794c862a05a42f075ca2f210a079ff42a
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909519"
---
# <a name="teams-approvals-app-availability"></a>Verfügbarkeit der Microsoft Teams-App "Genehmigungen"

Die App "Genehmigungen" steht als persönliche App für alle Benutzer von Microsoft Teams zur Verfügung.
Die App "Genehmigungen" bietet eine einfache Möglichkeit, um in Microsoft Teams Überwachung, Compliance, Verantwortlichkeit und Workflows sowohl in strukturierte als auch unstrukturierte Genehmigungen zu bringen.

 ![Abbildung der App "Genehmigungen"](media/approvals-selection.png)

Benutzer können die App "Genehmigungen" an der Menüleiste anheften.

 ![Abbildung der App "Genehmigungen" mit der Option zum Anheften](media/approvalApp-pin.png)

Durch die erste mit der App "Genehmigungen" erstellte Genehmigung wird die Bereitstellung der Genehmigungslösung in der CDS-Standardumgebung (Common Data Service) ausgelöst. Mit der App "Genehmigungen" erstellte Genehmigungen werden in der CDS-Standardumgebung gespeichert.

In diesem Artikel werden die Anforderungen und Rollen für die App "Genehmigungen" beschrieben.

## <a name="required-permissions-and-licenses"></a>Erforderliche Berechtigungen und Lizenzen

Um die App "Genehmigungen" verwenden zu können, benötigen Sie Berechtigungen für die folgenden Elemente:

- Berechtigungen zum Erstellen einer Microsoft CDS-Datenbank.

- Ein Konto auf [flow.microsoft.com](https://flow.microsoft.com/)

- Administratorrolle in der Zielumgebung.

- Lizenz für [Power Automate](https://docs.microsoft.com/power-automate/get-started-approvals), Office 365 oder Dynamics 365.

## <a name="storage-with-cds"></a>Speicher mit CDS

Das allgemeine Datenmodell (Common Data Model, CDM) ist die gemeinsame Datensprache, die von Geschäfts- und Analyseanwendungen im CDS verwendet wird. Sie besteht aus einer Reihe standardisierter, erweiterbarer Datenschemas, die von Microsoft und unseren Partnern veröffentlicht werden, und die anwendungs- und geschäftsprozessübergreifend für Einheitlichkeit der Daten und deren Bedeutung sorgen. Weitere Informationen zum [Allgemeinen Datenmodell der Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).

Weitere Informationen zum [Genehmigungsworkflow](https://docs.microsoft.com/power-automate/modern-approvals).

## <a name="approvals-teams-app-permissions"></a>Berechtigungen für die Microsoft Teams-App "Genehmigungen"

Über die Microsoft Teams-App "Genehmigungen" können Sie auf die folgenden Features zugreifen:

- Empfangen von Nachrichten und Daten, die Sie bereitstellen.

- Versand von Nachrichten und Benachrichtigungen an Sie.

- Rendern persönlicher Apps und Dialogfelder ohne eine von Microsoft Teams bereitgestellte Kopfzeile.

- Zugriff auf Ihre Profilinformationen wie Name, E-Mail-Adresse, Firmenname und bevorzugte Sprache.

- Empfangen von Nachrichten und Daten, die Teammitglieder in einem Kanal bereitstellen.

- Senden von Nachrichten und Benachrichtigungen in einem Kanal.

- Zugriff auf die Informationen Ihres Teams:
  - Teamname
  - Kanalliste
  - Liste (Namen und E-Mail-Adressen der Teammitglieder)

- Verwenden der Teaminformationen zur Kontaktaufnahme.

## <a name="disable-the-approvals-app"></a>Deaktivieren der App "Genehmigungen"

Die App "Genehmigungen" ist standardmäßig verfügbar. Sie können die App im Microsoft Teams Admin Center deaktivieren.

  1. Melden Sie sich beim Microsoft Teams Admin Center an.

  2. Erweitern Sie **Microsoft Teams-Apps**, und wählen Sie **Apps verwalten** aus.

  3. Suchen Sie nach der App "Genehmigungen".

![Abbildung der Admin Center-Navigation mit hervorgehobenen Optionen "Microsoft Teams-Apps" > "Apps verwalten"](media/manage-approval-apps.png)

  4. Wählen Sie "Genehmigungen" aus.

  5. Deaktivieren Sie die App für Ihre Organisation mithilfe des Schalters.

![Abbildung der Details für die App "Genehmigungen"](media/approvals-details.png)

## <a name="retention-policy"></a>Aufbewahrungsrichtlinie

Mit der App "Genehmigungen" erstellte Genehmigungen werden in der CDS-Standardumgebung gespeichert, die Sicherungen derzeit nicht unterstützt. Erfahren Sie mehr über das [Sichern und Wiederherstellen von Umgebungen – Power Platform \| Microsoft-Dokumentation](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).

## <a name="auditing"></a>Überwachung

Die App "Genehmigungen" protokolliert Überwachungsereignisse im Microsoft 365 Security & Compliance Center. Sie können dieses Überwachungsprotokoll einsehen.

1. Wechseln Sie zum Microsoft 365 Compliance Center.

2. Wählen Sie den Abschnitt **Überwachung** aus.

3. Suchen Sie nach Aktivitäten unter **Aktivitäten in Microsoft Teams "Genehmigungen"**.

Sie können nach den folgenden Aktivitäten suchen:

- Erstellen einer neuen Genehmigungsanforderung

- Anzeigen von Details zu Genehmigungsanforderungen

- Genehmigte Genehmigungsanforderung

- Abgelehnte Genehmigungsanforderung

- Stornierte Genehmigungsanforderung

- Freigegebene Genehmigungsanforderung

- An Genehmigungsanforderung angefügte Datei

- Neu zugewiesene Genehmigungsanforderung

- Zu Genehmigungsanforderung hinzugefügte digitale Signatur

Aktivieren und konfigurieren Sie für den Zugriff auf weitere Überwachungsgenehmigungen innerhalb von Flow die Überwachung in der Standardumgebung für die primären Genehmigungsentitäten Genehmigung, Genehmigungsanforderung und Genehmigungsantwort. Erstellen, Aktualisieren und Löschen sind überwachbare Ereignisse für Genehmigungseinträge. Weitere Informationen zur [Überwachung von Daten und Benutzeraktivitäten für Sicherheit und Compliance – Power Platform\| Microsoft-Dokumentation](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).

Die Überwachung kann im [Microsoft 365 Security & Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US) weiter angepasst werden.

1. Um die vorkonfigurierten Berichte zu verwenden, melden Sie sich bei Microsoft 365 Security and Compliance an.

2. Wählen Sie **Suche und Untersuchung** aus.

3. Suchen Sie das Überwachungsprotokoll, und wählen Sie die Registerkarte **Dynamics 365-Aktivitäten** aus.

Weitere Informationen über die [Microsoft Dataverse- und modellgesteuerte App-Aktivitätsprotokollierung – Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).

## <a name="security"></a>Sicherheit

Über die Microsoft Teams-App "Genehmigungen" können Benutzer neue Genehmigungen erstellen und solche anzeigen, die sie gesendet und erhalten haben. Die Benutzer haben keinen Zugriff auf Genehmigungen, die von anderen erstellt wurden, es sei denn, sie sind eine antwortende oder anzeigende Person der Anforderung.

> [!Note]
> Einem Benutzer wird eine Anzeigerolle für eine Anforderung erteilt, wenn er dem Chat oder Kanal angehört, in dem die Genehmigung erstellt wurde. Er hat nicht die Möglichkeit, Maßnahmen für die Anforderung zu ergreifen, wenn ihm diese Rolle beim Erstellen der Genehmigung nicht erteilt wurde.
