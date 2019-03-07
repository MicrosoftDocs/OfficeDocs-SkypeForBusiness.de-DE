---
title: Überlegungen zum Teams Only-Modus
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Vorbereiten des Upgrades auf Microsoft Teams nur Kopfzeilen herunterladen
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a9e42d8245afdd1deb33f22f3f7695bb5d71617
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30459556"
---
# <a name="teams-only-mode-considerations"></a>Überlegungen zum Teams Only-Modus

Wenn Sie bei Ihrem Office 365-Mandanten ein Administrator sind, sehen Sie jetzt die Möglichkeit, nur Teams Modus in der Microsoft-Teams-Verwaltungskonsole zu aktualisieren. Mit dieser Funktionalität können Sie einzelne Benutzer oder alternativ den gesamten Mandanten aktualisieren.  

Durchführen eines Upgrades auf Teams nur Modus bietet Benutzern die Vorteile der Microsoft-Teams, die-Hub für die Zusammenarbeit in Office 365, über einen einzelnen Clientumgebung. Benutzer in Teams nur Modus werden darüber hinaus erhalten alle Anrufe und Chats in Teams, unabhängig davon, ob der Absender Skype für Geschäftskunden und Teams verwendet werden und von Interop und Federation Support profitieren.

Tausende von Kunden, die Microsoft-Teams erfolgreich aktualisiert haben, werden Aspekte, die Ihre Organisation Upgrade Zeitachse und benutzerfreundlichkeit unterwegs beeinflussen können. Insbesondere müssen die Option für die Aktualisierung bedeutet dies nicht notwendigerweise, dass Ihre Organisation bereit, damit diese Änderung ist. Um ein optimales Benutzererlebnis zu erhalten, bestätigen Sie bitte, dass Teams Ihre Anforderungen für die Zusammenarbeit und Kommunikation erfüllt. Stellen Sie bitte weiterhin sicher, dass Ihr Netzwerk für die Unterstützung von Teams bereit ist, und setzen Sie vor dem Upgrade der Benutzer auf Teams Ihren Plan für die Benutzerbereitschaft um. 

> [!IMPORTANT]
> Wenn Sie nur die Upgrade-Planung beginnen, müssen Sie vollständige Upgrade in der Anleitung und Planen von Ressourcen zu überprüfen. [Beginnen Sie hier](upgrade-introduction.md). 

**Überlegungen zur Koexistenz**: Organisationen, die bereits Skype für Business Online und/oder Skype verwenden, für die Business Server Teams in ihre Umgebung eine Tempo einführen können, die ihren Anforderungen erfüllt. Organisationen können inkrementell Teams an eine bestimmte Gruppe von Benutzern einführen, je nach Bedarf, und Benutzer, die Teams verwenden mit Benutzer zum Verwenden von Skype für Unternehmen und umgekehrt kommunizieren können. Zum Verwalten dieser Erfahrung, die Administratoren verwenden Koexistenz Modi, die durch die Endbenutzer-Client zu definieren, das Routingverhalten eingehender chats und aufruft, sowie, ob neue Besprechungen in Teams oder Skype für Unternehmen geplant werden. Benutzer können mit Benutzern in anderen Organisationen verbinden, wenn der Benutzer auf **Teams nur**aktualisiert wird; jedoch ist am besten bereitgestellt, wenn beide Benutzer Teams verwenden. Benutzer, die auf Teams nur aktualisiert werden können dennoch Skype für Business-Besprechungen teilnehmen. 

> [!NOTE]
> Benutzer, die auf Teams nur aktualisiert werden, können nicht mit Benutzern kommunizieren, die für die Consumer Skype verwenden.

> [!IMPORTANT]
> Ausführlichere Informationen zur Koexistenz finden Sie [Microsoft-Teams, zu verstehen](teams-and-skypeforbusiness-coexistence-and-interoperability.md)und Skype für Interoperabilität und Koexistenz Business. 

**Gesamte Mandanten Aspekte**: Wir arbeiten zum Aktivieren von Teams in den folgenden Umgebungen; Jetzt sollte nicht Administratoren jedoch anderen Benutzern in ihrer Organisation aktualisieren, wenn ihre Skype für Business Mandanten in einem der folgenden Umgebungen gehostet wird:

 - US-Regierung Community Cloud hoch
 - US-Regierung Community-Cloud DoD
 - Office 365 handelt, das von 21Vianet
 - Office 365 Deutschland
 - Skype für Business Mandanten wird in South Korea **und** gehostet die Organisation Teams Daten in South Korea gespeichert werden muss. Organisationen mit Skype für Geschäftsdaten in South Korea gespeichert, die auf Teams aktualisieren werden derzeit ihre Teams Daten in dem Bereich der Asien-Datacenter, nicht in den Bereich im Rechenzentrum South Korea gespeichert haben.

**Benutzerspezifische Aspekte**: Einige Benutzerszenarien werden derzeit noch entwickelt und Administratoren beschließen, das Upgrade von bestimmten Benutzern beim Upgrade von anderen Benutzern in der Organisation vorübergehend zu verschieben. Wir arbeiten an reagieren auf diese Szenarien; Überwachen Sie die Website [Wegweiser für Office 365](https://www.microsoft.com/en-us/microsoft-365/roadmap) für Ansagen.

| Szenario | Notizen |
|----------|-------|
|Die primäre Arbeit Gerät des Benutzers ist eine Mac und dem Benutzer muss die Verfügbarkeit von Kollegen in Outlook finden Sie unter. | Outlook-Anwesenheitsinformationen in Teams ist noch nicht vollständig für Mac-Geräte unterstützt. |
| Benutzer wird regelmäßig Besprechungen mit Kunden oder externe Partner in unterschiedlichen Regionen internationale durchführen. | Externe Teilnehmer, dessen Mandant befindet sich in einem anderen Geo-Speicherort, nicht Sofortnachrichten finden Sie unter chatten klicken Sie in einer Besprechung **federated** . Teilnehmer können weiterhin als anonyme Benutzer die Besprechung teilnehmen. |
| Benutzer führt Skype für Besprechungen Business übertragen. |  Während Teams live Ereignisse (ersetzen Skype-Übertragung) ist bereits im öffentlichen Preview, diesen Benutzer müssen möglicherweise auf Skype für Unternehmen bleiben, bis allgemeine Verfügbarkeit von Teams live-Ereignissen.
| Primäre Gerät des Benutzers ist VDI-basierte. | |
|||

> [!IMPORTANT]
> **Denken Sie daran**: die Verschiebung Teams ist mehr als eine technische Migration. Ein erfolgreiches Upgrade bewertet Technische Verfügbarkeit und Bereitschaft für Endbenutzer. Lesen Sie unsere Skype für Business Teams für Weitere Informationen zum Planen einer Implementierung des Upgrades auf Teams [Anleitungen zu aktualisieren](upgrade-framework.md) .  
