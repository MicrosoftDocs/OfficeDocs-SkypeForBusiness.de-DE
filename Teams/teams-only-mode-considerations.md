---
title: Überlegungen zum Teams Only-Modus
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dearbeen
description: Vorbereiten des Upgrades auf den Microsoft Teams Only-Modus
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1.keywords: ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89aded4747bc0a3f41fd78ce1bdced7b3363775b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708311"
---
# <a name="teams-only-mode-considerations"></a>Überlegungen zum Teams Only-Modus

Wenn Sie ein Administrator für Ihren Office 365-Mandanten sind, sehen Sie jetzt die Option zum Upgraden auf den Modus nur für Teams im Microsoft Teams Admin Center. Mit dieser Funktion können Sie entweder einzelne Benutzer oder auch den gesamten Mandanten aktualisieren.  

Das Upgrade auf den nur für Teams bestimmten Modus bietet Benutzern die vollständigen Vorteile von Microsoft Teams, dem Hub für Teamarbeit in Office 365, über eine einzige Clientumgebung. Darüber hinaus erhalten Benutzer im Modus "nur für Teams" alle Anrufe und Chats in Teams, unabhängig davon, ob der Absender Skype for Business oder Teams verwendet, und profitieren von Interop-und Federation-Unterstützung.

Während Tausende von Kunden erfolgreich auf Microsoft Teams aktualisiert haben, gibt es Überlegungen, die die Upgrade-Zeitachse Ihrer Organisation und die Benutzererfahrung auf dem Weg beeinflussen können. Insbesondere bedeutet die Möglichkeit, ein Upgrade durchzuführen, nicht unbedingt, dass Ihre Organisation für diese Änderung bereit ist. Um ein optimales Benutzererlebnis zu erhalten, bestätigen Sie bitte, dass Teams Ihre Anforderungen für die Zusammenarbeit und Kommunikation erfüllt. Stellen Sie bitte weiterhin sicher, dass Ihr Netzwerk für die Unterstützung von Teams bereit ist, und setzen Sie vor dem Upgrade der Benutzer auf Teams Ihren Plan für die Benutzerbereitschaft um. 

> [!IMPORTANT]
> Wenn Sie gerade eine Upgrade-Planung beginnen, lesen Sie unbedingt unsere vollständigen Upgrade-Anleitungen und Planungsressourcen. [Beginnen Sie hier](upgrade-start-here.md). 

**Überlegungen zur Koexistenz**: Organisationen, die bereits Skype for Business Online und/oder Skype for Business Server verwenden, können Teams in Ihrer Umgebung mit einer Geschwindigkeit einführen, die Ihren Anforderungen entspricht. Organisationen können die Teams nach Bedarf inkrementell auf eine gewünschte Gruppe von Benutzern ausrollen, und Benutzer, die Teams verwenden, können mit Benutzern kommunizieren, die Skype for Business verwenden, und umgekehrt. Um diese Erfahrung zu verwalten, verwenden Administratoren Koexistenzmodus, die die Benutzeroberfläche des Endbenutzers, das Routingverhalten von eingehenden Chats und anrufen definieren, sowie ob neue Besprechungen in Teams oder Skype for Business geplant sind. Benutzer können mit Benutzern in anderen Organisationen eine Föderation durchführen, wenn der Benutzer **nur auf Teams**aktualisiert wird. die beste Vorgehensweise wird jedoch bereitgestellt, wenn beide Benutzer Teams verwenden. Benutzer, die nur auf Teams aktualisiert werden, können weiterhin an Skype for Business-Besprechungen teilnehmen. 

> [!NOTE]
> Benutzer, die auf Teams aktualisiert werden, können nur mit Benutzern kommunizieren, die Skype für Verbraucher verwenden.

> [!IMPORTANT]
> Ausführlichere Informationen zur Koexistenz finden Sie Untergrund [Legendes zu Microsoft Teams und zur Koexistenz und Interoperabilität von Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md). 

**Mandantenweite Überlegungen**: Wir arbeiten daran, Teams in den folgenden Umgebungen zu aktivieren: im Moment sollten Administratoren jedoch keine Benutzer in Ihrer Organisation aktualisieren, wenn Ihr Skype for Business-Mandant in einer der folgenden Umgebungen gehostet wird:

 - Government Community Cloud-stark
 - Government Community Cloud DoD
 - Office 365, betrieben von 21Vianet
 - Office 365 Deutschland
 - Skype for Business-Mandant wird in Südkorea gehostet **, und** die Organisation setzt voraus, dass die Teams-Daten in Südkorea gespeichert werden. Derzeit werden Organisationen mit Skype for Business-Daten, die in Südkorea gespeichert sind und für die ein Upgrade auf Teams durchgeführt wird, ihre Teams-Daten in der Region Asia Datacenter, nicht in der Region Süd-Korea, speichern.

**Benutzerspezifische Überlegungen**: einige Benutzerszenarien werden weiterhin entwickelt, und Administratoren können beschließen, das Upgrade bestimmter Benutzer vorübergehend zu verschieben, während Sie andere Benutzer in der Organisation aktualisieren. Insbesondere arbeiten wir weiterhin an Szenarien für Benutzer, deren primäres Gerät VDI-basiert ist. Überwachen Sie die [Office 365-Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap) -Website für Ankündigungen.

> [!NOTE]
> Bevor Sie in den Modus nur für Teams wechseln, müssen Sie Geräte ersetzen oder aktualisieren, die keine Teams unterstützen. 

> [!IMPORTANT]
> **Denken Sie daran**: der Wechsel zu Teams ist mehr als eine technische Migration. Bei einem erfolgreichen Upgrade werden sowohl die technische Bereitschaft als auch die Bereitschaft des Endbenutzers bewertet. Lesen Sie unseren [Leitfaden](upgrade-framework.md) für Skype for Business für Teams, um weitere Informationen zur Planung einer Implementierung des Upgrades für Teams zu erhalten.  
