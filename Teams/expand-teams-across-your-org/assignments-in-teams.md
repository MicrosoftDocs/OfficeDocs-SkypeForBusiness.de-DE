---
title: Zuweisungen für Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: Hier erfahren Sie, wie Sie Aufgaben im Microsoft Teams Admin Center in Teams für Bildung verwalten.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61caf4bc59387fd5c00cabf459976506b97ef9a0
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326762"
---
# <a name="assignments-in-teams-for-education"></a>Aufgaben in Teams für Bildungseinrichtungen

Aufgaben sind Aufgaben oder Arbeitseinheiten, die einem Kursteilnehmer oder Teammitglied in einer Klasse im Rahmen ihrer Studie zugewiesen sind. Sie können Aufgaben in Ihrer Team Klasse erstellen.

[Weitere Informationen zu Aufgaben](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

## <a name="assignments-in-the-microsoft-teams-admin-center"></a>Aufgaben im Microsoft Teams Admin Center

Mit den Administratoreinstellungen im Microsoft Teams Admin Center können Sie die folgenden Funktionen aktivieren oder deaktivieren, damit Sie für Schüler und Lehrer in Ihrer Organisation zur Verfügung stehen. Die folgenden Einstellungen beziehen sich auf Aufgaben:

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Wöchentlicher Guardian-e-Mail-Digest

Guardian-e-Mails sind wöchentliche e-Mails, die an die Eltern oder Erziehungsberechtigten der Schüler gesendet werden. Die e-Mail-Nachrichten enthalten Informationen zu den Aufgaben aus der vorherigen Woche und für die kommende Woche und werden über das Wochenende verschickt. Die e-Mail-Nachrichten müssen von den Administratoren über das School Data Sync-Feature aktualisiert werden.

Diese Einstellung ist standardmäßig deaktiviert.

<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode ist eine blockbasierte Codierungs Plattform, die die Computerwissenschaften für alle Kursteilnehmer zum Leben erweckt. 

MakeCode ist ein Microsoft-Produkt, das den Microsoft- [Nutzungsbedingungen](https://go.microsoft.com/fwlink/?LinkID=206977) und den [Datenschutz](https://go.microsoft.com/fwlink/?LinkId=521839) Richtlinien unterliegt.

Diese Einstellung ist standardmäßig deaktiviert. Navigieren Sie zum Aktivieren von MakeCode-Aufgaben in Teams im **Team Admin Center**zum Abschnitt **Aufgaben** , und aktivieren Sie die Option MakeCode-Umschaltfläche **auf ein**. Klicken Sie auf **Speichern** , und warten Sie einige Stunden, bis diese Einstellungen wirksam werden.

Weitere Informationen zur Funktionsweise dieses Features finden Sie in dieser [Video Demonstration](https://makecode.com/blog/teams/teams-assignments).

[Weitere Informationen zu MakeCode](https://aka.ms/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

Turnitin ist ein Plagiat-Erkennungsdienst. Hierbei handelt es sich um ein Produkt oder einen Dienst eines Drittanbieters, der seinen eigenen Bedingungen und Datenschutzrichtlinien unterliegt. Sie sind für die Nutzung von Produkten und Dienstleistungen von Drittanbietern verantwortlich.

Diese Einstellung ist standardmäßig deaktiviert.

Damit Sie Turnitin für Ihre Organisation erfolgreich aktivieren können, müssen Sie bereits über ein Turnitin-Abonnement verfügen. Sie müssen die folgenden zusätzlichen Informationen eingeben, die in ihrer Turnitin-Verwaltungskonsole zu finden sind:

  * _TurnitinApiKey_: Hierbei handelt es sich um eine 32-Zeichen-GUID, die in der Admin-Konsole unter Integrationen gefunden wird.
  * _TurnitinApiUrl_: Dies ist die HTTPS-URL Ihrer Turnitin-Verwaltungskonsole.

Hier sind einige Anweisungen, die Ihnen bei der Behebung dieser Informationen helfen.

Die TurnitinApiUrl ist die Hostadresse Ihrer Admin-Konsole.
Beispiel. `https://your-tenant-name.turnitin.com`

In der Admin-Konsole können Sie eine Integration und einen API-Schlüssel erstellen, der der Integration zugeordnet ist.

Wählen Sie **Integrationen** aus dem Seitenmenü und dann **Integration hinzufügen** aus, und geben Sie der Integration einen Namen.
![Screenshot mit dem Hinzufügen einer neuen Integration](./educationImages/Assignments_mopo_turnitin2.png)

Nachdem Sie den Anweisungen folgen, wird Ihnen der TurnitinApiKey mitgeteilt. Kopieren Sie den API-Schlüssel, und fügen Sie ihn in das Microsoft Teams Admin Center ein.  Dies ist das einzige Mal, dass Sie den Schlüssel anzeigen können.
![Screenshot mit dem Kopieren des API-Schlüssels](./educationImages/Assignments_mopo_turnitin3.png)

Wenn Sie im Admin Center für diese Einstellung auf die Schaltfläche " **Speichern** " klicken, können Sie diese Einstellungen einige Stunden in Kraft setzen.

Sind Sie bereit, die Turnitin-Integration in Teams zu verwenden? Registrieren Sie sich für das [Early Access-Programm](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration).
