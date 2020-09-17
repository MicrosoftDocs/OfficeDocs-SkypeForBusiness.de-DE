---
title: Upgrade auf Teams über eine lokale Skype for Business-Bereitstellung – Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Upgrade von Skype for Business auf Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80a7071cf6adbfa423e4c0fa12ac21a5bc777268
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940653"
---
# <a name="upgrade-methods-mdash-for-it-administrators"></a>Aktualisierungsmethoden &mdash; für IT-Administratoren

In diesem Artikel werden Aktualisierungsmethoden für die Migration zu Teams beschrieben. Dieser Artikel ist der zweite von mehreren, die Upgrade-Konzepte und Implementierung für IT-Administratoren beschreiben.  

- [Übersicht](upgrade-to-teams-on-prem-overview.md)
- **Aktualisierungsmethoden** (dieser Artikel)
- [Tools zum Verwalten des Upgrades](upgrade-to-teams-on-prem-tools.md)
- [Weitere Überlegungen für Organisationen mit Skype for Business lokal](upgrade-to-teams-on-prem-considerations.md)
- [Implementieren des Upgrades](upgrade-to-teams-on-prem-implement.md)
- [Überlegungen zum Public Switched Telephone Network (PSTN)](upgrade-to-teams-on-prem-pstn-considerations.md)

Darüber hinaus werden in den folgenden Artikeln wichtige Upgrade-Konzepte und Koexistenz-Verhaltensweisen beschrieben:

- [Koexistenz von Teams und Skype for Business](upgrade-to-teams-on-prem-coexistence.md)
- [Koexistenzmodus – Referenz](migration-interop-guidance-for-teams-with-skype.md)
- [Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="upgrade-methods"></a>Upgrade-Methoden

Es gibt zwei Methoden zum Aktualisieren einer vorhandenen Organisation mit Skype for Business (ob online oder lokal) für Teams: überlappende Funktionen und die Methode zum Auswählen von Funktionen.  Dieser Artikel unterstützt Sie bei der Auswahl der richtigen Methode für Ihre Organisation, indem beide Methoden beschrieben und die vor-und Nachteile der einzelnen Methoden vorgestellt werden. 

- [Überlappende Capabilities-Methode (im Modus "Inseln")](#overlapping-capabilities-method-using-islands-mode)

   Benutzer in einer vorhandenen Skype for Business-Organisation werden in Teams eingeführt, damit Sie beide Clients während einer Übergangsphase verwenden können. In diesem Zeitraum stehen Ihnen die meisten--aber nicht alle--Funktionen von Teams zur Verfügung. Der Modus für diese Konfiguration wird als "Inseln" bezeichnet, und dies ist der Standardmodus für jede vorhandene Organisation mit Skype for Business. Sobald die Organisation fertig ist, verschiebt der Administrator Benutzer in den TeamsOnly-Modus.

- [Auswählen von Funktionen (mit einem oder mehreren Skype for Business-Modi)](#select-capabilities-method-using-skype-for-business-modes)

   Der Administrator verwaltet den Übergang (von Skype for Business zu Teams) von Chat-, Anruf-und Besprechungs Planungsfunktionen für Benutzer in Ihrer Organisation.  Jede dieser Funktionen steht entweder in Skype for Business oder in Teams zur Verfügung, aber nicht in beiden. Administratoren verwenden TeamsUpgradePolicy, um zu steuern, wann diese Funktionalität für Ihre Benutzer in Teams verschoben werden soll. Benutzer, die noch nicht im TeamsOnly-Modus sind, verwenden weiterhin Skype for Business für Chats und Anrufe, und die beiden Benutzergruppen können über die Interop-Funktionalität kommunizieren. Administratoren verwalten den Übergang, indem Sie schrittweise mehr Benutzer in den TeamsOnly-Modus migrieren.  

Nachdem Sie die Upgrade-Methode verstanden und ausgewählt haben, können Sie sich mit den [Tools für die Verwaltung des Upgrades Ihrer Organisation auf Teams](upgrade-to-teams-on-prem-tools.md)vertraut machen.

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Überlappende Capabilities-Methode (im Modus "Inseln")

Mit der überlappenden Funktionen-Methode können Benutzer sowohl Teams als auch Skype for Business-Clients für Chats, VoIP-Anrufe und Besprechungen verwenden. Dieser Zustand wird als "Inseln"-Modus bezeichnet, da der Kommunikationsverkehr für Skype for Business und Teams getrennt bleibt (auch für denselben Benutzer) und die beiden verschiedenen Clients nie miteinander kommunizieren (für Benutzer innerhalb der gleichen Organisation). Nehmen Sie beispielsweise an, dass der Empfänger Benutzer A sich im Modus "Inseln" befindet:

- Die Kommunikation, die über den Skype for Business-Client eines anderen Benutzers initiiert wird, landet immer im Skype for Business-Client von User A.

- Die Kommunikation, die vom Team-Client eines anderen Benutzers initiiert wird, landet immer im Team-Client von User A, *Wenn sich der andere Benutzer in derselben Organisation befindet*. 

- Die Kommunikation, die vom Team-Client eines anderen Benutzers initiiert wird, landet immer im Skype for Business-Client von Benutzer A, *Wenn sich der andere Benutzer in einer Verbundorganisation befindet*.

Der Modus "Inseln" ist der Standardmodus von TeamsUpgradePolicy für jede vorhandene Organisation, die noch nicht auf TeamsOnly aktualisiert wurde. Wenn Sie eine Microsoft 365-oder Office 365-Lizenz zuweisen, werden standardmäßig beide Teams und Skype for Business Online-Lizenzen zugewiesen. (Dies gilt auch, wenn der Benutzer lokal in Skype for Business Server verwaltet wird. Unabhängig davon, ob der Benutzer lokal oder Online ist, lassen Sie die Skype for Business Online-Lizenz aktiviert, da Sie zurzeit für die vollständige Team Funktionalität erforderlich ist.) Wenn Sie zum Ändern der Standardkonfiguration noch keine Schritte unternommen haben, verfügen Sie möglicherweise bereits über eine beträchtliche Nutzung der Teams in Ihrer Organisation.  Dies ist einer der Vorteile des überlappenden Funktionen-Ansatzes. Es ermöglicht eine schnelle, Endnutzer gesteuerte Einführung innerhalb einer Organisation.

Damit diese Methode effektiv funktioniert, müssen alle Benutzer beide Clients gleichzeitig ausführen. Eingehende Chats und Anrufe innerhalb des Unternehmens an einen Benutzer im Inseln-Modus können entweder in den Skype for Business-oder Microsoft Teams-Client landen – und dies steht nicht unter der Kontrolle des Empfängers. Wenn sich der Absender und der Empfänger in derselben Organisation befinden, hängt dies davon ab, welchen Client der Absender zum Initiieren der Kommunikation verwendet. Wenn sich der Absender und der Empfänger in verschiedenen Organisationen befinden, sind eingehende Anrufe und Chats an einen Benutzer im Inseln-Modus immer im Skype for Business-Client zu Lande.  

Wenn beispielsweise ein Empfänger im Modus "Inseln" Skype for Business ausführt, aber keine Teams, und jemand in der gleichen Organisation ihn aus Teams Nachrichten kann, wird die Nachricht vom Empfänger im Modus "Inseln" nicht angezeigt (aber letztendlich erhalten Sie eine e-Mail, die besagt, dass Sie eine Nachricht in Teams verpasst haben). Wenn ein Benutzer Teams ausführt, aber nicht Skype for Business, und jemand diesen Nutzer von Skype for Business Nachrichten kann, wird dieser Chat dem Nutzer nicht angezeigt.  Sie erhalten eine e-Mail, die besagt, dass eine Nachricht verpasst wurde. Das Verhalten in jedem dieser Fälle ist für den Aufruf ähnlich. Wenn Benutzer nicht beide Clients ausführen, kann dies problemlos zu Frustration führen.

Wenn sich Benutzer a im Modus "Inseln" befindet, ist die Anwesenheit von Benutzer a, wie Sie von anderen Benutzern in Teams und in Skype for Business angezeigt wird, unabhängig:

- Andere Benutzer sehen bei der Verwendung von Teams die Anwesenheitsinformationen auf der Grundlage der Aktivitäten von Benutzer A in Teams. 
- Andere Benutzer können bei Verwendung von Skype for Business die Anwesenheitsinformationen auf der Grundlage der Aktivitäten von Benutzer A in Skype for Business sehen. 

Dies bedeutet, dass andere Benutzer möglicherweise unterschiedliche Anwesenheitsstatus für Benutzer A sehen, je nachdem, welchen Client Sie verwenden. Weitere Informationen finden Sie unter [Anwesenheits](upgrade-to-teams-on-prem-coexistence.md#presence)Informationen.

Wenn Sie bereit sind, Benutzer auf den TeamsOnly-Modus zu aktualisieren, können Sie Benutzer einzeln aktualisieren oder den gesamten Mandanten mithilfe der Mandanten weiten Richtlinie auf einmal aktualisieren. Sobald ein Benutzer auf den TeamsOnly-Modus aktualisiert wurde, erhalten alle eingehenden Chats und Anrufe in Teams. (Beachten Sie, dass die Migration von Skype for Business-Besprechungen in Teams-Besprechungen nur ausgelöst wird, wenn TeamsUpgradePolicy auf einzelne Benutzer angewendet wird, nicht auf Mandantenbasis. Details finden Sie unter [Besprechungs Migration](upgrade-to-teams-on-prem-tools.md#meeting-migration) .)

Nicht aktualisierte Empfänger im Inseln-Modus können jedoch weiterhin Chats und Anrufe von einem TeamsOnly-Benutzer in Ihren Skype for Business-oder Microsoft Teams-Clients empfangen.  Der Grund dafür ist, dass der Team-Client getrennte Konversations Threads für Teams-zu-Teams und Teams-zu-Skype for Business-Kommunikation verwaltet, selbst für denselben Benutzer.  (Siehe [Teams-Unterhaltungen – Interop versus native Threads](upgrade-to-teams-on-prem-coexistence.md#teams-conversations---interop-versus-native-threads).)  Nehmen Sie beispielsweise an, dass die Inseln-Benutzer a Teams für die Nachricht TeamsOnly Benutzer B verwendet. Wenn Benutzer B auf diesen Chat antwortet, landet die Kommunikation im Team-Client von Benutzer A. Nehmen Sie nun an, dass Benutzer a seinen Skype for Business-Client verwendet, um Nachrichten TeamsOnly Benutzer b. Benutzer b den Chat in Teams zu empfangen, aber dies ist eine separate Unterhaltung im Team-Client von Benutzer b im Vergleich zu den anderen Unterhaltungen. Wenn Benutzer B auf diese Unterhaltung mit Benutzer a antwortet, landet Sie im Skype for Business-Client von Benutzer a. 

In der folgenden Tabelle sind die Teams im Modus "Inseln" und im TeamsOnly-Modus zusammengefasst:  

| Teams-Erfahrung | Im Modus "Inseln" | Im TeamsOnly-Modus |
|:------------------ | :------------------- | :------------------ |
| Eingehende Chats und eingegangene Anrufe in:|  Teams oder Skype for Business | Teams |
| Empfangene PSTN-Anrufe: | Skype for Business <br>(Die Verwendung der PSTN-Funktionalität in Teams wird im Modus "Inseln" nicht unterstützt.)    | Teams |   
 |Anwesenheit  | Die Anwesenheit in Skype for Business und Teams ist unabhängig. Benutzer können je nach verwendetem Client unterschiedliche Zustände für denselben Inseln-Benutzer sehen. | Der Anwesenheitsstatus basiert ausschließlich auf der Aktivität des Benutzers in Teams. Alle anderen Benutzer, unabhängig davon, welchen Client Sie verwenden, sehen diesen Anwesenheitsstatus. | 
 | Besprechungsplanung   | Standardmäßig können Benutzer Besprechungen entweder in Teams oder in Skype for Business planen. Beide Add-Ins werden in Outlook angezeigt. |   Benutzer planen nur Besprechungen in Teams. In Outlook steht nur das Team-Add-in zur Verfügung. | 

In der folgenden Tabelle werden die vor-und Nachteile der Verwendung der überlappenden Funktionen-Methode zum Migrieren Ihrer Organisation zu Teams zusammengefasst.

| Experten     |       Nachteile |
| :------------------ | :---------------- |
| Ermöglicht eine schnelle Einführung in einem Unternehmen.| Potenzielle Verwirrung für Endbenutzer, da zwei Clients mit ähnlicher Funktionalität, aber unterschiedliche Benutzeroberflächen vorhanden sind. Darüber hinaus haben Sie keine Kontrolle darüber, in welchem Client die eingehenden Chats/Anrufe landen. |
| Ermöglicht Benutzern, Teams zu lernen und sich mit Ihnen vertraut zu machen, während Sie weiterhin vollen Zugriff auf Skype for Business haben. | Potenzielle Endbenutzer-Unzufriedenheit aufgrund verpasster Nachrichten, wenn der Benutzer nicht beide Clients ausführt. Benutzer können beklagen, dass Sie keine Nachrichten erhalten.|
| Minimaler Verwaltungsaufwand für den Einstieg in Teams. | Kann schwierig sein, den Modus "aus den Inseln zu verlassen" und in den TeamsOnly-Modus zu wechseln, wenn nicht jeder in der Organisation Teams verwendet, besonders, wenn nicht alle Benutzer in Teams aktiv sind. Wenn beispielsweise eine Teilmenge der Benutzer auf den TeamsOnly-Modus aktualisiert wird, senden diese Benutzer nur Teams. Für die restliche Bevölkerung im Inseln-Modus landen diese Nachrichten immer in Teams. Wenn aber einige dieser Personen keine Teams ausführen, werden diese Nachrichten als verpasst wahrgenommen. |
|  | Bei der Verwendung von Teams verfügen Benutzer, die über ein lokales Konto in Skype for Business Server verfügen, nicht über Interop-oder Federation-Unterstützung.  Dies kann möglicherweise Verwirrung stiften, wenn Sie über eine Mischung von Inseln-Benutzern verfügen--einige, die in Skype for Business Online und einige in Skype for Business lokal gehostet werden.   |

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>SELECT Capabilities-Methode (mit Skype for Business-Modi)

Einige Organisationen ziehen es möglicherweise vor, Ihren Endbenutzern eine einfachere und vorhersehbarere Erfahrung zu bieten, wenn Ihre Organisation von Skype for Business zu Teams wechselt. In diesem Modell verwenden IT-Administratoren einen der Skype for Business-Modi in TeamsUpgradePolicy, um explizit festzulegen, welche Benutzer vor der Migration in den TeamsOnly-Modus in Skype for Business verbleiben. Da Sie bereit sind, ausgewählte Benutzer in den TeamsOnly-Modus zu verschieben, aktualisiert der Administrator den Modus für diese Benutzer auf TeamsOnly. Während die Bereitstellung fortschreitet, werden immer mehr Benutzer von Skype for Business in den TeamsOnly-Modus gewechselt.  Während dieses Übergangs:

- Benutzer, die noch über Skype for Business verfügen, erhalten alle eingehenden Chats und Anrufe in Ihrem Skype for Business-Client, unabhängig davon, ob die Kommunikation von den Teams des anderen Benutzers oder dem Skype for Business-Client stammt. Darüber hinaus sind für diese Skype for Business-Benutzer die Funktionen für Anrufe und Chats im Teams-Client deaktiviert, um die Verwirrung des Endbenutzers zu verhindern und die ordnungsgemäße Weiterleitung zu gewährleisten. 

- Benutzer im TeamsOnly-Modus empfangen alle eingehenden Chats und Anrufe in Ihrem Teams-Client, unabhängig davon, woher die Kommunikation stammt: Teams, Skype for Business oder alle Arten von Verbundbenutzern. 

Im Gegensatz zur Insel-Methode können Skype for Business-Benutzer und TeamsOnly-Benutzer in der SELECT-Capabilities-Methode miteinander kommunizieren. Die Kommunikation zwischen einem Skype for Business-Benutzer und einem Microsoft Teams-Benutzer wird als "Interoperabilität" oder "Interop" bezeichnet. Interoperabilitäts Kommunikation ist 1:1 für Chats und Anrufe zwischen einem Benutzer in Skype for Business und einem anderen Benutzer in Microsoft Teams möglich. einige erweiterte Funktionen stehen jedoch möglicherweise nicht zur Verfügung. (Siehe [Interoperabilität](upgrade-to-teams-on-prem-coexistence.md#interoperability).) Darüber hinaus können eingeladene Benutzer immer an einer Skype for Business-oder Teams-Besprechung teilnehmen, doch müssen Sie einen Client verwenden, der dem Typ der Besprechung entspricht. Weitere Informationen finden Sie unter [Besprechungen](upgrade-to-teams-on-prem-coexistence.md#meetings).

Da sich Benutzer in einem Auswahlfunktionen-Übergang in der Regel nicht im Modus "Inseln" befinden, ist die Anwesenheit für einen Benutzer konsistent, unabhängig davon, welcher Client vom anderen Benutzer verwendet wird. Wenn sich der Benutzer in einem der Skype for Business-Modi befindet, sehen alle anderen Benutzer die Anwesenheitsinformationen auf der Grundlage der Aktivitäten dieses Benutzers in Skype for Business. Auch wenn sich ein Benutzer im TeamsOnly-Modus befindet, sehen alle anderen Benutzer die Anwesenheitsinformationen auf der Grundlage der Aktivitäten dieses Benutzers in Teams. Einzelheiten hierzu finden Sie unter [Anwesenheits](upgrade-to-teams-on-prem-coexistence.md#presence)Informationen.

Bei einer Organisation, die noch nicht mit der Verwendung von Teams begonnen hat, sollte der Administrator den Mandanten weiten Modus von Inseln in SfbWithTeamsCollab ändern. (Für Organisationen, die bereits über einige Teams verfügen, sollte der Administrator "Großvater"-Benutzer bereits in Teams aktiv sein, um sicherzustellen, dass diese Änderung nicht für Sie gilt. Ausführliche Informationen finden Sie unter [einer SELECT Capabilities-Methode für eine Organisation, die bereits Teams im Inseln-Modus verwendet](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode).)

Wenn sich der Modus von den Inseln in SfbWithTeamsCollab ändert, sieht ein Benutzer, der nie Teams verwendet hat, keinen Unterschied in der Verwendung von Skype for Business. Sollte der Benutzer jedoch mit der Verwendung von Teams beginnen, würden diese nur Funktionen wie Teams & Kanal und Dateien verfügbar gemacht. Chat, Anruf-und Besprechungsplanung stünden in Teams nicht zur Verfügung, da der Administrator Skype for Business für diese Funktionen als den gewünschten Client vorgesehen hat.  

Hinweis: Wenn der Benutzer eine Änderung von den Inseln zu einem der Skype for Business-Modi durchführt, muss der Team-Client eines anderen Benutzers, der mit dem Benutzer a kommuniziert, wissen, dass der Modus von Benutzer a geändert wurde, damit er die Kommunikation an den entsprechenden Client für Benutzer a weiterleiten kann.  Für Benutzer, die bereits systemeigene Teams-zu-Teams-Chats mit Benutzer A eingerichtet haben, kann es bis zu 36 Stunden dauern, bis sich die Teams-Clients dieser anderen Benutzer über die Änderung des Modus von den Inseln zu einem beliebigen Skype for Business-Modus bewusst sind.   Im Gegensatz dazu werden Änderungen für einen vorhandenen Benutzer in den TeamsOnly-Modus von anderen Clients innerhalb von 2 Stunden erkannt.

Wenn Administratoren bereit sind, können Sie die Chat-, Anruf-und Besprechungsplanung für einen bestimmten Benutzer in Teams auf einmal verschieben, indem Sie den Modus des Benutzers auf TeamsOnly aktualisieren.  

Alternativ kann der Administrator zunächst nur die Besprechungsplanung in Teams verschieben, während er Chat-und Anruffunktionen in Skype for Business über den SfBWithTeamsCollabAndMeetings-Modus verlässt. In diesem Modus können Organisationen zu Teams für Besprechungen wechseln – wenn Benutzer noch nicht bereit sind, in den TeamsOnly-Modus zu wechseln (in der Regel, weil zum Migrieren vorhandener PSTN-Funktionen möglicherweise mehr Zeit erforderlich ist). Dieses Übergangsszenario wird zuerst als " [Besprechungen](meetings-first.md)" bezeichnet.

In der folgenden Tabelle sind die vor-und Nachteile der Verwendung von Skype for Business-Modi als Übergangsschritt in Richtung TeamsOnly-Modus zusammengefasst.


| Experten     |       Nachteile |
| :------------------ | :---------------- |
| Vorhersehbares Routing für den Endbenutzer.  Alle Anrufe und Chats landen entweder in Skype for Business oder in Teams (aber nicht in beiden), basierend auf der Auswahl des Administrators.  | Bei Interop-Unterhaltungen fehlt die Unterstützung für Rich-Text, Dateifreigabe und Bildschirmfreigabe.  Dies kann mit on-Demand-Besprechungen funktionieren, ist aber nicht so nahtlos.  |
| Eliminieren Sie Verwirrung des Endbenutzers, da eine bestimmte Funktionalität nur in einem Client verfügbar ist.  | Benutzer können nicht beide Clients nebeneinander für denselben Funktionsumfang ausprobieren. Dies kann insbesondere dann ein Faktor sein, wenn die Benutzer den Wechsel von Skype for Business zu Teams als wichtigen Paradigmenwechsel wahrnehmen. |
| Ermöglicht die inkrementelle Einführung von Teams.  |  | |
| Der Administrator hat vollständige Kontrolle über den Übergang von Skype for Business zu Teams. |  | | 
| Ermöglicht es einer Organisation, Teams für Besprechungen zu verwenden, auch wenn Sie noch nicht bereit ist, vollständig in den TeamsOnly-Modus zu wechseln. |  | |
| Das vorhanden sein eines angegebenen Benutzers, wie er von anderen Personen angezeigt wird, ist derselbe, unabhängig davon, welchen Client er verwendet.  |  | |

## <a name="summary-of-upgrade-methods"></a>Zusammenfassung der Upgrade-Methoden

In der folgenden Tabelle sind die Upgrade-Methoden zusammengefasst:

| Überlappende Funktionen (im Modus "Inseln")     |      Auswählen von Funktionen (mit Skype for Business-Modi) |
| :------------------ | :---------------- |
| Vor dem Upgrade auf TeamsOnly müssen Benutzer beide Clients gleichzeitig ausführen, da eingehende Chats und Anrufe entweder in einem Client landen können.   | Chats und Anrufe landen nur in einem Client, basierend auf dem Modus des Empfängers. Nicht aktualisierte Benutzer können beide Clients ausführen, aber es gibt keine funktionellen Überlappungen (Anrufe und Chats sind in Teams nicht verfügbar).  Administratoren können auch steuern, ob Benutzer Besprechungen in Teams oder Skype for Business planen.   |
| Benutzer können Skype for Business und Teams nebeneinander für dieselbe Funktionalität verwenden.   | Ermöglicht Administratoren das Einführen neuer Funktionen von Teams für Endbenutzer (Teams und Kanäle), ohne dass die gleichen Funktionen wie in Skype for Business zur Verfügung stehen.   |
|Interoperabilität zwischen Skype for Business und Teams ist nicht vorhanden, während sich beide Benutzer im Inseln-Modus befinden. Sobald einige Benutzer auf TeamsOnly aktualisiert wurden, kann die Interop-Unterhaltung zwischen diesen Benutzern und anderen Benutzern auftreten, die sich noch im Inseln-Modus befinden. Der Benutzer der Inselgruppe kann sich jedoch für die Verwendung von Teams entscheiden und die Interop-Unterhaltung vermeiden. | Für die Kommunikation zwischen Skype for Business-und Microsoft Teams-Benutzern ist Interoperabilität erforderlich.   |


## <a name="related-links"></a>Verwandte Links

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Verwenden des Besprechungs Migrations Diensts (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

