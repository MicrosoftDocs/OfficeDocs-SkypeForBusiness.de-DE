---
title: Aktivieren von Teams Seite an Seite mit Skype for Business
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Anleitung zur gleichzeitigen Verwendung von Skype for Business und Microsoft Teams.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 27e6f4449f4568f9777be92c8520215721154e2f
ms.sourcegitcommit: 70fc5217f588e10ab0edb400f329ea597efaab52
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2018
---
<a name="enable-microsoft-teams-side-by-side-with-skype-for-business"></a>Aktivieren von Teams Seite an Seite mit Skype for Business 
=============================================================

Für Organisationen mit vorhandenen Bereitstellungen von Skype for Business Online stellt die kürzliche Einführung von Microsoft Teams eine Möglichkeit dar, das Potenzial von Teams als eigenständige Lösung für Kommunikation und Zusammenarbeit zu bewerten. Des Weiteren stellt sie eine Herausforderung dar, die beiden Lösungen gegenüber zu stellen und zu ermitteln, ob sie in Ihrer Umgebung koexistieren können.

Wenn Teams Ihre heutigen Geschäftsanforderungen erfüllen kann, können Sie mit der Übernahme von Teams als alleinige Lösung für Kommunikation und Zusammenarbeit in Ihrer Organisation beginnen.

Teams ist standardmäßig auf allen berechtigten Mandanten aktiviert. Aus diesem Grund müssen Sie entscheiden, wie Sie Teams bei gleichzeitiger Verwendung von Skype for Business verwalten möchten, und damit fortfahren, die Erwartungen Ihrer Benutzer zu erfüllen.

Im Allgemeinen gibt es zwei Szenarien für Kunden, beide Lösungen auszuführen. Bei diesen handelt es sich um:

-   **Option 1:** Nicht verwaltete Customer Journey beim Einsatz beider Lösungen

    Das IT-Team steuert die Verwendung von beiden Lösungen nicht aktiv, und die Benutzer werden angehalten, ihre bevorzugte App selbst auszuwählen.

-   **Option 2:** Verwaltete Customer Journey beim Einsatz beider Lösungen

    Das IT-Team steuert die Verwendung von beiden Lösungen, nimmt die Benutzer mit auf die Reise der schrittweisen Einführung in Teams und führt zuerst einen neuen chatbasierten Arbeitsbereich für Zusammenarbeit mit privatem Chat, dann die Besprechungsfunktionen und schließlich die Anruffunktionen von Teams ein.

![Diagramm, von zwei parallelen Customer Journeys: verwaltet und nicht verwaltet.](media/guidance_SkypeforBusiness_image1.png)

<a name="side-by-side-benefits-and-considerations"></a>Vorteile und Überlegungen zum gleichzeitigen Einsatz beider Lösungen
----------------------------------------

Um den richtigen Weg in Abhängigkeit vom Profil Ihrer Organisation zu beschreiten, müssen die Vorteile und Aspekte der jeweiligen Reise unter verschiedenen Gesichtspunkten betrachtet werden. In der Tabelle unten werden die verwaltete und nicht verwaltete Customer Journey beim Einsatz beider Lösungen gegenübergestellt.


<table>
<thead>
<tr class="header">
<th align="left">Migrationspfade</th>
<th align="left">Nicht verwalteter Einsatz beider Lösungen</th>
<th align="left">Verwalteter Einsatz beider Lösungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>Organisationsprofil</strong></td>
<td align="left"><ul>
<li>Normalerweise für kleinere Organisationen ohne dedizierte IT-Ressourcen</li>
<li>Das IT-Team stellt es den Benutzern frei, die richtigen Tools für ihre Arbeit auszuwählen</li>
<li>Primäre Skype for Business-Nutzung besteht aus Chats, Anrufen und Besprechungen</li>
</ul></td>
<td align="left"><ul><li>Normalerweise für Organisationen mittlerer Größe</li>
<li>Die IT-Abteilung möchte das Rollout von neuen Tools rigoroser kontrollieren</li>
<li>Derzeit größere Akzeptanz von Skype for Business</li>
<li>Erhöhte Komplexität für Netzwerk und Infrastruktur</li>
<li>Mehrere Standorte</p>
<li>Präferenz für einzelne App mit eindeutigen UC-Funktionen</li></ul></td>
</tr>
<tr class="even">
<td align="left"><strong>Vorteile</strong></td>
<td align="left"><ul>
<li>Nutzung von Funktionen in Teams, die in Skype for Business nicht verfügbar sind</li>
<li>Verbesserter moderner Arbeitsplatz mit Office 365</li>
<li>Erhöhte Benutzerflexibilität</li>
<li>Gleichzeitige Aktivierung aller Funktionen</li>
</ul></td>
<td align="left"><ul><li>Nutzung von Funktionen in Teams, die in Skype for Business nicht verfügbar sind</li>
<li>Verbesserter moderner Arbeitsplatz mit Office 365</li>
<li>Die Auswirkungen auf die Benutzerproduktivität werden minimiert</li>
<li>Die Funktionsüberlappung wird reduziert</li>
<li>Die Tool-Auswahl für UC-Szenarien wird optimiert</li>
<li>Die IT-Abteilung und die operative Abteilung werden bestärkt, die Funktionen nach Bedarf in der Organisation einzusetzen</li>
<li>Das Veränderungstempo wird für Benutzer gesteuert</li></ul></td>
</tr>
<tr class="odd">
<td align="left"><strong>Überlegungen</strong></td>
<td align="left"><ul>
<li>Mehrere Apps mit ähnlichen, sich überschneidenden Funktionen</li>
<li>Erhöhte Gefahr von Benutzerkonfusion, die zu vermehrten Supportanrufen, erhöhter Belastung des IT-Teams und Produktivitätseinbußen führt</li>
<li>Bei der Netzwerkplanung und -überwachung muss die Verwendung von zwei Diensten in Betracht gezogen werden</li>
<li>Ein erhöhter und unmittelbarer Change Management-Aufwand ist erforderlich: Sensibilisierung, Schulung und Support</li>
<li>Die Benutzer können auf Einschränkungen der Interoperabilität zwischen den Apps stoßen</li>
</ul></td>
<td align="left"><ul><li>Durch die granulare Kontrolle der IT-Abteilung – von der Lizenzierung bis zu den Funktionen für die Benutzer – sind zusätzliche Zyklen für Planung und Implementierung erforderlich</li>
<li>Benutzerschulungen und Aktionen sind erforderlich, um ausgewählte Funktionen in Teams zu deaktivieren</li>
<li>Change Management-Maßnahmen sind erforderlich, um ausgewählte Funktionen in Teams zu deaktivieren</li>
<li>Bei der Netzwerkplanung und -überwachung muss die Verwendung von zwei Diensten in Betracht gezogen werden</li>
<li>Die Benutzer können auf Einschränkungen der Interoperabilität zwischen den Apps stoßen</li></ul></td>
</tr>
</tbody>
</table>


<a name="unmanaged-side-by-side-customer-journey"></a>Nicht verwaltete Customer Journey beim Einsatz beider Lösungen
---------------------------------------


![Diagramm der nicht verwalteten Customer Journey beim Einsatz beider Lösungen](media/guidance_SkypeforBusiness_image4.png)

Auf einer nicht verwalteten Customer Journey beim Einsatz beider Lösungen wird Teams als Lösung zur Zusammenarbeit eingeführt (chatbasierter Arbeitsbereich, Kanäle, Apps, Integration in andere Office 365-Arbeitsauslastungen usw.), die Clientsoftware und einen Webclient auf Desktopcomputern (PC oder Mac) und Mobilgeräte mit einschließen.


Standardmäßig bietet Teams auch sich mit Skype for Business überlappende Funktionen. Diese beinhalten private Chats und Anrufe sowie geplante Besprechungen. Das heißt, dass Teams als vollständige Lösung für Kommunikation und Zusammenarbeit für die Organisation eingesetzt werden kann, während Skype for Business zur gleichen Zeit ähnliche Funktionen bietet.

Teams unterstützt die Interoperabilität mit Skype for Business Online-Benutzern, und Benutzer erhalten die Möglichkeit, ihre bevorzugte Chat- und Anruf-App auszuwählen, wenn sie Teams starten. Wenn ein Benutzer Teams als seine bevorzugte App verwendet, und ein anderer Benutzer Teams nicht installiert oder Skype for Business nicht als seine bevorzugte Chat- und Anruf-App nutzt, können die beiden weiterhin über die Interoperablititätsfunktionen, die Teil von Teams sind, miteinander chatten oder sich anrufen.

Microsoft verbessert kontinuierlich die Funktionen für Interoperablitität. Anfänglich können jedoch Situationen auftreten, in denen die Interoperabilität nicht die Erwartungen der Benutzer erfüllt. Da Skype for Business den Benutzern aber immer noch zur Verfügung steht, können Sie zu Skype for Business wechseln, um die Funktionen zu verwenden, die von Teams derzeit nicht bedient werden können.

„Geplante Besprechungen“ in Teams ist eine weitere überlappende Funktion, mit denen Benutzer Teams- oder Skype for Business-Besprechungen planen. Jede Lösung bietet ihre eigenen Vorteile, und mit der Zeit, wenn die Teams-Besprechungsfunktion die Geschäftsanforderungen erfüllt oder die Funktionen von Skype for Business-Besprechungen in puncto Qualität überholt, ist es nur natürlich, wenn die Benutzer zu Teams wechseln.

Bereiten Sie Ihr Helpdesk-Team auf diese nicht verwalteten Customer Journey beim Einsatz beider Lösungen vor, die Supportanrufe von Benutzern in Bezug auf Probleme mit der Interoperabilität zu bewältigen. Sie können die Benutzer auch dahingehend beraten, wann die Verwendung von Teams-Besprechungen sinnvoller als der Einsatz von Skype for Business-Besprechungen ist bzw. umgekehrt.

Diese Customer Journey beim Einsatz beider Lösungen kann für Ihre Organisation passend sein, wobei die Benutzer empfänglicher für die nicht verwaltete Reise sind, bei der die Organisation Ihre Benutzer offen dazu auffordert, die ihren Anforderungen am ehesten entsprechenden Tools zur Kommunikation und Zusammenarbeit auszuwählen.

<a name="managed-side-by-side-customer-journey"></a>Verwaltete Customer Journey beim Einsatz beider Lösungen
-------------------------------------

![Diagramm der verwalteten Customer Journey beim Einsatz beider Lösungen](media/guidance_SkypeforBusiness_image2.png)

Eine verwaltete Customer Journey beim Einsatz beider Lösungen beginnt damit, dass die Organisation mehr Kontrolle über die Art und Weise der Einführung von Teams wünscht.

-   Der **erste Schritt** dieser Reise ist ein limitiertes Teams-Pilotprojekt auf Basis von Anforderungen für moderne Zusammenarbeit (chatbasierter Arbeitsbereich, Kanäle, Apps, Integration in andere Office 365-Auslastungen usw.) Ad-hoc-Kanalbesprechungen und private Chats in Teams sind ebenfalls aktiviert, um Teilnehmern des Pilotprojekts die Chance zu geben, die Teams-Besprechungsfunktionen und die Funktionen für private Chats zu bewerten. In dieser Phase sind geplante Besprechungen und private Anruffunktionen in Teams deaktiviert. Um ein Pilotprojekt zu starten, navigieren Sie zu [Teams als Pilotprojekt neben Skype for Business](pilot-essentials.md).
    
-   Der **zweite Schritt** dieser Reise ist die Erweiterung des Rollouts von Teams für moderne Zusammenarbeit mit der Funktion für privaten Chat in der gesamten Organisation. Die Funktionen für geplante Besprechungen und private Anrufe sind in Teams weiterhin deaktiviert, um die Überlappung mit Skype for Business-Funktionen zu reduzieren.

    In dieser Phase müssen Sie darüber nachdenken, ob es sich bei der bevorzugten Chatanwendung für die gesamte Organisation um Teams oder Skype for Business handeln soll.

    - Wenn Sie sich für Teams entscheiden, bereiten Sie Ihre Benutzer darauf vor, bei der Kommunikation mit anderen Benutzern in der Organisation möglicherweise auftretende Probleme bei der Interoperabilität frühzeitig zu beheben.
    
    - Wenn Sie sich für Skype for Business entscheiden, werden private Chats innerhalb von Teams in Teams beibehalten. Endbenutzer können sofort die Vorteile der plattformübergreifenden und beständigen Chatfunktionen innerhalb von Teams nutzen und weiterhin Skype for Business für private Chats mit anderen Skype for Business-Benutzern innerhalb und außerhalb der Organisation nutzen.


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>Hinweis</p></td>
<td align="left"><br><br>Die Einstellung für die bevorzugte Chatanwendung ist derzeit nur auf der Clientebene verfügbar. Benutzerschulungen und Übernahmekampagnen sind erforderlich, um die beabsichtigte organisationsweite Konfiguration voranzutreiben.</td>
</tr>
</thead>
<tbody>
</tbody>
</table>

Der **dritte Schritt** der verwalteten Customer Journey beim Einsatz beider Lösungen startet, wenn die Organisation entscheidet, dass die Teams-Besprechungsfunktionen ihren Anforderungen entsprechen. Durch die Aktivierung von privaten und Kanalbesprechungen in Teams erhalten Benutzer Optionen zum Planen von Teams-Besprechungen und Skype for Business-Besprechungen. Es ist daher zu erwarten, dass Benutzer mit der Zeit aufgrund kontinuierlicher Innovationen in Teams zwangsläufig zu Teams-Besprechungen wechseln. Um den Übergang von Skype for Business zu Teams ordnungsgemäß zu lenken, implementieren Sie ein robustes Change Management-Programm, das unter anderem Schulungen, Support und Kommunikationsinitiativen enthält, die den Benutzern den Mehrwert von Teams erklären und ihnen klare Vorgaben für die ersten Schritte mit Teams bieten. Nutzen Sie Ihre Ressourcen für [Benutzerakzeptanz](http://aka.ms/UserReadiness) zur Unterstützung für den Entwurf Ihrer Sensibilisierungskampagne.


Der **vierte Schritt** der verwalteten Customer Journey beim Einsatz beider Lösungen beginnt mit der Aktivierung der Anruffunktion in Teams. Die Teams-Interoperabilitätsfunktionen nehmen in diesem Schritt eine zentrale Bedeutung ein, um eine nahtlose Erfahrung beider Lösungen nebeneinander zu erzielen. Idealerweise wird Teams als die Standardanruf-App festgelegt, um die Verwendung von Teams für private Anrufe durchzusetzen. 

Mit der Zeit kann sich die gesamte Organisation potenziell nur auf Teams verlassen, um die Anforderungen für Kommunikation und Zusammenarbeit zu erfüllen, und mit dem **fünften Schritt** beginnen. In der [Office 365-Roadmap](http://aka.ms/TeamsRoadmap) erfahren Sie, wann in Teams neue Funktionen verfügbar sind. 

<a name="managing-side-by-side-experience"></a>Verwalten der Funktionen beim Einsatz beider Lösungen
--------------------------------

Für Organisationen mit den entsprechenden Office 365-Abonnements ist Microsoft Teams standardmäßig aktiviert. Wenn Ihre Organisation dem Profil für die nicht verwaltete Customer Journey beim Einsatz beider Lösungen entspricht, wird dringend empfohlen, dieses Profil beizubehalten, um die organische Übernahme von Microsoft Teams zu unterstützen.

Der Zugriff auf Teams erfolgt über moderne Webbrowser-Desktopclients, für die keine administrativen Rechte (für die Installation, derzeit nur für PCs anwendbar) und keine mobilen Clients erforderlich sind.

Alle Funktionen in Teams – von privaten Chats und Anrufen, Ad-hoc- und geplanten Besprechungen bis zu Apps – werden standardmäßig aktiviert. Dadurch können Benutzer die Funktionen ausprobieren, die ihren Anforderungen am ehesten entsprechen. Bei der erstmaligen Ausführung von Teams werden Benutzer angeleitet, ihre bevorzugte Chat- und Anrufanwendung (Microsoft Teams oder Skype for Business) auszuwählen.

Wenn Ihre Organisation eine kontrolliertere Version der neuen Tools, wie zum Beispiel Teams, benötigt, können die folgenden Optionen für eine verwaltete Customer Journey beim Einsatz beider Lösungen in Betracht gezogen werden:

-   Einsatz und Rollout von Teams als Pilotprojekt für Zusammenarbeit. Siehe [Teams als Pilotprojekt neben Skype for Business](pilot-essentials.md).

-   Rollout von Teams für Besprechungen

-   Rollout von Teams für Anrufe

### <a name="teams-pilot-and-rollout-for-collaboration"></a>Einsatz von Teams als Pilotprojekt und Rollout für Zusammenarbeit

Durch die Optimierung von Office 365-Gruppen wurde Microsoft Teams im Kern um beständigen Chat und die Integration in Office 365 herum aufgebaut.

Da Benutzer in Ihrer Organisation mit einer Office 365-Abonnementlizenz standardmäßig für Teams aktiviert, wird in einem limitierten Teams-Pilotprojekt unter anderem die Teams-Lizenz für alle Benutzer deaktiviert, die nicht der Pilotprojektgruppe angehören.

Um den Schwerpunkt der Teams-Version auf Zusammenarbeit und privaten Chat zu legen und die Benutzerkonfusion aufgrund von sich mit Skype for Business-Funktionen überlappenden Funktionen zu verringern, können Sie die folgenden Einstellungen auf der Office 365-Mandantenebene vornehmen. Wenn diese Office 365-Einstellungen ändern möchten, finden Sie unter [Microsoft-Teams, Verwalten von Features in Office 365-Organisation](enable-features-office-365.md).

<table>
<thead>
<tr class="header">
<th align="left">Abschnittsüberschrift</th>
<th align="left">Einstellung</th>
<th align="left">Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br>Anrufe und Besprechungen</strong></td>
<td align="left"><p>Planen von privaten Besprechungen zulassen: <strong>Aus</strong></p><p>Planen von Kanalbesprechungen zulassen: <strong>Aus</strong></p><p>Private Anrufe zulassen: <strong>Aus</strong></p></td>
<td align="left"><p>Wenn diese Einstellung deaktiviert ist, können Benutzer keine privaten Besprechungen planen</p><p>Wenn diese Einstellung deaktiviert ist, können Benutzer keine Kanalbesprechungen planen</p><p>Wenn diese Einstellung deaktiviert ist, können Benutzer keine privaten Anrufe (Audio oder Video) tätigen</p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>Hinweis</p></td>
<td align="left"><br><br>Sie müssen die Option „Private Anrufe“ für Business- und Enterprise-Benutzer sowie für Gastbenutzer (falls Gastzugriff in Ihrer Organisation gewährt wird) deaktivieren.</td>
</tr>
</thead>
<tbody>
</tbody>
</table>



Mit dieser Konfiguration können Benutzer eine Einführung in die Funktionsweise von Besprechungen in Teams erhalten, indem sie die Verwendung von Ad-hoc-Kanal-MeetUps befürworten und VoIP, Video und Bildschirmfreigabe als Teil der Funktionen für moderne Zusammenarbeit verwenden. Endbenutzer können auch von den beständigen und plattformübergreifenden Funktionen für privaten Chat profitieren.

Darüber hinaus kann ein erfolgreiches Teams-Pilotprojekt für Zusammenarbeit und privaten Chat mit einem durch die Verteilung von Teams-Lizenzen für alle Benutzer großflächig angelegten Rollout in der Organisation durchgeführt werden.

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>Hinweis</p></td>
<td align="left">Während des Pilotprojekts und in Phase 2, wenn die Funktion für privaten Chat aktiviert ist, kann ein Teams-Benutzer, der mit einem Skype for Business-Benutzer chattet, folgende Aktionen nicht ausführen:<br>
- Starten eines Videoanrufs über eine Chatsitzung<br>
- Übertragen von Dateien <br>
- Initiieren eines Anrufs mit mehreren Parteien in der Chatsitzung<br>
- Benutzer können keine Desktopfreigabesitzung starten<br>

</td>
</tr>
</thead>
<tbody>
</tbody>
</table>


### <a name="rollout-of-teams-for-meetings"></a>Rollout von Teams für Besprechungen

Wenn sich Benutzer an die Zusammenarbeit unter Verwendung von Microsoft Teams gewöhnt haben, können geplante Besprechungen als nächste Funktion in der Organisation eingeführt werden.

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>Hinweis</p></td>
<td align="left"><br><br>Die Organisatoren von geplanten Besprechungen müssen über Postfächer verfügen, die sich in einer mehrinstanzfähigen Exchange Online-Version (oder in einer Exchange Online Dedicated vNext-Version) befinden.</td>
</tr>
</thead>
<tbody>
</tbody>
</table>

Die folgenden Einstellungen können auf der Mandantenebene konfiguriert werden, um geplante Besprechungen in Teams durchzuführen. Diese Einstellungen können nur von Business- und Enterprise-Benutzern verwendet werden.

<table>
<thead>
<tr class="header">
<th align="left">Abschnittsüberschrift</th>
<th align="left">Einstellung</th>
<th align="left">Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br>Anrufe und Besprechungen</strong></td>
<td align="left"><p>Planen von privaten Besprechungen zulassen: <strong>Ein</strong></p><p>Planen von Kanalbesprechungen zulassen: <strong>Ein</strong></p></td>
<td align="left"><p>Wenn diese Einstellung aktiviert ist, können Benutzer private Besprechungen planen</p><p>Wenn diese Einstellung aktiviert ist, können Benutzer Kanalbesprechungen planen</p></td>
</tr>
</tbody>
</table>


Geplante Besprechungen können über den Teams-Desktopclient, einen Browser oder über Microsoft Outlook mit dem Besprechungs-Add-In für Microsoft Teams organisiert werden. Sobald geplante Besprechungen in Teams aktiviert sind, wird eine Schulung der Benutzer zum Erstellen neuer Teams-Besprechungen oder zum Aktualisieren von vorhandenen Skype for Business-Besprechungen in Teams-Besprechungen empfohlen.

### <a name="rollout-of-teams-for-calling"></a>Rollout von Teams für Anrufe

„Private Anrufe“ ist die Funktion in Teams, die kontinuierlich entwickelt wird. Es dauert aber nicht mehr lange, bis sie sich gegenüber Skype for Business durchsetzen wird. Wenn Ihre Organisation der Ansicht ist, dass die Funktionen für private Anrufe die wichtigsten Geschäftsanforderungen erfüllt, können die folgenden Einstellungen auf der Mandantenebene konfiguriert werden, um die Funktion für private Anrufe in Teams zu aktivieren. 

<table>
<thead>
<tr class="header">
<th align="left">Abschnittsüberschrift</th>
<th align="left">Einstellung</th>
<th align="left">Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br>Anrufe und Besprechungen</strong></td>
<td align="left"><p>Private Anrufe zulassen: <strong>Ein</strong></p></td>
<td align="left"><p>Wenn diese Einstellung aktiviert ist, können Benutzer private Anrufe (Audio oder Video) tätigen</p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>Hinweis</p></td>
<td align="left"><br><br>Zulassen, dass Benutzer privat chatten: Wenn diese Einstellung aktiviert ist, können Benutzer mit anderen Benutzern privat chatten.</td>
</tr>
</thead>
<tbody>
</tbody>
</table>


In dieser Phase müssen alle Benutzer angewiesen werden, Teams als ihre bevorzugte Anruf-App auszuwählen.

Mit der Aktivierung der Funktion für private Anrufe stellt Teams alle der derzeit in Skype for Business verfügbaren Funktionen zur Verfügung, und Benutzer können mit dem Einsatz von Teams beginnen, um ihre Anforderungen an Kommunikation und Zusammenarbeit zu erfüllen.


<table>
<thead>
<tr class="header">
<td align="left"><p><img src="media/pilot_essentials_image2.png" /></p></td>
<td align="left">
<p><strong>Nächste Aktion</strong>: Sobald Teams eingerichtet und neben Skype for Business ausgeführt wird, [erzielen Sie durch die Benutzerakzeptanz von Teams einen Mehrwert](continue-journey.md), indem Sie Ihre Reise von Skype for Business nach Teams fortsetzen.</td>
</tr>
</thead>
<tbody>
</tbody>
</table>