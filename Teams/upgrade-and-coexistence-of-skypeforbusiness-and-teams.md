---
title: Wählen Sie Ihren Upgradeweg von Skype for Business zu Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl, bjwhalen
description: Details zu Skype for Business und Microsoft Teams Koexistenzoptionen sowie mögliche Upgrademöglichkeiten Teams Szenarien.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsfeatures.upgradetoteamsarticle
- ms.teamsadmincenter.upgradeoverride.learnmore
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: deb64412a96ece539decd8dc2145067a91a1b95f
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2021
ms.locfileid: "61562817"
---
# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Wählen Sie Ihre Upgradereise von Skype for Business Teams

![Upgrade journey diagram, hervorhebt die Project Definitionsphase.](media/upgrade-banner-project-definition.png "Phasen des Upgradeschritts, mit Betonung auf der Stufe Project Definition")

Dieser Artikel ist Teil der Project Phase "Definition" Ihres Upgrades. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](./upgrade-define-project-scope.md)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)

Als bestehender Skype for Business kann der vollständige Übergang zu Teams einige Zeit dauern. Sie können jedoch schon heute damit beginnen, den Wert ihrer Teams zu nutzen, indem Sie Ihren Benutzern ermöglichen, Teams neben Skype for Business. Da es zwischen den beiden Apps überlappende Funktionen gibt, sollten Sie die verfügbaren Koexistenz- und Upgrademodi überprüfen, um zu ermitteln, welcher Pfad für Ihre Organisation am besten ist. Beispielsweise können Sie sich entscheiden, alle Workloads für beide Lösungen ohne Interoperabilität zu aktivieren. Oder Sie entschließen sich, die Benutzeroberfläche zu verwalten, entweder durch schrittweise Einführung von Teams-Funktionen oder indem Sie Benutzergruppen für ausgewählte Funktionen als Zielgruppe festlegen, bis Ihre Organisation bereit ist, für alle Benutzer ein Upgrade auf Teams. Verwenden Sie das Ergebnis Ihres Pilotprojekts, um die richtige Upgradephase für Ihre Organisation zu bewerten.

> [!IMPORTANT]
> Skype for Business Online wurde am 31. Juli 2021 eingestellt. Um den maximalen Nutzen zu erzielen und sicherzustellen, dass Ihre Organisation genügend Zeit hat, Ihr Upgrade durchzuführen, empfehlen wir Ihnen, den Wechsel zu Microsoft Teams bereits heute zu planen.

In diesem Artikel werden die verschiedenen Modi beschrieben, mit denen Sie verwalten können, welche Modalitäten in Skype for Business und Teams Benutzern zur Verfügung stehen. Wie bei jeder Bereitstellung empfehlen [](pilot-essentials.md) wir Ihnen dringend, einen Pilotplan mit einer ausgewählten Gruppe von Benutzern zu planen, bevor Sie Ihre Organisation auf Teams. Denken Sie daran, dass die Einführung neuer Technologien für Benutzer störend sein kann. Nehmen Sie sich vor der Implementierung eines der hier beschriebenen Modi Zeit, um die Benutzerbereitschaft zu bewerten und einen Kommunikations- und Schulungsplan zu implementieren.

> [!TIP]
> Nehmen Sie an Live-, interaktiven Workshops teil, in denen wir Anleitungen, bewährte Methoden und Ressourcen teilen, die als Starthilfe für die Planung und Implementierung von Upgrades entwickelt wurden.
>
>Nehmen Sie zuerst [an der Upgradesitzung](./upgrade-workshops-landing-page.yml) planen teil, um zu beginnen.


## <a name="upgrade-journey-building-blocks"></a>Upgrade von Weg-Bausteinen

Um Ihre Organisation formell auf den Weg zu Teams vorzubereiten, müssen Sie mit der Planung der Upgradeszenarien beginnen, die es Ihrer Organisation schließlich ermöglichen werden, Teams vollständig als Ihre ausschließliche Kommunikations- und Zusammenarbeitslösung zu nutzen.

Um Sie bei der Entscheidungsfindung zu unterstützen, machen Sie sich mit den verschiedenen Modi, Konzepten und Terminologie vertraut, die für das Upgrade von Skype for Business System auf Teams. Weitere Informationen finden Sie [unter Microsoft Teams und Skype for Business Koexistenz und Interoperabilität.](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)

> [!NOTE]
> Sie müssen auch Ihre Szenarien für die Sprachmigration berücksichtigen. Telefonsystem microsoft-Technologie zum Aktivieren von Anrufsteuerung und PBX-Funktionen (Private Branch Exchange) in der Microsoft 365- oder Office 365 Cloud. Wenn Sie Telefonsystem mit dem öffentlichen Telefonnetz (PSTN) verbinden möchten, damit Benutzer auf der ganzen Welt Telefonanrufe telefonieren können, stehen Ihnen Optionen basierend auf Ihren geschäftlichen Anforderungen zur Verfügung. Weitere Informationen zu den Telefonsystem und PSTN-Konnektivitätsoptionen finden Sie unter [Sprach- Telefonsystem und PSTN-Anbindung.](cloud-voice-landing-page.md)

Ein Benutzer, der zu Teams migriert wurde, verwendet keinen Skype for Business-Client mehr, es sei denn, er tritt einer Besprechung bei, die in einem Skype for Business. Alle eingehenden Chats und Anrufe werden im Teams-Client des Benutzers landen, unabhängig davon, ob der Absender Teams oder Skype for Business. Alle neuen Besprechungen, die vom aktualisierten Benutzer organisiert werden, werden als Teams geplant. Wenn der Benutzer versucht, den Skype for Business-Client zu verwenden, wird die Initiierung von Chats und Anrufen<sup>blockiert 1</sup>. Der Benutzer kann (und muss) trotzdem den Skype for Business für Besprechungen verwenden, zu der er eingeladen wurde.

Administratoren verwalten ihren Übergang Teams mit dem Konzept des Modus [,](migration-interop-guidance-for-teams-with-skype.md)das eine Eigenschaft von [TeamsUpgradePolicy ist.](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps&preserve-view=true) Ein Benutzer, der wie oben beschrieben zu Teams migriert wurde, befindet sich im "TeamsOnly"-Modus. Für eine Organisation, die zu einem Teams, besteht das ultimative Ziel in der Umstellung aller Benutzer in den TeamsOnly-Modus.

Es gibt zwei Methoden zum Migrieren einer vorhandenen Organisation mit Skype for Business (online oder lokal) zu Teams:

- **Methode mit** überlappenden Funktionen (mithilfe des Islands-Modus): Benutzer in einer vorhandenen Skype for Business-Organisation werden mit Teams eingeführt, sodass sie beide Clients während einer Einführungsphase nebeneinander verwenden können. Während dieses Zeitraums stehen ihnen die meisten, aber nicht alle Funktionen Teams zur Verfügung. Der Modus für diese Konfiguration wird als "Inseln" bezeichnet, und dies ist der Standardmodus für jede bestehende Organisation mit Skype for Business. Sobald die Organisation bereit ist, verschiebt der Administrator die Benutzer in den TeamsOnly-Modus.

- Methode zum Auswählen von Funktionen **(mithilfe** eines oder mehreren Skype for Business-Modi): Der Administrator verwaltet den Übergang (von Skype for Business zu Teams) von Chat-, Anruf- und Besprechungsplanungsfunktionen für Benutzer in ihrer Organisation. Jede dieser Funktionen ist entweder in einer Skype for Business oder Teams, aber nicht in beiden. Administratoren verwenden TeamsUpgradePolicy, um zu steuern, wann diese Funktionalität für Teams Benutzer verschoben werden soll. Benutzer, die sich noch nicht im TeamsOnly-Modus befinden, verwenden Skype for Business weiterhin für Chats und Anrufe, und die beiden Gruppen von Benutzern können über Inaktivität kommunizieren. Administratoren verwalten den Übergang, indem sie nach und nach weitere Benutzer in den TeamsOnly-Modus migrieren.

<sup>1</sup> Ältere Skype for Business, die vor 2017 versandt wurden, halten TeamsUpgradePolicy nicht ein. Stellen Sie sicher, dass Sie den neuesten Skype for Business verwenden, der in Ihrem Kanal Office ist.

Nachdem Sie ihre Upgrademethode kennen und auswählen, erhalten Sie hier Informationen zu den Tools zum Verwalten des Upgrades Ihrer Organisation auf [Teams.](upgrade-to-teams-on-prem-tools.md)

Unten sind die wichtigsten Faktoren aufgeführt, die bei der Entscheidung für den geeigneten Pfad für Ihre Organisation hilfreich sind.

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Methode für überlappende Funktionen (mithilfe des Islands-Modus)

Mit der Überschneidungsfunktionen-Methode können Benutzer sowohl Teams als auch Skype for Business Clients für Chats, VoIP-Anrufe und Besprechungen verwenden. Bei dieser Methode sind Chat- und VOIP-Anrufe in Teams unternehmensintern ausgerichtet, während Skype for Business Chat- und VOIP-/PSTN-Anrufe mit externen Organisationen (sofern konfiguriert) ermöglicht. Besprechungen können in beiden Produkten geplant und besucht werden.

Bei Verwendung der Methode mit überlappenden Funktionen bleibt der Kommunikationsverkehr für Skype for Business und Teams getrennt (auch für denselben Benutzer), und die beiden verschiedenen Clients kommunizieren niemals miteinander (für Benutzer innerhalb derselben Organisation). Die Benutzeroberfläche basiert auf der Konfiguration des Empfängers. Angenommen, der Empfänger Benutzer A befindet sich im Islands-Modus:

- Kommunikation, die vom Skype for Business eines anderen Benutzers initiiert wurde, landet immer im Client von Benutzer A Skype for Business Client.

- Die vom Teams-Client initiierte Kommunikation von einem Benutzer *in* derselben Organisation wird immer im Client von Benutzer A Teams landen.

- Kommunikation, die Teams einem Benutzer in einer externen Organisation vom Client initiiert *wurde,* landet immer im Client von Benutzer A Skype for Business Client.

Wenn Sie Ihren Benutzern Microsoft 365 oder Office 365 zugewiesen haben, ist dies die standardmäßige Upgradeerfahrung für Ihre Organisation. Wenn Sie eine Lizenz Microsoft 365 oder Office 365, werden Teams und Skype for Business Online-Lizenzen standardmäßig zugewiesen.<sup> 2</sup>

Damit diese Methode effektiv funktioniert, müssen alle Benutzer beide Clients gleichzeitig ausführen. Eingehende Chats und Anrufe von innerhalb der Organisation an einen Benutzer im Islands-Modus können entweder im Skype for Business- oder Teams-Client landen, und dies liegt nicht unter der Kontrolle des Empfängers. Dies hängt davon ab, welchen Client der Absender verwendet, um die Kommunikation zu initiieren. Wenn sich Absender und Empfänger in verschiedenen Organisationen befinden, landen eingehende Anrufe und Chats mit einem Benutzer im Islands-Modus immer im Client Skype for Business Client.

Wenn z. B. ein Empfänger im Islands-Modus bei Skype for Business, aber nicht Teams angemeldet ist und jemand eine Nachricht von Teams erhält, wird die Nachricht des Empfängers im Islands-Modus nicht angezeigt (aber schließlich erhält er eine E-Mail, in der er informiert wird, dass er eine Nachricht in Teams verpasst hat). Ebenso wird der Chat nicht angezeigt, wenn ein benutzer Teams, aber nicht Skype for Business, und eine Person, die von Skype for Business gesendet wird, den Chat nicht sehen. Das Verhalten in jedem dieser Fälle ist beim Aufrufen von ähnlich. Wenn Benutzer nicht beide Clients ausführen, kann dies leicht zu Frustration führen.

Wenn Sie diese Upgrademethode verwenden Teams die Anwesenheitsfunktion Teams und Skype for Business unabhängig voneinander. Dies bedeutet, dass anderen Benutzern je nach verwendeter Client möglicherweise unterschiedliche Anwesenheitszustände für Benutzer A angezeigt werden. Weitere Informationen finden Sie unter [Anwesenheitsinformationen.](teams-and-skypeforbusiness-coexistence-and-interoperability.md#presence)

- Andere Benutzer sehen bei verwendung Teams Anwesenheitsinformationen basierend auf der Aktivität von Benutzer A in Teams.

- Andere Benutzer sehen bei Skype for Business Anwesenheitsinformationen basierend auf der Aktivität von Benutzer A in Skype for Business.

Nachdem Sie bereit sind, Benutzer in den TeamsOnly-Modus zu aktualisieren, können Sie die Benutzer einzeln aktualisieren, oder Sie können den gesamten Mandanten gleichzeitig mit der mandantenweiten Richtlinie<sup>3 aktualisieren.</sup> Nachdem ein Benutzer auf den TeamsOnly-Modus aktualisiert wurde, erhält er alle eingehenden Chats und Anrufe in Teams. (Beachten Sie, dass die Migration von Skype for Business-Besprechungen zu Teams-Besprechungen nur ausgelöst wird, wenn TeamsUpgradePolicy auf einzelne Benutzer und nicht pro Mandant angewendet wird. Details [finden Sie unter Besprechungsmigration.)](upgrade-to-teams-on-prem-tools.md#meeting-migration)

Nicht aktualisierte Empfänger im Islands-Modus empfangen jedoch möglicherweise weiterhin Chats und Anrufe von einem TeamsOnly-Benutzer entweder in seinen Skype for Business oder Teams Clients. Bei bestehenden Unterhaltungen antwortet der TeamsOnly-Benutzer dem Client, von dem der Absender den Chat oder Anruf initiiert hat. 

Für neue Unterhaltungen aus der Sicht des TeamsOnly-Benutzers wird der Chat oder Anruf immer an die Benutzer des Islands-Modus gesendet, Teams haben. Der Grund dafür ist, dass der Teams-Client separate Unterhaltungsthreads für die Kommunikation zwischen Teams-zu-Teams und Teams-to-Skype for Business-Kommunikation verwaltet – sogar für denselben Benutzer. Weitere Informationen finden Sie unter [Teams Unterhaltungen – Inop im Vergleich zu systemeigenen Threads.](teams-and-skypeforbusiness-coexistence-and-interoperability.md#interoperability)

In der folgenden Tabelle sind die Teams für den Islands-Modus und den TeamsOnly-Modus zusammengefasst:

| Teams-Erfahrung | Im Modus "Inseln" | Im TeamsOnly-Modus |
|:------------------ | :------------------- | :------------------ |
| Eingehende Chats und Anrufe, die in empfangen werden:|  Teams oder Skype for Business | Microsoft Teams |
| PstN-Anrufe empfangen in: | Skype for Business <br>(Die Verwendung der PSTN-Teams wird im Islands-Modus nicht unterstützt.)     | Microsoft Teams |   
 |Anwesenheit    | Die Anwesenheit in Skype for Business und Teams ist unabhängig. Je nachdem, welchen Client sie verwenden, werden den Benutzern möglicherweise unterschiedliche Zustände für die gleichen Inseln angezeigt. | Die Anwesenheit basiert ausschließlich auf der Aktivität des Benutzers in Teams. Alle anderen Benutzer sehen diese Anwesenheit, unabhängig davon, welchen Client sie verwenden. | 
 | Besprechungsplanung    | Benutzer können Besprechungen entweder in Teams Besprechungen oder Skype for Business. Standardmäßig werden beide Add-Ins in der Outlook. Sie können eine Teams-Besprechungsrichtlinie festlegen, um zu steuern, ob Benutzer nur das Teams Meeting-Add-In oder beides Teams-Besprechungs- und Skype for Business-Besprechungs-Add-Ins verwenden können. Weitere Informationen finden Sie unter [Festlegen des Besprechungsanbieters für Benutzer im Islands-Modus.](meeting-policies-in-teams-general.md#meeting-provider-for-islands-mode) |     Benutzer planen Besprechungen nur in Teams. Nur das Teams-Add-In ist in der Outlook. | 

In der folgenden Tabelle sind die Vor- und Nachteile der Verwendung der Methode mit überlappenden Funktionen zusammengefasst, um Ihre Organisation zu einem Teams.

| Vorteile     |       Nachteile |
| :------------------ | :---------------- |
| Ermöglicht eine schnelle Akzeptanz innerhalb einer Organisation.| Dies kann zu Verwirrung bei Endbenutzern führen, da es zwei Clients mit ähnlicher Funktionalität, aber unterschiedlichen Benutzeroberflächen gibt. Außerdem haben sie keine Kontrolle darüber, in welchem Client die eingehenden Chats/Anrufe landen. |
| Bietet Benutzern die Möglichkeit, sich mit ihren Teams vertraut zu machen, während sie weiterhin Vollzugriff auf Skype for Business. | Dies kann zu unzufriedenen Endbenutzern aufgrund verpasster Nachrichten führen, wenn der Benutzer nicht beide Clients ausführen kann.|
| Minimaler Verwaltungsaufwand für die ersten Schritte Teams. | Kann schwierig sein, den Modus "Von den Inseln zu verlassen" und in den "TeamsOnly"-Modus zu wechseln, wenn Benutzer und personen, mit denen sie regelmäßig kommunizieren, nicht aktiv mit Teams. Sobald beispielsweise für eine Teilmenge der Benutzer ein Upgrade auf den TeamsOnly-Modus durchgeführt wurde, werden diese Benutzer nur in Teams. Für die restliche Bevölkerung im Islands-Modus landen diese Nachrichten immer auf Teams. Wenn aber einige dieser Bevölkerungsgruppen nicht Teams, werden diese Nachrichten in ihrer Wahrnehmung als verpasst wahr.|
|Ermöglicht Benutzern die Nutzung von Funktionen zur Verbesserung der Teamarbeit, die in Ihrer App nicht Skype for Business.| Ein Benutzer, der Skype for Business lokal und Teams verwendet, kann nicht von Teams aus mit einem anderen Benutzer kommunizieren, der Skype for Business lokal verwendet, aber nicht über Teams.  |
|  | Bei verwendung Teams Benutzer, die über ein lokales Konto in ihrer Skype for Business Server verfügen, über keine Unterstützung für Inop oder einen Verbund.  Dies kann zu Verwirrung führen, wenn Sie über eine Mischung von Benutzern auf den Inseln verfügen, von denen einige in Skype for Business Online und andere Skype for Business sind.   |

<sup>2</sup> Dies gilt auch dann, wenn der Benutzer lokal in einem Skype for Business Server. Unabhängig davon, ob der Benutzer lokal oder online lebt, be lassen Sie die Skype for Business Online-Lizenz aktiviert, da sie derzeit für alle Funktionen Teams wird.

<sup>3</sup> Beachten Sie, dass die Migration von Skype for Business-Besprechungen zu Teams-Besprechungen nur ausgelöst wird, wenn TeamsUpgradePolicy auf einzelne Benutzer angewendet wird, nicht pro Mandant. Details [finden Sie unter Besprechungsmigration.](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>Select capabilities method (using Skype for Business modes)

Manche Organisationen bevorzugen es möglicherweise, den Endbenutzern beim Wechsel ihrer Organisation von einem Skype for Business zu Teams. Bei diesem Modell verwenden IT-Administratoren einen der Skype for Business-Modi in TeamsUpgradePolicy, um explizit zu kennzeichnen, welche Funktionen Skype for Business vor der Migration in den TeamsOnly-Modus verbleiben. Da sie bereit sind, ausgewählte Funktionen in denOnly-Modus zu verschieben, aktualisiert der Administrator den Modus für diese Benutzer auf TeamsOnly. Während dieses Übergangs:

- Administratoren haben die Möglichkeit, bestimmte Funktionen Teams Benutzer zu aktivieren und gleichzeitig Chat- und Anruffunktionen in Skype for Business, bevor Benutzer zur "TeamsOnly"-Erfahrung wechseln. Die Verwaltung kann Teams Zusammenarbeitsfunktionen oder Teams und Zusammenarbeit ermöglichen.

- Benutzer, die sich noch Skype for Business empfangen alle eingehenden Chats und Anrufe in ihrem Skype for Business-Client, unabhängig davon, ob die Kommunikation vom Teams- oder Skype for Business-Client des anderen Benutzers stammt. Darüber hinaus sind für diese Skype for Business-Benutzer die Anruf- und Chatfunktionen im Teams-Client deaktiviert, um Verwirrung bei Endbenutzern zu vermeiden und für ordnungsgemäße Weiterleitung und Anwesenheit zu sorgen.

- Benutzer im TeamsOnly-Modus empfangen alle eingehenden Chats und Anrufe in ihrem Teams-Client und die Anwesenheitsinformationen werden von Teams bereitgestellt, unabhängig davon, woher die Kommunikation stammt: Teams, Skype for Business oder beliebiger Art von Partnerbenutzer.

Im Gegensatz zur Überlappungsfunktionen-Methode (Islands) können Benutzer, die über "Skype for Business"-Funktionen verfügen, in der Methode "Funktionen auswählen" mit Benutzern kommunizieren, die sich in TeamsOnly befinden. Die Kommunikation zwischen einem Skype for Business und einem Teams-Benutzer [](teams-and-skypeforbusiness-coexistence-and-interoperability.md#interoperability) wird als Interoperabilität oder "Interoperabilität" bezeichnet. Die Inop-Kommunikation ist für Chats und Anrufe zwischen einem Benutzer in der Skype for Business und einem anderen Benutzer in einem Teams. Darüber hinaus können eingeladene Benutzer immer entweder an einer Skype for Business- oder Teams-Besprechung teilnehmen, müssen jedoch einen Client verwenden, der dem Besprechungstyp entspricht. Weitere Informationen finden Sie unter [Besprechungen.](teams-and-skypeforbusiness-coexistence-and-interoperability.md#meetings)

Für Benutzer in einer Auswahlfunktionen-Übergangsmethode ist die Anwesenheit für einen Benutzer konsistent, unabhängig davon, welcher Client vom anderen Benutzer verwendet wird. Wenn sich der Benutzer in einem der Skype for Business-Modi befindet, sehen alle anderen Benutzer die Anwesenheitsinformationen basierend auf der Aktivität dieses Benutzers in Skype for Business. Wenn sich ein Benutzer im TeamsOnly-Modus befindet, sehen auch alle anderen Benutzer anwesenheitsbezogene Anwesenheitsinformationen basierend auf der Aktivität dieses Benutzers in Teams. Details finden Sie unter [Anwesenheitsinformationen.](teams-and-skypeforbusiness-coexistence-and-interoperability.md#presence)

Für eine Organisation, die noch nicht mit der Verwendung von Teams begonnen hat, sollte der Administrator den mandantenweiten Modus von Islands in SfbWithTeamsCollab ändern. (Bei Organisationen, die bereits über eine bestimmte Nutzung Teams verfügen, sollte der Administrator Die benutzer, die bereits in Teams aktiv sind, "ein"ein", um sicherzustellen, dass diese Änderung nicht für sie gilt. Weitere Informationen finden Sie unter Eine Methode zum Auswählen von Funktionen für eine Organisation, die bereits Teams [im Islands-Modus verwendet.)](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode) 

Gastbenutzererfahrungen halten sich an den dem Mandanten zugewiesenen Koexistenzmodus. Wenn Sie einen Skype for Business auf Mandantenebene festlegen, können Gäste nicht chatten, anrufen oder ihre Anwesenheit anzeigen. Weitere Informationen finden Sie unter [Gastzugriff in Teams](guest-access.md).

Wenn der Modus von "Islands" in "SfbWithTeamsCollab" geändert wird, sieht ein Benutzer, der noch nie mit Teams verwendet hat, keinen Unterschied in seiner Verwendung Skype for Business. Sollte der Benutzer jedoch mit der Verwendung der Teams beginnen, werden sie nur für Funktionen wie "Teams & Channel" und "Dateien" verfügbar gemacht. Chats, Anrufe und Besprechungen waren in Teams nicht verfügbar, da der Administrator Skype for Business für diese Funktionen (vorerd) als gewünschten Client festgelegt hat.

> [!NOTE]
> Wenn Benutzer A von Islands in einen der Skype for Business-Modi wechselt, muss der Teams-Client jedes anderen Benutzers, der mit Benutzer A kommuniziert, wissen, dass sich der Modus von Benutzer A geändert hat, damit die Kommunikation an den entsprechenden Client für Benutzer A weiter geroutet werden kann. Für alle Benutzer, die bereits native Teams-zu-Teams-Chats mit Benutzer A eingerichtet haben, kann es bis zu 36 Stunden dauern, bis die Teams-Clients dieser Benutzer den Moduswechsel von Islands in einen beliebigen Skype for Business-Modus kennen. Im Gegensatz dazu werden Änderungen für einen vorhandenen Benutzer in den TeamsOnly-Modus von anderen Clients innerhalb von 2 Stunden ermittelt.<br>
> Wenn Administratoren bereit sind, können sie chatten, Anrufe und Die Besprechungsplanung für einen bestimmten Benutzer verschieben, um Teams auf einmal zu starten, indem der Benutzermodus auf TeamsOnly aktualisiert wird.

Alternativ kann der Administrator zunächst nur die Besprechungsplanung auf Teams verschieben, während die Chat- und Anruffunktionen im Skype for Business sfBWithTeamsCollabAndMeetings-Modus verlassen werden. Dieser Modus ermöglicht Organisationen den Umstieg auf Teams für Besprechungen – wenn Benutzer noch nicht bereit sind, in den TeamsOnly-Modus zu wechseln (z. B. wenn Sie noch nicht bereit sind, vorhandene PSTN-Funktionen zu migrieren). Dieses häufige Szenario wird als ["Meetings First" bezeichnet.](meetings-first.md)


|Teams-Erfahrung  |Im SfBWithTeamsCollab-Modus |Im SfBWithTeamsCollabAndMeetings-Modus |Im TeamsOnly-Modus  |
|---------|---------|---------|---------|
|Eingehende Chats und VOIP-Anrufe von Benutzern in Ihrer Organisation, die empfangen wurden:     | Skype for Business        | Skype for Business       | Microsoft Teams        |
|PstN-Anrufe empfangen in:     | Skype for Business        |Skype for Business         | Microsoft Teams        |
|Anwesenheit     | Skype for Business        |Skype for Business         | Microsoft Teams        |
|Besprechungsplanung     | Skype for Business         | Microsoft Teams        | Microsoft Teams        |


In der folgenden Tabelle sind die Vor- und Nachteile der Verwendung Skype for Business-Modi als ein wichtiger Schritt zum TeamsOnly-Modus zusammengefasst.

| Vorteile     |       Nachteile |
| :------------------ | :---------------- |
| Vorhersehbares Routing für den Endbenutzer. Alle Anrufe und Chats landen entweder im Skype for Business oder Teams (aber nicht beide), basierend auf der Auswahl durch den Administrator.|Inop-Unterhaltungen unterstützen keine Rich-Text-, Dateifreigabe- und Bildschirmfreigabe. Dies kann durch Nutzen der Funktion "Jetzt besprechungen" zum Initiieren einer Besprechung initiieren werden. |
|Dies kann zu Verwirrung bei Endbenutzern führen, da eine bestimmte Funktion nur in einem Client verfügbar ist. | Bevor Benutzer ein Upgrade auf TeamsOnly vorgenommen haben, haben sie keinen Zugriff auf Teams allgemeinen Aktivitäten, die in Skype for Business wie Chats und Anrufen ausgeführt werden. Dies bedeutet, dass keine Funktion zur Seite nebeneinander ist.|
|Der Administrator hat die Kontrolle über die Funktionen, die Benutzern während des Übergangs vom Computer Skype for Business Teams. Dieses Steuerelement bietet die Möglichkeit zur inkrementellen Einführung Teams Funktionen. | |
| Ermöglicht einer Organisation die Verwendung von Teams für Besprechungen, auch wenn der Wechsel in den TeamsOnly-Modus noch nicht abgeschlossen ist.||
|Die Anwesenheit eines bestimmten Benutzers, der von anderen angezeigt wird, ist identisch, unabhängig davon, welchen Client er verwendet.||

## <a name="summary-of-upgrade-methods"></a>Zusammenfassung der Upgrademethoden
In der folgenden Tabelle sind die Upgrademethoden zusammengefasst:


|Überlappende Funktionen (mithilfe des Islands-Modus)  |Ausgewählte Funktionen (mithilfe Skype for Business Modi)  |
|---------|---------|
|Vor dem Upgrade auf TeamsOnly müssen Benutzer beide Clients gleichzeitig ausführen, da eingehende Chats und Anrufe in beiden Clients landen können.     | Chats und Anrufe werden basierend auf dem Modus des Empfängers nur in einem Client landen. Benutzer ohne Upgrade können beide Clients ausführen, es gibt jedoch keine Funktionsüberlappung (Anrufe und Chats sind in der Teams). Administratoren können auch steuern, ob Benutzer Besprechungen in einem Teams oder Skype for Business.         |
|Ermöglicht Es Administratoren, sich überlappende Funktionen (Chats, Besprechungen, VOIP-Anrufe) sowohl in Skype for Business als auch Teams für Endbenutzer (die Funktionen nebeneinander verfügbar machen) sowie neue Funktionen (Teams und Kanäle) in Teams bereitzustellen.     | Ermöglicht Administratoren das Einführen ausgewählter Funktionen von Teams für Endbenutzer (Teams und Kanäle), ohne dieselbe Funktionalität bereitzustellen, die auch in Skype for Business.        |
|Die Inaktivität Skype for Business und Teams ist nicht vorhanden, während sich beide Benutzer im Islands-Modus befinden. Nachdem ein Upgrade für einige Benutzer auf Teams durchgeführt wurdeOnely Interop conversation may occur between those users and others users who are still in Islands mode. Die Benutzer der Inseln konnten sich jedoch entscheiden, Teams zu verwenden und die Ininteop-Unterhaltung zu vermeiden.      |Die Inaktivität ist für die Kommunikation zwischen Skype for Business und Teams Benutzern erforderlich.         |

> [!NOTE]
> Wenn Sie die unterstützten Methoden zum Migrieren Ihrer Skype for Business Server-Benutzer zu Teams nicht befolgen können, können Sie Ihre Benutzer auf Teams umstiegen, indem Sie Skype for Business Server und alle zugehörigen Benutzerattribute in Active Directory entfernen. Sobald die Azure Active Directory-Attribute der Benutzer von den Skype for Business Server-Attributen und DNS-Einträgen wieder auf Microsoft 365 oder Office 365 verwiesen wurden, wäre es dann möglich, die Benutzer unter Microsoft 365 oder Office 365, und führen Sie ein Upgrade auf Teams. 

> [!IMPORTANT]
> Bei der Umstellung werden Kontaktdaten und Besprechungsdaten nicht aus der lokalen Umgebung in die Lokale Microsoft Teams.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Entscheidungspunkt</td><td><ul> Welcher Upgradeweg eignet sich für die geschäftlichen Anforderungen Ihrer Organisation?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Nächster Schritt</td><td><ul> Das Identifizieren des aktuellen Bereitstellungsmodells, die Verwendung von Fallszenarien und wichtige Überlegungen für Ihre Organisation sind entscheidend für die Teams, die für Ihre Organisation am besten geeignet sind.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Entscheidungspunkt</td><td><ul> Welches Upgradeszenario gilt für Ihre Organisation?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul> Entscheiden Sie die Zeitskala für die Upgradezeit Ihrer Organisation basierend auf den Geschäftsanforderungen für Nachrichten, Besprechungen und Anrufe.<br><br> Entscheiden Sie, welche zusätzlichen Arbeiten erforderlich sind, um ihr Upgrade zu abschließen.<br><br></ul></td></tr>
</table>

Nachdem Sie das beste Upgrade für Ihre Organisation ausgewählt haben, führen Sie [Ihr Upgrade für Teams](./upgrade-to-teams.md)aus.

## <a name="related-links"></a>Links zu verwandten Themen

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps&preserve-view=true)

[Verwenden des Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)