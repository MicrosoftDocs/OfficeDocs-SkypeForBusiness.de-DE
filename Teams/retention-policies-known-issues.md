---
title: Bekannte Probleme mit Aufbewahrungsrichtlinien in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anach
description: Aktuelle Liste bekannter Probleme für Microsoft Teams-Aufbewahrungsrichtlinien.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a7dd5bac7c82814befab66247b1bfa8cf4943f6
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569962"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a>Bekannte Probleme mit Aufbewahrungsrichtlinien in Microsoft Teams

Im folgenden werden bekannte Probleme bei Aufbewahrungsrichtlinien in Teams aufgeführt, die nachverfolgt und untersucht werden.

- Unter "Teams auswählen" in der Zeile "Standort" des Teams "Channel-Nachrichten" werden möglicherweise Office 365-Gruppen angezeigt, die nicht auch Teams sind. Dies wird in Zukunft behoben.

- Unter Benutzer in der Zeile Teamchat-Standort auswählen werden möglicherweise Gäste und nicht-Postfachbenutzer angezeigt. Aufbewahrungsrichtlinien sollen nicht für Gäste eingerichtet werden, und wir arbeiten daran, diese aus der Liste zu entfernen.

- Exchange-Lebenszyklus-Assistent (ELC) wird täglich ausgeführt, hat aber eine SLA von 7 Tagen. Daher ist es möglich, dass diese Elemente für bis zu 67 Tage beibehalten werden, wenn Sie über eine Aufbewahrungsrichtlinie für Teams verfügen, um Elemente zu löschen, die älter als 60 Tage sind. Dies ist keine neue Situation – Sie folgt dem Exchange-Modell. In den meisten Fällen gibt es natürlich keine Verzögerung.


| | | |
|---------|---------|---------|
|![Ein Symbol, das einen Entscheidungspunkt darstellt](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Entscheidungspunkt         |Welche Sicherheits- und Compliance-Funktionen benötigt Ihre Organisation? Verfügt Ihre Organisation über die erforderlichen Lizenzen, um die geschäftlichen Sicherheits- und Compliance-Anforderungen zu erfüllen?         |
|![Ein Symbol, das die nächsten Schritte darstellt](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |Nächste Schritte         |Dokumentieren Sie die erforderlichen Sicherheits-und Compliance-Funktionen.         |
