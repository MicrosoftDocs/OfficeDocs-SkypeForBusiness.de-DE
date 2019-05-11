---
title: Zuweisungen für Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1keywords: ms.teamsadmincenter.assignments.overview
description: Informationen Sie zum Verwalten von Zuordnungen in der Microsoft-Teams-Verwaltungskonsole in Teams für Bildungseinrichtungen.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 263b9dda6929bd6956df803a33764634808cddf3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33914023"
---
# <a name="assignments-in-teams-for-education"></a>Aufgaben in Teams für Bildungseinrichtungen

Zuordnungen sind Vorgänge oder Arbeitseinheiten Mitglied Student oder ein Team in einer Klasse als Teil ihrer Studie zugewiesen. Sie können innerhalb einer Klasse Teams Zuordnungen erstellen.

[Erfahren Sie mehr über Zuordnungen](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

## <a name="assignments-in-the-microsoft-teams-admin-center"></a>Zuordnungen in der Verwaltungskonsole von Microsoft-Teams

Mit den Einstellungen Admin im Microsoft-Teams, Administrationscenter können Sie die folgenden Features aktivieren oder Deaktivieren für Schüler und Lehrer innerhalb Ihrer Organisation zur Verfügung stehen. Im folgenden sind die Einstellungen im Zusammenhang mit Zuordnungen:

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Wöchentliche Guardian e-Mail-digest
Guardian-e-Mails werden wöchentliche e-Mails an Eltern oder Aufsichtspersonen Schüler gesendet. Die e-Mails enthält Informationen zur Zuweisung von der vorhergehenden Woche und für die bevorstehende Woche und am Wochenende gesendet. Die e-Mail-Nachrichten von den Administratoren, die über das Feature Schule Daten Sync aktualisiert werden müssen.

Diese Einstellung ist standardmäßig deaktiviert.

<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
MakeCode ist eine Block-basierte Codierung Plattform die Lebensdauer für alle Schüler Computer Science bringt. 

Dies ist ein Produkt eines Drittanbieters oder Dienst, das eine eigene Begriffe und die Datenschutzrichtlinie fällt. Sie sind verantwortlich für die Verwendung von Drittanbieter-Produkte und Dienste.

Diese Einstellung ist standardmäßig deaktiviert.

[Erfahren Sie mehr über MakeCode](https://www.microsoft.com/${locale}/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

Turnitin ist ein Plagiate Erkennung-Dienst. Dies ist ein Produkt eines Drittanbieters oder Dienst, das eine eigene Begriffe und die Datenschutzrichtlinie fällt. Sie sind verantwortlich für die Verwendung von Drittanbieter-Produkte und Dienste.

Diese Einstellung ist standardmäßig deaktiviert.

Um erfolgreich Turnitin für Ihre Organisation zu aktivieren, müssen Sie bereits eine Turnitin-Abonnement verfügen. Sie müssen die folgende zusätzliche Informationen eingeben, die in der Verwaltungskonsole Turnitin nicht gefunden werden können:

  * _TurnitinApiKey_: Dies ist eine 32 Zeichen-GUID in der Verwaltungskonsole unter Integrationen gefunden wurde.
  * _TurnitinApiUrl_: Dies ist die HTTPS-URL der Admin-Konsole Turnitin.

Hier sind einige Anweisungen, damit Sie diese Informationen nutzen können.

Die TurnitinApiUrl ist die Adresse des Hosts der Administratorkonsole.
![Suchen die TurnItInApiUrl](./educationImages/Assignments_mopo_turnitin1.png)

Wechseln Sie zur Registerkarte Integrationen, und fügen Sie eine Integration.
![Suchen die TurnItInApiUrl](./educationImages/Assignments_mopo_turnitin2.png)

Die TurnitinApiKey Ihnen erhält, nachdem Sie die Anweisung befolgen. Kopieren Sie diesen Schlüssel, und fügen Sie ihn in der Microsoft-Teams-Verwaltungskonsole. 
![Suchen die TurnItInApiUrl](./educationImages/Assignments_mopo_turnitin3.png)

[Erfahren Sie mehr über die Integration zwischen Turnitin und Microsoft-Teams](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration)

[Erfahren Sie mehr über Turnitin](https://www.turnitin.com/)
