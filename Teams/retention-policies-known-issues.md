---
title: Bekannte Probleme beim Aufbewahrungsrichtlinien in Microsoft-Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Aktuelle Liste bekannter Probleme bei Microsoft-Teams, Aufbewahrungsrichtlinien.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 411ef4bf12d55af0b913443219a00f3f56c7eba2
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461188"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a>Bekannte Probleme beim Aufbewahrungsrichtlinien in Microsoft-Teams

Im folgenden werden bekannte Probleme für Aufbewahrungsrichtlinien in Teams, die werden nachverfolgt und untersucht.

- Klicken Sie unter Wählen Sie Teams in der Zeile Teams Channel Nachrichten Speicherort sehen Sie sich, dass Office 365-Gruppen, sind nicht auch Teams. Dieses Problem wird in der Zukunft behoben werden.

- Klicken Sie unter Wählen Sie Benutzer in der Zeile des Teams Chat Speicherort möglicherweise Gäste und nicht-Mailbox Benutzer angezeigt. Aufbewahrungsrichtlinien werden nicht vorgesehen für Gäste festgelegt werden soll, und wir arbeiten, um diese aus der Liste zu entfernen.

- Lebenszyklus der Exchange-Assistent (ELC) wird täglich ausgeführt, aber es wurde eine SLA von 7 Tage. Daher ist es möglich, dass, wenn Sie eine Aufbewahrungsrichtlinie Teams zum Löschen von Elementen, die älter als 60 Tage haben, diese Elemente für bis zu 67 Tage beibehalten werden konnte. Dies ist eine neue Situation nicht – es gilt das Exchange-Modell. In den meisten Fällen ist natürlich keine Verzögerung.


| | | |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Entscheidungspunkt         |Welche Sicherheits- und Compliance-Funktionen benötigt Ihre Organisation? Verfügt Ihre Organisation über die erforderlichen Lizenzen, um die geschäftlichen Sicherheits- und Compliance-Anforderungen zu erfüllen?         |
|![Symbol für „Nächste Schritte“](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |Nächste Schritte         |Dokumentieren der erforderlichen Features für Sicherheit und Compliance.         |
