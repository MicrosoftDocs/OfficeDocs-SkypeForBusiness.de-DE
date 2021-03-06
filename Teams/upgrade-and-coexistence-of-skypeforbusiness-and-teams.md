---
title: Wählen Sie Ihre Upgradereise von Skype for Business zu Microsoft Teams aus.
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl, bjwhalen
description: Details zu den Optionen für die Koexistenz von Skype for Business und Microsoft Teams sowie zu möglichen Upgradewegen zu Teams mit Beispielszenarien.
localization_priority: Normal
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
ms.openlocfilehash: a81b34bb028d81e7a79d771db7f0f406af364011
ms.sourcegitcommit: 79b19b326ef40bf04af03021a7c6506fdd9417ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2021
ms.locfileid: "50397420"
---
# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Wählen Sie Ihre Upgradereise von Skype for Business zu Teams aus.

![Upgrade des Reisediagramms, Hervorhebung der Projektdefinitionsphase](media/upgrade-banner-project-definition.png "Phasen des Upgradewegs mit Schwerpunkt auf der Projektdefinitionsphase")

Dieser Artikel ist Teil der Projektdefinitionsphase Ihrer Upgradereise. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](https://aka.ms/SkypetoTeams-Scope)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](https://aka.ms/SkypeToTeams-Coexist)

Als vorhandener Skype for Business-Kunde kann der vollständige Übergang zu Teams einige Zeit in Die Zeit dauern. Sie können jedoch damit beginnen, den Wert von Teams heute zu nutzen, indem Sie Ihren Benutzern die Verwendung von Teams zusammen mit Skype for Business ermöglichen. Da zwischen den beiden Apps überlappende Funktionen vorhanden sind, empfiehlt es sich, die verfügbaren Koexistenz- und Upgrademodi zu überprüfen, um festzustellen, welcher Pfad für Ihre Organisation richtig ist. Sie können beispielsweise alle Workloads für beide Lösungen ohne Interoperabilität aktivieren. Oder Sie können sich entscheiden, die Benutzererfahrung zu verwalten, indem Sie entweder schrittweise Teams-Funktionen einführen oder Benutzergruppen für ausgewählte Funktionen festlegen, bis Ihre Organisation bereit ist, ein Upgrade aller Benutzer auf Teams durchführen zu können. Verwenden Sie das Ergebnis Ihres Pilotprojekts, um den richtigen Upgradeweg für Ihre Organisation zu bewerten.

> [!IMPORTANT]
> Skype for Business Online wird am 31. Juli 2021 eingestellt. Ab diesem Zeitpunkt kann nicht mehr darauf zugegriffen werden, und es wird nicht mehr unterstützt. Um den maximalen Nutzen zu erzielen und sicherzustellen, dass Ihre Organisation genügend Zeit hat, Ihr Upgrade durchzuführen, empfehlen wir Ihnen, den Wechsel zu Microsoft Teams bereits heute zu planen.

In diesem Artikel werden die verschiedenen Modi beschrieben, mit denen Sie verwalten können, welche Modalitäten in Skype for Business und Teams für Ihre Benutzer verfügbar sind. Wie bei jeder Bereitstellung empfehlen [](pilot-essentials.md) wir Ihnen dringend, Ihren beabsichtigten Plan mit einer ausgewählten Gruppe von Benutzern zu piloten, bevor Sie Ihr Unternehmen auf Teams aktualisieren. Denken Sie daran, dass die Einführung neuer Technologien für Benutzer störend sein kann. Nehmen Sie sich Zeit, um die Benutzerbereitschaft zu bewerten und einen Kommunikations- und Schulungsplan zu implementieren, bevor Sie einen der hier beschriebenen Modi implementieren.

> [!TIP]
> Nehmen Sie an interaktiven Liveworkshops teil, in denen wir Ihnen Anleitungen, bewährte Methoden und Ressourcen für den Einstieg in die Upgradeplanung und -implementierung bieten.
>
>Nehmen Sie [zuerst an der Upgradesitzung](https://aka.ms/SkypeToTeamsPlanning) planen teil, um zu beginnen.


## <a name="upgrade-journey-building-blocks"></a>Upgrade von Reisebausteinen

Um Ihre Organisation auf den Weg zu Teams formal vorzubereiten, müssen Sie mit der Planung der Upgradeszenarien beginnen, die es Ihrer Organisation schließlich ermöglichen, Teams vollständig als Ihre einzige Kommunikations- und Zusammenarbeitslösung zu nutzen.

Um Ihnen bei der Entscheidungsfindung zu helfen, machen Sie sich mit den verschiedenen Modi, Konzepten und Terminologie vertraut, die für ein Upgrade von Skype for Business auf Teams relevant sind. Weitere Informationen finden Sie unter [Koexistenz und](https://aka.ms/SkypeToTeams-Coexist)Interoperabilität von Microsoft Teams und Skype for Business.

> [!NOTE]
> Sie müssen auch Ihre Sprachmigrationsszenarien berücksichtigen. Telefonsystem ist die Technologie von Microsoft zum Aktivieren von Anrufsteuerung und PbX (Private Branch Exchange) in der Microsoft 365- oder Office 365-Cloud. Um Telefonsystem mit dem öffentlichen Telefonnetz (Public Switched Telephone Network, PSTN) zu verbinden, damit Benutzer auf der ganzen Welt Telefonanrufe machen können, haben Sie Optionen, die auf Ihren geschäftlichen Anforderungen basieren. Weitere Informationen zu den Optionen für Telefonsystem- und PSTN-Konnektivität finden Sie unter [Voice – Telefonsystem- und PSTN-Konnektivität.](cloud-voice-landing-page.md)

Ein Benutzer, der zu Teams migriert wurde, verwendet keinen Skype for Business-Client mehr, außer an einer in Skype for Business gehosteten Besprechung teil zu nehmen. Alle eingehenden Chats und Anrufe landen im Teams-Client des Benutzers, unabhängig davon, ob der Absender Teams oder Skype for Business verwendet. Alle neuen Besprechungen, die vom aktualisierten Benutzer organisiert werden, werden als Teams-Besprechungen geplant. Wenn der Benutzer versucht, den Skype for Business-Client zu verwenden, wird die Initiierung von Chats und Anrufen<sup>blockiert 1</sup>. Der Benutzer kann (und muss) jedoch den Skype for Business-Client verwenden, um an Besprechungen teilzunehmen, zu der er eingeladen ist.

Administratoren verwalten den Übergang zu Teams mithilfe des Moduskonzepts [,](migration-interop-guidance-for-teams-with-skype.md)das eine Eigenschaft von [TeamsUpgradePolicy ist.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) Ein Benutzer, der wie oben beschrieben zu Teams migriert wurde, befindet sich im Modus "TeamsOnly". Für eine Organisation, die zu Teams migriert wird, besteht das ultimative Ziel in der Umstellung aller Benutzer in den TeamsOnly-Modus.

Es gibt zwei Methoden zum Migrieren einer vorhandenen Organisation mit Skype for Business (online oder lokal) zu Teams:

- **Methode für** überlappende Funktionen (im Inselmodus): Benutzer in einer vorhandenen Skype for Business-Organisation werden in Teams eingeführt, sodass sie beide Clients während einer Übergangsphase nebeneinander verwenden können. Während dieses Zeitraums steht ihnen die meiste -, aber nicht alle Funktionen von Teams zur Verfügung. Der Modus für diese Konfiguration wird als Inseln bezeichnet, und dies ist der Standardmodus für jede vorhandene Organisation mit Skype for Business. Sobald die Organisation bereit ist, verschiebt der Administrator die Benutzer in den TeamsOnly-Modus.

- **Methode** zum Auswählen von Funktionen (mit einem oder mehreren Skype for Business-Modi): Der Administrator verwaltet den Übergang (von Skype for Business zu Teams) von Chat-, Anruf- und Besprechungsplanungsfunktionen für Benutzer in ihrer Organisation. Jede dieser Funktionen steht entweder in Skype for Business oder Teams zur Verfügung, aber nicht beide Funktionen. Administratoren verwenden TeamsUpgradePolicy, um zu steuern, wann diese Funktionalität für ihre Benutzer in Teams verschoben werden soll. Benutzer, die sich noch nicht im TeamsOnly-Modus befinden, verwenden Skype for Business weiterhin für Chats und Anrufe, und die beiden Benutzergruppen können über Inopfunktionen kommunizieren. Administratoren verwalten den Übergang, indem mehr Benutzer schrittweise in den TeamsOnly-Modus migriert werden.

<sup>1</sup> Ältere Skype for Business-Clients, die vor 2017 versendet wurden, würdigen TeamsUpgradePolicy nicht. Stellen Sie sicher, dass Sie den neuesten Skype for Business-Client verwenden, der in Ihrem Office-Kanal verfügbar ist.

Nachdem Sie Die Upgrademethode kennen und auswählen, erfahren Sie mehr über die Tools zum Verwalten des Upgrades Ihrer Organisation [auf Teams.](upgrade-to-teams-on-prem-tools.md)

Im Folgenden sind die wichtigsten Faktoren aufgeführt, die Ihnen bei der Entscheidung des geeigneten Pfads für Ihre Organisation helfen.

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Methode für überlappende Funktionen (im Inselmodus)

Mit der Methode für überlappende Funktionen können Benutzer sowohl Teams- als auch Skype for Business-Clients für Chats, VoIP-Anrufe und Besprechungen verwenden. Bei dieser Methode sind Chat- und VOIP-Anrufe in Teams organisationsintern ausgerichtet, während Skype for Business Chat- und VOIP-/PSTN-Anrufe mit externen Organisationen (sofern konfiguriert) ermöglicht. Besprechungen können in beiden Produkten geplant und besucht werden.

Bei Verwendung der Methode für überlappende Funktionen bleibt der Kommunikationsverkehr für Skype for Business und Teams getrennt (auch für denselben Benutzer), und die beiden verschiedenen Clients kommunizieren nie miteinander (für Benutzer innerhalb derselben Organisation). Die Benutzererfahrung basiert auf der Konfiguration des Empfängers. Angenommen, Der Empfänger Benutzer A befindet sich im Inselmodus:

- Die vom Skype for Business-Client eines anderen Benutzers initiierte Kommunikation wird immer im Skype for Business-Client von Benutzer A angezeigt.

- Kommunikation, die vom Teamclient von einem Benutzer *in* derselben Organisation initiiert wird, wird immer im Teams-Client von Benutzer A angezeigt.

- Die kommunikation, die von einem Benutzer *in* einer externen Organisation vom Teams-Client initiiert wurde, wird immer im Skype for Business-Client von Benutzer A angezeigt.

Wenn Sie Ihren Benutzern eine Microsoft 365- oder Office 365-Lizenz zugewiesen haben, ist dies die Standardaktualisierungserfahrung für Ihre Organisation. Wenn Sie eine Microsoft 365- oder Office 365-Lizenz zuweisen, werden standardmäßig sowohl Teams- als auch Skype for Business Online-Lizenzen zugewiesen. <sup>2</sup>

Damit diese Methode effektiv funktioniert, müssen alle Benutzer beide Clients gleichzeitig ausführen. Eingehende Chats und Anrufe von innerhalb der Organisation an einen Benutzer im Inselmodus können entweder im Skype for Business- oder Teams-Client landen – und dies befindet sich nicht unter der Kontrolle des Empfängers. Dies hängt davon ab, welchen Client der Absender zum Initiieren der Kommunikation verwendet. Wenn sich Absender und Empfänger in verschiedenen Organisationen befinden, landen eingehende Anrufe und Chats für einen Benutzer im Inselmodus immer im Skype for Business-Client.

Wenn z. B. ein Empfänger des Islands-Modus bei Skype for Business, aber nicht bei Teams angemeldet ist und jemand ihn von Teams aus benachrichtigt, wird die Nachricht für den Empfänger des Islands-Modus nicht angezeigt (schließlich erhält er jedoch eine E-Mail, in der er anknah, dass er eine Nachricht in Teams verpasst hat). Ebenso wird dieser Chat nicht angezeigt, wenn ein Benutzer Teams, aber nicht Skype for Business ausgeführt hat, und eine andere Person nachrichten, die der Benutzer von Skype for Business aus gesendet hat. Das Verhalten in jedem dieser Fälle ist für Aufrufe ähnlich. Wenn Benutzer nicht beide Clients ausführen, kann dies leicht zu Frust führen.

Die Anwesenheit funktioniert auch unabhängig zwischen Teams und Skype for Business, wenn Sie diese Upgrademethode verwenden. Dies bedeutet, dass andere Benutzer je nach verwendeten Client unterschiedliche Anwesenheitszustände für Benutzer A sehen können. Weitere Informationen finden Sie unter [Anwesenheit](teams-and-skypeforbusiness-coexistence-and-interoperability.md#presence).

- Andere Benutzer sehen bei Verwendung von Teams die Anwesenheitsinformationen basierend auf den Aktivitäten von Benutzer A in Teams.

- Andere Benutzer sehen bei der Verwendung von Skype for Business die Anwesenheitsinformationen basierend auf den Aktivitäten von Benutzer A in Skype for Business.

Sobald Sie bereit sind, ein Upgrade von Benutzern auf den TeamsOnly-Modus durchführen zu können, können Sie die Benutzer einzeln aktualisieren, oder Sie können den gesamten Mandanten gleichzeitig mit der mandantenweiten Richtlinie<sup>3 aktualisieren.</sup> Sobald ein Benutzer ein Upgrade auf den TeamsOnly-Modus durchgeführt hat, erhält er alle eingehenden Chats und Anrufe in Teams. (Beachten Sie, dass die Migration von Skype for Business-Besprechungen zu Teams-Besprechungen nur ausgelöst wird, wenn TeamsUpgradePolicy auf einzelne Benutzer angewendet wird, nicht pro Mandant. Details [finden Sie unter Besprechungsmigration.)](upgrade-to-teams-on-prem-tools.md#meeting-migration)

Nicht aktualisierte Empfänger im Inselmodus können jedoch weiterhin Chats und Anrufe von einem TeamsOnly-Benutzer in seinen Skype for Business- oder Teams-Clients empfangen. Bei vorhandenen Unterhaltungen antwortet der TeamsOnly-Benutzer dem Client, von dem der Absender den Chat oder Anruf initiiert hat. 

Für neue Unterhaltungen aus Sicht des TeamsOnly-Benutzers wird der Chat oder Anruf immer zum Teams-Client des Benutzer-Teams im Islands-Modus geführt. Der Grund dafür ist, dass der Teams-Client separate Unterhaltungsthreads für Teams-zu-Teams und Teams-to-Skype for Business-Kommunikation verwaltet, auch für denselben Benutzer. Weitere Informationen finden Sie unter [Teams-Unterhaltungen – In- und Systemthreads.](teams-and-skypeforbusiness-coexistence-and-interoperability.md#interoperability)

In der folgenden Tabelle ist die Teams-Erfahrung für den Inselmodus und den TeamsOnly-Modus zusammengefasst:

| Teamerfahrung | Im Modus "Inseln" | Im TeamsOnly-Modus |
|:------------------ | :------------------- | :------------------ |
| Eingehende Chats und Empfangene Anrufe in:|  Teams oder Skype for Business | Teams |
| Empfangene PSTN-Anrufe in: | Skype for Business <br>(Die Verwendung von PSTN-Funktionen in Teams wird im Inselmodus nicht unterstützt.)     | Teams |   
 |Anwesenheit    | Die Anwesenheit in Skype for Business und Teams ist unabhängig. Je nachdem, welchen Client sie verwenden, werden den Benutzern möglicherweise unterschiedliche Zustände für denselben Benutzer angezeigt. | Die Anwesenheit basiert ausschließlich auf der Aktivität des Benutzers in Teams. Alle anderen Benutzer sehen diese Anwesenheit, unabhängig davon, welchen Client sie verwenden. | 
 | Besprechungsplanung    | Benutzer können Besprechungen in Teams oder Skype for Business planen. Standardmäßig werden beide Add-Ins in Outlook angezeigt. Sie können eine Teams-Besprechungsrichtlinie festlegen, um zu steuern, ob Benutzer nur das Teams Meeting-Add-In oder die Teams Meeting- und Skype for Business-Besprechungs-Add-Ins verwenden können. Weitere Informationen finden Sie unter [Festlegen des Besprechungsanbieters für Benutzer im Inselmodus.](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode) |     Benutzer planen nur Besprechungen in Teams. Nur das Teams-Add-In ist in Outlook verfügbar. | 

In der folgenden Tabelle sind die Vor- und Nachteile der Verwendung der Methode für überlappende Funktionen zum Migrieren Ihrer Organisation zu Teams zusammengefasst.

| Vorteile     |       Nachteile |
| :------------------ | :---------------- |
| Ermöglicht eine schnelle Einführung innerhalb einer Organisation.| Potenzielle Verwirrung bei Endbenutzern, da es zwei Clients mit ähnlicher Funktionalität, aber unterschiedlichen Benutzeroberflächen gibt. Außerdem haben sie keine Kontrolle darüber, in welchem Client die eingehenden Chats/Anrufe landen. |
| Ermöglicht Benutzern, Teams kennen zu lernen und sich mit Ihnen vertraut zu machen, während sie weiterhin voll auf Skype for Business zugreifen können. | Potenzieller Grund für unzufriedene Endbenutzer aufgrund verpasster Nachrichten, wenn der Benutzer nicht beide Clients ausgeführt hat.|
| Minimaler Verwaltungsaufwand für die ersten Schritte in Teams. | Kann schwierig sein, den Modus "Aus den Inseln" zu verlassen und in den TeamsOnly-Modus zu wechseln, wenn Benutzer und personen, mit denen sie regelmäßig kommunizieren, Teams nicht aktiv verwenden. Wenn beispielsweise eine Teilmenge der Benutzer auf den TeamsOnly-Modus aktualisiert wurde, werden diese Benutzer nur in Teams gesendet. Für die restliche Bevölkerung im Inselmodus werden diese Nachrichten immer in Teams angezeigt. Wenn jedoch einige dieser Bevölkerungsgruppen Teams nicht ausführen, werden diese Nachrichten als verpasst wahrgenommen.|
|Ermöglicht Benutzern die Nutzung von Funktionen, um die Teamarbeit zu verbessern, die in Skype for Business nicht verfügbar sind.| Ein Benutzer, der Skype for Business lokal und Teams verwendet, kann nicht von Teams aus mit einem anderen Benutzer kommunizieren, der Skype for Business lokal verwendet, aber nicht über Teams verfügt.  |
|  | Bei verwendung von Teams verfügen Benutzer, die über ein lokales Konto in Skype for Business Server verfügen, nicht über In-App- oder Verbundunterstützung.  Dies kann potenziell zu Verwirrung führen, wenn Sie über eine Mischung aus Benutzer auf Inseln verfügen– einige, die in Skype for Business Online und einige in Skype for Business lokal zu Hause sind.   |

<sup>2</sup> Dies gilt auch dann, wenn der Benutzer lokal in Skype for Business Server zu Hause ist. Unabhängig davon, ob der Benutzer lokal oder online zu Hause ist, lassen Sie die Skype for Business Online-Lizenz aktiviert, da sie zurzeit für die vollständige Funktionalität von Teams benötigt wird.

<sup>3</sup> Beachten Sie, dass die Migration von Skype for Business-Besprechungen zu Teams-Besprechungen nur ausgelöst wird, wenn TeamsUpgradePolicy auf einzelne Benutzer angewendet wird, nicht pro Mandant. Details [finden Sie unter Besprechungsmigration.](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>Select capabilities method (using Skype for Business modes)

Einige Organisationen möchten ihren Endbenutzern möglicherweise eine vorhersehbare Benutzererfahrung bieten, wenn ihre Organisation von Skype for Business zu Teams überwechselt. In diesem Modell verwenden IT-Administratoren einen der Skype for Business-Modi in TeamsUpgradePolicy, um explizit zu bestimmen, welche Funktionen vor der Migration in den TeamsOnly-Modus in Skype for Business verbleiben. Wenn sie bereit sind, ausgewählte Funktionen in den TeamsOnly-Modus zu verschieben, aktualisiert der Administrator den Modus für diese Benutzer auf TeamsOnly. Während dieses Übergangs:

- Administratoren haben Optionen, um bestimmte Teams-Funktionen für Benutzer zu aktivieren, während Chat- und Anruffunktionen in Skype for Business erhalten bleiben, bevor Benutzer zu TeamsOnly-Benutzererfahrung wechseln. Die Verwaltung kann Teams-Zusammenarbeitsfunktionen oder Teams-Besprechungen + Zusammenarbeitsfunktionen aktivieren.

- Benutzer, die skype for Business weiterhin nutzen, erhalten alle eingehenden Chats und Anrufe in ihrem Skype for Business-Client, unabhängig davon, ob die Kommunikation vom Team- oder Skype for Business-Client des anderen Benutzers stammt. Darüber hinaus werden für diese Skype for Business-Benutzer die Funktionen für Anrufe und Chats im Teams-Client deaktiviert, um Verwirrung zwischen Endbenutzern zu vermeiden und eine ordnungsgemäße Weiterleitung und Anwesenheit sicherzustellen.

- Benutzer im TeamsOnly-Modus empfangen alle eingehenden Chats und Anrufe in ihrem Teams-Client, und die Anwesenheitsinformationen werden von Teams bereitgestellt, unabhängig davon, woher die Kommunikation stammt: Teams, Skype for Business oder jede Art von Verbundbenutzer.

Im Gegensatz zur Methode für überlappende Funktionen (Islands) können Benutzer, die Skype for Business verwenden, in der Auswahlfunktionenmethode mit Benutzern kommunizieren, die sich in TeamsOnly befinden. Die Kommunikation zwischen einem Skype for Business-Benutzer und einem Teams-Benutzer wird als [Interoperabilität oder](teams-and-skypeforbusiness-coexistence-and-interoperability.md#interoperability) "Interoperabilität" bezeichnet. Die In-App-Kommunikation ist für Chats und Anrufe zwischen einem Benutzer in Skype for Business und einem anderen Benutzer in Teams 1:1 möglich. Darüber hinaus können eingeladene Benutzer immer an einer Skype for Business- oder Teams-Besprechung teilnehmen, müssen jedoch einen Client verwenden, der dem Typ der Besprechung entspricht. Weitere Informationen finden Sie unter [Besprechungen](teams-and-skypeforbusiness-coexistence-and-interoperability.md#meetings).

Für Benutzer in einer Übergangsmethode für Auswahlfunktionen ist die Anwesenheitsinformationen für einen Benutzer konsistent, unabhängig davon, welcher Client vom anderen Benutzer verwendet wird. Wenn sich der Benutzer in einem der Skype for Business-Modi befindet, wird für alle anderen Benutzer die Anwesenheitsinformationen basierend auf den Aktivitäten dieses Benutzers in Skype for Business angezeigt. Wenn sich ein Benutzer im TeamsOnly-Modus befindet, wird für alle anderen Benutzer die Anwesenheitsinformationen basierend auf der Aktivität dieses Benutzers in Teams angezeigt. Details finden Sie unter [Anwesenheit](teams-and-skypeforbusiness-coexistence-and-interoperability.md#presence).

Für eine Organisation, die noch nicht mit der Verwendung von Teams begonnen hat, sollte der Administrator den mandantenweiten Modus von "Islands" in "SfbWithTeamsCollab" ändern. (Für Organisationen, die bereits über eine gewisse Nutzung von Teams verfügen, sollte der Administrator bereits in Teams aktive Benutzer "unterstützen", um sicherzustellen, dass diese Änderung nicht für sie gilt. Einzelheiten finden Sie unter [Eine Auswahlfunktionenmethode für eine Organisation,](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)die Teams bereits im Inselmodus verwendet.) 

Benutzererfahrungen von Gästen halten sich an den dem Mandanten zugewiesenen Koexistenzmodus. Wenn Sie einen Skype for Business-Modus auf Mandantenebene festlegen, können Gäste nicht chatten, anrufen oder ihre Anwesenheitspräsenz anzeigen. Weitere Informationen finden Sie unter [Gastzugriff in Teams](guest-access.md).

Wenn der Modus von "Islands" in "SfbWithTeamsCollab" geändert wird, sieht ein Benutzer, der Noch nie Teams verwendet hat, keinen Unterschied in der Verwendung von Skype for Business. Sollte dieser Benutzer jedoch mit der Verwendung von Teams beginnen, wäre er nur für Funktionen wie Teams & Kanal und Dateien verfügbar. Chats, Anrufe und Besprechungsplanungen wären in Teams nicht verfügbar, da der Administrator Skype for Business (derzeit) als gewünschten Client für diese Funktionen festgelegt hat.

> [!NOTE]
> Wenn Benutzer A von Islands in einen der Skype for Business-Modi wechselt, muss der Teams-Client jedes anderen Benutzers, der mit Benutzer A kommuniziert, wissen, dass sich der Modus von Benutzer A geändert hat, damit er die Kommunikation an den geeigneten Client für Benutzer A weiterweisen kann. Für alle Benutzer, die bereits native Teams-to-Teams-Chats mit Benutzer A eingerichtet haben, kann es bis zu 36 Stunden dauern, bis die Teams-Clients dieser anderen Benutzer über den Moduswechsel von "Inseln" in einen beliebigen Skype for Business-Modus verfügen. Im Gegensatz dazu werden Änderungen für einen vorhandenen Benutzer im TeamsOnly-Modus von anderen Clients innerhalb von 2 Stunden erkannt.<br>
> Wenn Administratoren bereit sind, können sie Chats, Anrufe und Besprechungsplanungen für einen bestimmten Benutzer auf einmal zu Teams verschieben, indem sie den Modus des Benutzers auf TeamsOnly aktualisieren.

Alternativ kann der Administrator zunächst nur die Besprechungsplanung auf Teams verschieben, während Chat- und Anruffunktionen in Skype for Business über den SfBWithTeamsCollabAndMeetings-Modus verlassen werden. Dieser Modus ermöglicht Organisationen den Wechsel zu Teams für Besprechungen – wenn Benutzer noch nicht bereit sind, in den TeamsOnly-Modus zu wechseln (z. B. wenn Sie noch nicht bereit sind, vorhandene PSTN-Funktionen zu migrieren). Dieses Übergangsszenario wird als ["Erste Besprechungen" bezeichnet.](meetings-first.md)


|Teamerfahrung  |Im SfBWithTeamsCollab-Modus |Im SfBWithTeamsCollabAndMeetings-Modus |Im TeamsOnly-Modus  |
|---------|---------|---------|---------|
|Eingehende Chats und VOIP-Anrufe von Benutzern in Ihrer Organisation, die in empfangen wurden:     | Skype for Business        | Skype for Business       | Teams        |
|Empfangene PSTN-Anrufe in:     | Skype for Business        |Skype for Business         | Teams        |
|Anwesenheit     | Skype for Business        |Skype for Business         | Teams        |
|Besprechungsplanung     | Skype for Business         | Microsoft Teams        | Microsoft Teams        |


In der folgenden Tabelle sind die Vor- und Nachteile der Verwendung von Skype for Business-Modi als Übergangsschritt zum TeamsOnly-Modus zusammengefasst.

| Vorteile     |       Nachteile |
| :------------------ | :---------------- |
| Vorhersagbares Routing für den Endbenutzer. Alle Anrufe und Chats landen entweder in Skype for Business oder Teams (aber nicht beides), basierend auf der Administratorauswahl.|Inopopunterhaltungen unterstützen keine Rich-Text-, Dateifreigabe- und Bildschirmfreigabe. Dies kann mit der Nutzung der Funktion "Jetzt treffen" zum Initiieren einer Besprechung umgearbeitet werden. |
|Kann die Verwirrung der Endbenutzer verringern, da eine bestimmte Funktionalität nur in einem Client verfügbar ist. | Bevor Benutzer ein Upgrade auf TeamsOnly erhalten, haben sie keinen Zugriff auf Teams für allgemeine Aktivitäten, die in Skype for Business ausgeführt werden, z. B. Chats und Anrufe. Dies bedeutet, dass keine Funktion nebeneinander ist.|
|Der Administrator hat die Kontrolle über die Funktionen, die Benutzern beim Übergang von Skype for Business zu Teams zur Verfügung stehen. Dieses Steuerelement umfasst die Möglichkeit, Teams-Funktionen inkrementell einzuführen. | |
| Ermöglicht es einer Organisation, Teams für Besprechungen zu verwenden, auch wenn sie noch nicht bereit ist, vollständig in den TeamsOnly-Modus zu wechseln.||
|Die Anwesenheit eines bestimmten Benutzers, der von anderen Personen angezeigt wird, ist gleich, unabhängig davon, welchen Client er verwendet.||

## <a name="summary-of-upgrade-methods"></a>Zusammenfassung der Upgrademethoden
In der folgenden Tabelle sind die Upgrademethoden zusammengefasst:


|Überlappende Funktionen (im Inselmodus)  |Ausgewählte Funktionen (mithilfe von Skype for Business-Modi)  |
|---------|---------|
|Vor dem Upgrade auf TeamsOnly müssen Benutzer beide Clients gleichzeitig ausführen, da eingehende Chats und Anrufe in jedem Client landen können.     | Chats und Anrufe werden basierend auf dem Modus des Empfängers nur in einem Client angezeigt. Benutzer ohne Upgrade können beide Clients ausführen, es gibt jedoch keine funktionale Überlappung (Anrufe und Chats sind in Teams nicht verfügbar). Administratoren können auch steuern, ob Benutzer Besprechungen in Teams oder Skype for Business planen.         |
|Ermöglicht Es Administratoren, überlappende Funktionen (Chats, Besprechungen, VOIP-Anrufe) sowohl in Skype for Business als auch in Teams für Endbenutzer (die Funktionen nebeneinander verwenden) sowie neue Funktionen (Teams und Kanäle) in Teams einzuführen.     | Ermöglicht Administratoren die Einführung von Auswahlfunktionen von Teams für Endbenutzer (Teams und Kanäle), ohne die gleiche Funktionalität bereitzustellen, die auch in Skype for Business vorhanden ist.        |
|Die Inopop zwischen Skype for Business und Teams ist nicht vorhanden, während sich beide Benutzer im Inselmodus befinden. Sobald einige Benutzer ein Upgrade auf Teams Durchgeführte Inopop-Unterhaltungen zwischen diesen Benutzern und anderen Benutzern, die sich noch im Inselmodus befinden, auftreten können. Benutzer von Inseln könnten sich jedoch entscheiden, Teams zu verwenden und die Inopop-Unterhaltung zu vermeiden.      |Für die Kommunikation zwischen Skype for Business- und Teams-Benutzern ist Inopop erforderlich.         |

> [!NOTE]
> Wenn Sie die unterstützten Methoden zum Migrieren Ihrer Skype for Business Server-Benutzer zu Teams nicht befolgen können, wäre es möglich, Ihre Benutzer zu Teams zu übertragen, indem Sie Skype for Business Server und alle zugehörigen Benutzerattribute in Active Directory entfernen. Sobald die Azure Active Directory-Attribute der Benutzer von den Skype for Business Server-Attributen deaktiviert wurden und die DNS-Einträge erneut auf Microsoft 365 oder Office 365 verwiesen wurden, wäre es dann möglich, die Benutzer in Microsoft 365 oder Office 365 zu lizenzieren und ein Upgrade auf Teams zu durchführen. 

> [!IMPORTANT]
> Bei der Übergabemigration werden Die Kontaktdaten und Besprechungsdaten nicht aus der lokalen Umgebung zu Microsoft Teams migriert.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Entscheidungspunkt</td><td><ul> Welcher Upgradeweg eignet sich für die geschäftlichen Anforderungen Ihrer Organisation?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Nächster Schritt</td><td><ul> Die Identifizierung Ihres aktuellen Bereitstellungsmodells, Die Verwendung von Fallszenarien und wichtige Überlegungen für Ihre Organisation informieren Sie über den Weg zu Teams, das für Ihre Organisation am besten geeignet ist.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Entscheidungspunkt</td><td><ul> Welches Upgradeszenario gilt für Ihre Organisation?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul> Entscheiden Sie die Zeitachse des Upgradewegs Ihrer Organisation basierend auf den Anforderungen für Nachrichten, Besprechungen und Anrufe.<br><br> Entscheiden Sie, welche zusätzlichen Arbeiten erforderlich sind, um den Upgradeweg zu abschließen.<br><br></ul></td></tr>
</table>

Nachdem Sie die beste Upgradereise für Ihre Organisation ausgewählt haben, [führen Sie Das Upgrade auf Teams durch.](https://aka.ms/SkypeToTeams-Upgrade)

## <a name="related-links"></a>Verwandte Links

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Verwenden des Besprechungsmigrationsdiensts (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

