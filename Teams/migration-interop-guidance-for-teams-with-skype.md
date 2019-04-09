---
title: Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Leitfaden für den Übergang von Skype für Unternehmen, die Teams verwalten
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.teamsupgrade.overview
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ffe1a1eeef819833ec2efbdb6c7d49d85cb42a0d
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "31517184"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden

> [!Tip] 
> Sehen Sie sich die folgenden Sitzung um kennen zu lernen [Interoperabilität und Koexistenz](https://aka.ms/teams-upgrade-coexistence-interop)

Eine Organisation mit Skype für Unternehmen beginnt, Teams einführen, können Administratoren verwalten die Benutzeroberfläche in ihrer Organisation mit dem Konzept der Koexistenz "Mode" die einer Eigenschaft von TeamsUpgradePolicy ist. Modus verwalten Administratoren Interop und Migration, wie sie den Übergang von Skype für Unternehmen Teams verwalten.  Eines Benutzers Modus wird bestimmt, in welcher Client eingehende Chats und Anrufe Land sowie welche neuen Dienst (Teams oder Skype für Unternehmen) Besprechungen geplant werden. Modus wird in der Zukunft auch verwendet werden, definieren Teams Clientverhalten im Hinblick auf welche Funktionalität zur Verfügung stehen. 


## <a name="fundamental-concepts"></a>Grundlegende Konzepte

1.  *Interop* : 1: 1-Kommunikation zwischen einer Lync/Skype für Geschäftsbenutzer und einem Benutzer Teams.

2.  *Verbund* : Kommunikation zwischen Benutzern aus anderen Mandanten.

3.  Alle Benutzer einer zugrunde liegenden Skype verfügen, für die Business-Konto, das ist "entweder online befinden" Teams oder lokalen:
    - Benutzer, die bereits Skype für Business Online verwenden Sie ihre vorhandene online-Konto.
    - Benutzer, die bereits Skype für Business/Lync lokal verwenden Sie ihre vorhandenen lokalen Konto.
    - Benutzer, die für die wir eine vorhandene Skype für Business Konto nicht erkennt haben einen Skype für Business-Onlinekonto automatisch bereitgestellt werden, wenn der Benutzer Teams erstellt wird.

4.  Wenn Sie eine lokalen Bereitstellung von entweder Skype für Geschäftskunden und Lync haben und diese Benutzer Teams Benutzer werden sollen, Sie müssen mindestens sicherstellen, dass Azure AD-Verbinden der MsRTCSIP-DeploymentLocator synchronisiert wird-Attribut in AAD, sodass diese Teams/Skype für Unternehmen Online Ihrer lokalen Umgebung ordnungsgemäß erkennt. Darüber hinaus so verschieben Sie alle Benutzer in den Modus nur Teams (d. h., aktualisieren Sie einen Benutzer), *müssen Sie zuerst Skype für Business Hybrid-Modus konfigurieren*. Weitere Informationen finden Sie unter [Konfigurieren von Azure Active Directory verbinden für Skype für Unternehmen und Teams](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/configure-azure-ad-connect).

5.  Interoperabilität zwischen Teams und Skype für Unternehmensbenutzer ist nur möglich *, wenn der Benutzer Teams online in Skype für Unternehmen verwaltet wird*. Der Empfänger Skype für Geschäftsbenutzer verwaltet werden kann entweder lokal (und erfordert die Konfiguration der Skype für hybride Business) oder online. Benutzer, die in Skype für Business lokal verwaltet werden können Teams im Inseln Modus (weiter unten in diesem Dokument definiert) verwenden, aber nicht mit der Interop Teams oder Verbund mit anderen Benutzern für die Business Skype verwenden.  

6.  Upgrade und Interop-Verhalten werden basierend auf Koexistenzmodus eines Benutzers, der weiter unten beschriebenen bestimmt. Modus wird vom TeamsUpgradePolicy verwaltet. TeamsInteropPolicy ist nicht mehr berücksichtigt und gewähren von Mode = Legacy ist nicht mehr zulässig. 

7.  Aktualisieren eines Benutzers auf den TeamsOnly Modus wird sichergestellt, dass alle eingehenden Chats und Anrufe immer in der Client des Benutzers Teams, unabhängig davon welcher Client sorgt werden, die es stammt. Diese Benutzer werden auch alle neue Besprechungen in Teams planen. TeamsOnly den Modus ist, muss ein Benutzer online in Skype für Unternehmen verwaltet werden. Dies ist erforderlich, um sicherzustellen, dass Interop, Verbund und vollständige Verwaltung des Benutzers Teams. So aktualisieren einen Benutzer auf TeamsOnly:
    - Wenn der Benutzer online in Skype für Unternehmen verwaltet wird (oder nie hatte Skype-Konto), gewähren sie TeamsUpgradePolicy Modus = TeamsOnly mithilfe der "UpgradeToTeams" Instanz von PowerShell, oder verwenden Sie das Teams Admin Center die TeamsOnly Modus aus.
    - Wenn der Benutzer lokal ist, verwenden Sie `Move-CsUser` aus der lokalen Admin tools zum ersten verschieben den Benutzer Skype für Business Online.  Wenn Sie Skype für Business Server 2019 oder CU8 für Skype für Business Server 2015 haben, können Sie angeben die `-MoveToTeams` wechseln `Move-CsUser` so verschieben Sie den Benutzer direkt an Teams als Teil der Verschiebung online. Diese Option wird auch Besprechungen des Benutzers zu Teams migrieren, (obwohl Moment meeting Migration nur für Kunden TAP funktionsfähig ist). Wenn `-MoveToTeams` ist nicht angegeben oder nicht verfügbar ist, klicken Sie dann nach `Move-CsUser` abgeschlossen ist, weisen Sie diesen Benutzer mithilfe von PowerShell oder der Verwaltungskonsole Teams TeamsOnly Modus. Weitere Informationen finden Sie unter [Verschieben von Benutzern zwischen lokalen und Cloud](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).  Weitere Informationen zu Migration meeting finden Sie unter [Verwenden der Besprechung Migration Service (MMS)](https://docs.microsoft.com/en-us/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

8.  Um Teams Telefonsystem Features mit Teams verwenden, muss sich Benutzer in TeamsOnly-Modus (d. h., die in Skype für Business Online verwaltet und Teams aktualisiert), und muss entweder für die Microsoft-Telefonsystem [Direkten Routing](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277) (dem Telefonsystem verwenden können konfiguriert werden mit eigenen SIP-Trunks und SBC) oder über ein Office 365 aufrufen planen.   

9.  Planen von Teams Besprechungen mit Audiokonferenz (Einwählen oder Anwahl über PSTN) ist jetzt verfügbar sind, unabhängig davon, ob der Benutzer in Skype für Business Online oder Skype für Business lokal verwaltet wird. 


## <a name="coexistence-modes"></a>Koexistenz Modi

Interoperabilität und Migration werden basierend auf "Koexistenzmodus" mit TeamsUpgradePolicy verwaltet. Koexistenz Modi bieten eine einfache und vorhersehbare Erfahrung für Endbenutzer als Organisationen Übergang von Skype für Unternehmen Teams. Für eine Organisation verschieben, Teams ist der TeamsOnly-Modus der endgültigen Ziel für jeden Benutzer, wenn nicht alle Benutzer sich TeamsOnly (oder einem beliebigen Modus) zugewiesen werden zur gleichen Zeit müssen. Vor dem Benutzer TeamsOnly Modus erreichen können Organisationen verwenden die Skype für Business Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), um sicherzustellen, dass vorhersehbare Kommunikation zwischen Benutzern, die TeamsOnly sind und Personen, die noch nicht.


Aus der Sicht technical steuert eines Benutzers Modus verschiedene Aspekte des Benutzers:

- *Routing von eingehenden*: In welcher Client (Teams oder Skype für Unternehmen) eingehende chats und ruft Land? 
- *Veröffentlichung der Anwesenheit*: ist die Anwesenheit des Benutzers, die für andere Benutzer basierend auf ihrer Aktivität in Teams oder Skype für Unternehmen angezeigt werden? 
- *Besprechung planen*: welcher Dienst verwendet wird, für die Planung von neuer Besprechungen und sicherstellen, dass das richtige Add-in in Outlook vorhanden ist? Beachten Sie, dass TeamsUpgradePolicy Teilnahme an einer Besprechung nicht gesteuert wird. Benutzer können immer *Join* jede Besprechung, ob es sich um einen Skype für geschäftliche Besprechung oder einer Besprechung Teams sein.
- *Clientumgebung*: welche Funktionalität in Teams und/oder Skype für Business-Client verfügbar ist? Werden Benutzer können Anrufe und Chats in Teams, Skype für Unternehmen oder beides gestartet? Ist, dass Teams & Kanäle Erfahrung verfügbar?  

Weitere Informationen zu routing und Anwesenheit Verhalten basierend auf Modus finden Sie unter [Koexistenz mit Skype für Unternehmen](https://docs.microsoft.com/en-us/MicrosoftTeams/coexistence-chat-calls-presence).

Jedoch kann aus der Sicht Erfahrung Modus einfacher als beschrieben werden bei der definieren:
- *Chat und Aufrufen*: der Clientcomputer ein Benutzer verwenden?
- *Besprechung planen*: Führen Sie Benutzer neue Besprechungen als Teams oder Skype für Business Besprechungen planen?
- *Verfügbarkeit von Funktionen zur Zusammenarbeit in Teams Client*. Steht die Funktionalität Teams & Kanäle und Dateien während Benutzer weiterhin Skype für Unternehmen haben?

Die Modi sind unten aufgeführt.
</br>
</br>

|Modus|Anruf- und Chat|Besprechung planen<sup>1</sup>|Teams & Kanäle|Anwendungsfall|
|---|---|---|---|---|
|**TeamsOnly**</br>*Startseite erfordert in Skype für Business Online*|Microsoft Teams|Microsoft Teams|Ja|Der endgültige Zustand der gerade aktualisiert wird. Auch die Standardeinstellung für neue Mandanten mit <500 sitzen.|
|Inseln|Entweder|Entweder|Ja|Standardkonfiguration. Ermöglicht einem einzelnen Benutzer für beide Clients nebeneinander ausgewertet werden soll. Chats und Anrufe können entweder Client sorgt, damit Benutzer immer beide Clients ausgeführt werden müssen.|
|SfBWithTeamsCollabAndMeetings|Skype for Business|Teams|Ja|"Besprechungen ersten". In erster Linie für lokalen Organisationen profitieren Sie von Teams besprechungsfunktionen enthalten, wenn sie noch nicht zum Aufrufen der Cloud fortfahren bereit sind.|
|SfBWithTeamsCollab|Skype for Business|Skype for Business|Ja|Alternative Ausgangspunkt für komplexe Organisationen, die genauer Verwaltungsfunktionen benötigen.|
|SfBOnly|Skype for Business|Skype for Business|Keine<sup>2</sup>|Spezielle Szenario für Organisationen mit strikten Anforderungen, um Datensteuerelement. Teams wird nur von anderen Benutzern geplante Besprechungen teilnehmen.|
||||||

</br>
</br>

**Notizen:**

<sup>1</sup> die Möglichkeit, eine vorhandene Besprechung teilzunehmen (, ob in Teams oder in Skype für Unternehmen geplant) nicht Modus unterliegt. Standardmäßig können Benutzer immer jede Besprechung teilnehmen, die sie eingeladen wurden.

<sup>2</sup> derzeit Teams benötigt keinen die Möglichkeit, die Funktionalität Teams und Kanäle zu deaktivieren, damit dies jetzt aktiviert ist.



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

Für den Verbund von Teams an einen anderen Benutzer, die Verwendung von Skype für Unternehmen muss der Benutzer Teams online in Skype für Unternehmen verwaltet werden. Schließlich werden können nur Benutzer Föderation mit Teams Benutzer in Skype verwaltet für Business lokale-Teams.

TeamsUpgradePolicy steuert routing für eingehende federated Chats und Anrufe. Verbundpartner Routingverhalten entspricht der gleichen Mandanten Szenarien, *außer im Inseln Modus*.  Wenn Empfänger im Modus Inseln sind: 
- Chats und Anrufe, die von Teams Flächen in SfB initiiert werden, wenn der Empfänger befindet sich in einem *Verbundpartner Mandanten*.
- Chats und Anrufe, die von Teams Flächen in Teams initiiert werden, wenn der Empfänger befindet sich im *gleichen Mandanten*.
- Chats und immer aus SfB getätigte Anrufe sorgt in Skype für Unternehmen.

Weitere Informationen finden Sie unter [Koexistenz mit Skype für Unternehmen](https://docs.microsoft.com/en-us/MicrosoftTeams/coexistence-chat-calls-presence).

## <a name="the-teams-client-user-experience-when-using-sfb-modes"></a>SfB Modi mithilfe der Teams-Clientbenutzer auftreten
Wenn ein Benutzer in einer der der Skype für Business Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) ist, werden alle eingehenden Chats und Anrufe an Skype für Business-Client des Benutzers weitergeleitet. Endbenutzer Verwechslungen und die Sicherstellung ordnungsgemäßes routing, ist Anruf- und Chat Funktionalität in der Teams-Client deaktiviert, wenn ein Benutzer in einer der der Skype für Business Modi ist. In ähnlicher Weise ist Besprechung planen in Teams explizit deaktiviert, wenn Benutzer in den SfBOnly oder SfBWithTeamsCollab Modi sind und explizit aktiviert, wenn ein Benutzer in den Modus SfBWithTeamsCollabAndMeetings ist. Die Funktion zum Deaktivieren von automatisch chat und Funktionen aufrufen sowie Aktivieren/Deaktivieren der Besprechung planen, basierend auf Modus ist jetzt erhältlich. Weitere Informationen zu den neuen Funktionen finden Sie unter [Clientumgebung Teams und Konformität mit Koexistenz Modi](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes).

> [!Note] 
> - Vor der Bereitstellung von der automatischen Erzwingung von Teams und Kanäle Verhalten sich die Modi SfbOnly und SfBWithTeamsCollab.



## <a name="teamsinteroppolicy-and-legacy-mode-has-been-retired"></a>TeamsInteropPolicy und Legacymodus wurde zurückgezogen 

TeamsInteropPolicy wurde durch TeamsUpgradePolicy ersetzt. Alle Komponenten, die zuvor TeamsInteropPolicy berücksichtigt wurden aktualisiert, um stattdessen TeamsUpgradePolicy berücksichtigt. Microsoft hat zuvor "Legacymodus" in TeamsUpgradePolicy zur Erleichterung des Übergangs von TeamsInteropPolicy zu TeamsUpgradePolicy eingeführt. Routingkomponenten, die TeamsUpgradePolicy verstanden würde im Legacy-Modus auf TeamsInteropPolicy zurückgesetzt. Routing unterstützt jetzt vollständig TeamsUpgradePolicy. Legacymodus wird nicht mehr unterstützt, und es ist nicht mehr möglich, Legacymodus zu erteilen.


## <a name="detailed-mode-descriptions"></a>Beschreibungen der detaillierten Modus
</br>
</br>

|Modus|Erklärung|
|---|---|
|**Inseln**</br>(Standard)|Ein Benutzer führt beide Skype für Geschäfts- und Teams Side-by-Side. Diesen Benutzer:</br><ul><li>Chats können initiieren und VoIP-Anrufe in beiden Skype für Business oder Teams Client. Hinweis: Benutzer mit Skype für Unternehmen verwaltet lokale können nicht aus einer anderen Skype für Geschäftsbenutzer, unabhängig von der Aufgabenliste des Empfängers Modus erreichen Teams initiieren.<li>Empfängt Chats & VoIP-Anrufe, die in Skype für Unternehmen von einem anderen Benutzer in ihren Skype für Business-Client initiiert.<li>Empfängt Chats & VoIP initiierte in Teams von einem anderen Benutzer in ihren Teams Client Ruft, wenn diese sich in *derselben mandantenorganisation*befinden.<li>Empfängt Chats & VoIP von Anrufen in initiierte Teams von einem anderen Benutzer in ihren Skype für Business-Client werden in einem *Verbundpartner Mandanten*. <li>Verfügt über PSTN-Funktionen wie unten angegeben:<ul><li>Wenn der Benutzer in Skype für Business lokal verwaltet wird, sind PSTN-Anrufe initiiert und in Skype für Unternehmen erhalten.<li>Wenn der Benutzer online verwaltet wird, hat der Benutzer Telefonsystem, in dem den Benutzer case:<ul><li>Initiiert und PSTN-Anrufe in Teams erhält, wenn der Benutzer für das direkte Routing konfiguriert ist<li>Initiiert und PSTN-Anrufe in Skype für Unternehmen erhält, wenn der Benutzer ein MS aufrufen planen hat oder stellt eine mit dem PSTN-Netzwerk über entweder Skype für Business Cloud Connector Edition oder einer lokalen Bereitstellung von Skype für Business Server (Hybrid-VoIP Verbindung)</ul></ul><li>Planen von Besprechungen in Teams oder Skype für Unternehmen können (und sieht standardmäßig beide-Plug-ins).<li>Kann eine beliebige Skype für Business oder Teams Besprechung teilnehmen; die Besprechung wird in den jeweiligen Client geöffnet.</ul>|
|**SfBOnly**|Ein Benutzer führt nur Skype für Unternehmen. Diesen Benutzer:</br><ul><li>Können Chats und Anrufe von Skype für Unternehmen nur initiieren.<li>Empfängt alle Chat/Aufruf in ihren Skype für Business-Client unabhängig von wobei initiiert, es sei denn, der Initiator Teams Benutzer mit Skype für Unternehmen ist der lokale verwaltet. * <li>Können nur Skype für Business Besprechungen planen, aber Skype für Business oder Teams Besprechungen beitreten können. </br> *Using Inseln Modus mit lokalen Benutzern wird nicht in Kombination mit anderen Benutzern im SfBOnly Modus empfohlen. Wenn ein Benutzer Teams mit Skype für Unternehmen, verwaltet lokale initiiert einen Anruf oder Chat an einen Benutzer SfBOnly, der SfBOnly-Benutzer ist nicht erreichbar und erhält eine verpasste Chat/Anrufe email.*|
|**SfBWithTeamsCollab**|Ein Benutzer führt beide Skype für Geschäfts- und Teams Side-by-Side. Diesen Benutzer:</br><ul><li>Verfügt über die Funktionen eines Benutzers im SfBOnly Modus.<li>Teams hat nur für die Zusammenarbeit von Gruppen (Kanäle); aktiviert werden Chat/aufrufen/Besprechung planen sind deaktiviert.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|Ein Benutzer führt beide Skype für Geschäfts- und Teams Side-by-Side. Diesen Benutzer:<ul><li>Hat die Chat und Anruffunktionen des Benutzers im SfBOnly Modus.<li>Teams für die Zusammenarbeit von Gruppen aktiviert wurde (Kanäle - Kanal Unterhaltungen enthält); Chat und Aufrufen von sind deaktiviert.<li>Planen Sie nur Teams Besprechungen können, jedoch können Skype für Business oder Teams Besprechungen teilnehmen.</ul>|
|**TeamsOnly**</br>(erfordert SfB Online privat)|Ein Benutzer führt nur Teams. Diesen Benutzer:<ul><li>Empfängt alle Chats, und unabhängig von ihren Teams-Client aufruft, in denen initiiert hat.<li>Können Chats und nur von Teams Anrufe initiieren.<li>Können nur in Teams Besprechungen planen Sie, aber beitreten Sie Skype für Business oder Teams Besprechungen können.<li>Können weiterhin Skype für Business IP-Telefone verwenden.</ul> |
|||




## <a name="related-topics"></a>Verwandte Themen

[Koexistenz mit Skype for Business](https://docs.microsoft.com/en-us/microsoftteams/coexistence-chat-calls-presence)

[Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[GRANT-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)


