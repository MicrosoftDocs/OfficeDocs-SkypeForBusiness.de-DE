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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: d070180505081971eca6c4075bd5bc4563bcd184
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838205"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a>Bekannte Probleme mit Aufbewahrungsrichtlinien in Microsoft Teams

> [!NOTE]
> Wir unterstützen noch keine Konfiguration für die Aufbewahrung privater Kanal Nachrichten. Die Aufbewahrung von Dateien, die in privaten Kanälen freigegeben sind, wird unterstützt.

Im folgenden werden bekannte Probleme bei Aufbewahrungsrichtlinien in Teams aufgeführt, die nachverfolgt und untersucht werden.

- Unter "Teams auswählen" in der Zeile "Standort" des Teams "Channel-Nachrichten" werden möglicherweise Office 365-Gruppen angezeigt, die nicht auch Teams sind. Dies wird in Zukunft behoben.

- Unter Benutzer in der Zeile Teamchat-Standort auswählen werden möglicherweise Gäste und nicht-Postfachbenutzer angezeigt. Aufbewahrungsrichtlinien sollen nicht für Gäste eingerichtet werden, und wir arbeiten daran, diese aus der Liste zu entfernen.

- Exchange-Lebenszyklus-Assistent (ELC) wird täglich ausgeführt, hat aber eine SLA von 7 Tagen. Daher ist es möglich, dass diese Elemente für bis zu 67 Tage beibehalten werden, wenn Sie über eine Aufbewahrungsrichtlinie für Teams verfügen, um Elemente zu löschen, die älter als 60 Tage sind. Dies ist keine neue Situation – Sie folgt dem Exchange-Modell. In den meisten Fällen gibt es natürlich keine Verzögerung.


| | | |
|---------|---------|---------|
|![Ein Symbol, das einen Entscheidungspunkt darstellt](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Entscheidungspunkt         |Welche Sicherheits- und Compliance-Funktionen benötigt Ihre Organisation? Verfügt Ihre Organisation über die erforderlichen Lizenzen, um die geschäftlichen Sicherheits- und Compliance-Anforderungen zu erfüllen?         |
|![Ein Symbol, das die nächsten Schritte darstellt](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |Nächste Schritte         |Dokumentieren Sie die erforderlichen Sicherheits-und Compliance-Funktionen.         |
