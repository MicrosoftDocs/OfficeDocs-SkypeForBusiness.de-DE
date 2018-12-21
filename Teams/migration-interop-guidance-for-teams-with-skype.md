---
title: Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: bjwhalen
description: Leitfaden für den Übergang von Skype für Unternehmen, die Teams verwalten
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: d252b95496a3d86eb9667fd6dec9256d7ad98a00
ms.sourcegitcommit: b67c2cb5ffd6d27cc9257c5e81ee1ea494ef8bd1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2018
ms.locfileid: "27382678"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden

> [!Tip] 
> Sehen Sie sich die folgenden Sitzung um kennen zu lernen [Interoperabilität und Koexistenz](https://aka.ms/teams-upgrade-coexistence-interop)

Interoperabilität und Migration werden mit "Koexistenzmodus" von TeamsUpgradePolicy bestimmt verwaltet. Auswahl des Benutzers Modus steuert beide routing von eingehenden Anrufen und Chats und gibt an, ob Benutzer Besprechungen in Teams oder Skype für Unternehmen plant.  Bald wird in Verbindung mit der in Kürze verfügbare TeamsAppPermissionsPolicy, Modus auch bestimmen, in der Clientcomputer der Benutzer Chats und Anrufe initiieren kann. 

TeamsInteropPolicy wurde zurückgezogen wurden. Seine Funktionalität wurde in TeamsUpgradePolicy konsolidiert wurden, und ist nicht mehr erforderlich und wird im Allgemeinen nicht zugesichert TeamsInteropPolicy konfigurieren. TeamsInteropPolicy wurde nicht berücksichtigt werden, es sei denn, TeamsUpgradePolicy Modus = Legacy, aber dieses Modus wurde zurückgezogen.  Abschluss TeamsUpgradePolicy Support *müssen Kunden ihre Konfigurationen Verwendung ein anderer Druckmodus als Legacy aktualisieren*. Erteilen von Instanzen von TeamsUpgradePolicy Modus = Legacy wird jetzt blockiert.  Microsoft ist, entfernen Sie alle Instanzen von TeamsInteropPolicy und alle Instanzen der TeamsUpgradePolicy Modus = Legacy.

## <a name="fundamental-concepts"></a>Grundlegende Konzepte

1.  *Interop* : 1: 1-Kommunikation zwischen einer Lync/Skype für Geschäftsbenutzer und einem Benutzer Teams.

2.  *Verbund* : Kommunikation zwischen Benutzern aus anderen Mandanten.

3.  Alle Benutzer einer zugrunde liegenden Skype verfügen, für die Business-Konto, das ist "entweder online befinden" Teams oder lokalen:
    - Benutzer, die bereits Skype für Business Online verwenden Sie ihre vorhandene online-Konto.
    - Benutzer, die bereits Skype für Business/Lync lokal verwenden Sie ihre vorhandenen lokalen Konto.
    - Benutzer, die für die wir eine vorhandene Skype für Business Konto nicht erkennt haben einen Skype für Business-Onlinekonto automatisch bereitgestellt werden, wenn der Benutzer Teams erstellt wird. Keine Skype für Business-Lizenz ist erforderlich.

4.  Wenn Sie eine lokalen Bereitstellung von entweder Skype für Geschäftskunden und Lync haben und diese Benutzer Teams Benutzer werden sollen, Sie müssen mindestens sicherstellen, dass Azure AD-Verbinden der MsRTCSIP-DeploymentLocator synchronisiert wird-Attribut in AAD, sodass diese Teams/Skype für Unternehmen Online Ihrer lokalen Umgebung ordnungsgemäß erkennt. Darüber hinaus so verschieben Sie alle Benutzer in den Modus nur Teams (d. h., aktualisieren Sie einen Benutzer), *müssen Sie Skype für Business Hybrid-Modus konfigurieren*. Weitere Informationen finden Sie unter [Konfigurieren von Azure Active Directory verbinden für Skype für Unternehmen und Teams](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/configure-azure-ad-connect).

5.  Interoperabilität zwischen Teams und Skype für Unternehmensbenutzer ist nur möglich *, wenn der Benutzer Teams online in Skype für Unternehmen verwaltet wird*. Der Empfänger Skype für Geschäftsbenutzer verwaltet werden kann entweder lokal (und erfordert die Konfiguration der Skype für hybride Business) oder online. Benutzer, die in Skype für Business lokal verwaltet werden können Teams im Inseln Modus (weiter unten in diesem Dokument definiert) verwenden, aber nicht mit der Interop Teams oder Verbund mit anderen Benutzern für die Business Skype verwenden.  

6.  Einen Benutzer auf Teams aktualisieren (d. h., gewähren sie TeamsUpgradePolicy Modus = TeamsOnly), muss der Benutzer online in Skype für Unternehmen verwaltet werden. Dies ist erforderlich, um sicherzustellen, dass Interop, Verbund und vollständige Verwaltung des Benutzers Teams. Verwenden Sie zum Aktualisieren von Benutzern, die lokal sind Sie `Move-CsUser` aus der lokalen Admin tools zum ersten verschieben den Benutzer Skype für Business Online. Weitere Informationen finden Sie unter [Verschieben von Benutzern zwischen lokalen und Cloud](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud). In lässt sich sagen stehen 2 Optionen zur Verfügung:

    - Wenn Sie Skype für Business Server 2019 oder CU8 für Skype für Business Server 2015 haben, geben Sie die `-MoveToTeams` wechseln `Move-CsUser` zum Verschieben des Benutzers direkt in Teams.
    - Andernfalls, nach dem `Move-CsUser` abgeschlossen ist, weisen Sie diesen Benutzer mithilfe von PowerShell oder der Verwaltungskonsole Teams TeamsOnly Modus. 

7.  Die Core-Richtlinie für die Verwaltung des Upgrades und Interop ist TeamsUpgradePolicy. TeamsInteropPolicy wird nicht mehr berücksichtigt, außer bei Verwendung des Modus TeamsUpgradePolicy = Legacy und Kunden mithilfe des Modus = Legacy muss Aktualisieren ihrer Konfiguration von TeamsUpgradePolicy auf einen anderen Modus verwenden.  Gewähren von Mode = Legacy ist nicht mehr zulässig. 

8.  Um Teams Telefonsystem Features mit Teams verwenden, muss sich Benutzer in TeamsOnly-Modus (d. h., die in Skype für Business Online verwaltet und Teams aktualisiert), und muss entweder für die Microsoft-Telefonsystem [Direkten Routing](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277) (dem Telefonsystem verwenden können konfiguriert werden mit eigenen SIP-Trunks und SBC) oder über ein Office 365 aufrufen planen.   

9.  Planen von Besprechungen mit Audiokonferenz Teams ist (Einwählen oder Anwahl über PSTN) derzeit nur für Benutzer, die in Skype für Business Online verwaltet werden. Unterstützung für Benutzer mit Teams mit einer lokalen Skype für Business Konto befindet sich in TIPPEN.


## <a name="coexistence-modes"></a>Koexistenz Modi

Interoperabilität und Migration werden basierend auf "Koexistenzmodus" mit TeamsUpgradePolicy verwaltet. Ein Benutzer Modus bestimmt:

- *Routing von eingehenden*: In welcher Client (Teams oder Skype für Unternehmen) eingehende chats und ruft Land? 
- *Besprechung planen*: welcher Dienst verwendet wird, für die Planung von neuer Besprechungen und sicherstellen, dass das richtige Add-in in Outlook vorhanden ist. Beachten Sie, dass TeamsUpgradePolicy Teilnahme an einer Besprechung nicht gesteuert wird. Benutzer können immer *Join* jede Besprechung, ob es sich um einen Skype für geschäftliche Besprechung oder einer Besprechung Teams sein.
- *Clientumgebung*: welche Funktionalität in Teams und/oder Skype für Business-Client verfügbar ist? Dies ist für TeamsOnly Modus implementiert. Unterstützung für andere Modi ist abhängig von der in Kürze verfügbare TeamsAppPermissionsPolicy. Wenn diese neue Richtlinie vorhanden ist, müssen TeamsUpgradePolicy eine Abhängigkeit, um sicherzustellen, dass Teams für den gewünschten Modus ordnungsgemäß konfiguriert ist.

Die geplante Modi sind unten aufgeführt. SfBWithTeamsCollab und SfBWithTeamsCollabAndMeetings ermöglicht Einsatz der beiden Clients, wobei jedoch keine überlappenden Funktionalität. Inseln Modus ermöglicht die Verwendung der beiden Clients, jedoch mit überlappenden Funktionalität. Beispielsweise im Modus "Inseln" ein Benutzers konnte einen Chat in beiden Skype für Geschäftskunden und Teams initiieren, aber in SfBWithTeamsCollab, können sie nur eine Chatten in Skype für Unternehmen (obwohl sie Teams Channel Unterhaltungen teilnehmen können). Beachten Sie, dass nicht alle Modi noch vollständig zur Verfügung stehen.  
</br>
</br>

|Modus|Routingverhalten|Besprechung planen|Clientumgebung|
|---|---|---|---|
|Inseln|Eingehende VOIP-Anrufe und Land im gleichen Client als Absender, mit Ausnahme von chats, wenn der Empfänger im Verbund befindet und Inseln-Modus sorgt sie in diesem Fall in SfB.<sup>1</sup>|Both|Endbenutzer können Anrufe und Chats entweder Client aus initiieren und Besprechungen können entweder Client aus.|
|SfBOnly|Eingehende Anrufe und Chats werden an Skype für Unternehmen weitergeleitet.|Skype für Unternehmen nur|Endbenutzer können Anrufe und nur von Skype für Unternehmen Chats initiieren und Skype nur für Business Besprechungen planen. (NOCH NICHT ERZWUNGEN)|
|SfBWithTeamsCollab<sup>2</sup>|Eingehende Anrufe und Chats werden an Skype für Unternehmen weitergeleitet.|Skype für Unternehmen nur|Endbenutzer können Anrufe und nur von Skype für Unternehmen Chats initiieren und Skype nur für Business Besprechungen planen. Sie können auch Kanäle in Teams. (NOCH NICHT ERZWUNGEN)|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Eingehende Anrufe und Chats werden an Skype für Unternehmen weitergeleitet.|Nur Teams|Endbenutzer können Anrufe initiieren und Chats von Skype für Unternehmen nur und Teams Besprechungen planen. Sie können Teams Channel Unterhaltungen teilnehmen. (NOCH NICHT ERZWUNGEN)|
|TeamsOnly|Eingehende Anrufe und Chats werden Teams weitergeleitet.|Nur Teams|Endbenutzer können Anrufe und nur von Teams Chats initiieren. Skype für Unternehmen ist nur verfügbar, an Besprechungen teilnehmen.|
|||||

**Hinweise:**

Finden Sie <sup>1</sup> ausführliche Informationen zum Aufrufen von PSTN Tabelle am Ende dieses Dokuments.

<sup>2</sup> SfBWithTeamsCollab und SfBWithTeamsCollabAndMeetings nicht noch die Admin-Benutzeroberfläche verfügbar gemacht, da sie keine derzeit anders als SfBOnly Modus Verhalten. Nachdem die Clientumgebung gesendet wird, werden diese Modi verfügbar sein. 

## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy: Verwalten von Migration und Koexistenz

TeamsUpgradePolicy werden zwei wichtige Eigenschaften verfügbar gemacht: Modus und NotifySfbUsers. 
</br>
</br>

|Parameter|Typ|Zulässige Werte</br>(Standard kursiv)|Beschreibung|
|---|---|---|---|
|Modus|Enum|*Inseln*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>Legacy|Gibt den Modus, den in der Client ausgeführt wird. Wenn Mode = Legacy, Komponenten, die diese Richtlinie consuming berücksichtigt TeamsInteropPolicy wiederhergestellt werden. TeamsUpgradePolicy wird nun vollständig unterstützt und Kunden sollten ihre Konfigurationen mit einem anderen als dem Legacy aktualisieren.|
|NotifySfbUsers|Bool|*False* oder true|Gibt an, ob für ein Banner in der Skype für den Benutzer darüber informiert, dass die Teams Skype für Unternehmen schnell ersetzt Business-Client angezeigt werden soll. Dies kann nicht true, wenn Mode = TeamsOnly.|
|||||

Teams stellt alle relevante Instanzen der TeamsUpgradePolicy über integrierte, nur-Lese-Richtlinien. Aus diesem Grund nur Get- und Grant-Cmdlets sind verfügbar. Die Instanzen integrierten sind unten aufgeführt.
</br>
</br>

|Identität |Modus|NotifySfbUsers|Kommentare|
|---|---|---|---|
|Inseln|Inseln|Falsch||
|IslandsWithNotify|Inseln|True||
|SfBOnly|SfBOnly|Falsch|Für den Moment, in diesem Modus erfolgt effektiv als bevorzugter Client Einstellung = SfB. Wir in Zukunft zu erwarten, dass diese Teams Funktionalität eingeschränkt wird.|
|SfBOnlyWithNotify|SfBOnly|True|Für den Moment, in diesem Modus erfolgt effektiv als bevorzugter Client Einstellung = SfB. Wir in Zukunft zu erwarten, dass diese Teams Funktionalität eingeschränkt wird.|
|SfBWithTeamsCollab|SfBWithTeamsCollab|Falsch|In diesem Modus Ebene PowerShell vorhanden ist, aber noch nicht die Admin-Benutzeroberfläche zugänglich. Aus der Sicht routing ist identisch mit SfBOnly Modus. Wenn TeamsAppPolicy verfügbar ist, wird dies nur Kanäle Teams app zulassen.|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|True|In diesem Modus Ebene PowerShell vorhanden ist, aber noch nicht die Admin-Benutzeroberfläche zugänglich. Aus der Sicht routing ist identisch mit SfBOnly Modus. Wenn TeamsAppPolicy verfügbar ist, wird dies nur Kanäle Teams app zulassen.|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|Falsch|In diesem Modus Ebene PowerShell vorhanden ist, aber noch nicht die Admin-Benutzeroberfläche zugänglich. Aus der Sicht routing ist identisch mit SfBOnly Modus. Wenn TeamsAppPolicy verfügbar ist, wird diese Besprechung planen in Teams und Kanäle gestatten.|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|True|In diesem Modus Ebene PowerShell vorhanden ist, aber noch nicht die Admin-Benutzeroberfläche zugänglich. Aus der Sicht routing ist identisch mit SfBOnly Modus. Wenn TeamsAppPolicy verfügbar ist, wird diese Besprechung planen in Teams und Kanäle gestatten.|
|UpgradeToTeams|TeamsOnly|Falsch|Verwenden Sie diesen Modus aus, um Benutzer auf Teams aktualisiert und Chat, aufrufen und Planen der Besprechung in Skype für Unternehmen zu vermeiden.|
|Global|Inseln|Falsch|Das ist die Standardrichtlinie.|
|||||

Diese Richtlinieninstanzen können einzelnen Benutzern oder für einzelne Mandanten geltende erteilt werden. Beispiel:
- Wenn einen Benutzer ($SipAddress) auf Teams aktualisieren, gewähren Sie die Instanz "UpgradeToTeams":</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Um den gesamten Mandanten zu aktualisieren, Auslassen der Identitätsparameter aus dem Grant-Befehl:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`



## <a name="teamsinteroppolicy-and-legacy-mode-being-retired"></a>TeamsInteropPolicy und Zurückziehen Legacymodus 

Wie oben beschrieben wurde TeamsInteropPolicy durch TeamsUpgradePolicy ersetzt. Alle Komponenten, die zuvor TeamsInteropPolicy berücksichtigt wurden aktualisiert, um stattdessen TeamsUpgradePolicy berücksichtigt. 

Microsoft eingeführt zuvor "Legacymodus" in TeamsUpgradePolicy, um den Übergang von TeamsInteropPolicy zu TeamsUpgradePolicy zu vereinfachen. Routingkomponenten, die TeamsUpgradePolicy verstanden würde im Legacy-Modus auf TeamsInteropPolicy zurückgesetzt. TeamsUpgradePolicy Routing jetzt vollständig unterstützt, und es ist keine weitere Legacymodus verwenden müssen. *Kunden mit Legacymodus aktualisieren müssen ihre Konfiguration von TeamsUpgradePolicy zu einem anderen Modus verwenden.* 


## <a name="federation-considerations"></a>Verbund-Aspekte

Für den Verbund von Teams an einen anderen Benutzer, die Verwendung von Skype für Unternehmen muss der Benutzer Teams online in Skype für Unternehmen verwaltet werden. Schließlich werden können Sie den Verbund mit anderen Benutzern Teams Benutzer in Skype verwaltet für Business lokale-Teams.

TeamsUpgradePolicy steuert routing für eingehende federated Chats und Anrufe. Verbundpartner Routingverhalten entspricht der gleichen Mandanten Szenarien, *außer im Inseln Modus*.  Wenn Empfänger im Modus Inseln sind: 
- Chats und Anrufe, die von Teams Flächen in SfB initiiert werden, wenn der Empfänger befindet sich in einem *Verbundpartner Mandanten*.
- Chats und Anrufe, die von Teams Flächen in Teams initiiert werden, wenn der Empfänger befindet sich im *gleichen Mandanten*.
- Chats und immer aus SfB getätigte Anrufe sorgt in SfB.


## <a name="completing-the-transition-to-mode-management"></a>Abschließen des Übergangs zu Verwaltung der Modus

Weiter unten in diesem Jahr plant Microsoft Einführung einen neuen Richtlinientyp, TeamsAppPermissionsPolicy, um zu steuern, welche Teile des Teams-Clients (wie Sofortnachrichten, Besprechungen, Chat, Kanäle) aktiviert sind. Sobald die neue Richtlinie zum Aktivieren/Deaktivieren der Arbeitslasten in Teams verfügbar ist, wird TeamsUpgradePolicy aktualisiert werden, wenn ein Administrator versucht, einem Benutzer eine Instanz des TeamsUpgradePolicy erteilen, es zuerst überprüft, um sicherzustellen, dass TeamsAppPolicy richtig ist. für den gewünschten Modus konfiguriert. Wenn dies nicht der Fall ist, wird die Grant schlägt fehl, mit einem Fehler erläutert, wie die andere Richtlinie zuerst festgelegt werden muss. 

Bis TeamsAppPermissionsPolicy verfügbar ist, steuert TeamsUpgradePolicy im Wesentlichen routing von Anrufen und Chats als auch Besprechung planen (wie über Outlook-add-ins verfügbar gemacht werden). Da Clientverhalten Teams nicht noch vorhanden ist, werden nicht alle Modi auf modernen Portal aktiviert. Aus der Sicht routing sind die Modi SfBOnly, SfBWithTeamsCollab und SfBWithTeamsCollabAndMeetings identisch. 



## <a name="action-required-for-organizations-that-are-using-modelegacy-andor-teamsinteroppolicy"></a>Eine Aktion durchführen für Organisationen, die Modus verwenden = Legacy und/oder TeamsInteropPolicy
Kunden mit Mode = Legacy in TeamsUpgradePolicy (Richtlinieninstanz = NoUpgrade oder Richtlinie Instanz = NotifyForTeams) müssen Aktualisieren ihrer Konfiguration, um eine Richtlinie mit einer anderer Druckmodus als Legacy verwenden.  Darüber hinaus sollten Kunden mit TeamsInteropPolicy Zuweisungen diese Richtlinie entfernen, da es nicht mehr vom System, mit Ausnahme von im Legacy-Modus verwendet wird, wird zurückgezogen werden.  Beachten Sie, dass es ist nicht mehr möglich, Legacymodus zu erteilen. 

Aktionen erforderlich:
 - Kunden mit TeamsInteropPolicy mit Benutzern, die *nicht* im Legacymodus: die Richtlinie hat keine Auswirkung und seine empfohlen, entfernen Sie alle Benutzer level-Zuordnungen und verwenden Sie die globale Richtlinie einfach mit Standardwerten.
 - Kunden mit Legacymodus mit TeamsInteropPolicy routing an SfB (DisallowOverrideCallingSfbChatSfb): Diese Organisationen sollte wechseln, um einen der SfB Modi (SfBOnly, SfBWithTeamsCollab, SfbWithTeamsCollabAndMeetings) in TeamsUpgradePolicy verwenden. Aus der Sicht routing diese Modi verhält sich wie die Verwendung von Legacymodus mit TeamsInteropPolicy routing an SfB.
  - Kunden mit Legacymodus mit TeamsInteropPolicy routing Teams (DisallowOverrideCallingTeamsChatTeams): Diese Organisationen sollte TeamsOnly Modus wechseln.  Haben Sie aus der Sicht routing, die dieser immer dieselbe. Ein Unterschied ist jedoch, dass Benutzer in Teams nur Kopfzeilen herunterladen, Chats und Anrufe initiieren, und Planen von Besprechungen in Skype für Unternehmen nicht mehr möglich. Sie können jedoch weiterhin alle Skype für Business Besprechung teilnehmen.


 **Microsoft fordert an, dass Kunden alle Verwendung von Legacymodus durch 15 November 2018 entfernen.** Irgendwann danach wird Microsoft Instanzen von TeamsUpgradePolicy Modus entfernen = Legacy.</br> 


## <a name="detailed-mode-descriptions"></a>Beschreibungen der detaillierten Modus
</br>
</br>

|Modus|Erklärung|
|---|---|
|**Inseln**</br>(Standard)|Ein einzelner Benutzer führt beide Skype für Geschäfts- und Teams Side-by-Side. Diesen Benutzer:</br><ul><li>Chats können initiieren und VOIP-Anrufe in beiden Skype für Business oder Teams Client. Hinweis: Benutzer mit Skype für Unternehmen verwaltet lokale können nicht aus einer anderen Skype für Geschäftsbenutzer erreichen Teams initiieren.<li>Empfängt Chats & VOIP-Anrufe, die in Skype für Unternehmen von einem anderen Benutzer in ihren Skype für Business-Client initiiert.<li>Empfängt Chats & VOIP-Anrufe in Teams von einem anderen Benutzer in ihren Teams-Client gestartet wird, wenn diese sich in *derselben mandantenorganisation*befinden.<li>Empfängt Chats & VOIP-Anrufe in Teams von einem anderen Benutzer in ihren Skype für Business-Client gestartet wird, wenn sie einen *Verbund Mandanten*werden. <li>Verfügt über PSTN-Funktionen wie unten angegeben:<ul><li>Wenn der Benutzer in Skype für Business lokal verwaltet wird, sind PSTN-Anrufe initiiert und in Skype für Unternehmen erhalten.<li>Wenn der Benutzer online verwaltet wird, hat der Benutzer Telefonsystem, in dem den Benutzer case:<ul><li>Initiiert und PSTN-Anrufe in Teams erhält, wenn der Benutzer für das direkte Routing konfiguriert ist<li>Initiiert und PSTN-Anrufe in Skype für Unternehmen erhält, wenn der Benutzer ein MS aufrufen planen hat oder stellt eine mit dem PSTN-Netzwerk über entweder Skype für Business Cloud Connector Edition oder einer lokalen Bereitstellung von Skype für Business Server (Hybrid-VoIP Verbindung)</ul></ul><li>Planen von Besprechungen in Teams oder Skype für Unternehmen können (und sieht standardmäßig beide-Plug-ins).<li>Kann eine beliebige Skype für Business oder Teams Besprechung teilnehmen; die Besprechung wird in den jeweiligen Client geöffnet.</ul>|
|**SfBOnly**|Ein einzelner Benutzer führt nur Skype für Unternehmen. Diesen Benutzer:</br><ul><li>Können Chats und Anrufe von Skype für Unternehmen nur initiieren.<li>Empfängt alle Chat/Aufruf in ihren Skype für Business-Client unabhängig von wobei initiiert, es sei denn, der Initiator Teams Benutzer mit Skype für Unternehmen ist der lokale verwaltet. * <li>Können nur Skype für Business Besprechungen planen, aber Skype für Business oder Teams Besprechungen beitreten können. </br> *Using Inseln Modus mit lokalen Benutzern wird nicht in Kombination mit anderen Benutzern im SfBOnly Modus empfohlen. Wenn ein Benutzer Teams mit Skype für Unternehmen, verwaltet lokale initiiert einen Anruf oder Chat an einen Benutzer SfBOnly, der SfBOnly-Benutzer ist nicht erreichbar und erhält eine verpasste Chat/Anrufe email.*|
|**SfBWithTeamsCollab**|Ein einzelner Benutzer führt beide Skype für Geschäfts- und Teams Side-by-Side. Diesen Benutzer:</br><ul><li>Verfügt über die Funktionen eines Benutzers im SfBOnly Modus.<li>Teams hat nur für die Zusammenarbeit von Gruppen (Kanäle); aktiviert werden Chat/aufrufen/Besprechung planen sind deaktiviert.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|Ein einzelner Benutzer führt beide Skype für Geschäfts- und Teams Side-by-Side. Diesen Benutzer:<ul><li>Hat die Chat und Anruffunktionen des Benutzers im SfBOnly Modus.<li>Teams für die Zusammenarbeit von Gruppen aktiviert wurde (Kanäle - Kanal Unterhaltungen enthält); Chat und Aufrufen von sind deaktiviert.<li>Planen Sie nur Teams Besprechungen können, jedoch können Skype für Business oder Teams Besprechungen teilnehmen.</ul>|
|**TeamsOnly**</br>(erfordert SfB Online privat)|Ein einzelner Benutzer führt nur Teams. Diesen Benutzer:<ul><li>Empfängt alle Chats, und unabhängig von ihren Teams-Client aufruft, in denen initiiert hat.<li>Können Chats und nur von Teams Anrufe initiieren.<li>Können nur in Teams Besprechungen planen Sie, aber beitreten Sie Skype für Business oder Teams Besprechungen können.<li>Können weiterhin Skype für Business IP-Telefone verwenden.</ul> |
|||




## <a name="related-topics"></a>Verwandte Themen

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[GRANT-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsinteroppolicy?view=skype-ps)

[GRANT-CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsinteroppolicy?view=skype-ps)

[Remove-CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsinteroppolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Neue CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsupgradepolicy?view=skype-ps)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsupgradepolicy?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradepolicy?view=skype-ps)
