---
title: Genehmigungen Verfügbarkeit von Anwendungen in Teams
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
description: Erfahren Sie mehr über die Verfügbarkeit von Genehmigungs Anwendungen in Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4326408b7e27aa19af8e6c404d7275d26ba90969
ms.sourcegitcommit: d73d732591944b899a9366f79b4ea97f4a7f2260
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49675179"
---
# <a name="teams-approvals-app-availability"></a>Verfügbarkeit der APP für Teams-Genehmigungen

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Die Genehmigungs-APP ist als persönliche App für alle Microsoft Teams-Benutzer verfügbar.
Die app "Genehmigungen" bietet eine einfache Möglichkeit, um Überwachungs-, Konformitäts-, Rechenschafts-und Workflows sowohl strukturierten als auch unstrukturierten Genehmigungen in Teams zu ermöglichen.

 ![zeigt die app "Genehmigungen"](media/approvals-selection.png)

Benutzer können die Genehmigungs-App anheften, um Sie in der Menüleiste zu speichern.

 ![zeigt die app "Genehmigungen" mit der Option "Pin" an](media/approvalApp-pin.png)

Mit der ersten Genehmigung, die Sie über die Genehmigungs-App erstellt haben, wird die Bereitstellung der Genehmigungslösung in der Standardumgebung für gemeinsame Datendienste (Common Data Service, CDs) ausgelöst. Genehmigungen, die aus der Genehmigungs-App erstellt wurden, werden in der Standard-CD-Umgebung gespeichert.

In diesem Artikel werden die Anforderungen und Rollen der Genehmigungs-App beschrieben.

## <a name="required-permissions-and-licenses"></a>Erforderliche Berechtigungen und Lizenzen

Wenn Sie die Genehmigungs-App verwenden möchten, benötigen Sie die Berechtigung für die folgenden Elemente:

- Berechtigungen zum Erstellen einer Microsoft CDs-Datenbank

- Ein Konto auf [Flow.Microsoft.com](https://flow.microsoft.com/)

- Administrator Rolle in der Zielumgebung.

- Lizenz für [Power Automation](https://docs.microsoft.com/power-automate/get-started-approvals), Office 365 oder Dynamics 365.

## <a name="storage-with-cds"></a>Speicher mit CDs

Das gemeinsame Datenmodell (CDM) ist die Sprache für freigegebene Daten, die von Geschäfts-und Analyseanwendungen in den CDs verwendet wird. Es besteht aus einer Reihe von standardisierten, erweiterbaren Datenschemas, die von Microsoft und unseren Partnern veröffentlicht wurden und die Konsistenz von Daten und deren Bedeutung für Anwendungen und Geschäftsprozesse ermöglichen. Weitere Informationen zum [allgemeinen Datenmodell der Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).

Weitere Informationen zum [Genehmigungsworkflow](https://docs.microsoft.com/power-automate/modern-approvals).

## <a name="approvals-teams-app-permissions"></a>Genehmigungen Teams-App-Berechtigungen

Mit der Genehmigungs Teams-App können Sie auf die folgenden Features zugreifen:

- Empfangen von Nachrichten und Daten, die Sie bereitstellen.

- Senden Sie Nachrichten und Benachrichtigungen.

- Rendern Sie persönliche apps und Dialogfelder ohne einen vom Team bereitgestellten Header.

- Greifen Sie auf Ihre Profilinformationen wie Name, e-Mail-Adresse, Firmenname und bevorzugte Sprache zu.

- Empfangen von Nachrichten und Daten, die Teammitglieder in einem Kanal bereitstellen.

- Senden Sie Nachrichten und Benachrichtigungen in einem Kanal.

- Zugriff auf die Informationen Ihres Teams:
  - Teamname
  - Kanalliste
  - Dienstplan (Namen und e-Mail-Adressen des Teammitglieds).

- Verwenden Sie die Informationen des Teams, um sich mit Ihnen in Verbindung zu setzen.

## <a name="disable-the-approvals-app"></a>Deaktivieren der Genehmigungs-App

Standardmäßig ist die APP Genehmigungen verfügbar. Sie können die APP im Team Admin Center deaktivieren.

  1. Anmelden beim Team Admin Center.

  2. Erweitern Sie **Teams-apps** , und wählen Sie **apps verwalten** aus.

  3. Suchen Sie nach der APP Genehmigungen.

![zeigt die Admin Center-Navigation mit Teams-apps > hervorgehobene apps verwalten](media/manage-approval-apps.png)

  4. Wählen Sie Genehmigungen aus.

  5. Wählen Sie die Umschaltfläche aus, um die APP für Ihre Organisation zu deaktivieren.

![zeigt die Details für die Genehmigungs-APP an.](media/approvals-details.png)

## <a name="retention-policy"></a>Aufbewahrungsrichtlinie

Genehmigungen, die aus der Genehmigungs-App erstellt wurden, werden in der Standard-CD-Umgebung gespeichert, die derzeit keine Sicherungen unterstützt. Weitere Informationen zum [Sichern und Wiederherstellen von Umgebungen – Power Platform \| Microsoft docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).

## <a name="auditing"></a>Überwachung

Die Genehmigungs-App protokolliert Überwachungsereignisse im Microsoft 365 Security and Compliance Center. Sie können das Überwachungsprotokoll anzeigen.

1. Wechseln Sie zur M365-Kompatibilitätswebsite.

2. Wählen Sie den Abschnitt **Audit** aus.

3. Suchen Sie nach Aktivitäten unter **Microsoft Teams-Genehmigungsaktivitäten**.

Sie können nach den folgenden Aktivitäten suchen:

- Neue Genehmigungsanfrage erstellen

- Details zur Genehmigungsanforderung anzeigen

- Genehmigte Genehmigungsanforderung

- Abgelehnte Genehmigungsanforderung

- Genehmigungsanforderung abgebrochen

- Freigegebene Genehmigungsanforderung

- Datei, die an die Genehmigungsanforderung angefügt ist

- Erneut zugewiesene Genehmigungsanforderung

- E-Signatur zur Genehmigungsanfrage hinzugefügt

Für den Zugriff auf weitere Überwachungs Genehmigungen in Flow aktivieren und konfigurieren Sie die Überwachung in der Standardumgebung für die Genehmigung, Genehmigungsanforderung und Genehmigungs Antwort für primäre Genehmigungs Entitäten. Erstellen, aktualisieren und Löschen von Vorgängen sind Überwachungs Bare Ereignisse für Genehmigungs Einträge. Weitere Informationen zu [Überwachungsdaten und Benutzeraktivitäten für Sicherheit und Compliance – Power Platform \| Microsoft docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).

Die Überwachung kann im [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)weiter angepasst werden.

1. Wenn Sie die vorkonfigurierten Berichte verwenden möchten, müssen Sie sich bei Office 365-Sicherheit und-Compliance anmelden.

2. Wählen Sie **& Untersuchung suchen** aus.

3. Durchsuchen Sie das Überwachungsprotokoll, und wählen Sie die Registerkarte **Dynamik 365 Aktivitäten** aus.

Weitere Informationen zu [Microsoft Dataverse und modellgesteuerte apps-Aktivitätsprotokollierung – Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).

## <a name="security"></a>Sicherheit

In der App "Teams-Genehmigung" können Benutzer neue Genehmigungen erstellen und Genehmigungen anzeigen, die Sie gesendet und empfangen haben. Benutzer haben keinen Zugriff auf Genehmigungen, die von anderen Personen erstellt wurden, es sei denn, Sie sind entweder ein Responder oder ein Betrachter der Anforderung.

> [!Note]
> Ein Benutzer erhält eine Anzeige Rolle einer Anforderung, wenn er Teil des Chats oder Kanals ist, in dem die Genehmigung erstellt wurde. Sie verfügen nicht über die Möglichkeit, die Anforderung zu ergreifen, wenn diese Rolle bei der Erstellung der Genehmigung nicht angegeben wurde.
