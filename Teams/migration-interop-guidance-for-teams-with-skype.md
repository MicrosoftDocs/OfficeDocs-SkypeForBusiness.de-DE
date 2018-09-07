---
title: Hinweise zur Migration und Interoperabilität für Organisationen mit Teams zusammen mit Skype für Unternehmen
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: lehewe
description: Leitfaden für den Übergang von Skype für Unternehmen, die Teams verwalten
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 11ba2e2d6d59ecd53dd1824f50c53022e15f2b69
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854183"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Hinweise zur Migration und Interoperabilität für Organisationen mit Teams zusammen mit Skype für Unternehmen

Im April 2018 erläutert Microsoft seine Anleitung für die Migration zu Teams von Skype für Unternehmen und wie dieser beiden Clients in einem bestimmten Benutzer koexistieren können. Zu diesem Zeitpunkt hat geplante Änderungen zum Vereinfachen der verwaltungsmöglichkeiten eingeführt und steigern der Endbenutzer Kundenzufriedenheit bekannt gegeben. Seitdem hat Microsoft ein Update auf die Admin-Benutzeroberfläche, konsistent mit diesem Plan übermittelt. Die Anweisungen in diesem Dokument entspricht diese Änderungen.

Als zuvor bekannt gegebenen TeamsInteropPolicy (für das Ende des Q3 gezielte) zurückgezogen und seine Funktionalität ist in TeamsUpgradePolicy konsolidiert werden. Interoperabilität und Migration werden mit "Koexistenzmodus", wie durch TeamsUpgradePolicy, bestimmt das jetzt verfügbar ist verwaltet werden. Auswahl des Benutzers Modus wird gesteuert, beide routing von eingehenden Anrufen und Chats und der Benutzer kann in der Clientcomputer Chats und Anrufe initiieren oder Besprechungen planen. Während der TeamsInteropPolicy gültig ist, muss sie während der Phaseout parallel mit TeamsUpgradePolicy festgelegt werden.  

Im Rahmen der Maßnahme hat Microsoft kürzlich der "Microsoft-Teams & Skype für Business-Verwaltungskonsole" (auch bekannt als modernen Portal) entsprechend den neuen Model im Projektmanagement basierend auf Koexistenz Modi aktualisiert. In modernen Portal festgelegt konfigurieren TeamsUpgradePolicy wird nun automatisch auch TeamsInteropPolicy auf konsistente Wert, damit TeamsInteropPolicy nicht mehr in der Benutzeroberfläche verfügbar gemacht wird. *Administratoren über PowerShell müssen jedoch weiterhin sowohl TeamsUpgradePolicy und TeamsInteropPolicy zusammen ordnungsgemäßes routing sicherzustellen festgelegt.* Nach Abschluss der Übergang zur TeamsUpgradePolicy werden nicht mehr erforderlich, auch TeamsInteropPolicy festgelegt.
</br>
</br>
|**Verwalten von Interop und Migration**|**Moderne Portal**|**PowerShell**|
|----|----|----|----|
|Bis September 2018 (Datumsangaben kann geändert werden)|Verwenden Sie TeamsUpgradePolicy|Verwenden Sie TeamsUpgradePolicy und TeamsInteropPolicy |
|Posten Sie September 2018 (Datumsangaben kann geändert werden)|Verwenden Sie TeamsUpgradePolicy|Verwenden Sie nur TeamsUpgradePolicy. Veraltete TeamsInteropPolicy|
|||||

Um die Einführung der Koexistenz Modi und die ausstehenden Stilllegung der TeamsInteropPolicy berücksichtigt werden, ist Microsoft dieser Anleitung jetzt bereit, damit Kunden Teams heute mit den Übergang verwalten können.

## <a name="in-this-article"></a>In diesem Artikel

- [Grundlegende Konzepte](#fundamental-concepts)
- [Koexistenz Modi](#coexistence-modes)
- [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](#teamsupgradepolicy-managing-migration-and-co-existence)
- [TeamsInteropPolicy zurückgezogen werden](#teamsinteroppolicy-to-be-retired)
- [Abschließen des Übergangs zu Verwaltung der Modus](#completing-the-transition-to-mode-management)
- [Eine Aktion durchführen für Organisationen, die bereits TeamsInteropPolicy verwendet haben](#action-required-for-organizations-that-have-already-used-teamsinteroppolicy)   
- [Beschreibungen der detaillierten Modus](#detailed-mode-descriptions) 
- [Zusammenfassung der Änderungen der geplanten Funktionen zur Vereinfachung der Migration und Koexistenz](#summary-of-planned-functionality-changes-to-simplify-coexistence-and-migration) 
- [Bekannte Probleme](#known-issues)

## <a name="fundamental-concepts"></a>Grundlegende Konzepte

1.  *Interop* : 1: 1-Kommunikation zwischen einer Lync/Skype für Geschäftsbenutzer und einem Benutzer Teams.

2.  *Verbund* : Kommunikation zwischen Benutzern aus anderen Mandanten.

3.  Alle Benutzer einer zugrunde liegenden Skype verfügen, für die Business-Konto, das ist "entweder online befinden" Teams oder lokalen:
    - Benutzer, die bereits Skype für Business Online verwenden Sie ihre vorhandene online-Konto.
    - Benutzer, die bereits Skype für Business/Lync lokal verwenden Sie ihre vorhandenen lokalen Konto.
    - Benutzer, die für die wir eine vorhandene Skype für Business Konto nicht erkennt haben einen Skype für Business-Onlinekonto automatisch bereitgestellt werden, wenn der Benutzer Teams erstellt wird. Keine Skype für Business-Lizenz ist erforderlich.

4.  Wenn Sie eine lokalen Bereitstellung von entweder Skype für Geschäftskunden und Lync haben und diese Benutzer Teams Benutzer werden sollen, Sie müssen mindestens sicherstellen, dass Azure AD-Verbinden der MsRTCSIP-DeploymentLocator synchronisiert wird-Attribut in AAD, sodass diese Teams/Skype für Unternehmen Online Ihrer lokalen Umgebung ordnungsgemäß erkennt. Darüber hinaus so verschieben Sie alle Benutzer in den Modus nur Teams (d. h., aktualisieren Sie einen Benutzer), *müssen Sie Skype für Business Hybrid-Modus konfigurieren*.

5.  Interoperabilität zwischen Teams und Skype für Unternehmensbenutzer ist nur möglich *, wenn der Benutzer Teams online in Skype für Unternehmen verwaltet wird*. Die Skype für Geschäftsbenutzer verwaltet werden kann entweder lokal (und erfordert die Konfiguration der Skype für hybride Business) oder online. Benutzer, die in Skype für Business lokal verwaltet werden können Teams im Inseln Modus (weiter unten in diesem Dokument definiert) verwenden, aber nicht mit der Interop Teams oder Verbund mit anderen Benutzern für die Business Skype verwenden.  

6.  Einen Benutzer auf Teams aktualisieren (d. h., gewähren sie TeamsUpgradePolicy Modus = TeamsOnly), muss der Benutzer online in Skype für Unternehmen verwaltet werden. Dies ist erforderlich, um sicherzustellen, dass Interop, Verbund und vollständige Verwaltung des Benutzers Teams. Verwenden Sie zum Aktualisieren von Benutzern, die lokal sind Sie `Move-CsUser` aus der lokalen Admin tools zum ersten verschieben den Benutzer Skype für Business Online. Klicken Sie dann die online-Benutzer TeamsUpgradePolicy und TeamsInteropPolicy erteilen oder modernen Portal zuweisen TeamsOnly-Modus verwenden.

7.  Die zentrale Richtlinien zum Verwalten von Upgrades und Interop sind TeamsUpgradePolicy und TeamsInteropPolicy.  Allerdings TeamsInteropPolicy wird gerade wird zurückgezogen und alle Funktionen werden durch TeamsUpgradePolicy ersetzt werden. Bis zum Abschluss des Übergangs Kunden müssen TeamsUpgradePolicy und TeamsInteropPolicy konsistent (als beschrieben [später](#important) in diesem Dokument) um sicherzustellen, dass ordnungsgemäße Funktion oder verwenden Sie das neue modernen Portal, die dies automatisch erfolgt.

8.  Um Teams Telefonsystem Features verwenden, muss sich Benutzer in TeamsOnly-Modus (d. h., die in Skype für Business Online verwaltet und Teams aktualisiert), und muss entweder für Microsoft Phone System direkten Routing (die Sie mit Ihrer eigenen SIP Telefonsystem verwenden können konfiguriert werden Trunks und SBC) oder über ein Office 365 aufrufen planen. Direktes Routing ist [im Allgemeinen verfügbar](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277) ab Juni 28, 2018.  

9.  Planen von Besprechungen mit Audiokonferenz Teams ist (Einwählen oder Anwahl über PSTN) derzeit nur für Benutzer, die in Skype für Business Online verwaltet werden. Unterstützung für Benutzer mit Teams mit einer lokalen Skype für Business Konto ist geplant.

10. Nachrichtenrouting für Organisationen, die noch nicht für Unified Anwesenheit Service (USV) aktiviert haben, ist nicht TeamsInteropPolicy (ChatDefaultClient) oder TeamsUpgradePolicy (Modus) berücksichtigt. Wie USV Einführung über den nächsten Wochen abgeschlossen ist, wird TeamsInteropPolicy oder TeamsUpgradePolicy berücksichtigt. Schließlich nur TeamsUpgradePolicy wird berücksichtigt.

## <a name="coexistence-modes"></a>Koexistenz Modi

Zum Vereinfachen der verwaltungsmöglichkeiten eingeführt, und steigern der Endbenutzer Kundenzufriedenheit, werden Interop und Migration jetzt basierend auf "Koexistenzmodus" mit TeamsUpgradePolicy verwaltet. Ein Benutzer Modus bestimmt:

- *Routing von eingehenden* : In welcher Client (Teams oder Skype für Unternehmen) eingehende chats und ruft Land? Diese Funktionalität ersetzt, was zuvor durch TeamsInteropPolicy behandelt wurde. TeamsInteropPolicy wird zurückgezogen werden, nachdem der Übergang abgeschlossen ist. ***Während des Übergangs TeamsUpgradePolicy und TeamsInteropPolicy muss festgelegt werden koordiniert, wie im nächsten Abschnitt beschrieben***.
- *Besprechung planen* : welcher Dienst verwendet wird, für die Planung von neuer Besprechungen und sicherstellen, dass das richtige Add-in in Outlook vorhanden ist? Unterstützung von Outlook-add-in wird erwartet, dass in den nächsten Wochen bereitgestellt werden. Beachten Sie, dass TeamsUpgradePolicy Teilnahme an einer Besprechung nicht gesteuert wird. Benutzer können immer *Join* jede Besprechung, ob es sich um einen Skype für geschäftliche Besprechung oder einer Besprechung Teams sein.
- *Clientumgebung* : welche Funktionalität in Teams und/oder Skype für Business-Client verfügbar ist? Dies ist für TeamsOnly Modus implementiert. Unterstützung für andere Modi ist abhängig von der in Kürze verfügbare TeamsAppPolicy. Wenn diese neue Richtlinie vorhanden ist, müssen TeamsUpgradePolicy eine Abhängigkeit, um sicherzustellen, dass Teams für den gewünschten Modus ordnungsgemäß konfiguriert ist.

Die geplante Modi sind unten aufgeführt. SfBWithTeamsCollab und SfBWithTeamsCollabAndMeetings ermöglicht Einsatz der beiden Clients, wobei jedoch keine überlappenden Funktionalität. Inseln Modus ermöglicht die Verwendung der beiden Clients, jedoch mit überlappenden Funktionalität. Im Modus Inseln konnte ein Benutzer einen Chat in beiden Skype initiieren, für Geschäftskunden und Teams, aber in SfBWithTeamsCollab, können sie nur in Skype für Unternehmen chat aus. Beachten Sie, dass nicht alle Modi noch zur Verfügung stehen.  
</br>
</br>
|Modus|Routingverhalten|Besprechung planen|Clientumgebung|
|---|---|---|---|
|Inseln|Eingehende VOIP-Anrufe und chats Land im gleichen Client als Absender<sup>1</sup>|Beide|Endbenutzer können Anrufe und Chats entweder Client aus initiieren und Besprechungen können entweder Client aus.|
|SfBOnly|Eingehende Anrufe und Chats werden an Skype für Unternehmen weitergeleitet.|Skype für Unternehmen nur|Endbenutzer können Anrufe und nur von Skype für Unternehmen Chats initiieren und Skype nur für Business Besprechungen planen. (NOCH NICHT ERZWUNGEN)|
|SfBWithTeamsCollab<sup>2</sup>|Eingehende Anrufe und Chats werden an Skype für Unternehmen weitergeleitet.|Skype für Unternehmen nur|Endbenutzer können Anrufe und nur von Skype für Unternehmen Chats initiieren und Skype nur für Business Besprechungen planen. Sie können auch Kanäle in Teams. (NOCH NICHT ERZWUNGEN)|
|SfBWithTeamsCollabAndMeetings<sup>3</sup>|Eingehende Anrufe und Chats werden an Skype für Unternehmen weitergeleitet.|Nur Teams|Endbenutzer können Anrufe initiieren und Chats von Skype für Unternehmen nur und Teams Besprechungen planen. Sie können auch Kanäle in Teams. (NOCH NICHT ERZWUNGEN)|
|TeamsOnly|Eingehende Anrufe und Chats werden Teams weitergeleitet.|Nur Teams|Endbenutzer können Anrufe und nur von Teams Chats initiieren. Skype für Unternehmen ist nur verfügbar, an Besprechungen teilnehmen.|
|Legacy|Routing TeamsInteropPolicy basiert auf|Keine Auswirkung|Keine Auswirkung. In einem temporären Modus zum Übergang von TeamsInteropPolicy zu TeamsUpgradePolicy zu vereinfachen. Nachdem der Übergang abgeschlossen ist, wird in diesem Modus entfernt werden. |
|||||

**Hinweise:**

Finden Sie <sup>1</sup> ausführliche Informationen zum Aufrufen von PSTN Tabelle am Ende dieses Dokuments.

<sup>2</sup> SfBWithTeamsCollab nicht noch die Admin-Benutzeroberfläche verfügbar gemacht, da es derzeit SfBOnly Modus oder anders verhält. Wenn die Clientumgebung übermittelt werden, wird in diesem Modus verfügbar sein.

<sup>3</sup> SfBWithTeamsCollabAndMeetings ist noch nicht verfügbar. 

## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy: Verwalten von Migration und Koexistenz

TeamsUpgradePolicy wird jetzt drei Eigenschaften verfügbar gemacht. Die primären Eigenschaften sind Modus und NotifySfbUsers. Aktion ist ein legacy-Parameter und ist mit der Kombination Modus und NotifySfbUsers vollständig redundant.
</br>
</br>
|Parameter|Typ|Zulässige Werte</br>(Standard kursiv)|Beschreibung|
|---|---|---|---|
|Modus|Enum|*Inseln*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>Legacy|Gibt den Modus, den in der Client ausgeführt wird. Wenn Mode = Legacy, Komponenten, die diese Richtlinie consuming berücksichtigt TeamsInteropPolicy wiederhergestellt werden. Dies ist der Umstellung auf das neue Schema zu unterstützen, wie Komponenten, die zuvor TeamsInteropPolicy berücksichtigt aktualisiert werden, um TeamsUpgradePolicy berücksichtigt.</br>Modus = TeamsOnly entspricht dem Action = Upgrade.|
|NotifySfbUsers|Bool|*False* oder true|Gibt an, ob für ein Banner in der Skype für den Benutzer darüber informiert, dass die Teams Skype für Unternehmen schnell ersetzt Business-Client angezeigt werden soll. Dies kann nicht true, wenn Mode = TeamsOnly. Dies entspricht der Aktion = benachrichtigen.|
|Aktion|Enum|*Keine*Aktualisierung zu benachrichtigen|Dies ist ein legacy-Parameter, der schließlich entfernt wird, da es durch die Kombination von Modus und NotifySfbUsers darstellt. |
|||||

Teams stellt alle relevante Instanzen der TeamsUpgradePolicy über integrierte, nur-Lese-Richtlinien. Aus diesem Grund nur Get- und Grant-Cmdlets sind verfügbar. Die Instanzen integrierten sind unten aufgeführt.
</br>
</br>
|Identität |Modus|NotifySfbUsers|Aktion|Kommentare|
|---|---|---|---|---|
|Inseln|Inseln|False|Keine||
|IslandsWithNotify|Inseln|True|Benachrichtigen||
|SfBOnly|SfBOnly|False|Keine|Für den Moment, in diesem Modus erfolgt effektiv als bevorzugter Client Einstellung = SfB. Wir in Zukunft zu erwarten, dass diese Teams Funktionalität eingeschränkt wird.|
|SfBOnlyWithNotify|SfBOnly|True|Benachrichtigen|Für den Moment, in diesem Modus erfolgt effektiv als bevorzugter Client Einstellung = SfB. Wir in Zukunft zu erwarten, dass diese Teams Funktionalität eingeschränkt wird.|
|SfBWithTeamsCollab|SfBWithTeamsCollab|False|Keine|In diesem Modus Ebene PowerShell vorhanden ist, aber noch nicht die Admin-Benutzeroberfläche zugänglich. Aus der Sicht routing ist identisch mit SfBOnly Modus. Wenn TeamsAppPolicy verfügbar ist, wird dies nur Kanäle Teams app zulassen.|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|True|Benachrichtigen|In diesem Modus Ebene PowerShell vorhanden ist, aber noch nicht die Admin-Benutzeroberfläche zugänglich. Aus der Sicht routing ist identisch mit SfBOnly Modus. Wenn TeamsAppPolicy verfügbar ist, wird dies nur Kanäle Teams app zulassen.|
|UpgradeToTeams|TeamsOnly|False|Upgrade|Verwenden Sie diesen Modus aus, um Benutzer auf Teams aktualisiert und Chat, aufrufen und Planen der Besprechung in Skype für Unternehmen zu vermeiden.|
|Global|Legacy|False|Keine|Der Modus wird schließlich Inseln aktualisiert.|
|NoUpgrade|Legacy|False|Keine|Diese Instanz wird schließlich zurückgezogen werden.|
|NotifyForTeams|Legacy|True|Benachrichtigen|Diese Instanz wird schließlich zurückgezogen werden.|
||||||

Diese Richtlinieninstanzen können einzelnen Benutzern oder für einzelne Mandanten geltende erteilt werden. Beispiel:
- Wenn einen Benutzer ($SipAddress) auf Teams aktualisieren, gewähren Sie die Instanz "UpgradeToTeams":</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Um den gesamten Mandanten zu aktualisieren, Auslassen der Identitätsparameter aus dem Grant-Befehl:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

### <a name="important"></a>WICHTIG!
Komponenten, die zuvor TeamsInteropPolicy berücksichtigt werden aktualisiert, um TeamsUpgradePolicy berücksichtigt. Während des Übergangs muss Management dieser beiden Richtlinien koordinierte wie unten angegeben werden. Beachten Sie, dass die letzte Aktualisierung modernen Portal automatisch beide Richtlinien ordnungsgemäß erteilt bei der Auswahl eines Koexistenzmodus.
</br>
</br>
|Wenn Sie eine Instanz des TeamsUpgradePolicy gewähren</br>mit diesem Wert des Modus...|... Übergeben Sie diese Instanz von TeamsInteropPolicy|
|---|---|
|Inseln|`DisallowOverrideCallingDefaultChatDefault`|
|SfBOnly, SfBWithTeamsCollab,</br>SfBWithTeamsCollabAndMeetings|`DisallowOverrideCallingSfbChatSfb`|
|TeamsOnly |`DisallowOverrideCallingTeamsChatTeams`|
|||

## <a name="teamsinteroppolicy-to-be-retired"></a>TeamsInteropPolicy zurückgezogen werden 

Wie oben beschrieben, werden TeamsInteropPolicy durch TeamsUpgradePolicy ersetzt. Bis dieser Übergang abgeschlossen ist, werden nur die drei bestimmten Instanzen von unten aufgeführten TeamsInteropPolicy unterstützt. In jedem Fall der Wert der CallingDefaultClient entspricht dem Wert des ChatDefaultClient und AllowEndUserClientOverride ist immer false. 
</br>
</br>
**Unterstützte Instanzen von TeamsInteropPolicy vor der Stilllegung**
|Identität |AllowEndUserClientOverride|CallingDefaultClient|ChatDefaultClient|
|---|---|---|---|
|`DisallowOverrideCallingDefaultChatDefault`|False|Standard|Standard|
|`DisallowOverrideCallingSfbChatSfb`|False|SFB|SFB|
|`DisallowOverrideCallingTeamsChatTeams`|False|Microsoft Teams|Microsoft Teams|
|||||

Verwenden Sie die folgende Cmdlet Syntax, wobei $policy eine der oben genannten Werte der Identität ist:`Grant-CsTeamsInteropPolicy -PolicyName $policy -Identity $SipAddress`

## <a name="federation-considerations"></a>Verbund-Aspekte

Für den Verbund von Teams an einen anderen Benutzer, die Verwendung von Skype für Unternehmen muss der Benutzer Teams online in Skype für Unternehmen verwaltet werden. Verbund bezeichnet in Pilot- und stetig immer verfügbar. Wenn Ihre Organisation Verbund erfordert, sollten Sie nicht aktualisieren, bis ein Verbund unterstützt werden. Schließlich werden können Sie den Verbund mit anderen Benutzern Teams Benutzer in Skype verwaltet für Business lokale-Teams.

Nachdem die verbundunterstützung aktiviert ist, steuert TeamsUpgradePolicy (zusammen mit TeamsInteropPolicy während des Übergangs) routing für eingehende federated Chats und Anrufe. Um anderen Organisationen initiieren federated Kommunikation mit Benutzern in Ihrer Organisation zu ermöglichen, ist es wird empfohlen, einen Modus wählen, das speziell entweder weiterleitet, Skype für Business oder Teams, statt der Inseln.
</br>
|Anrufrouting und Chats...|Eine Instanz des TeamsUpgradePolicy erteilen</br> mit einem der folgenden Modi|Und gewähren Sie diese Instanz von TeamsInteropPolicy|
|---|---|---|
|Skype for Business|SfBOnly, SfBWithTeamsCollab, </br>SfBWithTeamsCollabAndMeetings|`DisallowOverrideCallingSfbChatSfb`|
|Microsoft Teams|TeamsOnly |`DisallowOverrideCallingTeamsChatTeams`|
||||

## <a name="completing-the-transition-to-mode-management"></a>Abschließen des Übergangs zu Verwaltung der Modus

Weiter unten in diesem Jahr plant Microsoft Einführung einen neuen Richtlinientyp, TeamsAppPolicy, um zu steuern, welche Teile des Teams-Clients (wie Sofortnachrichten, Besprechungen, Chat, Kanäle) aktiviert sind. Sobald die neue Richtlinie zum Aktivieren/Deaktivieren der Arbeitslasten in Teams verfügbar ist, wird TeamsUpgradePolicy aktualisiert werden, wenn ein Administrator versucht, einem Benutzer eine Instanz des TeamsUpgradePolicy erteilen, es zuerst überprüft, um sicherzustellen, dass TeamsAppPolicy richtig ist. für den gewünschten Modus konfiguriert. Wenn dies nicht der Fall ist, wird die Grant schlägt fehl, mit einem Fehler erläutert, wie die andere Richtlinie zuerst festgelegt werden muss. 

Bis TeamsAppPolicy verfügbar ist, steuert TeamsUpgradePolicy im Wesentlichen routing von Anrufen und Chats als auch Besprechung planen (wie über Outlook-add-ins verfügbar gemacht werden). Da Clientverhalten Teams nicht noch vorhanden ist, werden nicht alle Modi auf modernen Portal aktiviert. Aus der Sicht routing sind die Modi SfBOnly, SfBWithTeamsCollab und SfBWithTeamsCollabAndMeetings identisch. 

## <a name="action-required-for-organizations-that-have-already-used-teamsinteroppolicy"></a>Eine Aktion durchführen für Organisationen, die bereits TeamsInteropPolicy verwendet haben

Um diese anstehenden Änderungen bei der Vorbereitung müssen Kunden Folgendes ausführen:

1. Stellen Sie sicher, dass Benutzer mit TeamsInteropPolicy nur eine dieser drei integrierten Instanzen, für welche CallingDefaultClient zugeordnet werden = ChatDefaultClient und für welche AllowEndUserClientOverride = False. Diese Instanzen sind:
</br>
</br>
   |Identität |AllowEndUserClientOverride |CallingDefaultClient|ChatDefaultClient|
   |---|---|---|---|
   |`DisallowOverrideCallingDefaultChatDefault`|False|Standard|Standard|
   |`DisallowOverrideCallingSfbChatSfb`|False|SFB|SFB|
   |`DisallowOverrideCallingTeamsChatTeams`|False|Microsoft Teams|Microsoft Teams|
   |||||

    Verwenden Sie die folgende Cmdlet Syntax, wobei $policy eine der oben genannten Werte der Identität ist:

    `Grant-CsTeamsInteropPolicy -PolicyName $policy -Identity $SipAddress`

    **Microsoft fordert an, dass Kunden ihre Richtlinien von 30 Juni 2018 aktualisieren.** Irgendwann danach wird Microsoft anderen Instanzen von TeamsInteropPolicy entfernt werden.</br> 
    ***Organisationen, die nicht auf eine der folgenden Instanzen aktualisieren müssen schließlich die Benutzer auf eine der folgenden Instanzen automatisch aktualisiert. Wir bevorzugen offensichtlich, dass Kunden hierzu, damit Sie auswählen können, was am besten für Ihre Benutzer ist.***

2. Wenn Sie die integrierte globale Richtlinie angepasst, rückgängig machen Sie dies. Die globale Richtlinie sollten die folgenden Werte haben:
</br>
</br>
    |Parameter|Wert|
    |---|---|
    |`AllowEndUserClientOverride`|False|
    |`CallingDefaultClient`|Standard|
    |`ChatDefaultClient`|Standard|
    |||

    Wenn die Werte anders als oben angegeben werden, führen Sie Folgendes ein, um alle Mandanten-spezifische Anpassungen zu entfernen:

    `Grant-CsTeamsInteropPolicy -PolicyName $null`

## <a name="detailed-mode-descriptions"></a>Beschreibungen der detaillierten Modus
</br>
</br>

|Modus|Erklärung|
|---|---|
|**Inseln**|Ein einzelner Benutzer führt beide Skype für Geschäfts- und Teams Side-by-Side. Diesen Benutzer:</br><ul><li>Chats können initiieren und VOIP-Anrufe in beiden Skype für Business oder Teams Client. Hinweis: Benutzer mit Skype für Unternehmen verwaltet lokale können nicht aus einer anderen Skype für Geschäftsbenutzer erreichen Teams initiieren.<li>Empfängt Chats & VOIP-Anrufe, die in Skype für Unternehmen von einem anderen Benutzer in ihren Skype für Business-Client initiiert.<li>Empfängt VOIP Teams von einem anderen Benutzer in ihren Teams Client getätigte Anrufe.<li>Von einem anderen Benutzer in Teams getätigte Chats erhält:<ul><li>Skype für Unternehmen bereitgestellt werden, der Empfänger online verwaltet und nie Teams angemeldet ist<li>Teams in allen anderen Fällen.</ul><li>Verfügt über PSTN-Funktionen wie unten angegeben:<ul><li>Wenn der Benutzer in Skype für Business lokal verwaltet wird, sind PSTN-Anrufe initiiert und in Skype für Unternehmen erhalten.<li>Wenn der Benutzer online verwaltet wird, hat der Benutzer Telefonsystem, in dem den Benutzer case:<ul><li>Initiiert und PSTN-Anrufe in Teams erhält, wenn der Benutzer für das direkte Routing konfiguriert ist<li>Initiiert und PSTN-Anrufe in Skype für Unternehmen erhält, wenn der Benutzer ein MS aufrufen planen hat oder stellt eine mit dem PSTN-Netzwerk über entweder Skype für Business Cloud Connector Edition oder einer lokalen Bereitstellung von Skype für Business Server (Hybrid-VoIP Verbindung)</ul></ul><li>Planen von Besprechungen in Teams oder Skype für Unternehmen können (und sieht standardmäßig beide-Plug-ins).<li>Kann eine beliebige Skype für Business oder Teams Besprechung teilnehmen; die Besprechung wird in den jeweiligen Client geöffnet.</ul>|
|**SfBOnly**|Ein einzelner Benutzer führt nur Skype für Unternehmen. Diesen Benutzer:</br><ul><li>Können Chats und Anrufe von Skype für Unternehmen nur initiieren.<li>Empfängt alle Chat/Aufruf in ihren Skype für Business-Client unabhängig von wobei initiiert, es sei denn, der Initiator Teams Benutzer mit Skype für Unternehmen ist der lokale verwaltet. * <li>Können nur Skype für Business Besprechungen planen, aber Skype für Business oder Teams Besprechungen beitreten können. </br> *Using Inseln Modus mit lokalen Benutzern wird nicht in Kombination mit anderen Benutzern im SfBOnly Modus empfohlen. Wenn ein Benutzer Teams mit Skype für Unternehmen, verwaltet lokale initiiert einen Anruf oder Chat an einen Benutzer SfBOnly, der SfBOnly-Benutzer ist nicht erreichbar und erhält eine verpasste Chat/Anrufe email.*|
|**SfBWithTeamsCollab**|Ein einzelner Benutzer führt beide Skype für Geschäfts- und Teams Side-by-Side. Diesen Benutzer:</br><ul><li>Verfügt über die Funktionen eines Benutzers im SfBOnly Modus.<li>Teams hat nur für die Zusammenarbeit von Gruppen (Kanäle); aktiviert werden Chat/aufrufen/Besprechung planen sind deaktiviert.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**</br>(geplant)|Ein einzelner Benutzer führt beide Skype für Geschäfts- und Teams Side-by-Side. Diesen Benutzer:<ul><li>Hat die Chat und Anruffunktionen des Benutzers im SfBOnly Modus.<li>Teams wurde für die Zusammenarbeit von Gruppen (Kanäle); aktiviert werden Chat und Aufrufen von sind deaktiviert.<li>Planen Sie nur Teams Besprechungen können, jedoch können Skype für Business oder Teams Besprechungen teilnehmen.</ul>|
|**TeamsOnly**</br>(erfordert SfB Online privat)|Ein einzelner Benutzer führt nur Teams. Diesen Benutzer:<ul><li>Empfängt alle Chats, und unabhängig von ihren Teams-Client aufruft, in denen initiiert hat.<li>Können Chats und nur von Teams Anrufe initiieren.<li>Können nur in Teams Besprechungen planen Sie, aber beitreten Sie Skype für Business oder Teams Besprechungen können.<li>Können weiterhin Skype für Business IP-Telefone verwenden.</ul> |
|**Legacy**</br>(Standard)|Dieser Modus wird während des Übergangs verwendet, während wir out TeamsInteropPolicy phase. Verschiedene Komponenten des Systems werden aktualisiert werden, um TeamsUpgradePolicy zu unterschiedlichen Zeiten zu verwenden. Benutzer mit diesen Modus werden während dieses Übergangs weiterhin den vorhandenen Wert TeamsInteropPolicy berücksichtigt. Dies ermöglicht eine einheitliche benutzererfahrung, obwohl verschiedene Komponenten im Dienst zu unterschiedlichen Zeiten aktualisiert werden.|
|||

## <a name="summary-of-planned-functionality-changes-to-simplify-coexistence-and-migration"></a>Zusammenfassung der Änderungen der geplanten Funktionen zur Vereinfachung der Migration und Koexistenz

Basierend auf starken Feedback von Kunden TAP und andere frühen Übernahmen, angekündigt Microsoft geplante Änderungen im April zum Vereinfachen der verwaltungsmöglichkeiten eingeführt und Endbenutzer Kundenzufriedenheit erhöhen, wie Organisationen von Skype für Unternehmen zu Teams migrieren. Diese Änderungen werden eine vereinfachte und zuverlässigere Endbenutzer wünschen, eine vereinfachte Richtlinienmodell für die Verwaltung von Upgrade und Interoperabilität mit übermitteln. Die unten beschriebenen Änderungen werden in den nächsten Monaten schrittweise eingeführt. Auf allgemeiner Ebene gibt es vier geplante funktionsänderungen, nachstehend beschriebenen.
</br>
</br>
**Änderung #1: Keine weiteren überlappenden Modalitäten beim bevorzugter Client festgelegt wird.**
|||
|---|---|
|**ENTSCHEIDUNG**|*Wenn bevorzugten Client des Benutzers auf "Teams" oder "Sfb" festgelegt ist*, einen angegebenen Modalität (Instant Messaging, Besprechung planen, aufrufen) werden nur verfügbar und in einem Client (Teams oder Skype für Unternehmen) für diesen Benutzer unterstützt. (*Bevorzugte Client* bezieht sich auf die Parameter DefaultChatClient und DefaultCallingClient in TeamsInteropPolicy.) Nur, wenn der bevorzugte Client, wird "Default" (in der Zukunft als "Inseln Modus" bezeichnet festgelegt ist) einer angegebenen Modalität verfügbar sind und in beiden Clients unterstützt werden. |
|**BEGRÜNDUNG**|Das konsistente Feedback wir erhaltenen ist, dass Benutzer beim Versuch, beide Clients verwenden mit überlappenden Modalitäten für einen oder anderen Grund verwechselt werden. Es ist schwierig, vorhersehen und verstehen, warum Nachrichten und Anrufe in einem Client im Vergleich zu anderen sorgt, und die Anwesenheit unrichtige oder irreführende werden kann.|
|**STATUS**|Dies ist für den Modus unterstützt = TeamsOnly. Unterstützung für andere Modi wird in den nächsten Monaten verfügbar sein. |
|||

**Änderung #2: Vereinheitlichen Sie bevorzugten Client für Messaging und Aufrufen von**
|||
|---|---|
|**ENTSCHEIDUNG**|Verwaltung der bevorzugte Client für Sofortnachrichten und Aufrufen von wird von Microsoft zusammengeführt werden. Insbesondere müssen DefaultChatClient DefaultCallingClient sowohl den gleichen Wert - beides Standard (Inseln), sowohl Teams oder beide Skype für Unternehmen ist.  |
|**BEGRÜNDUNG**|Wenn diese nicht ausgerichtet werden, werden Anwesenheitsinformationen in einigen Fällen irreführende und verwirrend werden. Darüber hinaus konnte Initiieren eines Anrufs von einem vorhandenen Chat verwirrend, da der Anruf in einem anderen Client als den vorhandenen Chat sorgt kann. |
|**STATUS**|Diese Änderung wurde auf die Richtlinie Ebene mit TeamsUpgradePolicy ebenso wie in der administrativen UX (moderne Portal) implementiert. Jedoch ist der Übergang noch nicht abgeschlossen, sodass Kunden auch TeamsInteropPolicy festgelegt werden müssen. Kunden müssen nur eine der drei unterstützten Instanzen von TeamsInteropPolicy, die sind festlegen: DisallowOverrideCallingTeamsChatTeams, DisallowOverrideCallingDefaultChatDefault, DisallowOverrideCallingSfbChatSfb|
|||

**Änderung #3: Keine weitere Endbenutzer Wahl des bevorzugten client**
|||
|---|---|
|**ENTSCHEIDUNG**|Endbenutzer müssen die Wahl der bevorzugte Client nicht mehr. (AllowEndUserClientOverride in TeamsInteropPolicy muss auf False festgelegt sein). Bevorzugte Client basiert auf den Modus, die durch den Administrator festgelegt ist|
|**BEGRÜNDUNG**|Analyse von Verwendungsdaten zeigt, dass fast keine Benutzer festzulegen. Eliminierung diese Option vereinfacht die Admin-Helpdesk-Szenarien und reduziert die Komplexität engineering. Schließlich würde der Endbenutzer wählen einen anderen bevorzugten Client aus, den der Administrator für VoIP-routing in einer Organisation mit Enterprise-VoIP konfiguriert wurde, kann das verwirrend Endbenutzers verursacht haben, da es VOIP führen würde und PSTN-Anrufe, die in verschiedenen Zielseite Clients.|
|**STATUS**|Diese Änderung wurde auf die Richtlinie Ebene mit TeamsUpgradePolicy ebenso wie in der administrativen UX (moderne Portal) implementiert. Jedoch der Übergang noch nicht abgeschlossen ist, damit Kunden von Cmdlets TeamsInteropPolicy auf eine der drei unterstützten Instanzen von TeamsInteropPolicy, legen Sie auch müssen alle dürfen außer Kraft setzen.|
|||

**Änderung #4: Management basierend auf Client "Mode"**
|||
|---|---|
|**ENTSCHEIDUNG**|Microsoft ist Einführung in das Konzept der "Mode" Clientverhalten beim Strukturieren von Skype für Unternehmen starten, um Teams einführen zu verwalten. Administratoren können den Modus für jeden Benutzer einzeln festlegen und eines Benutzers Modus wird steuern, welche Funktionen in der Clientcomputer verfügbar ist sowie Anrufe und Chats, in dem sorgt. Administratoren werden dies über die überarbeitete TeamsUpgradePolicy verwalten die zur Unterstützung von Modus aktualisiert wurde. TeamsInteropPolicy wird schließlich veraltet und entfernt, nachdem alle Komponenten zum Lesen aus TeamsUpgradePolicy aktualisiert wurden.|
|**BEGRÜNDUNG**|Zum Vereinfachen der verwaltungsmöglichkeiten eingeführt, und steigern der Endbenutzer Kundenzufriedenheit, werden Interop und Migration verwaltet "Koexistenz im Modus" TeamsUpgradePolicy verwenden. Auswahl des Benutzers Modus wird gesteuert, das routing von eingehenden Anrufen und Chats, und der Benutzer kann in der Clientcomputer Chats und Anrufe initiieren oder Besprechungen planen. Konsolidierung von TeamsUpgradePolicy und TeamsInteropPolicy verhindert auch, dass fehlerhafte Konfigurationen, die führen können, wenn diese beiden Richtlinien nicht konsistent festgelegt wurden. |
|**STATUS**|Tippen Sie auf Kunden jetzt finden Sie unter drei Modi in der Admin UX. Wie für Änderung #1 Länder unterstützen, werden zusätzliche Modi zur Verfügung gestellt. SfBOnly Modus nicht aktuell hindert Benutzer mithilfe von Teams, aber er wird in der Zukunft. |
|||

## <a name="known-issues"></a>Bekannte Probleme

- Beim Erstellen von neuer Unterhaltungen in Teams, führen Sie Chats noch TeamsUpgradePolicy oder TeamsInteropPolicy des Zielbenutzers berücksichtigt nicht. Ein Update geplant ist.
- Beim Erstellen von neuer Unterhaltungen in Skype für Unternehmen, führen Sie Chats nicht noch TeamsUpgradePolicy oder TeamsInteropPolicy berücksichtigt werden, wenn die Organisation noch nicht für Interop USV/messaging aktiviert ist.

## <a name="related-topics"></a>Verwandte Themen

[Get-CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsinteroppolicy?view=skype-ps)

[GRANT-CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsinteroppolicy?view=skype-ps)

[Remove-CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsinteroppolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[GRANT-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Neue CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsupgradepolicy?view=skype-ps)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsupgradepolicy?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradepolicy?view=skype-ps)
