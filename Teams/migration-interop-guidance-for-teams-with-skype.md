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
ms.openlocfilehash: 44c60dbad9b2b31e18716c79dea73795cda4a803
ms.sourcegitcommit: e53749714dcde9f7b184d5ef554bffbc77f54267
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/18/2019
ms.locfileid: "28729436"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden

> [!Tip] 
> Sehen Sie sich die folgenden Sitzung um kennen zu lernen [Interoperabilität und Koexistenz](https://aka.ms/teams-upgrade-coexistence-interop)

Eine Organisation mit Skype für Unternehmen beginnt, Teams einführen, können Administratoren verwalten die Benutzeroberfläche in ihrer Organisation mit dem Konzept der Koexistenz "Mode" die einer Eigenschaft von TeamsUpgradePolicy ist. Modus verwalten Administratoren Interop und Migration, wie sie den Übergang von Skype für Unternehmen Teams verwalten.  Eines Benutzers Modus wird bestimmt, in der Clientcomputer eingehende Chats und Anrufe Land sowie welche neuen Dienst (Teams oder Skype für Unternehmen)-Besprechungen in geplant werden. Modus wird in der Zukunft auch verwendet werden, definieren Teams Clientverhalten im Hinblick auf welche Funktionalität zur Verfügung stehen. 


## <a name="fundamental-concepts"></a>Grundlegende Konzepte

1.  *Interop* : 1: 1-Kommunikation zwischen einer Lync/Skype für Geschäftsbenutzer und einem Benutzer Teams.

2.  *Verbund* : Kommunikation zwischen Benutzern aus anderen Mandanten.

3.  Alle Benutzer einer zugrunde liegenden Skype verfügen, für die Business-Konto, das ist "entweder online befinden" Teams oder lokalen:
    - Benutzer, die bereits Skype für Business Online verwenden Sie ihre vorhandene online-Konto.
    - Benutzer, die bereits Skype für Business/Lync lokal verwenden Sie ihre vorhandenen lokalen Konto.
    - Benutzer, die für die wir eine vorhandene Skype für Business Konto nicht erkennt haben einen Skype für Business-Onlinekonto automatisch bereitgestellt werden, wenn der Benutzer Teams erstellt wird. Keine Skype für Business-Lizenz ist erforderlich.

4.  Wenn Sie eine lokalen Bereitstellung von entweder Skype für Geschäftskunden und Lync haben und diese Benutzer Teams Benutzer werden sollen, Sie müssen mindestens sicherstellen, dass Azure AD-Verbinden der MsRTCSIP-DeploymentLocator synchronisiert wird-Attribut in AAD, sodass diese Teams/Skype für Unternehmen Online Ihrer lokalen Umgebung ordnungsgemäß erkennt. Darüber hinaus so verschieben Sie alle Benutzer in den Modus nur Teams (d. h., aktualisieren Sie einen Benutzer), *müssen Sie zuerst Skype für Business Hybrid-Modus konfigurieren*. Weitere Informationen finden Sie unter [Konfigurieren von Azure Active Directory verbinden für Skype für Unternehmen und Teams](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/configure-azure-ad-connect).

5.  Interoperabilität zwischen Teams und Skype für Unternehmensbenutzer ist nur möglich *, wenn der Benutzer Teams online in Skype für Unternehmen verwaltet wird*. Der Empfänger Skype für Geschäftsbenutzer verwaltet werden kann entweder lokal (und erfordert die Konfiguration der Skype für hybride Business) oder online. Benutzer, die in Skype für Business lokal verwaltet werden können Teams im Inseln Modus (weiter unten in diesem Dokument definiert) verwenden, aber nicht mit der Interop Teams oder Verbund mit anderen Benutzern für die Business Skype verwenden.  

6.  Upgrade und Interop-Verhalten werden bestimmt basierend auf Koexistenzmodus eines Benutzers, der vom TeamsUpgradePolicy verwaltet wird. TeamsInteropPolicy ist nicht mehr berücksichtigt und gewähren von Mode = Legacy ist nicht mehr zulässig. 

7.  Aktualisieren eines Benutzers auf den TeamsOnly Modus wird sichergestellt, dass alle eingehenden Chats und Anrufe immer in der Client des Benutzers Teams, unabhängig davon welcher Client es Orignated aus sorgt werden. Diese Benutzer werden auch alle neue Besprechungen in Teams planen. TeamsOnly den Modus ist, muss ein Benutzer online in Skype für Unternehmen verwaltet werden. Dies ist erforderlich, um sicherzustellen, dass Interop, Verbund und vollständige Verwaltung des Benutzers Teams. So aktualisieren einen Benutzer auf TeamsOnly:
  - Wenn der Benutzer online in Skype für Unternehmen verwaltet wird (oder nie hatte Skype-Konto), gewähren sie TeamsUpgradePolicy Modus = TeamsOnly mithilfe der "UpgradeToTeams" Instanz von PowerShell, oder verwenden Sie das Teams Admin Center die TeamsOnly Modus aus.
  - Wenn der Benutzer lokal ist, verwenden Sie `Move-CsUser` aus der lokalen Admin tools zum ersten verschieben den Benutzer Skype für Business Online. Beim Verschieben von Benutzern von lokalen sind 2 Optionen:
    
       - Wenn Sie Skype für Business Server 2019 oder CU8 für Skype für Business Server 2015 haben, können Sie angeben die `-MoveToTeams` wechseln `Move-CsUser` zum Verschieben des Benutzers direkt in Teams. Diese Option wird auch Besprechungen des Benutzers zu Teams migrieren, (obwohl Moment meeting Migration nur für Kunden TAP funktionsfähig ist). 
       - Andernfalls, nach dem `Move-CsUser` abgeschlossen ist, weisen Sie diesen Benutzer mithilfe von PowerShell oder der Verwaltungskonsole Teams TeamsOnly Modus.  
    Weitere Informationen finden Sie unter [Verschieben von Benutzern zwischen lokalen und Cloud](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).  Weitere Informationen zu Migration meeting finden Sie unter [Verwenden der Besprechung Migration Service (MMS)](https://docs.microsoft.com/en-us/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).


8.  Um Teams Telefonsystem Features mit Teams verwenden, muss sich Benutzer in TeamsOnly-Modus (d. h., die in Skype für Business Online verwaltet und Teams aktualisiert), und muss entweder für die Microsoft-Telefonsystem [Direkten Routing](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277) (dem Telefonsystem verwenden können konfiguriert werden mit eigenen SIP-Trunks und SBC) oder über ein Office 365 aufrufen planen.   

9.  Planen von Besprechungen mit Audiokonferenz Teams ist (Einwählen oder Anwahl über PSTN) derzeit nur für Benutzer, die in Skype für Business Online verwaltet werden. Unterstützung für Benutzer mit Teams mit einer lokalen Skype für Business Konto befindet sich in TIPPEN.


## <a name="coexistence-modes"></a>Koexistenz Modi

Interoperabilität und Migration werden basierend auf "Koexistenzmodus" mit TeamsUpgradePolicy verwaltet. Ein Benutzer Modus bestimmt:

- *Routing von eingehenden*: In welcher Client (Teams oder Skype für Unternehmen) eingehende chats und ruft Land? 
- *Besprechung planen*: welcher Dienst verwendet wird, für die Planung von neuer Besprechungen und sicherstellen, dass das richtige Add-in in Outlook vorhanden ist. Beachten Sie, dass TeamsUpgradePolicy Teilnahme an einer Besprechung nicht gesteuert wird. Benutzer können immer *Join* jede Besprechung, ob es sich um einen Skype für geschäftliche Besprechung oder einer Besprechung Teams sein.
- *Clientumgebung*: welche Funktionalität in Teams und/oder Skype für Business-Client verfügbar ist? Dies ist für TeamsOnly Modus implementiert. Unterstützung für andere Modi ist für die Zukunft geplant. 

Die Modi sind unten aufgeführt. SfBWithTeamsCollab und SfBWithTeamsCollabAndMeetings ermöglicht Einsatz der beiden Clients, wobei jedoch keine überlappenden Funktionalität. Inseln Modus ermöglicht die Verwendung der beiden Clients, jedoch mit überlappenden Funktionalität. Beispielsweise im Modus "Inseln" ein Benutzers konnte einen Chat in beiden Skype für Geschäftskunden und Teams initiieren, aber in SfBWithTeamsCollab, können sie nur eine Chatten in Skype für Unternehmen (obwohl sie Teams Channel Unterhaltungen teilnehmen können). Beachten Sie, dass der Client Expeirence für die Modi SfB noch nicht vollständig funktionsfähig ist.  
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

<sup>2</sup> SfBWithTeamsCollab und SfBWithTeamsCollabAndMeetings nicht noch die Admin-Benutzeroberfläche verfügbar gemacht, da sie derzeit nicht anders als SfBOnly-Modus, mit Ausnahme den Outlook-Add-ins steuern Verhalten. Nachdem die Clientumgebung angeboten wird, werden diese Modi im Admin-Portal zur Verfügung. 

## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy: Verwalten von Migration und Koexistenz

TeamsUpgradePolicy werden zwei wichtige Eigenschaften verfügbar gemacht: Modus und NotifySfbUsers. 
</br>
</br>

|Parameter|Typ|Zulässige Werte</br>(Standard kursiv)|Beschreibung|
|---|---|---|---|
|Modus|Enum|*Inseln*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Gibt den Modus, den in der Client ausgeführt wird.|
|NotifySfbUsers|Bool|*False* oder true|Gibt an, ob für ein Banner in der Skype für den Benutzer darüber informiert, dass die Teams Skype für Unternehmen schnell ersetzt Business-Client angezeigt werden soll. Dies kann nicht true, wenn Mode = TeamsOnly.|
|||||

Teams stellt alle relevante Instanzen der TeamsUpgradePolicy über integrierte, nur-Lese-Richtlinien. Aus diesem Grund nur Get- und Grant-Cmdlets sind verfügbar. Die Instanzen integrierten sind unten aufgeführt.
</br>
</br>

|Identität |Modus|NotifySfbUsers|
|---|---|---|
|Inseln|Inseln|Falsch|
|IslandsWithNotify|Inseln|True|
|SfBOnly|SfBOnly|Falsch|
|SfBOnlyWithNotify|SfBOnly|True|
|SfBWithTeamsCollab|SfBWithTeamsCollab|Falsch|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|True|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|Falsch|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|True|
|UpgradeToTeams|TeamsOnly|Falsch|
|Global</br>*Standard*|Inseln|Falsch|
||||

Diese Richtlinieninstanzen können einzelnen Benutzern oder für einzelne Mandanten geltende erteilt werden. Beispiel:
- Wenn einen Benutzer ($SipAddress) auf Teams aktualisieren, gewähren Sie die Instanz "UpgradeToTeams":</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Um den gesamten Mandanten zu aktualisieren, Auslassen der Identitätsparameter aus dem Grant-Befehl:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`


## <a name="federation-considerations"></a>Verbund-Aspekte

Für den Verbund von Teams an einen anderen Benutzer, die Verwendung von Skype für Unternehmen muss der Benutzer Teams online in Skype für Unternehmen verwaltet werden. Schließlich werden können Sie den Verbund mit anderen Benutzern Teams Benutzer in Skype verwaltet für Business lokale-Teams.

TeamsUpgradePolicy steuert routing für eingehende federated Chats und Anrufe. Verbundpartner Routingverhalten entspricht der gleichen Mandanten Szenarien, *außer im Inseln Modus*.  Wenn Empfänger im Modus Inseln sind: 
- Chats und Anrufe, die von Teams Flächen in SfB initiiert werden, wenn der Empfänger befindet sich in einem *Verbundpartner Mandanten*.
- Chats und Anrufe, die von Teams Flächen in Teams initiiert werden, wenn der Empfänger befindet sich im *gleichen Mandanten*.
- Chats und immer aus SfB getätigte Anrufe sorgt in SfB.


## <a name="the-intended-client-user-experience-in-teams-when-using-sfb-modes"></a>Die vorgesehenen Client Benutzerinteraktion in Teams bei Verwendung von SfB Modi

Wenn Benutzer befinden sich in keines der Skype für Business Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) *Anruf- und Chat Funktionalität in der Teams app deaktiviert werden soll*, aber derzeit nicht noch deaktiviert ist. Auf ähnliche Weise, wenn Benutzer in den Modi SfBOnly oder SfBWithTeamsCollab *Besprechung planen in Teams soll deaktiviert werden*, sind derzeit ist aber keine. Eine Lösung für diese Erfahrung automatisch bereit ist geplant.

Bis dieser Lösung angeboten wird, können Administratoren die vorgesehene Clientumgebung des TeamsUpgradePolicy-Modus erzwingen, indem Manuelles Konfigurieren der Werte von TeamsMessagingPolicy, TeamsCallingPolicy und TeamsMeetingPolicy. Darüber hinaus bei Verwendung `Grant-CsTeamsUpgradePolicy` in PowerShell mit dem Cmdlet prüft automatisch die Konfiguration der entsprechenden Einstellungen in TeamsMessagingPolicy, TeamsCallingPolicy und TeamsMeetingPolicy zu Determmine ab, ob diese Einstellungen mit kompatibel sind. den angegebenen Modus. Wenn eine nicht ordnungsgemäß konfiguriert sind, die Grant wird erfolgreich ausgeführt, aber eine Warnung erhalten, der angibt, welche Einstellungen nicht ordnungsgemäß konfiguriert sind. Der Administrator sollte die angezeigten Richtlinien, um eine kompatible Endbenutzer Erlebnis in Teams anschließend aktualisieren. Entscheidet der Administrator keine Aktion als Ergebnis der Warnung, können Benutzer weiterhin auf chat, zugreifen aufrufen und/oder meeting Planungsfunktionen in Teams abhängig von den Werten der TeamsMessagingPolicy, TeamsCallingPolicy und TeamsMeetingPolicy, die möglicherweise etwas verwirrend Endbenutzers.


`PS C:\Users\janedoe> Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab
WARNING: The user 'user1@contoso.com' currently has effective policy enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. In the near term, when granting TeamsUpgradePolicy with mode=SfBWithTeamsCollab to a user, you must also separately assign policy to ensure the user has effective policy disabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. In the future, the capability will automatically honor TeamsUpgradePolicy.
PS C:\Users\janedoe>`


Vor der Zustellung der automatische Umsetzung der oben beschriebenen Clientverhalten jede der Modi SfB Verhalten sich im Wesentlichen. Die Modi SfBOnly, SfBWithTeamsCollab und SfBWithTeamsCollabAndMeetings sind alle identisch wie leiten Sie eingehende Anrufe und Chats. Der einzige Unterschied ist jetzt in der Outlook-Add-Ins für Teams und Skype für Unternehmen, ob aktiviert wurden. Bis die Experiece differenzierten Client angeboten wird, ist nur 1 der Modi SfB dem Verwaltungsportal aktiviert. Aber in PowerShell sind alle Modi verfügbar.


### <a name="powershell-warning-matrix"></a>Matrix der PowerShell-Warnung

Diese Tabelle zeigt die Benutzerrichtlinien, die überprüft werden, wenn TeamsUpgradeMode gewährt wird. In der Zukunft ist die Absicht für SfBOnly Modus Kanäle in Teams auch deaktivieren. Es ist derzeit keine Einstellung Channel-Feature in Teams deaktiviert werden können.


|**Modalität (App)**|**Policy.Setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Anrufe|TeamsCallingPolicy.AllowPrivateCalling|
|Besprechung planen|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||


Der Administrator wird eine Warnung angezeigt, wenn eine Trennung zwischen der Arbeitslast-Aktivierung und den gewünschten Modus vorhanden ist. Vorübergehend, der Administrator sollte Aktivieren/der Arbeitslast über Core arbeitsauslastungsrichtlinie deaktivieren.  Nachdem Automatische Erzwingung basierend auf TeamsUpgradePolicy implementiert ist, werden die PowerShell-Warnungen aktualisiert werden, um dem Administrator mitzuteilen, den die Clientumgebung automatisch angewendet wird. In diesem Fall die Werte der TeamsMessagingPolicy, TeamsCallingPolicy und TeamsMeetingPolicy bleiben unverändert –, aber die vorgesehene Clientumgebung werden gemäß TeamsUpgradePolicy erzwungen.



## <a name="teamsinteroppolicy-and-legacy-mode-being-retired"></a>TeamsInteropPolicy und Zurückziehen Legacymodus 

TeamsInteropPolicy wurde durch TeamsUpgradePolicy ersetzt. Alle Komponenten, die zuvor TeamsInteropPolicy berücksichtigt wurden aktualisiert, um stattdessen TeamsUpgradePolicy berücksichtigt.  Microsoft hat zuvor "Legacymodus" in TeamsUpgradePolicy zur Erleichterung des Übergangs von TeamsInteropPolicy zu TeamsUpgradePolicy eingeführt. Routingkomponenten, die TeamsUpgradePolicy verstanden würde im Legacy-Modus auf TeamsInteropPolicy zurückgesetzt. Routing TeamsUpgradePolicy nun vollständig unterstützt und Legacymodus wird nicht mehr unterstützt. *Kunden mit Legacymodus aktualisieren müssen ihre Konfiguration von TeamsUpgradePolicy zu einem anderen Modus verwenden.* 


### <a name="action-required-for-organizations-that-are-using-modelegacy-andor-teamsinteroppolicy"></a>Eine Aktion durchführen für Organisationen, die Modus verwenden = Legacy und/oder TeamsInteropPolicy
Kunden mit Mode = Legacy in TeamsUpgradePolicy (Richtlinieninstanz = NoUpgrade oder Richtlinie Instanz = NotifyForTeams) müssen Aktualisieren ihrer Konfiguration, um eine Richtlinie mit einer anderer Druckmodus als Legacy verwenden.  Darüber hinaus sollten Kunden mit TeamsInteropPolicy Zuweisungen diese Richtlinie entfernen, da es nicht mehr vom System verwendet wird.  Beachten Sie, dass es ist nicht mehr möglich, Legacymodus zu erteilen. 

Aktionen erforderlich:
 - Kunden mit TeamsInteropPolicy mit Benutzern, die *nicht* im Legacymodus: die Richtlinie hat keine Auswirkung und seine empfohlen, entfernen Sie alle Benutzer level-Zuordnungen und verwenden Sie die globale Richtlinie einfach mit Standardwerten.
 - Kunden mit Legacymodus mit TeamsInteropPolicy routing an SfB (DisallowOverrideCallingSfbChatSfb): Diese Organisationen sollte wechseln, um einen der SfB Modi (SfBOnly, SfBWithTeamsCollab, SfbWithTeamsCollabAndMeetings) in TeamsUpgradePolicy verwenden. Aus der Sicht routing diese Modi verhält sich wie die Verwendung von Legacymodus mit TeamsInteropPolicy routing an SfB.
  - Kunden mit Legacymodus mit TeamsInteropPolicy routing Teams (DisallowOverrideCallingTeamsChatTeams): Diese Organisationen sollte TeamsOnly Modus wechseln.  Haben Sie aus der Sicht routing, die dieser immer dieselbe. Ein Unterschied ist jedoch, dass Benutzer in Teams nur Kopfzeilen herunterladen, Chats und Anrufe initiieren, und Planen von Besprechungen in Skype für Unternehmen nicht mehr möglich. Sie können jedoch weiterhin alle Skype für Business Besprechung teilnehmen.


 **Microsoft fordert an, dass Kunden alle Verwendung von Legacymodus durch 15 November 2018 entfernen.** Irgendwann danach wird Microsoft Instanzen von TeamsUpgradePolicy Modus entfernen = Legacy.</br> 


## <a name="detailed-mode-descriptions"></a>Beschreibungen der detaillierten Modus
</br>
</br>

|Modus|Erläuterung (Includeding geplant Clientumgebung)|
|---|---|
|**Inseln**</br>(Standard)|Ein Benutzer führt beide Skype für Geschäfts- und Teams Side-by-Side. Diesen Benutzer:</br><ul><li>Chats können initiieren und VOIP-Anrufe in beiden Skype für Business oder Teams Client. Hinweis: Benutzer mit Skype für Unternehmen verwaltet lokale können nicht aus einer anderen Skype für Geschäftsbenutzer erreichen Teams initiieren.<li>Empfängt Chats & VOIP-Anrufe initiierte in Skype für Unternehmen von einem anderen Benutzer in ihren Skype für Business-Client.<li>Empfängt Chats & VOIP initiierte in Teams von einem anderen Benutzer in ihren Teams Client Ruft, wenn diese sich in *derselben mandantenorganisation*befinden.<li>Empfängt Chats & VOIP von Anrufen in initiierte Teams von einem anderen Benutzer in ihren Skype für Business-Client werden in einem *Verbundpartner Mandanten*. <li>Verfügt über PSTN-Funktionen wie unten angegeben:<ul><li>Wenn der Benutzer in Skype für Business lokal verwaltet wird, sind PSTN-Anrufe initiiert und in Skype für Unternehmen erhalten.<li>Wenn der Benutzer online verwaltet wird, hat der Benutzer Telefonsystem, in dem den Benutzer case:<ul><li>Initiiert und PSTN-Anrufe in Teams erhält, wenn der Benutzer für das direkte Routing konfiguriert ist<li>Initiiert und PSTN-Anrufe in Skype für Unternehmen erhält, wenn der Benutzer ein MS aufrufen planen hat oder stellt eine mit dem PSTN-Netzwerk über entweder Skype für Business Cloud Connector Edition oder einer lokalen Bereitstellung von Skype für Business Server (Hybrid-VoIP Verbindung)</ul></ul><li>Planen von Besprechungen in Teams oder Skype für Unternehmen können (und sieht standardmäßig beide-Plug-ins).<li>Kann eine beliebige Skype für Business oder Teams Besprechung teilnehmen; die Besprechung wird in den jeweiligen Client geöffnet.</ul>|
|**SfBOnly**|Ein Benutzer führt nur Skype für Unternehmen. Diesen Benutzer:</br><ul><li>Können Chats und Anrufe von Skype für Unternehmen nur initiieren.<li>Empfängt alle Chat/Aufruf in ihren Skype für Business-Client unabhängig von wobei initiiert, es sei denn, der Initiator Teams Benutzer mit Skype für Unternehmen ist der lokale verwaltet. * <li>Können nur Skype für Business Besprechungen planen, aber Skype für Business oder Teams Besprechungen beitreten können. </br> *Using Inseln Modus mit lokalen Benutzern wird nicht in Kombination mit anderen Benutzern im SfBOnly Modus empfohlen. Wenn ein Benutzer Teams mit Skype für Unternehmen, verwaltet lokale initiiert einen Anruf oder Chat an einen Benutzer SfBOnly, der SfBOnly-Benutzer ist nicht erreichbar und erhält eine verpasste Chat/Anrufe email.*|
|**SfBWithTeamsCollab**|Ein Benutzer führt beide Skype für Geschäfts- und Teams Side-by-Side. Diesen Benutzer:</br><ul><li>Verfügt über die Funktionen eines Benutzers im SfBOnly Modus.<li>Teams hat nur für die Zusammenarbeit von Gruppen (Kanäle); aktiviert werden Chat/aufrufen/Besprechung planen sind deaktiviert.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|Ein Benutzer führt beide Skype für Geschäfts- und Teams Side-by-Side. Diesen Benutzer:<ul><li>Hat die Chat und Anruffunktionen des Benutzers im SfBOnly Modus.<li>Teams für die Zusammenarbeit von Gruppen aktiviert wurde (Kanäle - Kanal Unterhaltungen enthält); Chat und Aufrufen von sind deaktiviert.<li>Planen Sie nur Teams Besprechungen können, jedoch können Skype für Business oder Teams Besprechungen teilnehmen.</ul>|
|**TeamsOnly**</br>(erfordert SfB Online privat)|Ein Benutzer führt nur Teams. Diesen Benutzer:<ul><li>Empfängt alle Chats, und unabhängig von ihren Teams-Client aufruft, in denen initiiert hat.<li>Können Chats und nur von Teams Anrufe initiieren.<li>Können nur in Teams Besprechungen planen Sie, aber beitreten Sie Skype für Business oder Teams Besprechungen können.<li>Können weiterhin Skype für Business IP-Telefone verwenden.</ul> |
|||




## <a name="related-topics"></a>Verwandte Themen

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[GRANT-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Neue CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsupgradepolicy?view=skype-ps)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsupgradepolicy?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradepolicy?view=skype-ps)
