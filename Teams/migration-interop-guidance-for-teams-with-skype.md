---
title: Migration und Interoperabilität – Skype for Business
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Leitfaden zum Verwalten des Übergangs zu Teams von Skype for Business
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.coexistence
- ms.teamsadmincenter.teamsupgrade.overview
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bf12dc366de030329b306fdd2f68291b5ff532d
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140274"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden

> [!Tip] 
> Sehen Sie sich die folgende Sitzung an, um mehr über [Koexistenz und Interoperabilität](https://aka.ms/teams-upgrade-coexistence-interop) zu erfahren.

Da eine Organisation mit Skype for Business beginnt, Teams zu übernehmen, können Administratoren die Benutzererfahrung in Ihrer Organisation mithilfe des Konzepts der Koexistenz "Modus" verwalten, bei dem es sich um eine Eigenschaft von TeamsUpgradePolicy handelt. Mithilfe des Modus verwalten Administratoren Interop und Migration, während Sie den Übergang von Skype for Business zu Teams verwalten.  Der Modus eines Benutzers bestimmt, in welchem Client eingehende Chats und Anrufe landen sowie in welchem Dienst (Teams oder Skype for Business) neue Besprechungen geplant sind. Darüber hinaus wird geregelt, welche Funktionen im Team-Client verfügbar sind. 


## <a name="fundamental-concepts"></a>Grundlegende Konzepte

1.  *Interop* : 1 bis 1 Kommunikation zwischen einem lync/Skype for Business-Benutzer und einem Teams-Benutzer.

2.  *Föderation* : Kommunikation zwischen Benutzern aus verschiedenen Mandanten.

3.  Alle Teams-Benutzer verfügen über ein zugrunde liegendes Skype for Business-Konto, das entweder online oder lokal "verwaltet" ist:
    - Nutzer, die Skype for Business Online bereits nutzen, verwenden Ihr vorhandenes Online-Konto.
    - Benutzer, die Skype for Business/lync bereits lokal verwenden, verwenden Ihr vorhandenes lokales Konto.
    - Für Benutzer, für die ein vorhandenes Skype for Business-Konto nicht erkannt werden kann, wird beim Erstellen des Teams-Benutzers automatisch ein Skype for Business Online-Konto bereitgestellt.

4.  Wenn Sie über eine lokale Bereitstellung von Skype for Business oder lync verfügen und diese Benutzer Team Benutzer sein sollen, müssen Sie mindestens sicherstellen, dass Azure AD Connect das Attribut msRTCSIP-DeploymentLocator-Attribut in Aad synchronisiert, damit Teams/Skype for Business Online Ihre lokale Umgebung ordnungsgemäß erkennt. Darüber hinaus *müssen Sie zuerst den Skype for Business-Hybrid Modus konfigurieren*, um alle Benutzer in den Modus "nur für Teams" zu verschieben (also einen Benutzer zu aktualisieren). Weitere Informationen finden Sie unter [Konfigurieren von Azure AD Connect für Skype for Business und Teams](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).

5.  Interop zwischen Teams und Skype for Business-Benutzern ist nur möglich, *Wenn der Benutzer von Teams in Skype for Business Online ist*. Der Empfänger Skype for Business-Benutzer kann entweder lokal verwaltet werden (und erfordert die Konfiguration von Skype for Business-Hybrid) oder online. Benutzer, die in Skype for Business lokal gehostet werden, können Teams im Modus "Inseln" (später in diesem Dokument definiert) verwenden, aber Sie können keine Teams für Interop oder Föderation mit anderen Benutzern verwenden, die Skype for Business verwenden.  

6.    Das Upgrade-und Interop-Verhalten wird basierend auf dem Koexistenzmodus eines Benutzers bestimmt, der später weiter unten beschrieben wird. Der Modus wird von TeamsUpgradePolicy verwaltet. 

7.  Durch das Upgrade eines Benutzers auf den TeamsOnly-Modus wird sichergestellt, dass alle eingehenden Chats und Anrufe immer im Team-Client des Benutzers landen, unabhängig davon, von welchem Client er stammt. Diese Benutzer planen auch alle neuen Besprechungen in Teams. Um im TeamsOnly-Modus zu sein, muss ein Benutzer in Skype for Business online sein. Dies ist erforderlich, damit Interop, Federation und die vollständige Verwaltung des Teams-Benutzers sichergestellt sind. So aktualisieren Sie einen Benutzer auf TeamsOnly:
    - Wenn sich der Benutzer in Skype for Business Online befindet (oder nie über ein Skype-Konto verfügt), gewähren Sie ihm TeamsUpgradePolicy mit Mode = TeamsOnly mit der "UpgradeToTeams"-Instanz mithilfe von PowerShell, oder verwenden Sie das Team Admin Center, um den TeamsOnly-Modus auszuwählen.
    - Wenn der Benutzer lokal verwaltet wird, verwenden Sie `Move-CsUser` die lokalen Verwaltungstools, um den Benutzer zuerst in Skype for Business Online zu verschieben.  Wenn Sie über Skype for Business Server 2019 oder CU8 für Skype for Business Server 2015 verfügen, können Sie den `-MoveToTeams` Schalter angeben `Move-CsUser` , um den Benutzer im Rahmen des Online-Umzugs direkt in Teams zu verschieben. Mit dieser Option werden auch die Besprechungen des Benutzers in Teams migriert. Wenn `-MoveToTeams` nicht angegeben oder nicht verfügbar ist, weisen Sie `Move-CsUser` dem Benutzer nach Abschluss den TeamsOnly-Modus zu, indem Sie entweder PowerShell oder das Team Admin Center verwenden. Weitere Informationen finden Sie unter [Verschieben von Benutzern zwischen lokalen und der Cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).  Weitere Informationen zur Besprechungs Migration finden Sie unter [Verwenden des Besprechungs Migrations Diensts (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

8.    Damit Microsoft Phone System mit Teams verwendet werden kann, müssen sich die Benutzer im TeamsOnly-Modus befinden (d. h., Sie werden in Skype for Business Online verwaltet und auf Teams aktualisiert), und Sie müssen entweder für das [direkte Routing](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277) von Microsoft Phone System konfiguriert sein (damit können Sie das Telefonsystem mit ihren eigenen SIP-Stämmen und SBC verwenden) oder einen Office 365-Anrufplan haben Das direkte Routing von Microsoft Phone-Systemen wird im Modus "Inseln" nicht unterstützt.    

9.  Das Planen von Teams-Besprechungen mit Audiokonferenzen (Einwahl oder Dial-Out über PSTN) steht unabhängig davon zur Verfügung, ob der Benutzer in Skype for Business Online oder in Skype for Business lokal gehostet ist. 


## <a name="coexistence-modes"></a>Koexistenzmodus

Interop und Migration werden basierend auf dem "Koexistenzmodus" mithilfe von TeamsUpgradePolicy verwaltet. Koexistenzmodus bietet für Endbenutzer eine einfache, vorhersagbare Erfahrung, da Organisationen von Skype for Business zu Teams wechseln. Für eine Organisation, die in Teams wechselt, ist der TeamsOnly-Modus das endgültige Ziel für jeden Benutzer, wobei nicht allen Benutzern gleichzeitig TeamsOnly (oder ein beliebiger Modus) zugewiesen werden muss. Bevor Benutzer den TeamsOnly-Modus erreichen, können Organisationen alle Skype for Business-Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) verwenden, um eine vorhersagbare Kommunikation zwischen Benutzern, die TeamsOnly sind, und denjenigen, die noch nicht sind, zu gewährleisten.


Aus technischer Sicht regelt der Benutzermodus verschiedene Aspekte der Benutzererfahrung:

- *Eingehendes Routing*: in welchem Client (Teams oder Skype for Business) führen Sie eingehende Chats und Anrufe Land? 
- *Anwesenheits Veröffentlichung*: ist die Anwesenheit des Benutzers, die anderen Benutzern auf der Grundlage ihrer Aktivitäten in Microsoft Teams oder Skype for Business angezeigt wird? 
- *Besprechungsplanung*: welcher Dienst wird für das Planen neuer Besprechungen verwendet, und es wird sichergestellt, dass das richtige Add-in in Outlook vorhanden ist? Beachten Sie, dass TeamsUpgradePolicy keine Besprechungsteilnahme regelt. Benutzer können immer *an einer Besprechung teilnehmen* , und zwar unabhängig davon, ob es sich um eine Skype for Business-Besprechung oder eine Teams-Besprechung handelt.
- *Client Experience*: welche Funktionen stehen in Teams und/oder Skype for Business-Client zur Verfügung? Können Benutzer Anrufe und Chats in Teams, Skype for Business oder beides initiieren? Sind Teams & Kanäle verfügbar?  

Weitere Informationen zu Routing und Anwesenheits Verhalten basierend auf dem Modus finden Sie unter [Koexistenz mit Skype for Business](https://docs.microsoft.com/MicrosoftTeams/coexistence-chat-calls-presence).

Im Hinblick auf die Erfahrung kann der Modus jedoch einfacher als die Definition der Benutzeroberfläche beschrieben werden:
- *Chat und Anrufe*: welcher Client wird von einem Benutzer verwendet?
- *Besprechungsplanung*: planen Benutzer neue Besprechungen als Teams oder Skype for Business-Besprechungen?
- *Verfügbarkeit der Funktionen für die Zusammenarbeit im Team-Client*. Sind Teams & Kanal-und Dateifunktionen verfügbar, während Benutzer weiterhin Skype for Business nutzen?

Die Modi sind im folgenden aufgeführt.
</br>
</br>

|Modus|Anrufen und chatten|Besprechungsplanung<sup>1</sup>|Teams & Kanäle|Anwendungsfall|
|---|---|---|---|---|
|**TeamsOnly<sup>2</sup>**</br>*Erfordert Home in Skype for Business Online*|Microsoft Teams|Microsoft Teams|Ja|Der endgültige Zustand des Upgrades. Auch die Standardeinstellung für neue Mandanten.|
|Inselmodus|Entweder|Entweder|Ja|Standardkonfiguration. Ermöglicht einem einzelnen Benutzer die Auswertung beider Clients nebeneinander. Chats und Anrufe können in einem der beiden Clients erfolgen, sodass Benutzer stets beide Clients ausführen müssen. Um eine verwirrende oder rückläufige Skype for Business-Erfahrung zu vermeiden, werden externe (Verbund-) Kommunikationen, PSTN-Sprachdienste und Sprachanwendungen, Office-Integration und verschiedene andere Integrationen weiterhin von Skype for Business gehandhabt.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype for Business|Teams|Ja|"Besprechungen zuerst". In erster Linie für lokale Organisationen, um von den Funktionen der Teambesprechung zu profitieren, wenn Sie noch nicht bereit sind, Anrufe in die Cloud zu verschieben.|
|SfBWithTeamsCollab|Skype for Business|Skype for Business|Ja|Alternativer Ausgangspunkt für komplexe Organisationen, die eine strengere administrative Steuerung benötigen.|
|SfBOnly|Skype for Business|Skype for Business|No<sup>3</sup>|Spezielles Szenario für Organisationen mit strengen Anforderungen im Hinblick auf die Datensteuerung. Teams wird nur für die Teilnahme an Besprechungen verwendet, die von anderen Personen geplant wurden.|
||||||

</br>
</br>

**Notizen**

<sup>1</sup> die Möglichkeit, an einer vorhandenen Besprechung teilzunehmen (unabhängig davon, ob Sie in Teams oder in Skype for Business geplant ist), wird nicht vom Modus geregelt. Standardmäßig können Benutzer immer an einer Besprechung teilnehmen, zu der Sie eingeladen wurden.

<sup>2</sup> Wenn Sie einem einzelnen Benutzer entweder TeamsOnly oder SfbWithTeamsCollabAndMeetings zuweisen, werden alle vorhandenen Skype for Business-Besprechungen, die dieser Benutzer für die Zukunft geplant hat, in Teams-Besprechungen umgewandelt. Falls gewünscht, können Sie diese Besprechungen als Skype for Business-Besprechungen belassen, indem Sie entweder angeben `-MigrateMeetingsToTeams $false` , ob Sie TeamsUpgradePolicy gewähren möchten, oder indem Sie das Kontrollkästchen im Team-Administratorportal deaktivieren.   Beachten Sie, dass die Möglichkeit, Besprechungen von Skype for Business in Teams umzuwandeln, nicht verfügbar ist, wenn TeamsUpgradePolicy auf Mandantenebene gewährt wird. 

<sup>3</sup> zurzeit hat Teams nicht die Möglichkeit, die Funktionen Teams und Kanäle zu deaktivieren, sodass dies für jetzt aktiviert bleibt.



## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy: Verwalten von Migration und Koexistenz

TeamsUpgradePolicy macht zwei wichtige Eigenschaften verfügbar: Mode und NotifySfbUsers. 
</br>
</br>

|Parameter|Typ|Zulässige Werte</br>(standardmäßig in Kursivschrift)|Beschreibung|
|---|---|---|---|
|Modus|Enumerationswert|*Inselmodus*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Gibt den Modus an, in dem der Client ausgeführt werden soll.|
|NotifySfbUsers|Boolescher Wert|*Falsch* oder wahr|Gibt an, ob ein Banner im Skype for Business-Client angezeigt wird, in dem der Benutzer informiert wird, dass Teams in Kürze Skype for Business ersetzen werden. Dies kann nicht wahr sein, wenn Mode = TeamsOnly.|
|||||

Teams stellt alle relevanten Instanzen von TeamsUpgradePolicy über integrierte, schreibgeschützte Richtlinien bereit. Daher stehen nur Get-und Grant-Cmdlets zur Verfügung. Die integrierten Instanzen sind im folgenden aufgeführt.
</br>
</br>

|Identität |Modus|NotifySfbUsers|
|---|---|---|
|Inselmodus|Inselmodus|Falsch|
|IslandsWithNotify|Inselmodus|Wahr|
|SfBOnly|SfBOnly|Falsch|
|SfBOnlyWithNotify|SfBOnly|Wahr|
|SfBWithTeamsCollab|SfBWithTeamsCollab|Falsch|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|Wahr|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|Falsch|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|Wahr|
|UpgradeToTeams|TeamsOnly|Falsch|
|Global</br>*Standard*|Inselmodus|Falsch|
||||

Diese Richtlinieninstanzen können entweder einzelnen Benutzern oder auf Mandantenebene gewährt werden. Beispiel:
- Wenn Sie einen Benutzer ($SipAddress) auf Teams aktualisieren möchten, gewähren Sie die "UpgradeToTeams"-Instanz:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Um den gesamten Mandanten zu aktualisieren, lassen Sie den Parameter Identity aus dem Befehl Grant aus:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`


## <a name="federation-considerations"></a>Überlegungen zu Föderationen

Föderation von Teams zu einem anderen Benutzer unter Verwendung von Skype for Business setzt voraus, dass der Benutzer von Teams in Skype for Business Online ist.

TeamsUpgradePolicy steuert das Routing für eingehende Federated-Chats und-Anrufe. Das Verhalten des Verbund Routings ist identisch mit den Szenarien für denselben Mandanten, *mit Ausnahme des Modus "Inseln"*.  Wenn sich die Empfänger im Inseln-Modus befinden: 
- Chats und Anrufe, die von Teams initiiert werden, landen im SFB, wenn sich der Empfänger in einem *Federated-Mandanten*befindet.
- Chats und Anrufe, die von Teams initiiert werden, landen in Teams, wenn sich der Empfänger im *gleichen Mandanten*befindet.
- Chats und Anrufe, die vom SFB initiiert werden, landen immer in Skype for Business.

Weitere Informationen finden Sie unter [Koexistenz mit Skype for Business](https://docs.microsoft.com/MicrosoftTeams/coexistence-chat-calls-presence).

## <a name="the-teams-client-user-experience-when-using-sfb-modes"></a>Benutzerfreundlichkeit des Teams-Clients bei Verwendung der SFB-Modi
Wenn sich ein Nutzer in einem der Skype for Business-Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) befindet, werden alle eingehenden Chats und Anrufe an den Skype for Business-Client des Benutzers weitergeleitet. Um die Verwirrung des Endbenutzers zu vermeiden und die ordnungsgemäße Weiterleitung zu gewährleisten, werden Anruf-und Chatfunktionen im Teams-Client automatisch deaktiviert, wenn sich ein Benutzer in einem der Skype for Business-Modi befindet. Ebenso wird die Terminplanung in Teams automatisch deaktiviert, wenn sich Benutzer im SfBOnly-oder SfBWithTeamsCollab-Modus befinden, und automatisch aktiviert, wenn sich ein Benutzer im SfBWithTeamsCollabAndMeetings-Modus befindet. Ausführliche Informationen finden Sie unter [Teams-Clientumgebung und Konformität mit Koexistenzmodus](https://docs.microsoft.com/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes).

> [!Note] 
> - Vor der Bereitstellung der automatischen Erzwingung von Teams und Kanälen Verhalten sich der SfbOnly-und der SfBWithTeamsCollab-Modus identisch.


## <a name="detailed-mode-descriptions"></a>Beschreibungen des detaillierten Modus
</br>
</br>

|Modus|Erklärung|
|---|---|
|**Inselmodus**</br>Standard|Ein Benutzer führt sowohl Skype for Business als auch Teams nebeneinander aus. Dieser Nutzer:</br><ul><li>Kann Chats und VoIP-Anrufe in Skype for Business-oder Microsoft Teams-Client initiieren. Hinweis: Benutzer mit Skype for Business, die sich lokal vernetzen, können unabhängig vom Modus des Empfängers nicht aus Teams initiieren, um einen anderen Skype for Business-Benutzer zu erreichen.<li>Empfängt Chats & VoIP-Anrufe, die in Skype for Business von einem anderen Nutzer in seinem Skype for Business-Client initiiert wurden.<li>Empfängt Chats & VoIP-Anrufe, die in Teams von einem anderen Benutzer in seinem Team-Client initiiert wurden, wenn Sie sich im *gleichen Mandanten*befinden.<li>Empfängt Chats & VoIP-Anrufe, die in Teams von einem anderen Benutzer in Ihrem Skype for Business-Client initiiert wurden, wenn Sie sich in einem *Federated*-Mandanten befinden. <li>Hat die PSTN-Funktionalität wie nachstehend beschrieben:<ul><li>Wenn der Benutzer in Skype for Business lokal beheimatet ist und Enterprise-VoIP hat, werden PSTN-Anrufe immer in Skype for Business initiiert und empfangen.<li>Wenn sich der Benutzer in Skype for Business Online befindet und über ein Microsoft Phone System verfügt, initiiert und empfängt der Benutzer immer PSTN-Anrufe in Skype for Business:<ul><li>Dies geschieht unabhängig davon, ob der Benutzer über einen Microsoft-Anrufplan verfügt oder eine Verbindung mit dem PSTN-Netzwerk über eine Skype for Business Cloud Connector Edition oder eine lokale Bereitstellung von Skype for Business Server (Hybrid-VoIP) herstellt.<li>**Hinweis: Microsoft Teams Phone System Direct Routing wird im Modus "Inseln" nicht unterstützt.**</ul></ul><li>Empfängt Microsoft-Anrufwarteschlangen und automatische Telefonzentralen-Anrufe in Skype for Business:<ul><li>Telefonnummern, die den Anrufwarteschlangen und automatischen Telefonzentralen zugewiesen sind, **können nicht** im Modus "Inseln" Direktes Routing Nummern von Microsoft Teams sein.</ul></ul><li>Sie können Besprechungen in Teams oder Skype for Business planen (und beide Plug-ins werden standardmäßig angezeigt).<li>Kann an einer Skype for Business-oder Teams-Besprechung teilnehmen die Besprechung wird im jeweiligen Client geöffnet.</ul>|
|**SfBOnly**|Ein Benutzer führt nur Skype for Business aus. Dieser Nutzer:</br><ul><li>Kann Chats und Anrufe nur über Skype for Business initiieren.<li>Empfängt alle Chats/Anrufe in Ihrem Skype for Business-Client, unabhängig davon, wo Sie initiiert wurden, es sei denn, der Initiator ist ein Team Nutzer, in dem Skype for Business lokal gehostet wird. *Kann nur Skype for Business-Besprechungen planen, kann aber an Skype for Business-oder Teams-Besprechungen teilnehmen. <li> </br> *Die Verwendung des Modus "Inseln" mit lokalen Benutzern wird in Verbindung mit anderen Benutzern im SfBOnly-Modus nicht empfohlen. Wenn ein Benutzer von Teams, in dem Skype for Business lokal gehostet wird, einen Anruf oder einen Chat mit einem SfBOnly-Nutzer initiiert, ist der SfBOnly-Nutzer nicht erreichbar und erhält eine verpasste Chat-/Anruf-e-Mail. *|
|**SfBWithTeamsCollab**|Ein Benutzer führt sowohl Skype for Business als auch Teams nebeneinander aus. Dieser Nutzer:</br><ul><li>Hat die Funktionalität eines Benutzers im SfBOnly-Modus.<li>Hat Teams nur für Gruppenzusammenarbeit (Kanäle) aktiviert; Chat/Anruf-und Besprechungsplanung sind deaktiviert.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|Ein Benutzer führt sowohl Skype for Business als auch Teams nebeneinander aus. Dieser Nutzer:<ul><li>Hat die Chat-und Anruffunktion des Benutzers im SfBOnly-Modus.<li>Verfügt über Teams, die für die Gruppenzusammenarbeit aktiviert sind (Kanäle – umfasst Kanal Unterhaltungen); Chat und Anrufe sind deaktiviert.<li>Kann nur Teambesprechungen planen, kann aber an Skype for Business-oder Teams-Besprechungen teilnehmen.</ul>|
|**TeamsOnly**</br>(erfordert SFB Online-Startseite)|Ein Benutzer führt nur Teams aus. Dieser Nutzer:<ul><li>Empfängt alle Chats und Anrufe in Ihrem Teams-Client, unabhängig davon, wo Sie initiiert wurden.<li>Kann Chats und Anrufe nur von Teams aus initiieren.<li>Sie können Besprechungen nur in Teams planen, aber Sie können an Skype for Business-oder Teams-Besprechungen teilnehmen.<li>Skype for Business-IP-Telefone weiterhin nutzen können.<br><br>*Die Verwendung des TeamsOnly-Modus in Kombination mit anderen Benutzern im Modus "Inseln" wird erst empfohlen, wenn die Einführung von Teams gesättigt ist, d. h. alle Benutzer im Modus "Inseln" aktiv die Teams und Skype for Business-Clients verwenden und überwachen. Wenn ein TeamsOnly-Benutzer einen Anruf oder Chat mit einem Nutzer der Inselgruppe initiiert, landet dieser Anruf oder Chat im Team-Client der Inseln des Benutzers. Wenn der Benutzer der Inseln keine Teams verwendet oder überwacht, wird dieser Benutzer als offline angezeigt und ist vom TeamsOnly-Benutzer nicht erreichbar.*</ul> |
|||




## <a name="related-topics"></a>Verwandte Themen

[Koexistenz mit Skype for Business](https://docs.microsoft.com/microsoftteams/coexistence-chat-calls-presence)

[Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](https://docs.microsoft.com/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Verwenden des Besprechungs Migrations Diensts (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
