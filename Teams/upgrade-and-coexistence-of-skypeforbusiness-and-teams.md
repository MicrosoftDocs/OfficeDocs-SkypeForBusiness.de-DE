---
title: Microsoft Teams-Upgrade von Skype for Business | Modi, Koexistenz
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen, bjwhalen
description: Details zu den Optionen und Modi von Skype for Business und Microsoft Teams für Koexistenz sowie zum Upgrade von Reisen zu Teams von Skype for Business mit Beispielszenarien.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords:
- ms.teamsadmincenter.orgwidesettings.teamsfeatures.upgradetoteamsarticle
- ms.teamsadmincenter.upgradeoverride.learnmore
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5de243402cd5694b2e4a498f7ff7650cd8f49f4a
ms.sourcegitcommit: 2e005b335b1566c99b93fc311498702838466324
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2019
ms.locfileid: "37931643"
---
![Diagramm zum Upgrade von Fahrten mit Hervorhebung der Projekt Definitions Stufe](media/upgrade-banner-project-definition.png "Phasen der Upgrade-Reise mit dem Schwerpunkt auf der Projekt Definitions Stufe")

Dieser Artikel ist Teil der Projekt Definitionsphase ihrer Upgrade-Reise. Bevor Sie fortfahren, bestätigen Sie, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](https://aka.ms/SkypetoTeams-Scope)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](https://aka.ms/SkypeToTeams-Coexist)

# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Wählen Sie Ihre Upgrade-Reise von Skype for Business zu Teams aus.

Als vorhandener Skype for Business-Kunde kann es einige Zeit dauern, bis Ihr vollständiger Wechsel zu Teams stattfinden kann. Allerdings können Sie den Wert von Teams heute erkennen, indem Sie es Ihren Benutzern ermöglichen, Teams neben Skype for Business zu verwenden. Da es zwischen den beiden apps einige überlappende Funktionen gibt, empfehlen wir, dass Sie die verfügbaren Koexistenz-und Aktualisierungsmodi überprüfen, um zu ermitteln, welcher Pfad für Ihre Organisation richtig ist. So können Sie beispielsweise alle Arbeitsauslastungen für beide Lösungen ohne Interoperabilität aktivieren. Oder Sie entscheiden sich möglicherweise für die Verwaltung der Benutzeroberfläche, indem Sie schrittweise die Teamfunktionen einführen oder Benutzergruppen auf ausgewählte Funktionen ausrichten, bis Ihre Organisation bereit ist, alle Personen auf Teams zu aktualisieren. Mithilfe des Ergebnisses Ihres Pilotprojekts können Sie die richtige Upgrade-Reise für Ihre Organisation bewerten.

> [!IMPORTANT]
> Skype for Business Online wird am 31. Juli 2021 eingestellt. Ab diesem Zeitpunkt kann nicht mehr darauf zugegriffen werden, und es wird nicht mehr unterstützt. Um den maximalen Nutzen zu erzielen und sicherzustellen, dass Ihre Organisation genügend Zeit hat, Ihr Upgrade durchzuführen, empfehlen wir Ihnen, den Wechsel zu Microsoft Teams bereits heute zu planen.

In diesem Artikel werden die verschiedenen Modi erläutert, mit denen Sie verwalten können, welche Modalitäten in Skype for Business und Teams für Ihre Benutzer zur Verfügung stehen. Wie bei jeder Bereitstellung empfehlen wir Ihnen dringend, [ihren beabsichtigten Plan](pilot-essentials.md) mit einer ausgewählten Gruppe von Benutzern zu pilotieren, bevor Sie Ihre Organisation auf Teams aktualisieren. Denken Sie daran, dass die Einführung neuer Technologien für Benutzer störend sein kann. Nehmen Sie sich Zeit, um die Benutzer Bereitschaft zu bewerten und einen Kommunikations-und Schulungsplan zu implementieren, bevor Sie einen der hierin beschriebenen Modi implementieren.

> [!TIP]
> Begleiten Sie uns in interaktiven, interaktiven Workshops, in denen wir Anleitungen, bewährte Methoden und Ressourcen austauschen, die für die Planung und Implementierung von Upgrades entwickelt wurden.
>
>Nehmen Sie zuerst an der [Planung Ihrer Upgrade](https://aka.ms/SkypeToTeamsPlanning) -Sitzung Teil, bevor Sie beginnen.


## <a name="upgrade-journey-building-blocks"></a>Bausteine für Upgrade-Fahrten

Wenn Sie Ihre Organisation formell für Ihre Reise in Teams vorbereiten möchten, müssen Sie mit der Planung für die Upgrade-Szenarien beginnen, die es Ihrem Unternehmen ermöglichen, Teams als ihre einzige Lösung für Kommunikation und Zusammenarbeit umfassend zu integrieren.

Um ihre Entscheidungsfindung zu erleichtern, sollten Sie sich mit den verschiedenen Modi, Konzepten und Terminologie vertraut machen, die für das Upgrade von Skype for Business auf Teams relevant sind. Weitere Informationen finden Sie unter [Microsoft Teams und Skype for Business-Koexistenz und-Interoperabilität](https://aka.ms/SkypeToTeams-Coexist) .

Ein Benutzer, der in Teams migriert wurde, verwendet keinen Skype for Business-Client mehr, es sei denn, Sie nehmen an einer in Skype for Business gehosteten Besprechung Teil. Alle eingehenden Chats und Anrufe landen im Team-Client des Benutzers, unabhängig davon, ob der Absender Teams oder Skype for Business verwendet. Alle neuen Besprechungen, die vom aktualisierten Benutzer organisiert werden, werden als Teams-Besprechungen geplant. Wenn der Benutzer versucht, den Skype for Business-Client zu verwenden, wird das Initiieren von Chats und anrufen blockiert<sup>1</sup>. Allerdings kann der Benutzer den Skype for Business-Client weiterhin verwenden, um an Besprechungen teilzunehmen, zu denen er eingeladen wurde.

Administratoren verwalten Ihren Übergang zu Teams mithilfe des Konzepts des [Modus](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes), bei dem es sich um eine Eigenschaft von [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)handelt. Ein Benutzer, der wie oben beschrieben zu Teams migriert wurde, befindet sich im Modus "TeamsOnly". Für eine Organisation, die zu Teams migriert, besteht das ultimative Ziel darin, alle Benutzer in den TeamsOnly-Modus zu verschieben.

Es gibt zwei Methoden zum Migrieren einer vorhandenen Organisation mit Skype for Business (ob online oder lokal) in Teams:

- Über **Lapp Ende Capabilities-Methode** (im Modus "Inseln"): Benutzer in einer vorhandenen Skype for Business-Organisation werden in Teams eingeführt, damit Sie in einer Übergangsphase beide Clients nebeneinander verwenden können. In diesem Zeitraum stehen Ihnen die meisten--aber nicht alle--Funktionen von Teams zur Verfügung. Der Modus für diese Konfiguration wird als "Inseln" bezeichnet, und dies ist der Standardmodus für jede vorhandene Organisation mit Skype for Business. Sobald die Organisation fertig ist, verschiebt der Administrator die Benutzer in den TeamsOnly-Modus.
- **Wählen Sie** die Funktion Funktionen (mit einem oder mehreren Skype for Business-Modi): der Administrator verwaltet den Übergang (von Skype for Business zu Teams) von Chat-, Anruf-und Besprechungs Planungsfunktionen für Benutzer in Ihrer Organisation. Jede dieser Funktionen steht entweder in Skype for Business oder in Teams zur Verfügung, aber nicht in beiden. Administratoren verwenden TeamsUpgradePolicy, um zu steuern, wann diese Funktionalität für Ihre Benutzer in Teams verschoben werden soll. Benutzer, die noch nicht im TeamsOnly-Modus sind, verwenden weiterhin Skype for Business für Chats und Anrufe, und die beiden Benutzergruppen können über die Interop-Funktionalität kommunizieren. Administratoren verwalten den Übergang, indem Sie schrittweise mehr Benutzer in den TeamsOnly-Modus migrieren.

<sup>1</sup> Ältere Skype for Business-Clients, die vor 2017 ausgeliefert wurden, Ehren TeamsUpgradePolicy nicht. Stellen Sie sicher, dass Sie den neuesten Skype for Business-Client verwenden, der in Ihrem Office-Kanal verfügbar ist.

Nachfolgend sind die wichtigsten Faktoren aufgeführt, die Ihnen bei der Entscheidung über den geeigneten Pfad für Ihre Organisation helfen. 

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Überlappende Capabilities-Methode (im Modus "Inseln")

Mit der überlappenden Funktionen-Methode können Benutzer sowohl Teams als auch Skype for Business-Clients für Chats, VoIP-Anrufe und Besprechungen verwenden. Bei dieser Methode sind Chats und VoIP-Anrufe in Teams Intra-Organization-orientiert, während Skype for Business Chats und VoIP/PSTN-Anrufe mit externen Organisationen ermöglicht (sofern konfiguriert). Besprechungen können in beiden Produkten geplant und besucht werden.

Bei Verwendung der überlappenden Funktionen-Methode bleibt der Kommunikationsverkehr für Skype for Business und Teams getrennt (auch für denselben Benutzer), und die beiden unterschiedlichen Clients kommunizieren nie miteinander (für Benutzer innerhalb der gleichen Organisation). Die Benutzererfahrung basiert auf der Konfiguration des Empfängers. Nehmen Sie beispielsweise an, dass der Empfänger Benutzer A Diese Aktualisierungsmethode verwendet:

- Die Kommunikation, die über den Skype for Business-Client eines anderen Benutzers initiiert wird, landet immer im Skype for Business-Client von User A.
- Die von einem *Benutzer in der gleichen Organisation* initiierte Kommunikation vom Team-Client wird immer im Team-Client von User a landen.
- Die von einem Team-Client initiierte Kommunikation von einem *Benutzer in einer externen Organisation* landet immer im Skype for Business-Client von Benutzer a.

Wenn Sie Ihren Benutzern eine Office 365-Lizenz zugewiesen haben, ist dies die standardmäßige Upgrade-Erfahrung für Ihre Organisation. Wenn Sie eine Office 365-Lizenz zuweisen, werden standardmäßig beide Teams und Skype for Business Online-Lizenzen zugewiesen. <sup>2</sup>

Damit diese Methode effektiv funktioniert, müssen alle Benutzer beide Clients gleichzeitig ausführen. Eingehende Chats und Anrufe innerhalb des Unternehmens an einen Benutzer im Inseln-Modus können entweder in den Skype for Business-oder Microsoft Teams-Client landen – und dies steht nicht unter der Kontrolle des Empfängers. Dies hängt davon ab, welchen Client der Absender zum Initiieren der Kommunikation verwendet. Wenn sich der Absender und der Empfänger in verschiedenen Organisationen befinden, sind eingehende Anrufe und Chats an einen Benutzer im Inseln-Modus immer im Skype for Business-Client zu Lande.

Wenn beispielsweise ein Empfänger für inselnmodus bei Skype for Business angemeldet ist, aber nicht in Teams, und jemand Sie aus Teams Nachrichten kann, wird die Nachricht vom Empfänger für inselnmodus nicht angezeigt (aber Sie erhalten schließlich eine e-Mail, die besagt, dass Sie eine Nachricht in Teams verpasst haben). Wenn ein Benutzer Teams ausführt, aber nicht Skype for Business, und jemand diesen Nutzer von Skype for Business Nachrichten kann, wird dieser Chat dem Nutzer nicht angezeigt. Das Verhalten in jedem dieser Fälle ist für den Aufruf ähnlich. Wenn Benutzer nicht beide Clients ausführen, kann dies problemlos zu Frustration führen.

Die Anwesenheitsfunktion funktioniert auch unabhängig von Teams und Skype for Business mithilfe dieser Upgrade-Methode. Dies bedeutet, dass andere Benutzer möglicherweise unterschiedliche Anwesenheitsstatus für Benutzer A sehen, je nachdem, welchen Client Sie verwenden. Weitere Informationen finden Sie unter [Anwesenheits](upgrade-to-Teams-on-prem-overview.md#presence)Informationen.

- Andere Benutzer sehen bei der Verwendung von Teams die Anwesenheitsinformationen auf der Grundlage der Aktivitäten von Benutzer A in Teams.
- Andere Benutzer können bei Verwendung von Skype for Business die Anwesenheitsinformationen auf der Grundlage der Aktivitäten von Benutzer A in Skype for Business sehen.

Wenn Sie bereit sind, Benutzer auf den TeamsOnly-Modus zu aktualisieren, können Sie Benutzer einzeln aktualisieren oder den gesamten Mandanten mithilfe der Mandanten weiten Richtlinie<sup>3</sup>aktualisieren. Sobald ein Benutzer auf den TeamsOnly-Modus aktualisiert wurde, erhalten alle eingehenden Chats und Anrufe in Teams.

Nicht aktualisierte Empfänger im Inseln-Modus können jedoch weiterhin Chats und Anrufe von einem TeamsOnly-Benutzer in Ihren Skype for Business-oder Microsoft Teams-Clients empfangen. Bei vorhandenen Unterhaltungen antwortet der TeamsOnly-Benutzer an den Client, von dem der Absender den Chat initiiert hat. 

Für neue Konversationen aus der Sicht des TeamsOnly-Benutzers wechselt der Chat oder Anruf immer zum Client Teams-Client für Inseln-Modus. Der Grund dafür ist, dass der Team-Client getrennte Konversations Threads für Teams-zu-Teams und Teams-zu-Skype for Business-Kommunikation verwaltet, selbst für denselben Benutzer. Weitere Informationen finden Sie unter [Konversationen in Teams – Interop versus native Threads](upgrade-to-Teams-on-prem-overview.md#teams-conversations---interop-versus-native-threads).

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
| Ermöglicht Benutzern, Teams zu lernen und sich mit Ihnen vertraut zu machen, während Sie weiterhin vollen Zugriff auf Skype for Business haben. | Potenzielle Endbenutzer-Unzufriedenheit aufgrund verpasster Nachrichten, wenn der Benutzer nicht beide Clients ausführt.|
| Minimaler Verwaltungsaufwand für den Einstieg in Teams. | Kann schwierig sein, den Modus "aus den Inseln zu verlassen" und in den TeamsOnly-Modus zu wechseln, wenn Benutzer und Personen, mit denen Sie regelmäßig kommunizieren, keine Teams aktiv verwenden.|
|Ermöglicht Benutzern die Nutzung von Funktionen zur Verbesserung der Teamarbeit, die in Skype for Business nicht zur Verfügung stehen.| Ein Benutzer, der Skype for Business in Räumlichkeiten und Teams verwendet, kann nicht von Teams mit einem anderen Benutzer kommunizieren, der Skype for Business lokal verwendet, aber keine Teams hat.  |

<sup>2</sup> Dies gilt auch, wenn der Benutzer lokal in Skype for Business Server verwaltet wird. Unabhängig davon, ob der Benutzer lokal oder Online ist, lassen Sie die Skype for Business Online-Lizenz aktiviert, da Sie zurzeit für die vollständige Team Funktionalität benötigt wird.

<sup>3</sup> Beachten Sie, dass die Migration von Skype for Business-Besprechungen in Teams-Besprechungen nur dann ausgelöst wird, wenn Sie TeamsUpgradePolicy auf einzelne Benutzer anwenden, nicht auf Mandantenbasis. Details finden Sie unter [Besprechungs Migration](upgrade-to-Teams-on-prem-overview.md#meeting-migration) .

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>SELECT Capabilities-Methode (mit Skype for Business-Modi)

Einige Organisationen ziehen es vor, Ihren Endbenutzern eine vorhersagbarere Erfahrung zu bieten, wenn Ihre Organisation von Skype for Business zu Teams wechselt. In diesem Modell verwenden IT-Administratoren einen der Skype for Business-Modi in TeamsUpgradePolicy, um explizit festzulegen, welche Funktionen vor der Migration in den TeamsOnly-Modus in Skype for Business verbleiben. Da Sie bereit sind, ausgewählte Funktionen in den TeamsOnly-Modus zu verschieben, aktualisiert der Administrator den Modus für diese Benutzer auf TeamsOnly. Während dieses Übergangs:

- Administratoren haben die Möglichkeit, bestimmte Teamfunktionen für Benutzer zu aktivieren, während Sie Chat-und Anruffunktionen in Skype for Business beibehalten, bevor Benutzer zu TeamsOnly-Erfahrung wechseln. Die Verwaltung kann Teamzusammenarbeitsfunktionen oder Teams-Besprechungen sowie Zusammenarbeitsfunktionen aktivieren.
- Benutzer, die noch über Skype for Business verfügen, erhalten alle eingehenden Chats und Anrufe in Ihrem Skype for Business-Client, unabhängig davon, ob die Kommunikation von den Teams des anderen Benutzers oder dem Skype for Business-Client stammt. Darüber hinaus sind für diese Skype for Business-Benutzer die Funktionen für Anrufe und Chats im Teams-Client deaktiviert, um die Verwirrung des Endbenutzers zu verhindern und die ordnungsgemäße Weiterleitung und Anwesenheit zu gewährleisten.
- Benutzer im TeamsOnly-Modus empfangen alle eingehenden Chats und Anrufe in Ihrem Teams-Client, und die Anwesenheitsinformationen werden von Teams bereitgestellt, unabhängig davon, woher die Kommunikation stammt: Teams, Skype for Business oder jede Art von Federated-Nutzer.

Im Gegensatz zur überlappenden Capabilities-Methode können Benutzer, die Skype for Business verwenden, mit den Benutzern in TeamsOnly kommunizieren. Die Kommunikation zwischen einem Skype for Business-Benutzer und einem Microsoft Teams-Benutzer wird als " [Interoperabilität](upgrade-to-Teams-on-prem-overview.md#interoperability) " oder "Interop" bezeichnet. Interoperabilitäts Kommunikation ist 1:1 für Chats und Anrufe zwischen einem Benutzer in Skype for Business und einem anderen Benutzer in Microsoft Teams möglich. Darüber hinaus können eingeladene Benutzer immer an einer Skype for Business-oder Teams-Besprechung teilnehmen, doch müssen Sie einen Client verwenden, der dem Typ der Besprechung entspricht. Weitere Informationen finden Sie unter [Besprechungen](upgrade-to-Teams-on-prem-overview.md#meetings).

Für Benutzer in einer SELECT-Capabilities-Methode ist die Anwesenheit für einen Benutzer konsistent, unabhängig davon, welcher Client vom anderen Benutzer verwendet wird. Wenn sich der Benutzer in einem der Skype for Business-Modi befindet, sehen alle anderen Benutzer die Anwesenheitsinformationen auf der Grundlage der Aktivitäten dieses Benutzers in Skype for Business. Auch wenn sich ein Benutzer im TeamsOnly-Modus befindet, sehen alle anderen Benutzer die Anwesenheitsinformationen auf der Grundlage der Aktivitäten dieses Benutzers in Teams. Einzelheiten hierzu finden Sie unter [Anwesenheits](upgrade-to-Teams-on-prem-overview.md#presence)Informationen.

Bei einer Organisation, die sich für die Auswahl der Methoden zur Auswahl von Funktionen entschieden hat, sollte der Administrator den Mandanten weiten Modus von Inseln in den entsprechenden Skype for Business-Koexistenzmodus (SfbWithTeamsCollab oder SfBWithTeamsCollabAndMeetings) ändern.  

Die Benutzer Erfahrungen des Gastes halten sich an den dem Mandanten zugewiesenen Koexistenzmodus. Wenn Sie einen Skype for Business-Modus auf Mandantenebene einrichten, können Gäste nicht chatten, Anrufe tätigen oder deren Anwesenheit anzeigen. Weitere Informationen finden Sie unter [Gastzugriff in Teams](guest-access.md).

Wenn sich der Modus von "Inseln" auf "SfbWithTeamsCollab" ändert, sieht ein Benutzer, der nie Teams verwendet hat, keinen Unterschied in der Verwendung von Skype for Business. Sollte der Benutzer jedoch mit der Verwendung von Teams beginnen, würden diese nur Funktionen wie Teams #a0 Kanal und Dateien verfügbar gemacht. Chat, Anruf-und Besprechungsplanung stünden in Teams nicht zur Verfügung, da der Administrator Skype for Business für diese Funktionen als den gewünschten Client vorgesehen hat.

> [!NOTE]
> Wenn der Benutzer eine Änderung von den Inseln zu einem der Skype for Business-Modi durchführt, muss der Team-Client eines anderen Benutzers, der mit dem Benutzer a kommuniziert, wissen, dass der Modus von Benutzer a geändert wurde, damit er die Kommunikation an den entsprechenden Client für Benutzer a weiterleiten kann. Für Benutzer, die bereits systemeigene Teams-zu-Teams-Chats mit Benutzer A eingerichtet haben, kann es Zeit dauern, bis sich die Teams-Clients dieser anderen Benutzer über den Modus "ändern" von den Inseln zu einem beliebigen Skype for Business-Modus bewusst sind. Wenn Administratoren bereit sind, können Sie die Chat-, Anruf-und Besprechungsplanung für einen bestimmten Benutzer in Teams auf einmal verschieben, indem Sie den Modus des Benutzers auf TeamsOnly aktualisieren.

Alternativ kann der Administrator zunächst nur die Besprechungsplanung in Teams verschieben, während er Chat-und Anruffunktionen in Skype for Business über den SfBWithTeamsCollabAndMeetings-Modus verlässt. In diesem Modus können Organisationen zu Teams für Besprechungen wechseln – wenn Benutzer noch nicht bereit sind, in den TeamsOnly-Modus zu wechseln (beispielsweise sind Sie noch nicht bereit, vorhandene PSTN-Funktionen zu migrieren). Dieses Übergangsszenario wird zuerst als " [Besprechungen](meetings-first.md)" bezeichnet.


|Teams-Erfahrung  |Im SfBWithTeamsCollab-Modus |Im SfBWithTeamsCollabAndMeetings-Modus |Im TeamsOnly-Modus  |
|---------|---------|---------|---------|
|Eingehende Chats und VoIP-Anrufe von Benutzern in Ihrer Organisation erhalten in:     | Skype for Business        | Skype for Business       | Teams        |
|Empfangene PSTN-Anrufe:     | Skype for Business        |Skype for Business         | Teams        |
|Anwesenheit     | Skype for Business        |Skype for Business         | Teams        |
|Besprechungsplanung     | Skype for Business         | Teams        | Microsoft Teams        |


In der folgenden Tabelle sind die vor-und Nachteile der Verwendung von Skype for Business-Modi als Übergangsschritt in Richtung TeamsOnly-Modus zusammengefasst.

| Experten     |       Nachteile |
| :------------------ | :---------------- |
| Vorhersehbares Routing für den Endbenutzer. Alle Anrufe und Chats landen entweder in Skype for Business oder in Teams (aber nicht in beiden), basierend auf der Auswahl des Administrators.|Bei Interop-Unterhaltungen fehlt die Unterstützung für Rich-Text, Dateifreigabe und Bildschirmfreigabe. Dies kann durch die Nutzung von "jetzt erfüllen"-Funktionen zum Initiieren einer Besprechung aufgearbeitet werden. |
|Kann die Verwirrung des Endbenutzers reduzieren, da eine bestimmte Funktionalität nur in einem Client verfügbar ist. | Benutzer haben keinen Zugriff auf Teams für allgemeine Aktivitäten, die in Skype for Business durchgeführt werden, wie Chats und Anrufe vor dem Upgrade auf TeamsOnly.|
|Der Administrator hat die Kontrolle über die für Benutzer verfügbaren Funktionen während des Übergangs von Skype for Business zu Teams verbessert. | |
| Ermöglicht es einer Organisation, Teams für Besprechungen zu verwenden, auch wenn Sie noch nicht bereit ist, vollständig in den TeamsOnly-Modus zu wechseln.||
|Das vorhanden sein eines angegebenen Benutzers, wie er von anderen Personen angezeigt wird, ist derselbe, unabhängig davon, welchen Client er verwendet.||

## <a name="summary-of-upgrade-methods"></a>Zusammenfassung der Upgrade-Methoden
In der folgenden Tabelle sind die Upgrade-Methoden zusammengefasst:


|Überlappende Funktionen (im Modus "Inseln")  |Ausgewählte Funktionen (mit Skype for Business-Modi)  |
|---------|---------|
|Vor dem Upgrade auf TeamsOnly müssen Benutzer beide Clients gleichzeitig ausführen, da eingehende Chats und Anrufe entweder in einem Client landen können.     | Chats und Anrufe landen nur in einem Client, basierend auf dem Modus des Empfängers. Nicht aktualisierte Benutzer können beide Clients ausführen, aber es gibt keine funktionellen Überlappungen (Anrufe und Chats sind in Teams nicht verfügbar).         |
|Ermöglicht Administratoren, überlappende Funktionen (Chats, Besprechungen, VoIP-Anrufe) sowohl in Skype for Business als auch in Teams für Endbenutzer sowie neue Funktionen (Teams und Kanäle) in Teams einzuführen.     | Ermöglicht Administratoren, ausgewählte Funktionen von Teams für Endbenutzer (Teams und Kanäle) einzuführen, ohne dieselben Funktionen bereitzustellen, die auch in Skype for Business vorhanden sind.        |
|Interoperabilität zwischen Skype for Business und Teams ist nicht vorhanden, während sich beide Benutzer im Inseln-Modus befinden.      |Für die Kommunikation zwischen Skype for Business-und Microsoft Teams-Benutzern ist Interoperabilität erforderlich.         |

> [!NOTE]
> Wenn Sie nicht in der Lage sind, die unterstützten Methoden für die Migration Ihrer Skype for Business Server-Benutzer in Teams zu befolgen, können Sie Ihre Benutzer in Teams übertragen, indem Sie Skype for Business Server und alle zugehörigen Benutzerattribute in Active Directory entfernen. Nachdem die Active Directory-Attribute der Benutzer Azure für die Skype for Business Server-Attribute gelöscht wurden und die DNS-Einträge auf Office 365 neu festgesetzt wurden, wäre es dann möglich, die Benutzer in Office 365 zu lizenzieren und auf Teams zu aktualisieren. 

> [!IMPORTANT]
> Mit der Übernahme-Migration werden Kontaktdaten und Besprechungsdaten nicht von der lokalen Umgebung zu Microsoft Teams migriert.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Entscheidungspunkt</td><td><ul> Welche Upgrade-Reise eignet sich für die geschäftlichen Anforderungen Ihrer Organisation?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Nächster Schritt</td><td><ul> Wenn Sie Ihr aktuelles Bereitstellungsmodell, Anwendungsfall Szenarien und wichtige Überlegungen für Ihre Organisation identifizieren, werden Sie die Reise zu Teams informieren, die für Ihre Organisation am besten geeignet sind.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Entscheidungspunkt</td><td><ul> Welches Upgrade-Szenario ist für Ihre Organisation anwendbar?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul> Entscheiden Sie die Zeitachse der Upgrade-Reise Ihrer Organisation auf der Grundlage von Nachrichten, Besprechungen und geschäftlichen Anforderungen für Anrufe.<br><br> Entscheiden Sie, welche zusätzlichen Aufgaben erforderlich sind, um die Upgrade-Reise abzuschließen.<br><br></ul></td></tr>
</table>

Nachdem Sie die beste Upgrade-Reise für Ihre Organisation ausgewählt haben, führen Sie das [Upgrade auf Teams durch](https://aka.ms/SkypeToTeams-Upgrade).
