---
title: Verfügbarkeit von Genehmigungen für Anwendungen in Teams
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
description: Erfahren Sie mehr über die Verfügbarkeit der Genehmigungsanwendung in Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f916b4e794c862a05a42f075ca2f210a079ff42a
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909519"
---
# <a name="teams-approvals-app-availability"></a>Verfügbarkeit der App "Teams-Genehmigungen"

Die App "Genehmigungen" steht als persönliche App für alle Microsoft Teams-Benutzer zur Verfügung.
Die App "Genehmigungen" bietet eine einfache Möglichkeit, Überwachung, Compliance, Verantwortlichkeit und Workflows sowohl für strukturierte als auch unstrukturierte Genehmigungen in Teams zu übernehmen.

 ![zeigt die Genehmigungs-App an](media/approvals-selection.png)

Benutzer können die Genehmigungs-App anheften, um sie auf der Menüleiste zu speichern.

 ![Zeigt die Genehmigungs-App mit der Option "Anheften" an.](media/approvalApp-pin.png)

Die erste Genehmigung, die aus der App für Genehmigungen erstellt wurde, löst die Bereitstellung der Genehmigungslösung in der standardumgebung des gemeinsamen Datendiensts (Common Data Service, CDS) aus. Genehmigungen, die mit der Genehmigungs-App erstellt wurden, werden in der Standard-CDS-Umgebung gespeichert.

In diesem Artikel werden die Anforderungen und Rollen der Genehmigungs-App beschrieben.

## <a name="required-permissions-and-licenses"></a>Erforderliche Berechtigungen und Lizenzen

Um die Genehmigungs-App zu verwenden, benötigen Sie Berechtigungen für die folgenden Elemente:

- Berechtigungen zum Erstellen einer Microsoft CDS-Datenbank.

- Ein Konto auf [flow.microsoft.com](https://flow.microsoft.com/)

- Administratorrolle in der Zielumgebung.

- Lizenz für [Power Automate,](https://docs.microsoft.com/power-automate/get-started-approvals)Office 365 oder Dynamics 365.

## <a name="storage-with-cds"></a>Speicher mit CDS

Das Common Data Model (CDM) ist die Sprache freigegebener Daten, die von Geschäfts- und Analyseanwendungen im CDS verwendet wird. Sie besteht aus einem Satz standardisierter, erweiterbarer Datenschemas, die von Microsoft und unseren Partnern veröffentlicht wurden und die Konsistenz der Daten und deren Bedeutung in allen Anwendungen und Geschäftsprozessen ermöglichen. Erfahren Sie mehr über [das allgemeine Datenmodell der Microsoft Power Platform.](https://docs.microsoft.com/power-automate/get-started-approvals)

Weitere Informationen zum [Genehmigungsworkflow.](https://docs.microsoft.com/power-automate/modern-approvals)

## <a name="approvals-teams-app-permissions"></a>Genehmigungen für die Teams-App-Berechtigungen

Mit der App "Approvals Teams" können Sie auf die folgenden Features zugreifen:

- Empfangen Sie Nachrichten und Daten, die Sie ihr zur Verfügung stellen.

- Senden Sie Ihnen Nachrichten und Benachrichtigungen.

- Rendern sie persönliche Apps und Dialogfelder ohne den von Teams bereitgestellten Header.

- Greifen Sie auf Ihre Profilinformationen wie Ihren Namen, Ihre E-Mail-Adresse, den Firmennamen und die bevorzugte Sprache zu.

- Empfangen Sie Nachrichten und Daten, die Teammitglieder in einem Kanal bereitstellen.

- Senden sie Nachrichten und Benachrichtigungen in einem Kanal.

- Greifen Sie auf die Informationen Ihres Teams zu:
  - Teamname
  - Kanalliste
  - Liste (Namen und E-Mail-Adressen des Teammitglieds).

- Verwenden Sie die Informationen des Teams, um kontaktiert zu werden.

## <a name="disable-the-approvals-app"></a>Deaktivieren der Genehmigungs-App

Die App "Genehmigungen" ist standardmäßig verfügbar. Sie können die App im Teams Admin Center deaktivieren.

  1. Melden Sie sich beim Teams Admin Center an.

  2. Erweitern Sie **die Teams-Apps,** und wählen **Sie "Apps verwalten" aus.**

  3. Suchen Sie nach der Genehmigungs-App.

![admin center navigation with Teams Apps > Manage Apps highlighted](media/manage-approval-apps.png)

  4. Wählen Sie "Genehmigungen" aus.

  5. Wählen Sie den Umschalter aus, um die App für Ihre Organisation zu deaktivieren.

![zeigt die Details für die Genehmigungs-App an.](media/approvals-details.png)

## <a name="retention-policy"></a>Aufbewahrungsrichtlinie

Mit der Genehmigungs-App erstellte Genehmigungen werden in der Standard-CDS-Umgebung gespeichert, die derzeit keine Sicherungen unterstützt. Erfahren Sie mehr über das Sichern und Wiederherstellen von [Umgebungen – Microsoft \| Docs für die Power Platform.](https://docs.microsoft.com/power-platform/admin/backup-restore-environments)

## <a name="auditing"></a>Überwachung

Die Genehmigungs-App protokolliert Überwachungsereignisse im Microsoft 365 Security and Compliance Center. Sie können das Überwachungsprotokoll anzeigen.

1. Wechseln Sie zur Microsoft 365-Compliancewebsite.

2. Wählen Sie den **Abschnitt "Überwachung"** aus.

3. Suchen Sie nach Aktivitäten unter **"Microsoft Teams-Genehmigungsaktivitäten".**

Sie können nach den folgenden Aktivitäten suchen:

- Erstellen einer neuen Genehmigungsanforderung

- Anzeigen von Details zur Genehmigungsanforderung

- Genehmigte Genehmigungsanforderung

- Abgelehnte Genehmigungsanforderung

- Genehmigungsanforderung abgebrochen

- Anforderung zur gemeinsamen Genehmigung

- An Genehmigungsanforderung angefügte Datei

- Neu zugewiesene Genehmigungsanforderung

- E-Signatur zur Genehmigungsanforderung hinzugefügt

Für den Zugriff auf weitere Überwachungsgenehmigungen in Flow aktivieren und konfigurieren Sie die Überwachung in der Standardumgebung für die primären Genehmigungsentitäten "Genehmigung", "Genehmigungsanforderung" und "Genehmigungsantwort". Erstellungs-, Aktualisierungs- und Löschvorgänge sind überwachungsfähige Ereignisse für Genehmigungsdatensätze. Weitere Informationen zu [Überwachungsdaten und Benutzeraktivitäten für Sicherheit und Compliance – Microsoft \| Docs für die Power Platform.](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity)

Die Überwachung kann im [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)weiter angepasst werden.

1. Wenn Sie die vorkonfigurierten Berichte verwenden möchten, melden Sie sich bei Microsoft 365 Security and Compliance an.

2. Wählen Sie **"Suche & Untersuchung" aus.**

3. Durchsuchen Sie das Überwachungsprotokoll, und wählen Sie die **Registerkarte "Dynamics 365-Aktivitäten"** aus.

Weitere Informationen zur [Microsoft Dataverse- und modellgesteuerten App-Aktivitätsprotokollierung – Power Platform.](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing)

## <a name="security"></a>Sicherheit

Über die App "Teams-Genehmigungen" haben Benutzer Zugriff auf das Erstellen neuer Genehmigungen und das Anzeigen von Genehmigungen, die sie gesendet und erhalten haben. Benutzer haben keinen Zugriff auf Genehmigungen, die von anderen Personen erstellt wurden, es sei denn, sie sind entweder ein Befragter oder ein Anzeigenr der Anfrage.

> [!Note]
> Einem Benutzer wird eine Anzeigerolle einer Anforderung übertragen, wenn er Teil des Chats oder Kanals ist, in dem die Genehmigung erstellt wurde. Sie können für die Anforderung keine Maßnahmen ergreifen, wenn ihnen diese Rolle bei der Genehmigungserstellung nicht erteilt wurde.
