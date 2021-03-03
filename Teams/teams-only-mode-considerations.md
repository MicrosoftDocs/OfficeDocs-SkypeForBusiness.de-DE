---
title: Überlegungen zum Teams Only-Modus
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: Administratoren erfahren, wie Sie sich im Microsoft Teams Admin Center auf ein Upgrade auf den Modus "Nur für Microsoft Teams" vorbereiten.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86c27d8619a436c6a77ab435cfcb2cc4133befe0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802375"
---
# <a name="teams-only-mode-considerations"></a>Überlegungen zum Teams Only-Modus

Wenn Sie Administrator in Ihrer Microsoft 365- oder Office 365-Organisation sind, wird jetzt im Microsoft Teams Admin Center die Option zum Upgrade auf den Modus "Nur für Teams" angezeigt. Mit dieser Funktionalität können Sie entweder einzelne Benutzer oder alternativ den gesamten Mandanten aktualisieren.  

Das Upgrade auf den Modus "Nur für Teams" bietet Benutzern über eine einzige Clienterfahrung die vollen Vorteile von Microsoft Teams, dem Hub für Teamarbeit in Microsoft 365 oder Office 365. Darüber hinaus erhalten Benutzer im Nur-Teams-Modus alle Anrufe und Chats in Teams, unabhängig davon, ob der Absender Skype for Business oder Teams verwendet, und profitieren von Inop- und Verbundunterstützung.

Obwohl Tausende von Kunden erfolgreich ein Upgrade auf Microsoft Teams durchgeführt haben, gibt es Überlegungen, die die Upgradezeitachse und die Benutzererfahrung Ihrer Organisation im Weg haben können. Insbesondere bedeutet die Möglichkeit zum Upgrade nicht unbedingt, dass Ihre Organisation für diese Änderung bereit ist. Um ein optimales Benutzererlebnis zu erhalten, bestätigen Sie bitte, dass Teams Ihre Anforderungen für die Zusammenarbeit und Kommunikation erfüllt. Stellen Sie bitte weiterhin sicher, dass Ihr Netzwerk für die Unterstützung von Teams bereit ist, und setzen Sie vor dem Upgrade der Benutzer auf Teams Ihren Plan für die Benutzerbereitschaft um. 

> [!IMPORTANT]
> Wenn Sie gerade erst mit der Upgradeplanung beginnen, lesen Sie unbedingt unseren Leitfaden für die ersten Schritte mit Ihrem [Upgradehandbuch für Microsoft Teams.](upgrade-start-here.md) 

**Überlegungen zur Koexistenz:** Organisationen, die bereits Skype for Business Online und/oder Skype for Business Server verwenden, können Teams in einem Tempo, das ihren Anforderungen entspricht, in ihre Umgebung einführen. Organisationen können Teams nach Bedarf inkrementell für eine gewünschte Gruppe von Benutzern einrichten, und Benutzer, die Teams verwenden, können mit Benutzern kommunizieren, die Skype for Business verwenden und umgekehrt. Um diese Benutzererfahrung zu verwalten, verwenden Administratoren Koexistenzmodi, die die Clienterfahrung für Endbenutzer, das Routingverhalten eingehender Chats und Anrufe sowie die Festlegung definieren, ob neue Besprechungen in Teams oder Skype for Business geplant werden. Benutzer können mit Benutzern in anderen Organisationen zusammenarbeiten, wenn für den Benutzer ein Upgrade auf **"Nur Teams Only" durchgeführt wird.** Die beste Benutzererfahrung wird jedoch bereitgestellt, wenn beide Benutzer Teams verwenden. Benutzer, die auf Teams Only aktualisiert wurden, können weiterhin an Skype for Business-Besprechungen teilnehmen. 

> [!IMPORTANT]
> Ausführlichere Informationen zur Koexistenz finden Sie unter "Verstehen der Koexistenz und Interoperabilität von Microsoft Teams und [Skype for Business".](teams-and-skypeforbusiness-coexistence-and-interoperability.md) Weitere Informationen zu Teams und Skype (Consumer) finden Sie unter [Teams und Skype-Interoperabilität.](teams-skype-interop.md)

**Mandantenweite Überlegungen:** Wir arbeiten an der Aktivierung von Teams in den folgenden Umgebungen. Derzeit sollten Administratoren jedoch keine Benutzer in ihrer Organisation aktualisieren, wenn ihr Skype for Business-Mandant in einer der folgenden Umgebungen gehostet wird:

 - Office 365, betrieben von 21Vianet
 - Office 365 Deutschland
 - Der Skype for Business-Mandant wird in Südkorea **gehostet,** und die Organisation erfordert, dass Die Daten von Teams in Südkorea gespeichert werden. Organisationen mit Skype for Business-Daten, die in Südkorea gespeichert sind und ein Upgrade auf Teams durchführen, werden ihre Teamdaten derzeit in der Region des asiatischen Rechenzentrums und nicht in der Rechenzentrumsregion Südkorea gespeichert.

**Benutzerspezifische Überlegungen:** Einige Benutzerszenarien entwickeln sich noch in Entwicklung, und Administratoren beschließen möglicherweise, das Upgrade bestimmter Benutzer vorübergehend zu verschieben, während sie ein Upgrade für andere Benutzer in der Organisation durchführen. Insbesondere arbeiten wir weiterhin an Szenarien für Benutzer, deren primäres Gerät VDI-basiert ist. Überwachen Sie die [Microsoft 365-Roadmap-Website](https://www.microsoft.com/microsoft-365/roadmap) auf Ankündigungen.

> [!NOTE]
> Bevor Sie in den Modus "Nur für Teams" wechseln, müssen Sie Geräte ersetzen oder aktualisieren, die Teams nicht unterstützen. 

> [!IMPORTANT]
> **Denken Sie** daran: Der Wechsel zu Teams ist mehr als nur eine technische Migration. Ein erfolgreiches Upgrade bewertet sowohl die technische Bereitschaft als auch die Endbenutzerbereitschaft. Weitere Informationen zum Planen der Implementierung Ihres Upgrades auf [Teams](upgrade-framework.md) finden Sie in unseren Upgradeanleitungen für Skype for Business zu Teams.  
