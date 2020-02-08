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
ms.openlocfilehash: b9bac6ee38c166250746b6ce9f4fb48afe3cbfe2
ms.sourcegitcommit: eb2182617d8f72f8a7ea95f7af101d10c6f4e9a0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2020
ms.locfileid: "41852102"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Upgrade von Skype for Business auf Teams &mdash; für IT-Administratoren

## <a name="overview"></a>Übersicht

Bei der Aktualisierung von Skype for Business auf Teams benötigen einige Organisationen einen progressiven Rollout, der von den IT-Abteilungen geplant und verwaltet wird. Dieser Artikel richtet sich in erster Linie an IT-Administratoren in umfangreichen lokalen Organisationen, kann aber auch für einige Skype for Business Online-Organisationen gelten.  Bevor Sie diesen Artikel lesen, lesen Sie [Erste Schritte mit Ihrem Team-Upgrade](upgrade-start-here.md) und [das Upgrade-Framework](upgrade-framework.md).

>[!NOTE]
>In diesem Artikel werden die Begriffe Skype for Business Online, Skype for Business lokal und Skype for Business verwendet.  Der letzte Ausdruck bezieht sich auf sowohl online als auch lokale Versionen.

Ein Benutzer, der in Teams migriert wurde, verwendet keinen Skype for Business-Client mehr, es sei denn, Sie nehmen an einer in Skype for Business gehosteten Besprechung Teil.  Alle eingehenden Chats und Anrufe landen im Team-Client des Benutzers, unabhängig davon, ob der Absender Teams oder Skype for Business verwendet. Alle neuen Besprechungen, die vom migrierten Benutzer organisiert werden, werden als Teams-Besprechungen geplant. Wenn der Benutzer versucht, den Skype for Business-Client zu verwenden, wird das Initiieren von Chats und anrufen blockiert.  Allerdings kann der Benutzer den Skype for Business-Client weiterhin verwenden, um an Besprechungen teilzunehmen, zu denen er eingeladen wurde. (Ältere Skype for Business-Clients, die vor 2017 ausgeliefert wurden, Ehren TeamsUpgradePolicy nicht. Stellen Sie sicher, dass Sie den neuesten Skype for Business-Client verwenden.)
 
Administratoren verwalten Ihren Übergang zu Teams mithilfe des Konzepts des [Modus](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes), bei dem es sich um eine Eigenschaft von [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)handelt. Ein Benutzer, der wie oben beschrieben zu Teams migriert wurde, befindet sich im Modus "TeamsOnly".  Für eine Organisation, die zu Teams migriert, besteht das ultimative Ziel darin, alle Benutzer in den TeamsOnly-Modus zu verschieben.

Es gibt zwei Methoden zum Migrieren einer vorhandenen Organisation mit Skype for Business (ob online oder lokal) in Teams:

- Über **Lapp Ende Capabilities-Methode** (im Modus "Inseln"): Benutzer in einer vorhandenen Skype for Business-Organisation werden in Teams eingeführt, damit Sie beide Clients während einer Übergangsphase verwenden können. In diesem Zeitraum stehen Ihnen die meisten--aber nicht alle--Funktionen von Teams zur Verfügung. Der Modus für diese Konfiguration wird als "Inseln" bezeichnet, und dies ist der Standardmodus für jede vorhandene Organisation mit Skype for Business. Sobald die Organisation fertig ist, verschiebt der Administrator die Benutzer in den TeamsOnly-Modus.

- **Wählen Sie** die Funktion Funktionen (mit einem oder mehreren Skype for Business-Modi): der Administrator verwaltet den Übergang (von Skype for Business zu Teams) von Chat-, Anruf-und Besprechungs Planungsfunktionen für Benutzer in Ihrer Organisation.  Jede dieser Funktionen steht entweder in Skype for Business oder in Teams zur Verfügung, aber nicht in beiden. Administratoren verwenden TeamsUpgradePolicy, um zu steuern, wann diese Funktionalität für Ihre Benutzer in Teams verschoben werden soll. Benutzer, die noch nicht im TeamsOnly-Modus sind, verwenden weiterhin Skype for Business für Chats und Anrufe, und die beiden Benutzergruppen können über die Interop-Funktionalität kommunizieren. Administratoren verwalten den Übergang, indem Sie schrittweise mehr Benutzer in den TeamsOnly-Modus migrieren.  

Dieser Artikel unterstützt Sie bei der Auswahl der richtigen Methode für Ihre Organisation, indem beide Methoden beschrieben und die vor-und Nachteile der einzelnen Methoden vorgestellt werden. 

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Überlappende Capabilities-Methode (im Modus "Inseln")

Mit der überlappenden Funktionen-Methode können Benutzer sowohl Teams als auch Skype for Business-Clients für Chats, VoIP-Anrufe und Besprechungen verwenden. Dieser Zustand wird als "Inseln"-Modus bezeichnet, da der Kommunikationsverkehr für Skype for Business und Teams getrennt bleibt (auch für denselben Benutzer) und die beiden verschiedenen Clients nie miteinander kommunizieren (für Benutzer innerhalb der gleichen Organisation). Nehmen Sie beispielsweise an, dass der Empfänger Benutzer A sich im Modus "Inseln" befindet:

- Die Kommunikation, die über den Skype for Business-Client eines anderen Benutzers initiiert wird, landet immer im Skype for Business-Client von User A.
- Die Kommunikation, die vom Team-Client eines anderen Benutzers initiiert wird, landet immer im Team-Client von User A, *Wenn sich der andere Benutzer in derselben Organisation befindet*. 
- Die Kommunikation, die vom Team-Client eines anderen Benutzers initiiert wird, landet immer im Skype for Business-Client von Benutzer A, *Wenn sich der andere Benutzer in einer Verbundorganisation befindet*.

Der Modus "Inseln" ist der Standardmodus von TeamsUpgradePolicy für jede vorhandene Organisation, die noch nicht TeamsOnly ist. Wenn Sie eine Office 365-Lizenz zuweisen, werden standardmäßig beide Teams und Skype for Business Online-Lizenzen zugewiesen. (Dies gilt auch, wenn der Benutzer lokal in Skype for Business Server verwaltet wird. Unabhängig davon, ob der Benutzer lokal oder Online ist, lassen Sie die Skype for Business Online-Lizenz aktiviert, da Sie zurzeit für die vollständige Team Funktionalität erforderlich ist.) Wenn Sie zum Ändern der Standardkonfiguration noch keine Schritte unternommen haben, verfügen Sie möglicherweise bereits über eine beträchtliche Nutzung der Teams in Ihrer Organisation.  Dies ist einer der Vorteile des überlappenden Funktionen-Ansatzes. Es ermöglicht eine schnelle, Endnutzer gesteuerte Einführung innerhalb einer Organisation.

Damit diese Methode effektiv funktioniert, müssen alle Benutzer beide Clients gleichzeitig ausführen. Eingehende Chats und Anrufe innerhalb des Unternehmens an einen Benutzer im Inseln-Modus können entweder in den Skype for Business-oder Microsoft Teams-Client landen – und dies steht nicht unter der Kontrolle des Empfängers. Dies hängt davon ab, welchen Client der Absender zum Initiieren der Kommunikation verwendet. Wenn sich der Absender und der Empfänger in verschiedenen Organisationen befinden, sind eingehende Anrufe und Chats an einen Benutzer im Inseln-Modus immer im Skype for Business-Client zu Lande.  

Wenn beispielsweise ein Empfänger im Modus "Inseln" Skype for Business ausführt, aber keine Teams, und jemand Sie aus Teams Nachrichten kann, wird die Nachricht vom Empfänger im Modus "Inseln" nicht angezeigt (aber letztendlich erhalten Sie eine e-Mail, die besagt, dass Sie eine Nachricht in Teams verpasst haben). Wenn ein Benutzer Teams ausführt, aber nicht Skype for Business, und jemand diesen Nutzer von Skype for Business Nachrichten kann, wird dieser Chat dem Nutzer nicht angezeigt.  Sie erhalten eine e-Mail, die besagt, dass eine Nachricht verpasst wurde. Das Verhalten in jedem dieser Fälle ist für den Aufruf ähnlich. Wenn Benutzer nicht beide Clients ausführen, kann dies problemlos zu Frustration führen.

Wenn sich Benutzer a im Modus "Inseln" befindet, ist die Anwesenheit von Benutzer a, wie Sie von anderen Benutzern in Teams und in Skype for Business angezeigt wird, unabhängig:

- Andere Benutzer sehen bei der Verwendung von Teams die Anwesenheitsinformationen auf der Grundlage der Aktivitäten von Benutzer A in Teams. 
- Andere Benutzer können bei Verwendung von Skype for Business die Anwesenheitsinformationen auf der Grundlage der Aktivitäten von Benutzer A in Skype for Business sehen. 

Dies bedeutet, dass andere Benutzer möglicherweise unterschiedliche Anwesenheitsstatus für Benutzer A sehen, je nachdem, welchen Client Sie verwenden. Weitere Informationen finden Sie unter [Anwesenheits](#presence)Informationen.

Wenn Sie bereit sind, Benutzer auf den TeamsOnly-Modus zu aktualisieren, können Sie Benutzer einzeln aktualisieren oder den gesamten Mandanten mithilfe der Mandanten weiten Richtlinie auf einmal aktualisieren. Sobald ein Benutzer auf den TeamsOnly-Modus aktualisiert wurde, erhalten alle eingehenden Chats und Anrufe in Teams. (Beachten Sie, dass die Migration von Skype for Business-Besprechungen in Teams-Besprechungen nur ausgelöst wird, wenn TeamsUpgradePolicy auf einzelne Benutzer angewendet wird, nicht auf Mandantenbasis. Details finden Sie unter [Besprechungs Migration](#meeting-migration) .)

Nicht aktualisierte Empfänger im Inseln-Modus können jedoch weiterhin Chats und Anrufe von einem TeamsOnly-Benutzer in Ihren Skype for Business-oder Microsoft Teams-Clients empfangen.  Der Grund dafür ist, dass der Team-Client getrennte Konversations Threads für Teams-zu-Teams und Teams-zu-Skype for Business-Kommunikation verwaltet, selbst für denselben Benutzer.  (Siehe [Teams-Unterhaltungen – Interop versus native Threads](#teams-conversations---interop-versus-native-threads).)  Nehmen Sie beispielsweise an, dass die Inseln-Benutzer a Teams für die Nachricht TeamsOnly Benutzer B verwendet. Wenn Benutzer B auf diesen Chat antwortet, landet die Kommunikation im Team-Client von Benutzer A. Nehmen Sie nun an, dass Benutzer a seinen Skype for Business-Client verwendet, um Nachrichten TeamsOnly Benutzer b. Benutzer b den Chat in Teams zu empfangen, aber dies ist eine separate Unterhaltung im Team-Client von Benutzer b im Vergleich zu den anderen Unterhaltungen. Wenn Benutzer B auf diese Unterhaltung mit Benutzer a antwortet, landet Sie im Skype for Business-Client von Benutzer a. 

In der folgenden Tabelle sind die Teams im Modus "Inseln" und im TeamsOnly-Modus zusammengefasst:  

| Teams-Erfahrung | Im Modus "Inseln" | Im TeamsOnly-Modus |
|:------------------ | :------------------- | :------------------ |
| Eingehende Chats und eingegangene Anrufe in:|  Teams oder Skype for Business | Teams |
| Empfangene PSTN-Anrufe: | Skype for Business <br>(Die Verwendung der PSTN-Funktionalität in Teams wird im Modus "Inseln" nicht unterstützt.)    | Teams |   
 |Anwesenheit  | Die Anwesenheit in Skype for Business und Teams ist unabhängig. Benutzer können je nach verwendetem Client unterschiedliche Zustände für denselben Inseln-Benutzer sehen. | Der Anwesenheitsstatus basiert ausschließlich auf der Aktivität des Benutzers in Teams. Alle anderen Benutzer, unabhängig davon, welchen Client Sie verwenden, sehen diesen Anwesenheitsstatus. | 
 | Besprechungsplanung   | Benutzer können Besprechungen entweder in Teams oder in Skype for Business planen. Beide Add-Ins werden in Outlook angezeigt. |   Benutzer planen nur Besprechungen in Teams. In Outlook steht nur das Team-Add-in zur Verfügung. | 

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

Im Gegensatz zur Insel-Methode können Skype for Business-Benutzer und TeamsOnly-Benutzer in der SELECT-Capabilities-Methode miteinander kommunizieren. Die Kommunikation zwischen einem Skype for Business-Benutzer und einem Microsoft Teams-Benutzer wird als "Interoperabilität" oder "Interop" bezeichnet. (Siehe [Interoperabilität](#interoperability).) Interoperabilitäts Kommunikation ist 1:1 für Chats und Anrufe zwischen einem Benutzer in Skype for Business und einem anderen Benutzer in Microsoft Teams möglich. Darüber hinaus können eingeladene Benutzer immer an einer Skype for Business-oder Teams-Besprechung teilnehmen, doch müssen Sie einen Client verwenden, der dem Typ der Besprechung entspricht. Weitere Informationen finden Sie unter [Besprechungen](#meetings).

Da sich Benutzer in einem Auswahlfunktionen-Übergang in der Regel nicht im Modus "Inseln" befinden, ist die Anwesenheit für einen Benutzer konsistent, unabhängig davon, welcher Client vom anderen Benutzer verwendet wird. Wenn sich der Benutzer in einem der Skype for Business-Modi befindet, sehen alle anderen Benutzer die Anwesenheitsinformationen auf der Grundlage der Aktivitäten dieses Benutzers in Skype for Business. Auch wenn sich ein Benutzer im TeamsOnly-Modus befindet, sehen alle anderen Benutzer die Anwesenheitsinformationen auf der Grundlage der Aktivitäten dieses Benutzers in Teams. Einzelheiten hierzu finden Sie unter [Anwesenheits](#presence)Informationen.

Bei einer Organisation, die noch nicht mit der Verwendung von Teams begonnen hat, sollte der Administrator den Mandanten weiten Modus von Inseln in SfbWithTeamsCollab ändern. (Für Organisationen, die bereits über einige Teams verfügen, sollte der Administrator "Großvater"-Benutzer bereits in Teams aktiv sein, um sicherzustellen, dass diese Änderung nicht für Sie gilt. Ausführliche Informationen finden Sie unter [Upgrade für ausgewählte Funktionen für eine Organisation, die bereits Teams im Inseln-Modus verwendet](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode).)

Wenn sich der Modus von den Inseln in SfbWithTeamsCollab ändert, sieht ein Benutzer, der nie Teams verwendet hat, keinen Unterschied in der Verwendung von Skype for Business. Sollte der Benutzer jedoch mit der Verwendung von Teams beginnen, würden diese nur Funktionen wie Teams #a0 Kanal und Dateien verfügbar gemacht. Chat, Anruf-und Besprechungsplanung stünden in Teams nicht zur Verfügung, da der Administrator Skype for Business für diese Funktionen als den gewünschten Client vorgesehen hat.  

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

## <a name="tools-for-managing-the-upgrade"></a>Tools für die Verwaltung des Upgrades

Für eine der oben beschriebenen Methoden verwalten Administratoren den Übergang zu TeamsOnly mithilfe von [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), der den Koexistenzmodus eines Benutzers steuert. Weitere Informationen zu den einzelnen Modi finden Sie unter [Koexistenz Modi](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes).

Unabhängig davon, ob der Administrator einen Auswahlfunktionen-Übergang mithilfe von Skype for Business-Modi ausführt oder einfach von der Standardkonfiguration der Inseln auf den TeamsOnly-Modus wechselt, ist TeamsUpgradePolicy das wichtigste Tool.  Wie bei jeder anderen Richtlinie in Microsoft Teams kann TeamsUpgradePolicy einem Benutzer direkt zugewiesen werden, und er kann auch als Mandantenweite Standardeinstellung eingestellt werden. Jede Zuordnung zu einem Benutzer hat Vorrang vor der Standardeinstellung Mandanten.  Sie kann sowohl in der Team-Admin-Konsole als auch in PowerShell verwaltet werden.

Administratoren können Benutzern jede Art von TeamsUpgradePolicy zuweisen, unabhängig davon, ob sich der Benutzer in Skype for Business Online oder lokal befindet, mit der Ausnahme, dass der TeamsOnly-Modus nur einem Nutzer zugewiesen werden kann, der bereits in Skype for Business Online ist. Dies liegt daran, dass Interop mit Skype for Business-Benutzern und-Föderationen nur möglich ist, wenn der Benutzer in Skype for Business Online verwaltet wird.

Benutzer mit Skype for Business-Konten, die sich lokal [benetzen, müssen](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) mit Move-CsUser im lokalen Skype for Business-Toolset Online (entweder in Skype for Business Online oder direkt an Teams) verschoben werden. Diese Benutzer können in 1 oder 2 Schritten in TeamsOnly verschoben werden:

-   1 Schritt: Geben Sie den Schalter-MoveToTeams in Move-CsUser an. Hierfür ist Skype for Business Server 2019 oder Skype for Business Server 2015 mit CU8 erforderlich.

-   2 Schritte: Nachdem Sie Move-CsUser ausgeführt haben, gewähren Sie dem Benutzer den TeamsOnly-Modus mithilfe von TeamsUpgradePolicy.

Im Gegensatz zu anderen Richtlinien ist es nicht möglich, neue Instanzen von TeamsUpgradePolicy in Office 365 zu erstellen. Alle vorhandenen Instanzen sind in den Dienst integriert.  (Beachten Sie, dass Mode eine Eigenschaft in TeamsUpgradePolicy und nicht der Name einer Richtlinieninstanz ist.) In einigen-aber nicht in allen Fällen ist der Name der Richtlinieninstanz derselbe wie der Modus. Um einem Benutzer den TeamsOnly-Modus zuzuweisen, erteilen Sie diesem Benutzer die Instanz "UpgradeToTeams" von TeamsUpgradePolicy. Um eine Liste aller Instanzen anzuzeigen, können Sie den folgenden Befehl ausführen:

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

Wenn Sie einen Online Benutzer auf den TeamsOnly-Modus aktualisieren möchten, weisen Sie die "UpgradeToTeams"-Instanz zu: 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

Um einen lokalen Skype for Business-Benutzer in den TeamsOnly-Modus zu aktualisieren, verwenden Sie Move-CsUser im lokalen Toolset:

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

Führen Sie den folgenden Befehl aus, um den Modus für alle Benutzer im Mandanten zu ändern, mit Ausnahme derjenigen, die über eine explizite pro-Benutzer-Grant (die Vorrang hat) verfügen:

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Wenn Sie Benutzer mit Skype for Business-Konten lokal haben, sollten Sie den TeamsOnly-Modus nicht auf Mandantenebene zuweisen, es sei denn, Sie weisen allen Benutzern mit lokalen Skype for Business-Konten explizit einen anderen Modus zu.


### <a name="using-notifications-in-skype-for-business-clients"></a>Verwenden von Benachrichtigungen in Skype for Business-Clients

Administratoren können im Skype for Business-Clientbenachrichtigungen für Endbenutzer bereitstellen, um die Benutzer darüber zu informieren, dass Sie in Kürze auf Teams aktualisiert werden, wie in der nachstehenden Abbildung zu sehen ist. Wenn beispielsweise eine Woche vor dem Administrator die Aktualisierung einer Gruppe von Benutzern auf den TeamsOnly-Modus plant, möchte der Administrator diese Benachrichtigungen für diese Benutzergruppe aktivieren. Diese Benachrichtigungen werden mit einer Instanz von TeamsUpgradePolicy mit NotifySfbUsers = true aktiviert.  Für alle anderen Modi als TeamsOnly gibt es tatsächlich zwei Instanzen pro Modus, die den beiden Werten von NotifySfbUsers entsprechen.  Für alle anderen Modi als TeamsOnly gibt es tatsächlich zwei Instanzen pro Modus, die den beiden Werten von NotifySfbUsers entsprechen. 

![Diagramm mit Benachrichtigungen](media/teams-upgrade-sfb-with-notifications.png)

Wenn Ihre Benutzer in Skype for Business online gehostet werden, weisen Sie einfach die Richtlinieninstanz zu, die den gleichen Modus wie der Benutzer hat, aber mit NotifySfbUsers = true. 

Wenn Ihre Benutzer in Skype for Business Server lokal gehostet werden, müssen Sie das lokale Toolset verwenden, und Sie benötigen Skype for Business Server 2019 oder CU8 für Skype for Business Server 2015. Erstellen Sie im lokalen PowerShell-Fenster eine neue Instanz von TeamsUpgradePolicy mit NotifySfbUsers = true:

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

Weisen Sie dann mithilfe desselben lokalen PowerShell-Fensters die neue Richtlinie den gewünschten Benutzern zu:

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

### <a name="meeting-migration"></a>Besprechungs Migration

Wenn ein Benutzer in den TeamsOnly-Modus migriert wird, werden die vorhandenen Skype for Business-Besprechungen, die Sie organisiert haben, standardmäßig in Teams konvertiert. Sie können das Standardverhalten beim Zuweisen des TeamsOnly-Modus zu einem Benutzer optional deaktivieren. Beim Verschieben von Benutzern aus dem lokalen Bereich müssen Besprechungen in die Cloud migriert werden, damit Sie mit dem Online Benutzerkonto funktionieren, aber wenn Sie MoveToTeams nicht angeben, werden die Besprechungen als Skype for Business-Besprechungen migriert und nicht in Teams konvertiert. 

Wenn Sie den TeamsOnly-Modus auf Mandantenebene zuweisen, wird die Besprechungs Migration für keine Benutzer ausgelöst. Wenn Sie den TeamsOnly-Modus auf Mandantenebene zuweisen und Besprechungen migrieren möchten, können Sie mithilfe von PowerShell eine Liste der Benutzer im Mandanten abrufen (beispielsweise die Verwendung von Get-CsOnlineUser mit den benötigten Filtern) und dann jeden dieser Benutzer durchlaufen, um eine Besprechung auszulösen. Migration mithilfe von Start-CsExMeetingMigration. Ausführliche Informationen finden Sie unter [Verwenden des Besprechungs Migrations Diensts (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).


### <a name="additional-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Weitere Überlegungen für Organisationen mit Skype for Business Server lokal

- Das Einrichten von Skype for Business-Hybriden ist eine Voraussetzung für die Migration in den TeamsOnly-Modus. Obwohl es möglich ist, Teams im Modus "Inseln" ohne Hybrid zu verwenden, kann der Übergang in den TeamsOnly-Modus erst dann erfolgen, wenn der Benutzer von Skype for Business lokal zu Skype for Business Online (mit [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)) verschoben wird. Weitere Informationen finden Sie unter [Konfigurieren der Hybrid Konnektivität](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).

- Benutzer von Teams, die ein Skype for Business-Konto lokal haben (das heißt, dass Sie mit Move-CsUser noch nicht in die Cloud verschoben wurden), können nicht mit Skype for Business-Benutzern zusammenarbeiten und können auch nicht mit externen Benutzern zusammenarbeiten. Diese Funktion steht nur zur Verfügung, wenn die Benutzer in die Cloud verschoben werden (entweder im Modus "Inseln" oder als TeamsOnly-Benutzer). 

- Wenn Sie Benutzer mit Skype for Business-Konten lokal haben, sollten Sie den TeamsOnly-Modus nicht auf Mandantenebene zuweisen, es sei denn, Sie weisen allen Benutzern mit lokalen Skype for Business-Konten explizit einen anderen Modus zu. 

- Sie müssen sicherstellen, dass Ihre Benutzer mit den korrekten Skype for Business-Attributen richtig in Azure AD synchronisiert sind. Diese Attribute sind alle Präfixe mit "Attribut msRTCSIP-". Wenn Benutzer nicht ordnungsgemäß mit Azure AD synchronisiert werden, können die Verwaltungstools in Microsoft Teams diese Benutzer nicht verwalten. Weitere Informationen finden Sie unter [Konfigurieren von Azure AD Connect für Teams und Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).

- Wenn Sie einen neuen TeamsOnly-oder Skype for Business Online-Benutzer in einer Hybrid Organisation erstellen möchten, *müssen Sie zunächst den Benutzer in Skype for Business Server lokal aktivieren*und den Benutzer dann mithilfe von Move-CsUser von lokal in die Cloud verschieben.  Durch das Erstellen des Benutzers im lokalen Bereich wird zunächst sichergestellt, dass andere verbleibende lokale Skype for Business-Benutzer an den neu erstellten Benutzer weiterleiten können. Nachdem alle Benutzer online verschoben wurden, ist es nicht mehr notwendig, Benutzer zunächst lokal zu aktivieren.

- Wenn ein Benutzer von lokal in die Cloud verschoben wird, werden Besprechungen, die von diesem Benutzer organisiert werden, entweder in Skype for Business Online oder in Teams migriert – je nachdem, ob der-MoveToTeams-Schalter angegeben ist.

- Wenn Sie Benachrichtigungen im Skype for Business-Client für lokale Benutzer anzeigen möchten, müssen Sie im lokalen Toolset TeamsUpgradePolicy verwenden. Nur der NotifySfbUsers-Parameter ist für lokale Benutzer relevant.  Lokale Benutzer erhalten Ihren Modus aus den Online Instanzen von TeamsUpgradePolicy. Sehen Sie sich die Notizen in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). 

>[!NOTE]
> Alle neuen Mandanten, die nach dem 3. September erstellt wurden, werden als TeamsOnly-Mandanten erstellt 2019, ohne dass Administratoren eine Downgrade vornehmen können. Organisationen mit Skype for Business Server lokal, die zuvor nie ein Office 365-Abonnement vor dem 3. September hatten, 2019 müssen sich an den Microsoft-Support wenden, damit Ihr Mandant heruntergestuft wird, nachdem Sie ein Abonnement mit Office 365 erworben haben. 


## <a name="perform-the-upgrade-for-your-organization"></a>Durchführen des Upgrades für Ihre Organisation

In diesem Abschnitt werden die folgenden Aktualisierungsoptionen beschrieben:

- Überlappende Funktionen Upgrade (im Modus "Inseln")
- Ein Upgrade der Auswahlfunktionen für eine Organisation, die noch nicht mit der Verwendung von Teams begonnen hat
- Ein Upgrade der Auswahlfunktionen für eine Organisation, die bereits Teams im Inseln-Modus verwendet

### <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>Überlappende Funktionen Upgrade (im Modus "Inseln")

Für die Option zum überlappenden Funktions Upgrade:

- Bedenken Sie diese Option, wenn Sie ein schnelles Upgrade für Ihre gesamte Organisation durchführen können.  Da bei der Ausführung beider Clients potenzielle Verwirrung besteht, ist es am besten, wenn Sie diesen Zeitraum minimieren können. Sie sollten sicherstellen, dass Ihre Benutzer wissen, dass beide Clients ausgeführt werden.

- Bei dieser Option handelt es sich um das Out-of-the-Box-Modell, das keine Administratoraktion erfordert, um mit Teams zu beginnen, es sei denn, Sie weisen die Office 365-Lizenz zu. Wenn Ihre Benutzer bereits über Skype for Business Online verfügen, sind Sie möglicherweise bereits in diesem Modell.

- Es kann schwierig sein, den überlappenden Funktionsmodus zu verlassen und zu TeamsOnly zu wechseln. Da aktualisierte Benutzer nur über Teams kommunizieren, müssen alle anderen Benutzer in der Organisation, die mit diesem Benutzer kommunizieren, Teams verwenden.  Wenn Sie über Benutzer verfügen, die nicht mit der Verwendung von Teams begonnen haben, werden Sie fehlenden Nachrichten ausgesetzt. Darüber hinaus werden die TeamsOnly-Benutzer in Skype for Business nicht online angezeigt. Einige Unternehmen entscheiden sich für ein mandantenweites Upgrade mithilfe der globalen Mandanten Richtlinie, um dies zu vermeiden, allerdings erfordert das warten, bis alle Benutzer zum Upgrade bereit sind.


### <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Ein Upgrade der Auswahlfunktionen für eine Organisation, die noch nicht mit der Verwendung von Teams begonnen hat

Wenn in Ihrer Organisation noch keine aktiven Benutzer in Teams vorhanden sind, besteht der erste Schritt darin, die standardmäßige Mandantenweite Richtlinie für TeamsUpgradePolicy auf einen der Skype for Business-Modi zu setzen, beispielsweise SfbWithTeamsCollab.  Benutzer, die noch nicht mit der Verwendung von Teams begonnen haben, bemerken keinen Unterschied im Verhalten. Durch das Festlegen dieser Richtlinie auf Mandantenebene ist es jedoch möglich, Benutzer auf den TeamsOnly-Modus zu aktualisieren und sicherzustellen, dass die aktualisierten Benutzer weiterhin mit nicht aktualisierten Benutzern kommunizieren können.  Nachdem Sie Ihre Pilotbenutzer identifiziert haben, können Sie Sie auf TeamsOnly aktualisieren.  Wenn Sie lokal sind, verwenden Sie Move-CsUser. Wenn Sie online sind, weisen Sie Ihnen einfach den TeamsOnly-Modus mithilfe von TeamsUpgradePolicy zu.  Standardmäßig werden alle von diesen Benutzern geplanten Skype for Business-Besprechungen in Teams migriert.

Im folgenden finden Sie die wichtigsten Befehle:

1. Setzen Sie die Mandantenweite Standardeinstellung auf Mode SfbWithTeamsCollab wie folgt:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. Aktualisieren Sie den Benutzer wie folgt auf TeamsOnly:

   - Wenn der Benutzer bereits online ist:

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - Wenn der Benutzer lokal ist:

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

Hinweise
 
- Anstatt die Mandantenweite Richtlinie auf "SfbWithTeamsCollab" festzulegen, können Sie Sie auf "SfbWithTeamsCollabAndMeetings" festlegen. Dies bewirkt, dass alle Benutzer alle neuen Besprechungen in Teams planen.
- Move-CsUser ist ein Cmdlet in den lokalen Tools. Für den MoveToTeams-Switch ist Skype for Business Server 2019 oder Skype for Business Server 2015 mit CU8 erforderlich. Wenn Sie eine frühere Version verwenden, können Sie den Benutzer zunächst in Skype for Business Online verschieben und dann dem Benutzer den TeamsOnly-Modus erteilen.
- Standardmäßig werden Skype for Business-Besprechungen in Teams migriert, wenn Sie auf den TeamsOnly-Modus aktualisieren oder den SfbWithTeamsCollabAndMeetings-Modus zuweisen.  

Das folgende Diagramm zeigt die konzeptionellen Phasen des Upgrades von SELECT-Funktionen für eine Organisation ohne vorherige Verwendung von Teams. Die Höhe der Balken steht für die Anzahl der Benutzer. In jeder Phase des Upgrades können alle Benutzer miteinander kommunizieren.  Skype for Business-Benutzer kommunizieren mit TeamsOnly-Benutzern über Interop und umgekehrt.

![Diagramm mit Auswahlmöglichkeiten für Upgrades ohne vorherige Verwendung von Teams](media/teams-upgrade-1.png)


### <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Ein Upgrade der Auswahlfunktionen für eine Organisation, die bereits Teams im Inseln-Modus verwendet

Wenn einige Benutzer in Ihrer Organisation Teams im Modus "Inseln" aktiv verwenden, möchten Sie möglicherweise die Funktionalität von vorhandenen Benutzern nicht entfernen. Daher ist ein zusätzlicher Schritt erforderlich, bevor die Mandantenweite Richtlinie geändert wird. Die Lösung besteht darin, diese vorhandenen aktiven Teams-Benutzer in den Modus "Inseln" zu übersetzen, bevor Sie die Mandantenweite Richtlinie auf "SfbWithTeamsCollab" festlegen.  Nachdem Sie dies abgeschlossen haben, können Sie die Bereitstellung wie oben beschrieben fortsetzen, jedoch haben Sie zwei Gruppen von Benutzern, die zu TeamsOnly wechseln: die Benutzer, die in Teams aktiv waren, befinden sich im Modus "Inseln", und die restlichen Benutzer befinden sich im SfbWithTeamsCollab-Modus. Sie können diese Benutzer schrittweise in den TeamsOnly-Modus verschieben.

1. Suchen Sie nach Benutzern, die in Teams wie folgt aktiv sind:

   1. Wechseln Sie im Office 365-Administrator Portal in der linken Navigationsleiste zu Berichte, und verwenden Sie dann die Verwendung. 
   2. Wählen Sie im Dropdownmenü "Bericht auswählen" den Eintrag Microsoft Teams und dann Benutzeraktivität aus. Dadurch wird eine exportierbare Tabelle mit Benutzern bereitgestellt, die in Teams aktiv waren. 
   3. Klicken Sie auf exportieren, öffnen Sie Excel, und Filtern Sie, um nur die Benutzer anzuzeigen, die in Teams aktiv sind.

2. Weisen Sie für jeden in Schritt 1 gefundenen aktiven Teams-Benutzer den Modus "Inseln" in der Remote-PowerShell zu. So können Sie mit dem nächsten Schritt fortfahren und sicherstellen, dass Sie die Benutzeroberfläche nicht ändern.  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. Setzen Sie die Mandantenweite Richtlinie auf SfbWithTeamsCollab:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. Ausgewählte Benutzer auf den TeamsOnly-Modus aktualisieren. Sie können entweder Benutzer im Inseln-Modus oder im SfbWithTeamsCollab-Modus aktualisieren, obwohl Sie möglicherweise zuerst die Aktualisierung der Benutzer im Modus "Inseln" priorisieren möchten, um die Verwirrung zu minimieren, die entstehen kann, wenn sich Benutzer im Inseln-Modus befinden.   

   Für Benutzer, die in Skype for Business Online verwaltet werden:  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   Für Benutzer, die in Skype for Business Server lokal verwaltet werden:  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

Das folgende Diagramm zeigt die konzeptionellen Phasen eines Auswahl Funktions Übergangs, in dem am Anfang aktive Inseln-Benutzer vorhanden sind. Die Höhe der Balken steht für die Anzahl der Benutzer. In jeder Phase des Upgrades können alle Benutzer miteinander kommunizieren.  Skype for Business-Benutzer kommunizieren mit TeamsOnly-Benutzern über Interop und umgekehrt.


![Diagramm mit Auswahlmöglichkeiten für das Upgrade für aktive Benutzer im Modus "Inseln"](media/teams-upgrade-2.png)

   

## <a name="considerations-for-pstn-calling"></a>Überlegungen für PSTN-Anrufe

Wenn die PSTN-Anruf Funktionalität betroffen ist, gibt es vier mögliche Szenarien beim Umstieg auf den TeamsOnly-Modus:

- *Ein Benutzer in Skype for Business Online mit einem Microsoft-Anrufplan*. Nach dem Upgrade wird dieser Benutzer weiterhin über einen Microsoft-Anrufplan verfügen.

- *Ein Benutzer in Skype for Business Online mit lokalen Sprachfunktionen* über Skype for Business lokal oder Cloud Connector Edition. Das Upgrade des Benutzers auf Teams muss mit der Migration des Benutzers an Direct Routing koordiniert werden, um sicherzustellen, dass der TeamsOnly-Benutzer über PSTN-Funktionalität verfügt.

- *Ein Benutzer in Skype for Business lokal mit Enterprise-VoIP, der zu Online wechseln und die lokale PSTN-Konnektivität*aufrecht erhalten soll.  Wenn Sie diesen Benutzer zu Teams migrieren, muss das lokale Skype for Business-Konto des Benutzers in die Cloud verschoben und koordiniert werden, um die Migration des Benutzers zur direkten Weiterleitung zu koordinieren. 

- *Ein Benutzer in Skype for Business lokal mit Enterprise-VoIP*, der in den Online-und mit einem Microsoft-Anrufplan umziehen wird.  Das Migrieren dieses Benutzers zu Teams erfordert das Verschieben des lokalen Skype for Business-Kontos des Benutzers in die Cloud und das koordinieren dieser Bewegung mit einem) des Ports dieser Benutzer Telefonnummer zu einem Microsoft-Anrufplan oder B) Zuweisen einer neuen Teilnehmernummer von Verfügbare Regionen.

Dieser Artikel enthält nur eine allgemeine Übersicht. Weitere Informationen finden Sie unter [direkte Routing](direct-routing-landing-page.md) -und [Anrufpläne](calling-plan-landing-page.md)für Telefonsysteme. Beachten Sie außerdem, dass die Verwendung von Telefonsystemen mit Teams nur unterstützt wird, wenn sich der Benutzer im TeamsOnly-Modus befindet.  Wenn sich der Benutzer im Modus "Inseln" befindet, wird das Telefon System nur von Skype for Business unterstützt. 

### <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Von Skype for Business Online mit Microsoft-Anrufplänen 

Hierbei handelt es sich um das einfachste Upgrade-Szenario mit Sprachausgabe. 

1. Stellen Sie sicher, dass Benutzern eine Teams-Lizenz zugewiesen wurde. Wenn Sie eine Office 365-Lizenz zuweisen, werden die Teams standardmäßig aktiviert, es sei denn, Sie haben zuvor die Teams-Lizenz deaktiviert, sollte keine Aktion erforderlich sein.

2.  Wenn Benutzer bereits über einen Microsoft-Anrufplan mit einer Telefonnummer verfügen, besteht die einzige erforderliche Änderung darin, den Benutzer TeamsOnly-Modus in TeamsUpgradePolicy zuzuweisen.  Vor dem Zuweisen des TeamsOnly-Modus werden eingehende PSTN-Anrufe im Skype for Business-Client des Benutzers landen. Nach dem Upgrade auf den TeamsOnly-Modus werden eingehende PSTN-Anrufe im Team-Client des Benutzers landen.  

### <a name="from-skype-for-business-online-with-on-premises-voice"></a>Von Skype for Business Online mit Lokalsprache

In diesem Szenario befindet sich der Benutzer bereits in Skype for Business Online, seine PSTN-Konnektivität ist aber lokal, entweder mit Skype for Business Server im Hybrid Modus oder mit Cloud Connector Edition. Das Migrieren dieser Benutzer in den TeamsOnly-Modus mit PSTN-Funktionalität bedeutet, dass Sie für das direkte Routing aktiviert werden können, in dem PSTN-Trunks über Ihren lokalen Session Border Controller (SBC) direkt mit dem Direct Routing-Dienst in der Cloud verbunden sind.

Die grundlegenden Schritte sind im folgenden aufgeführt.  Die Schritte 1-4 sind in der vorgeschlagenen Reihenfolge aufgeführt, können aber in beliebiger Reihenfolge ausgeführt werden. Der Schlüssel besteht darin, dass alle diese Schritte vor Schritt 5 abgeschlossen sein sollten.

1. Wenn Sie die Mandantenweite Richtlinie auf einen der Skype for Business-Modi festlegen, sollten Sie sicherstellen, dass Sie alle vorhandenen Inseln-Benutzer übernehmen, indem Sie Ihnen, wie zuvor beschrieben, explizit den Inseln-Modus zuweisen.

2. Konfigurieren Sie Ihren Mandanten für die direkte Weiterleitung. Siehe [Zusammenfassung der Konfiguration des direkten Routings pro Mandanten](#summary-of-per-tenant-configuration-of-direct-routing).

3. Konfigurieren Sie bei Bedarf verschiedene Teamrichtlinien für diese Benutzer (beispielsweise TeamsMessagingPolicy, TeamsMeetingPolicy usw.). Dies kann jederzeit erfolgen, doch wenn Sie sicherstellen möchten, dass Benutzer beim Upgrade die richtige Konfiguration haben, empfiehlt es sich, dies zu tun, bevor der Benutzer in den TeamsOnly-Modus wechselt.

4. Vorbereiten der Auswahl von Benutzern für die Sprach Migration: 
   - Falls erforderlich, weisen Sie die Teams-Lizenz zu.  Vorausgesetzt, dass der Benutzer bereits in der lokalen Skype for Business Online-Sprachausgabe funktionsfähig ist, verfügt der Benutzer bereits über Skype for Business Plan 2 und Microsoft Phone System. Belasse beide Pläne aktiviert, einschließlich der Lizenz für Skype for Business Online Plan 2.  
   - Weisen Sie den gewünschten OnlineVoiceRoutingPolicy zu. 

5. Aktualisieren des Benutzers: diese Schritte sollten koordiniert werden. 

   - Aktualisieren Sie in Office 365 den Benutzer in den TeamsOnly-Modus (Grant-CsTeamsUpgradePolicy).
   - Konfigurieren Sie auf dem SBC das VoIP-Routing, um eingehende Anrufe zu aktivieren, indem Sie Anrufe an das direkte Routing statt an den lokalen Vermittlungs Server senden.


### <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>Von Skype for Business Server lokal mit Enterprise-VoIP zur direkten Weiterleitung

In diesem Szenario ist der Benutzer weiterhin in Skype for Business lokal beheimatet, und seine PSTN-Konnektivität ist auch lokal. Das Migrieren dieser Benutzer in den TeamsOnly-Modus mit PSTN-Funktionalität bedeutet, dass Sie für direktes Routing und anschließendes Verschieben des Benutzers in die Cloud aktiviert werden können. 
 
Die grundlegenden Schritte sind im folgenden aufgeführt.  Die Schritte 1-5 sind in der vorgeschlagenen Reihenfolge aufgeführt, können aber in beliebiger Reihenfolge ausgeführt werden. Der Schlüssel besteht darin, dass alle diese Schritte vor Schritt 6 abgeschlossen sein sollten.

1. Wenn Sie die Mandantenweite Richtlinie auf einen der Skype for Business-Modi festlegen, sollten Sie sicherstellen, dass die Benutzer von bestehenden Inseln auf dem Stand sind, indem Sie den Inseln-Modus explizit zuweisen (wie zuvor beschrieben).

2. Wenn Sie dies noch nicht getan haben, [Konfigurieren Sie die Organisation für Skype for Business-Hybrid](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

3. Konfigurieren Sie Ihren Mandanten für die direkte Weiterleitung. Siehe [Zusammenfassung der Konfiguration des direkten Routings pro Mandanten](#summary-of-per-tenant-configuration-of-direct-routing).

4. Konfigurieren Sie bei Bedarf verschiedene Teamrichtlinien für diese Benutzer (z. b. TeamsMessagingPolicy, TeamsMeetingPolicy usw.). Dies kann jederzeit erfolgen, doch wenn Sie sicherstellen möchten, dass Benutzer beim Upgrade die richtige Konfiguration haben, empfiehlt es sich, dies zu tun, bevor der Benutzer auf TeamsOnly aktualisiert wird.

5. Weisen Sie bei Bedarf die Office 365-Lizenzen zu.  Der Benutzer sollte sowohl über Teams als auch über Skype for Business Online Plan 2 sowie über das Telefon System verfügen. Wenn Skype for Business Online Plan 2 deaktiviert ist, aktivieren Sie es erneut.  

6. Aktualisieren des Benutzers: diese Schritte sollten koordiniert werden. 

   - Führen Sie mit den lokalen Skype for Business-Tools Move-CsUser mit-MoveToTeams-Switch aus. Wenn Sie eine Version von Skype for Business Server verwenden, die den-MoveToTeams-Schalter nicht unterstützt, führen Sie zuerst Move-CsUser aus, und weisen Sie dann den TeamsOnly-Modus in der Mandanten-Remote-PowerShell oder der Team-Admin-Konsole zu.

   - Konfigurieren Sie auf dem SBC das VoIP-Routing, um eingehende Anrufe zu aktivieren, indem Sie Anrufe an das direkte Routing statt an den lokalen Vermittlungs Server senden. 

   - In Office 365: weisen Sie die relevanten OnlineVoiceRoutingPolicy zu, um ausgehende Anrufe zu ermöglichen. 


### <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>Von Skype for Business Server lokal mit Enterprise-VoIP zu Microsoft-Anrufplan

In diesem Szenario ist der Benutzer weiterhin in Skype for Business lokal beheimatet, und seine PSTN-Konnektivität ist auch lokal. Das Migrieren dieser Benutzer in den TeamsOnly-Modus mit PSTN-Funktionalität bedeutet, den Benutzer in die Cloud zu verschieben und entweder seine Nummer vom alten Netzbetreiber zu einem Microsoft-Anrufplan zu portieren oder dem Benutzer eine neue Nummer zuzuweisen. 

Die grundlegenden Schritte sind im folgenden aufgeführt.Die Schritte 1-5 sind in der vorgeschlagenen Reihenfolge aufgeführt, können aber in beliebiger Reihenfolge ausgeführt werden. Der Schlüssel besteht darin, dass alle diese Schritte vor Schritt 6 abgeschlossen sein sollten. 

1. Wenn Sie die Mandantenweite Richtlinie auf einen der Skype for Business-Modi festlegen, sollten Sie sicherstellen, dass die Benutzer von bestehenden Inseln auf dem Stand sind, indem Sie den Inseln-Modus explizit zuweisen (wie zuvor beschrieben). 

2. Wenn Sie dies noch nicht getan haben, [Konfigurieren Sie die Organisation für Skype for Business-Hybrid](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity). 

3. Konfigurieren Sie bei Bedarf verschiedene Teamrichtlinien für diese Benutzer (beispielsweise TeamsMessagingPolicy, TeamsMeetingPolicy usw.). Dies kann jederzeit erfolgen, doch wenn Sie sicherstellen möchten, dass Benutzer beim Upgrade die richtige Konfiguration haben, empfiehlt es sich, dies zu tun, bevor der Benutzer auf TeamsOnly aktualisiert wird. 

4. Weisen Sie bei Bedarf die Office 365-Lizenzen zu.Der Benutzer sollte sowohl über Teams als auch über Skype for Business Online Plan 2 sowie über das Telefon System verfügen. Wenn Skype for Business Online Plan 2 deaktiviert ist, aktivieren Sie es erneut.  

5. Holen Sie sich Telefonnummern für Ihre Benutzer. (Einzelheiten finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).)

   - Wenn Sie die Nummern wieder verwenden werden, senden Sie eine Portierungs Anfrage an Ihren Netzbetreiber.  
   - Alternativ können Sie neue Nummern direkt von Microsoft erwerben. 

6. Aktualisieren Sie den Benutzer. Führen Sie mithilfe der lokalen Skype for Business-Tools Move-CsUser mit dem-MoveToTeams-Schalter aus.  

    - Wenn Sie Nummern an Microsoft portieren, sollten Sie die Anzeigedauer dieses Vorgangs koordinieren, damit diese beim Auftreten des Ports erfolgen kann. 

    - Wenn Sie neue Nummern von Microsoft verwenden, müssen Sie die LineUri für den Benutzer ändern.Dies sollte in den on-Prem-Tools erfolgen und dann über Azure AD Connect mit der Cloud synchronisiert werden. Wenn Azure AD Connect die Änderung synchronisiert, sollten Sie die Verschiebungs-CsUser-Operation gleichzeitig ausführen. 

### <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Zusammenfassung der Konfiguration des direkten Routings pro Mandanten 

1. Überprüfen Sie [Diese Liste](direct-routing-border-controllers.md), um sicherzustellen, dass Ihr Session Border Controller (SBC) beim direkten Routing unterstützt wird. Sie müssen auch sicherstellen, dass Sie über die richtige Firmware-Version verfügen.  

2. Koppeln Sie Ihren lokalen SBC mit dem Direct Routing-Dienst von Teams. Ausführliche Informationen finden Sie unter [Koppeln des SBC mit dem Direct Routing-Dienst des Telefonsystems](direct-routing-configure.md#pair-the-sbc-to-the-direct-routing-service-of-phone-system). 

3. Diese Konfiguration ist im Grunde eine Spiegelung der lokalen Konfiguration. Die Online-Konfiguration besteht aus: 
   - OnlineVoiceRoutingPolicy (basierend auf dem lokalen VoiceRoutingPolicy, wenn Benutzer von Skype for Business Online migriert werden, und basierend auf VoicePolicy, wenn Benutzer von lokal mit Enterprise-VoIP migriert werden).
   - OnlinePSTNUsage-Objekte (basierend auf der lokalen PSTN-Nutzung). 
   - OnlineVoiceRoute-Objekte (basierend auf lokalen VoiceRoute) 

Weitere Informationen finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md). 

### <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Verwalten der EnterpriseVoiceEnabled-Eigenschaft während der Migration 

Unabhängig davon, ob Sie das direkte Routing oder einen Microsoft-Anrufplan verwenden, muss ein Benutzer EnterpriseVoiceEnabled = true in Azure AD besitzen, damit der Benutzer PSTN-Funktionalität hat.  EnterpriseVoiceEnabled ("EV-Enabled") ist eine Eigenschaft (keine Richtlinie), die sowohl in einem lokalen Verzeichnis als auch in der Cloud vorhanden ist. Der Wert in der Cloud ist wichtig für Teams.  Die genaue Logik, wie EV-Enabled auf true festgelegt wird, hängt vom folgenden Szenario ab: 

- Wenn der Benutzer in lokalen Skype for Business-Servern EV-fähig ist und dem Benutzer eine Telefon System Lizenz zugewiesen ist, bevor der Benutzer mit Move-CsUser in die Cloud verschoben wird, wird der Online-Benutzer mit EV-Enabled = true bereitgestellt. 

- Wenn einem vorhandenen TeamsOnly-oder Skype for Business Online-Benutzer eine Telefon System Lizenz zugewiesen ist, ist EV-Enabled standardmäßig nicht auf "true" festgelegt.  Dies ist auch der Fall, wenn ein lokales Benutzer vor dem Zuweisen der Telefon System Lizenz in die Cloud verschoben wird. In beiden Fällen muss der Administrator das folgende Cmdlet angeben: 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="coexistence-of-teams-with-skype-for-business"></a>Koexistenz von Teams mit Skype for Business

In diesem Abschnitt werden die Verhaltensweisen zusammengefasst, die beim Ausführen von Teams und Skype for Business-Clients in derselben Organisation auftreten können, unabhängig davon, in welchem Modus und welche Aktualisierungsmethode verwendet wird:

- [Besprechungen](#meetings)
- [Interoperabilität](#interoperability)
- [Teams-Unterhaltungen – Interop versus native Threads](#teams-conversations---interop-versus-native-threads)
- [Anwesenheit](#presence)
- [Partnerverbund](#federation)
- [Kontakte](#contacts)

### <a name="meetings"></a>Besprechungen

Unabhängig von Ihrem Modus können Benutzer immer an jeder Art von Besprechung teilnehmen, zu der Sie eingeladen werden, egal ob es sich um Skype for Business oder Teams handelt.  Benutzer müssen jedoch an der Besprechung mit einem entsprechenden Clientteil nehmen, der dem Besprechungstyp entspricht:

- Wenn es sich bei der Besprechung um eine Teambesprechung handelt, verwenden alle Teilnehmer (ob TeamsOnly, Inseln oder Skype for Business-Benutzer) den Team-Client, um an der Besprechung teilzunehmen. Wenn Teams nicht installiert ist, wird der Benutzer beim Versuch, an einer Besprechung teilzunehmen, an das Internet weitergeleitet.

- Wenn es sich bei der Besprechung um eine Skype for Business-Besprechung handelt, verwenden alle Teilnehmer (ob TeamsOnly, Inseln oder Skype for Business-Benutzer) den Skype for Business-Client, um an der Besprechung teilzunehmen. Wenn der Skype for Business-Client nicht installiert ist, wird der Benutzer an das Web weitergeleitet, um über die Skype-Besprechungs-App teilnehmen zu können.

Beim Organisieren von Besprechungen basiert der Besprechungstyp, der geplant wird, auf dem Modus des Organisators, wie in der folgenden Tabelle dargestellt:

| Modus von Organizer    |      Verhalten |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Alle in Teams geplanten Besprechungen Das Skype for Business-Add-in steht in Outlook nicht zur Verfügung. | 
| SfbWithTeamsCollab, SfbOnly   | Alle in Skype for Business geplanten Besprechungen Das Team-Add-in steht in Outlook nicht zur Verfügung. | 
| Inseln |     Besprechungen können entweder in Skype for Business oder in Teams geplant werden. Beide Add-Ins stehen in Outlook zur Verfügung. | 


### <a name="interoperability"></a>Interoperabilität

Teams unterstützt Interoperabilität ("Interop") mit Skype for Business in bestimmten Szenarien. Die Interop-Kommunikation bezieht sich auf einen Chat oder einen Anruf zwischen einem Skype for Business-Benutzer und einem Teams-Benutzer.  Die Interop-Kommunikation ist nur zwischen zwei Benutzern möglich. mehr Parteien-Chat/-Anrufe oder das Hinzufügen weiterer Benutzer werden nicht unterstützt.

Ein Interop-Chat oder-Anruf zwischen zwei Benutzern wird erstellt, wenn jede der folgenden Bedingungen zutrifft:

- Ein Benutzer verwendet Teams, und der andere Nutzer nutzt Skype for Business.

- Der Modus des Empfängers der anfänglichen Kommunikation ist keine Inseln (andernfalls würde die Kommunikation in demselben Client landen), wenn sich beide Benutzer in derselben Organisation befinden. In Verbundszenarien verwendet der sendende Benutzer Teams, und der Empfänger befindet sich nicht im TeamsOnly-Modus. 

- Der Benutzer des Teams hat nicht auch ein Skype for Business-Konto, das lokal verwaltet wird. 

In der Interop-Kommunikation ist Chat nur mit nur-Text-Funktion. Darüber hinaus sind Dateifreigabe und Bildschirmübertragung *im Interop-Chat selbst*nicht möglich. Benutzer in einer Interop-Unterhaltung können jedoch problemlos Datei-und/oder Bildschirm Freigaben erreichen, indem Sie im Interop-Chat wie nachstehend beschrieben eine on-Demand-Besprechung erstellen:

- Wenn der Benutzer des Teams versucht, seinen Bildschirm freizugeben, wird automatisch eine Besprechung auf Anforderungs Teams erstellt, und ein Einladungslink zu dieser Besprechung wird an den Client des Skype for Business-Benutzers gesendet. Wenn Sie auf den Link klicken, wird der Skype for Business-Benutzer Teams öffnen und an der Besprechung teilnehmen. Beide Benutzer sind jetzt in einer Teams-Besprechung und können nach Bedarf freigeben.

- Wenn der Skype for Business-Benutzer einen Client von 2018 oder höher verwendet und versucht, Inhalte freizugeben, wird automatisch eine Skype for Business-on-Demand-Besprechung erstellt, und ein Einladungslink zu dieser Besprechung wird an den Client des Teams gesendet. Wenn Sie auf den Link klicken, versucht der Benutzer von Teams, an der Skype for Business-Besprechung teilzunehmen. Wenn der Benutzer des Teams den Skype for Business-Client installiert hat, wird er geöffnet, und der Benutzer wird aufgefordert, sich anzumelden (sofern er noch nicht angemeldet ist).  Wenn der Benutzer des Teams nicht über den Skype for Business-Client verfügt, wird der Benutzer aufgefordert, die Webversion zu verwenden. Nachdem beide Benutzer angemeldet sind, befinden Sie sich in einer Skype for Business-Besprechung und können Sie nach Bedarf freigeben.

### <a name="teams-conversations---interop-versus-native-threads"></a>Teams-Unterhaltungen – Interop versus native Threads

Da die Interop-Kommunikation nicht alle Features von Native Teams-Konversationen unterstützt, verwaltet der Team-Client getrennte Konversations Threads für Teams-zu-Teams und Teams-zu-Skype for Business-Kommunikation. Diese Unterhaltungen werden in der Benutzeroberfläche anders gerendert: Interop-Threads können von einem regulären systemeigenen Teams-Thread unterschieden werden:

- Fehlende Steuerungen für Rich-Text, Datei-und Bildschirmübertragung, Unfähigkeit zum Hinzufügen von Benutzern.
- Eine Änderung des Symbols des Zielbenutzers mit einem "s" für Skype for Business.

Diese Unterschiede werden in den folgenden Screenshots gezeigt:

Eine native Unterhaltung von Teams zu Teams mit dem Benutzer G3-Test

![Diagramm mit einer nativen Unterhaltung von Teams zu Teams](media/teams-upgrade-native-thread.png)

Eine Interop-Unterhaltung mit dem gleichen Benutzer G3-Test

![Diagramm mit einer Unterhaltung von Interop-Teams zu Teams](media/teams-upgrade-interop-thread.png)

Nachdem ein konversationsthread erstellt wurde, ändert sich dessen Typ nie. Nach der Erstellung wird ein Interop-Thread in Teams immer zum Skype for Business-Client des Zielbenutzers weitergeleitet. Ein systemeigener Thread wird immer an den Team-Client des Zielbenutzers weitergeleitet.  Wenn sich der Modus eines Empfänger Benutzers ändert, funktionieren vorhandene Teams für diesen Benutzer nicht mehr, und in diesem Chat wird eine Notiz mit einem Link angezeigt, um eine neue systemeigene Konversation zu starten, wie im folgenden Screenshot gezeigt. Weitere Informationen finden Sie unter [Chats und Anrufe von bereits vorhandenen Threads](coexistence-chat-calls-presence.md#chats-and-calls-from-pre-existing-threads).


![Diagramm, das einen Chat mit aktualisierten Skype for Business-Benutzern zeigt](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>Anwesenheit

Die Anwesenheitsinformationen für einen bestimmten Benutzer basieren auf der Aktivität des Benutzers im Dienst über den Client. Die Anwesenheitsinformationen werden dann für andere Benutzer veröffentlicht.  Skype for Business und Teams sind getrennte Dienste mit separaten Clients, sodass jeder Dienst seinen eigenen Anwesenheitsstatus für einen Benutzer hat.   Es gibt auch eine Synchronisierung zwischen den Anwesenheits Diensten in Teams und in Skype for Business Online.  Dadurch kann ein Dienst möglicherweise das vorhanden sein des Benutzers aus dem anderen Dienst veröffentlichen, falls erforderlich. 

Das Verhalten der Anwesenheits Veröffentlichung basiert auf dem Modus des Benutzers. Es gibt drei grundlegende Fälle:

- Wenn sich ein Benutzer im TeamsOnly-Modus befindet, sehen alle anderen Benutzer die Anwesenheit von Teams für diesen Benutzer, unabhängig davon, welchen Client Sie verwenden.

- Wenn sich ein Benutzer in einem der Skype for Business-Modi befindet, sehen alle anderen Benutzer die Skype for Business-Anwesenheit für diesen Benutzer, unabhängig davon, welchen Client Sie verwenden.

- Wenn sich ein Benutzer im Modus "Inseln" befindet, ist die in Skype for Business und Microsoft Teams veröffentlichte Anwesenheit unabhängig, sodass die Anwesenheitsanzeige für Benutzer innerhalb der gleichen Organisation vom Client des anderen Benutzers abhängt. Benutzer in Verbundorganisationen sehen die Anwesenheit dieses Benutzers auf der Grundlage Ihrer Skype for Business-Aktivität, da der Verbund Verkehr zu einem Nutzer der Inseln-Modus in Skype for Business landet.

Nehmen Sie beispielsweise an, dass Benutzer A sich im Modus "Inseln" befindet. Wenn Benutzer a in Microsoft Teams aktiv ist, aber nicht bei Skype for Business angemeldet ist, sehen andere Benutzer den Benutzer a als aktiv von Ihrem Team-Client, aber in Ihrem Skype for Business-Client sehen Benutzer a als offline. Dies ist beabsichtigt, da Benutzer A nicht erreicht werden kann, wenn Sie den Client nicht ausführen. 

Weitere Informationen finden Sie unter [Anwesenheits](coexistence-chat-calls-presence.md#presence)Informationen.

### <a name="federation"></a>Partnerverbund

Föderation von Teams zu einem anderen Benutzer unter Verwendung von Skype for Business muss der Team Benutzer in Skype for Business online sein. TeamsUpgradePolicy steuert das Routing für eingehende Federated-Chats und-Anrufe. Das Verhalten des Verbund Routings ist identisch mit den Szenarien für denselben Mandanten, mit Ausnahme des Modus "Inseln". Wenn sich die Empfänger im Inseln-Modus befinden:

- Chats und Anrufe, die von Teams initiiert werden, landen in Skype for Business, wenn sich der Empfänger in einem Federated-Mandanten befindet.
- Chats und Anrufe, die von Teams initiiert werden, landen in Teams, wenn sich der Empfänger im gleichen Mandanten befindet.
- Chats und Anrufe, die von Skype for Business initiiert werden, landen immer in Skype for Business.

Ein Federated-Chat zwischen einem Teams-Benutzer und einem Skype for Business ist ein Interop-Thread, sodass Rich-Text und Freigabe nicht möglich sind. Die Benutzeroberfläche macht Federated-Chats auf ähnliche Weise für identische Mandanten-Interop-Threads verfügbar, es sei denn, es gibt eine Notiz, die angibt, dass der Benutzer extern ist.

Wenn Teams erstmals Federation eingeführt haben, war ein Federated-Chat zwischen zwei Teams-Benutzern ebenfalls ein Interop-Thread, aber in Zukunft wird der Federation Native Teams eingeführt, der vollständige Funktionen für Konversationen zwischen Benutzern bietet, die sich im TeamsOnly-Modus befinden. . 

Weitere Informationen finden Sie unter [Federated-Routing für neue Chats oder Anrufe](coexistence-chat-calls-presence.md#federated-routing-for-new-chats-or-calls).

### <a name="contacts"></a>Kontakte

Teams und Skype for Business haben getrennte Kontaktlisten. Das bedeutet, dass die in einem System vorgenommenen Kontakt Ergänzungen,-Entfernungen und-Änderungen nicht mit dem anderen System synchronisiert werden. Kontakte von Skype for Business werden jedoch automatisch in Teams kopiert, wenn eines von zwei bestimmten Ereignissen Eintritt: 

- Bei einem Skype for Business Online-Benutzer werden die Kontakte aus Skype for Business bei der ersten Anmeldung in Teams in Teams kopiert.  Dieses Verhalten steht Benutzern mit einem lokalen Konto in Skype for Business Server nicht zur Verfügung.  

- Nachdem ein Benutzer auf TeamsOnly aktualisiert wurde (entweder über die Zuweisung von TeamsUpgradePolicy oder über Move-CsUser-MoveToTeams), wird das nächste Mal, wenn sich ein Benutzer bei Teams anmeldet, vorhandene Kontakte in Skype for Business mit vorhandenen Kontakten zusammengeführt, die bereits in Teams sind. Dieses Verhalten tritt auf, wenn das Skype for Business-Konto des Benutzers lokal oder online gehostet wird. 

In beiden Fällen ist die Übertragung von Kontakten von Skype for Business in Teams asynchron, daher kann es ein paar Minuten dauern, bis Kontakte in Teams angezeigt werden. Die beiden obigen Ereignisse lösen die Kopie aus.  

## <a name="related-links"></a>Verwandte Links

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Verwenden des Besprechungs Migrations Diensts (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

