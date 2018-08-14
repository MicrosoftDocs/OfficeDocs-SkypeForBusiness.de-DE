---
title: Bewerten der Umgebung vor der Aktualisierung auf Teams - Microsoft-Teams
author: turgayo
ms.author: turgayo
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Verwenden Sie dieses Handbuchs, um Informationen zu den Anforderungen für ordnungsgemäß bewerten der aktuellen Umgebung für das Upgrade auf Teams.
localization_priority: Priority
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: aa717d08f951d872894474d98f5b3155614595ca
ms.sourcegitcommit: 4660539cf0a6f7fde5de0a68bc4866089962ce80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "22102061"
---
![Phasen der Upgrade Reise, mit Schwerpunkt auf die Phase technische Bereitschaft] (media/upgrade-banner-tech-readiness.png "Phasen der Upgrade Reise, mit Schwerpunkt auf die Phase technische Bereitschaft")

Dieser Artikel ist Teil technische Bereitschaft Stufe des Ihrem Upgrade Weg, eine Aktivität, die gleichzeitig mit der User Readiness Phase ausgeführt werden. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie diese Aktivitäten aus vorherigen Phasen abgeschlossen haben:

-   [Ihre Projektbeteiligten eingetragen](upgrade-enlist-stakeholders.md)
-   [Definiert die Projektumfang](https://aka.ms/SkypetoTeams-Scope)
-   [Skype-Interoperabilität und Koexistenz für Unternehmen und Teams verstanden](https://aka.ms/SkypeToTeams-Coexist)
-   [Ihre Reise Upgrade ausgewählt](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="evaluate-your-environment-before-upgrading-to-teams"></a>Bewerten der Umgebung vor der Aktualisierung auf Teams

Dieser Artikel bietet eine Übersicht über die Anforderungen für ordnungsgemäß funktionieren Teams Bewerten der aktuellen Umgebung. Bewerten der Umgebung, geben Sie an Risiken und Anforderungen, die Ihre gesamte Bereitstellung beeinflussen werden. Durch das Identifizieren von dieser Elemente im voraus, können Sie die Planung für Laufwerk Erfolg anpassen.

## <a name="introduction-to-the-discovery-questionnaire"></a>Einführung in den Fragebogen Discovery

Um Ihre objektive wichtige Ergebnisse (OKRs) zu erzielen, haben Sie zuvor wichtige Service Entscheidungen. Im nächste Schritt wird zum Ausführen der Umwelt Discovery zum Auswerten alle Aspekte, die für Ihre IT-Infrastruktur, Netzwerk und Vorgänge zu bestätigen, dass Ihre Organisation bereit, um die Lösung zu implementieren ist. Ermittlung ist einer der ersten, wichtige Schritte, die Sie ergreifen bei der Planung für Ihre Reise Teams. Umwelt Discovery muss ein Netzwerk Bereitschaft, um sicherzustellen, dass Ihr Netzwerk Unternehmensebene Durchführen eines Upgrades auf Teams enthalten. Führen Sie eine detaillierte Suche von Ihrer Umgebung, um den aktuellen Zustand besser zu verstehen und um Probleme anzuzeigen oder – noch wichtiger – mögliche Popupblockern zur Ausführung der nahezubringen Teams.

Sie identifizieren Risiken technische als Teil einer Umgebung zur Bewertung und Annahme Bereitschaft Bewertung und entwickeln Sie einen Plan zur Risikominderung für jedes identifizierte Risiko. Sie sollten diese Informationen in das Risiko Register integrieren.

Alle Fragen im Zusammenhang mit Ihrer vorhandenen Infrastruktur für die Zusammenarbeit und Office 365-Mandanten, Netzwerke, Endpunkte, Vorgänge, und Annahme und Bereitschaft sind Bestandteil der Umwelt Discovery Fragebogen. Der Fragebogen ist in mehreren Abschnitten zur Bestätigung der Bereitschaft Ihrer Organisation für Ihre Bereitstellung Teams in mehrere Bereiche unterteilt. Arbeiten Sie mit Ihrem Projektteam Geben Sie die angeforderte Informationen so genau wie möglich, um Ihre Planungsaktivitäten zu vereinfachen.

> [!TIP]
> Sie können durch Kopieren den Fragebogen in Microsoft Word-Dokument starten. Versuchen Sie alle Fragen beantworten und erfassen alle Details beim Navigieren durch.

## <a name="project-team"></a>Das Projektteam

Stellen Sie sicher, dass Sie die richtigen Personen für Ihr Projektteam anderweitig haben. Überprüfen Sie die Schritte, die Sie in [Ihrem Projekt Stakekholders eintragen](upgrade-enlist-stakeholders.md)abgeschlossen.

## <a name="office-365-tenant-details"></a>Office 365-Mandanten details

Es wird dringend empfohlen, dass Sie beim Arbeiten mit diesen Fragebogen einer aktiven Office 365-Mandanten verfügen. Wenn Sie noch nicht aktiviert oder ein Office 365-Mandanten noch nicht konfiguriert wurde, finden Sie unter [planen die Installation von Office 365 für Unternehmen](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645).

Verwenden Sie in der folgenden Tabelle, um Informationen über die Office 365-Mandanten zu erfassen.

> | Frage | Antwort | Kommentare |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Beachten Sie die Office 365-produktionsmandanten <br>Namen und die ID in der Spalte Antwort <br/>Wenn Sie mehrere Mandanten haben <br>mit Ihrer Organisation verknüpft ist, <br>Beachten Sie alle IDs.  | Name des Mandanten: <br/>Mandanten-ID:| |
> | In welchen Bereichen sind die Mandanten bereitgestellt?| | |
> | Diese Mandanten Office 365 Multitenant sind oder <br>Dedizierte werden verwendet? | <input type="checkbox">Multitenant<br/> <input type="checkbox">Dedizierte | |
> | Welche Microsoft Online-Produkte werden zurzeit verwendet? <br/>Beachten Sie die Anzahl der Benutzer für jede aktiviert <br>Dienst in der Spalte Kommentare. | <input type="checkbox">Microsoft-Teams <br/> <input type="checkbox">Skype für Unternehmen <br>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive für Unternehmen <br/> <input type="checkbox">Yammer <br/> <input type="checkbox">Andere|                                   |
> | Welche Lizenz-Ebene für Skype für aktiviert ist <br>Geschäftsbenutzer Online? | <input type="checkbox">E1/G1 <br/> <input type="checkbox">E2/S2 <br/> <input type="checkbox">E3/G3 <br/> <input type="checkbox">E4/G4 E5 <br/> <input type="checkbox">Eigenständige | Die Anzahl der Benutzer <br>für jede SKU: |
> | Was ist die aktuelle Active Directory-Gesamtstruktur <br>Funktionsebene in der Umgebung? <br/>Wenn mehrere Gesamtstrukturen vorhanden ist, beachten Sie die details <br>in der Spalte Kommentare. | <input type="checkbox">WindowsServer 2000 <br/> <input type="checkbox">WindowsServer 2003 <br/> <input type="checkbox">WindowsServer 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">WindowsServer 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">WindowsServer 2016| |
> | Was sind Sie für Verzeichnis verwenden <br>Synchronisierung heute? |<input type="checkbox">Keine Synchronisierung (reine Cloud-) <br/> <input type="checkbox">Azure Active Directory <br>&nbsp;&nbsp; &nbsp;Verbinden <br/> <input type="checkbox">Andere (Geben Sie in der <br>&nbsp;&nbsp; &nbsp;Spalte Kommentare.)| |
> | Ist zurzeit eine Partneridentität bereitgestellt? <br/>(Active Directory-Verbunddienste oder <br>Drittanbieter-) | <input type="checkbox">"Ja" <br/> <input type="checkbox">Nein | |
> | Wenn Sie Identitätsverbund verwenden, was ist die <br>verbundinfrastruktur? | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox">Drittanbieter-Verbund <br>&nbsp;&nbsp; &nbsp;Gateway <br>&nbsp;&nbsp; &nbsp;(Beachten Sie die Details in der <br>&nbsp;&nbsp; &nbsp;Spalte Kommentare.) | |
> | Wenn Sie derzeit aktiven Office 365 verwalten <br>Mandanten, wird die SMTP-/ SIP-Domäne Ihrer <br>die Endbenutzer zur Verfügung, die den Mandanten zugeordnet? | <input type="checkbox">Nicht zutreffend – keine Office 365 <br>&nbsp;&nbsp; &nbsp;Mandanten direkten <br/> <input type="checkbox">Nein, Benutzer SMTP/SIP <br>&nbsp;&nbsp; &nbsp;Domäne nicht zugeordnet ist. <br>&nbsp;&nbsp; &nbsp;mit alle Mandanten in <br>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox">Ja, Benutzer SMTP/SIP <br>&nbsp;&nbsp; &nbsp;Domäne zugeordnet ist. <br>&nbsp;&nbsp; &nbsp;mit einem vorhandenen Mandanten <br>&nbsp;&nbsp; &nbsp;in Office 365 | |
> | Entsprechen UPNs Benutzer ihre primäre SMTP-Adresse? | <input type="checkbox">"Ja" <br/> <input type="checkbox">Nein <br/> <input type="checkbox">Inkonsistent | |

## <a name="existing-collaboration-platform-summary"></a>Vorhandene Zusammenarbeitsplattform Zusammenfassung

Anhand der folgenden Tabelle zum Erfassen von Informationen über Ihre vorhandenen Zusammenarbeit Plattform-Bereitstellung.

> | Frage | Antwort | Kommentare |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Ist Microsoft Teams bereitgestellt? | <input type="checkbox">"Ja" <br/> <input type="checkbox">Nein | |
> | Ist Skype for Business bereitgestellt? <br/>Für lokale und hybride Bereitstellungen, stellen Sie sicher, dass <br>Beachten Sie die Version und das kumulative Update (CU) <br>Details in der Spalte Kommentare. | <input type="checkbox">Ja, Office 365 <br/> <input type="checkbox">Ja, Hybrid (mit Office 365) <br/> <input type="checkbox">Ja, lokalen <br/> <input type="checkbox">Ja, online, fest zugeordneten <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">Ja, gehosteten, dedizierte <br>&nbsp;&nbsp; &nbsp;(Drittanbieter) <br/> <input type="checkbox">Ja, gehostet, freigegebenen (Drittanbieter) <br/> <input type="checkbox">Nein, andere | |
> | Ist Exchange bereitgestellt? <br/>Für lokale und hybride Bereitstellungen, stellen Sie sicher, dass <br>Beachten Sie die Version und den CU Details in den Kommentaren <br>Spalte. | <input type="checkbox">Ja, Office 365 <br/> <input type="checkbox">Ja, Hybrid (mit Office 365) <br/> <input type="checkbox">Ja, lokalen <br/> <input type="checkbox">Ja, online, fest zugeordneten <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">Ja, gehosteten, dedizierte <br>&nbsp;&nbsp; &nbsp;(Drittanbieter) <br/> <input type="checkbox">Ja, gehosteten, gemeinsam genutzt <br>&nbsp;&nbsp; &nbsp;(Drittanbieter) <br/> <input type="checkbox">Nein, andere | |
> | Ist SharePoint bereitgestellt? <br/>Für lokale und hybride Bereitstellungen, stellen Sie sicher, dass <br>Beachten Sie die Version und den CU Details in den Kommentaren <br>Spalte. | <input type="checkbox">Ja, Office 365 <br/> <input type="checkbox">Ja, Hybrid (mit Office 365) <br/> <input type="checkbox">Ja, lokalen <br/> <input type="checkbox">Ja, online, fest zugeordneten <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">Ja, gehosteten, dedizierte <br>&nbsp;&nbsp; &nbsp;(Drittanbieter) <br/> <input type="checkbox">Ja, gehosteten, gemeinsam genutzt <br>&nbsp;&nbsp; &nbsp;(Drittanbieter) <br/> <input type="checkbox">Nein, andere | |
> | Ist Office 365 OneDrive für Unternehmen bereitgestellt? | <input type="checkbox">"Ja" <br/> <input type="checkbox">Nein | |
> | Haben Sie auch für andere Drittanbieter-Plattformen bereitgestellt <br>und heute verwendet? Wenn dies der Fall ist, beachten Sie die Anzahl der Benutzer <br>Diese Plattformen und die Verwendungsdetails in den Kommentaren <br>Spalte. | <input type="checkbox">Cisco WebEx <br/> <input type="checkbox">Pufferzeit <br/> <input type="checkbox">Andere (Geben Sie in den Kommentaren <br>&nbsp;&nbsp; &nbsp;Spalte.) | Anzahl der Benutzer: <br/>Details:|
> | Planen Sie die Benutzer aus dieser von Drittanbietern zu verschieben <br>Plattformen Teams? | <input type="checkbox">"Ja" <br/> <input type="checkbox">Nein | |
> | Was ist die aktuelle Telefonie- und Konferenzfeatures Lösung <br>der Benutzer, die im Gültigkeitsbereich für diese Initiative sind? | | |
> | Haben Sie [SBCs direkten Routing, die Unterstützung](direct-routing-plan.md#supported-session-border-controllers-sbcs) für Ihre Büros, die im Gültigkeitsbereich für diese Initiative sind bereitgestellt? <br>Wenn Ja, beachten Sie die Details in der Spalte Kommentare.| <input type="checkbox">"Ja" <br/> <input type="checkbox">Nein ||

## <a name="collaboration-platform-deployment-details"></a>Plattform-Deployment-Details für die Zusammenarbeit

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (falls zutreffend)

Falls zutreffend, erfassen Sie die Details der Teams Bereitstellung mithilfe der folgenden Beispieltabelle. Wenn Sie Teams bereitgestellt haben, überspringen Sie diesen Abschnitt.

> | Frage | Antwort | Kommentare |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Welche Benutzertypen sind für Microsoft Teams aktiviert? | <input type="checkbox">Alle Benutzer in der Organisation <br/> <input type="checkbox">Bestimmte Benutzer/Benutzergruppen <br>&nbsp;&nbsp; &nbsp;(Geben Sie in der Spalte Kommentare) ||
> | Welche Features von Teams und Modalitäten verwendet werden? | <input type="checkbox">Channel-basierter Unterhaltungen <br/> <input type="checkbox">Private chat <br/> <input type="checkbox">Gastzugriff <br/> <input type="checkbox">Kanal-Besprechungen <br/> <input type="checkbox">Private Konferenzen <br/> <input type="checkbox">Private aufrufen <br/> <input type="checkbox">Ad-hoc-Kanal meetup <br/> <input type="checkbox">Videos in Besprechungen <br/> <input type="checkbox">Bildschirmfreigabe an Besprechungen <br/> <input type="checkbox">Audiokonferenzen <br/><input type="checkbox">Applications (apps)<br> &nbsp;&nbsp; &nbsp; <input type="checkbox"> Registerkarten<br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Bots <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Connectors<br><input type="checkbox">Benutzerdefinierte Cloud-Speicher-integration <br>&nbsp;&nbsp; &nbsp; (Feld, Ablage, ShareFile, Google Laufwerk) <br/> <input type="checkbox">DDE-Kanal e-Mail-integration <br/> <input type="checkbox">Andere (Geben Sie in der Spalte Kommentare). | |
> | Welche Anwendungen haben Sie Teams bereitgestellt? | | |
> | Haben Sie Funktionen von Microsoft Teams ausdrücklich gesperrt? <br/>Wenn Ja, beachten Sie die Details in der Spalte Kommentare. | <input type="checkbox">"Ja" <br/> <input type="checkbox">Nein ||
> | Welche Microsoft Teams-Clients werden verwendet? | <input type="checkbox">Web <br/> <input type="checkbox">Windows <br/> <input type="checkbox">Mac <br/> <input type="checkbox">iOS <br/> <input type="checkbox">Android (engl.) <br/> <input type="checkbox">Windows Mobile | |
> | Wer verfügt über Berechtigungen zum Erstellen von Teams? | <input type="checkbox">Jede Person in der Organisation <br>&nbsp;&nbsp; &nbsp;(Dies ist die Standardeinstellung) <br/> <input type="checkbox">Bestimmte Personen <br>&nbsp;&nbsp; &nbsp;(Geben Sie in der Spalte Kommentare). | |
> | Verwenden Sie Sicherheits- und Compliance-Funktionen in Microsoft Teams? | <input type="checkbox">"Ja" <br/> <input type="checkbox">Nein | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online (falls zutreffend)

Falls zutreffend, erfassen Sie die Details zu Ihrer Skype für Business Online-Bereitstellung mithilfe der folgenden Beispieltabelle. Wenn Sie für die Bereitstellung von Business Online Skype bereitgestellt haben, überspringen Sie diesen Abschnitt.

> | Frage | Antwort | Kommentare |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Welche Arten von Benutzern für Skype aktiviert sind <br>für Unternehmen Online? | <input type="checkbox">Alle Benutzer in der Organisation <br/> <input type="checkbox">Bestimmte Benutzer/Benutzergruppen <br>&nbsp;&nbsp; &nbsp;(Geben Sie in der Spalte Kommentare) | |
> | Welche Modalitäten und Funktionen sind derzeit <br>in heute verwenden? | <input type="checkbox">Sofortnachrichten und Anwesenheit (Instant Messaging/P)<br/> <input type="checkbox">Besprechungen <br/> <input type="checkbox">Verbund <br/> <input type="checkbox">Meeting-Aufzeichnung <br/> <input type="checkbox">Microsoft-Audiokonferenzen <br/> <input type="checkbox">Drittanbieter-Audiokonferenzen <br>&nbsp;&nbsp; &nbsp;(Beachten Sie die Details in der Spalte Kommentare). <br/> <input type="checkbox">Aufrufen von Pläne (früher PSTN aufrufen) <br/> <input type="checkbox">Organisatorische automatische Telefonzentralen <br/> <input type="checkbox">Aufrufen von Warteschlangen | |
> | Sie haben Skype für ausdrücklich blockiert <br>Business-Online-Funktionen? <br>Wenn Ja, beachten Sie die Details in der Spalte Kommentare. | <input type="checkbox">"Ja" <br/> <input type="checkbox">Nein | |
> | Welche Methode Sie verwenden oder planen, mit dem sind <br>Herstellen einer Verbindung mit Telefonsystem (früher Cloud, PBX) <br>Das Telefonfestnetz? <br/>Wählen Sie alle zutreffenden an. | <input type="checkbox">Aufrufen von Pläne (früher PSTN aufrufen) <br/> <input type="checkbox">Lokale (nutzen vorhandene PSTN-Anbindung <br>&nbsp;&nbsp; &nbsp;Skype für Business 2015 oder Lync Server 2013 <br>&nbsp;&nbsp; &nbsp;Bereitstellung) <br/> <input type="checkbox">PSTN-Anbindung: lokal (über Cloud-Connector) | |
> | Haben Sie Telefonnummern zu Microsoft portiert? <br/>Dies gilt für die Pläne aufrufen und Audio <br>Konferenzfunktionen. | <input type="checkbox">"Ja" <br/> <input type="checkbox">Nein | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype für Business lokal (falls zutreffend)

Falls zutreffend, erfassen Sie die Details zu Ihrer Skype für die Bereitstellung von Business mithilfe der folgenden Beispieltabelle. Wenn Sie Skype für Business lokal bereitgestellt haben, überspringen Sie diesen Abschnitt.

> | Frage | Antwort | Kommentare |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Welche Versionen von Lync oder Skype für Unternehmen derzeit <br>werden lokal bereitgestellt? | <input type="checkbox">Office communicationsserver 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype für Business Server 2015 <br/> <input type="checkbox">Skype für Business Cloud Connector Edition | |
> | Ist eine hybride Bereitstellung mit Skype for Business Online konfiguriert? | <input type="checkbox">"Ja" <br/> <input type="checkbox">Nein | |
> | Diese Umgebung gehostet und wird von einem Drittanbieter verwaltet? <br/>Wenn Ja, beachten Sie die Details in der Spalte Kommentare. | <input type="checkbox">"Ja" <br/> <input type="checkbox">Nein | |
> | Welche Modalitäten und Funktionen sind derzeit in Gebrauch <br>heute? | <input type="checkbox">Sofortnachrichten und Anwesenheit (Instant Messaging/P) <br/> <input type="checkbox">Besprechungen <br/> <input type="checkbox">Verbund <br/> <input type="checkbox">Meeting-Aufzeichnung <br/> <input type="checkbox">Beständiger Chat / Group Chat <br/> <input type="checkbox">Microsoft-Audiokonferenzen <br>&nbsp;&nbsp; &nbsp;(früher in Konferenzen einwählen) auf Ihrem <br>&nbsp;&nbsp; &nbsp;lokale Lync Server oder <br>&nbsp;&nbsp; &nbsp;Skype für die Business-Bereitstellung <br/> <input type="checkbox">Drittanbieter-Audiokonferenzen <br>&nbsp;&nbsp; &nbsp;(Beachten Sie die Details in der Spalte Kommentare) <br/> <input type="checkbox">Verwenden von Enterprise-VoIP: lokal PSTN <br>&nbsp;&nbsp; &nbsp;Konnektivität <br/> <input type="checkbox">Aufrufen von Pläne (früher PSTN aufrufen) über <br>&nbsp;&nbsp; &nbsp;Hybrid mit Skype für Unternehmen Online | |
> | Welche Edgeserverversionen sind bereitgestellt? | <input type="checkbox">Office communicationsserver 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype für Business Server 2015 | |
> | Lync oder Skype haben für Business Edgeserver bereitgestellt Sie <br>in mehr als einem Rechenzentrum? <br/>Wenn Ja, beachten Sie die Details in der Spalte Kommentare. | <input type="checkbox">"Ja" <br/> <input type="checkbox">Nein | |
> | Wählen Sie Dienste, die Ihre Rolle Edge heute bereitstellt. | <input type="checkbox">Zugriff durch externe Benutzer (Benutzer) <br/> <input type="checkbox">Zugriff durch Remotebenutzer (anonyme extern <br>&nbsp;&nbsp; &nbsp;Besprechungsteilnehmern) <br/> <input type="checkbox">Verbund <br/> <input type="checkbox">Mediarelay | |
> | Welche der folgenden Stimme Anruffunktionen führen Sie aus <br>Derzeit sind abhängig? <br/>Beachten Sie zusätzlichen Abhängigkeiten in den Kommentaren <br>Spalte. | <input type="checkbox">Ausgelastet Optionen <br/> <input type="checkbox">Parken von Anrufen <br/> <input type="checkbox">Rufen Sie Pickup- oder Gruppe Anruf Pickup- <br/> <input type="checkbox">Telefone in öffentlichen Bereichen oder "hot Desking" <br/> <input type="checkbox">Reaktionsgruppen oder Sammelanschlüsse <br/> <input type="checkbox">Darstellung einer freigegebenen Linie <br/> <input type="checkbox">Private Leitung <br/> <input type="checkbox">Voicemail <br/> <input type="checkbox">Anruf über den Arbeitsplatz <br/> <input type="checkbox">Emergency oder Informationen Zahlen <br>&nbsp;&nbsp; &nbsp;(911, 811, 411) <br/> <input type="checkbox">Erweiterung Wählvorgang <br/> <input type="checkbox">Automatische Telefonzentrale <br/> <input type="checkbox">Teilnehmerzugriff <br/> <input type="checkbox">Analoge Geräte <br/> <input type="checkbox">Fax <br/> <input type="checkbox">Anrufer-ID-Maskierung oder ändern <br/> <input type="checkbox">Standortbasierte Weiterleitung <br/> <input type="checkbox">Routing zu minimalen Kosten <br/> <input type="checkbox">Vorteile Telefone | |

## <a name="networking-and-access-to-office-365-services"></a>Netzwerk- und Zugriff auf Office 365-Dienste

Anhand der folgenden Tabelle zum Erfassen von Ihrer Organisation Netzwerkdetails und wie die Benutzer sind (oder werden) mit Office 365-Diensten verbunden ist.

> | Frage | Antwort | Kommentare |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Gewusst wie (oder wie) Benutzer im Bereich für die migration <br>zugreifen Teams, wenn sie im Büro sind? <br/>Wählen Sie alle zutreffenden an. | <input type="checkbox">Weitergeleitete NAT-Verbindung <br/> <input type="checkbox">Proxy-server <br/> <input type="checkbox">Öffentliche Wi-Fi <br/> <input type="checkbox">Verwaltete (nicht öffentliche) Wi-Fi <br/> <input type="checkbox">ExpressRoute (Microsoft peering) ||
> | Wenn der Zugriff auf Office 365 über einen Proxyserver ist, gibt es <br>eine Möglichkeit, den Proxy zu umgehen? | <input type="checkbox">"Ja" <br/> <input type="checkbox">Nein | |
> | Wird ExpressRoute zurzeit genutzt? | <input type="checkbox">"Ja" <br/> <input type="checkbox">Nein <br/> <input type="checkbox">Nein, aber es ist geplant werden | |
> | Haben Sie eine Netzwerk-Bereitschaft durchgeführt? <br/>Weitere Informationen finden Sie unter [Bereitschaft des Netzwerks](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness). | <input type="checkbox">"Ja" <br/> <input type="checkbox">Nein | |
> | Sind erforderliche, um ein VPN verwenden Sie beim Herstellen einer Verbindung mit Benutzern <br>Unternehmensressourcen Remote? | <input type="checkbox">"Ja" <br/> <input type="checkbox">Nein | |
> | Wenn ein VPN verwendet wird, kann Teams Datenverkehr von ausgeschlossen werden <br>das VPN zum direkt auf die Office 365-Dienste zugreifen? | <input type="checkbox">"Ja" <br/> <input type="checkbox">Nein | |
> | Unterstützt Ihr Netzwerk QoS? | <input type="checkbox">"Ja" <br/> <input type="checkbox">Nein | |
> | Sie können Audio- und videodatenverkehr Teams priorisieren <br>Um eine hohe Qualität wünschen zu steuern? | <input type="checkbox">"Ja" <br/> <input type="checkbox">Nein | |
> | Alle Speicherorte innerhalb einer Region verfügen Internet Ausgang, <br>oder für den gesamten Bereich zentrale Internet Ausgang? | <input type="checkbox">Regionale Zugriff auf das internet <br/> <input type="checkbox">Zentralisierten Zugriff auf das internet | |

> [!TIP]
> Um die Bandbreite und anderen netzwerkanforderungen für Ihre Cloud-VoIP zu berechnen Bereitstellung, je nach Details und geschätzte Nutzung Ihrer Organisation finden Sie auf [Netzwerk Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) in [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/).

## <a name="endpoints"></a>Endpunkte

Anhand der folgenden Tabelle die Details der Clients und Endpunkte in Verwendung erfasst.

> | Frage | Antwort | Kommentare |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Welches Desktopbetriebssystem verwenden die Benutzer? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows-10 <br/> <input type="checkbox">Mac (Geben Sie die Version in der Spalte Kommentare.) <br/> <input type="checkbox">Andere (Beachten Sie die Details in der Spalte Kommentare). | |
> | Welche Version von Microsoft Office bereitgestellt wird <br>mit diesen Geräten? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office für Mac 2011 <br/> <input type="checkbox">Office für Mac 2016 <br/> <input type="checkbox">Andere (Beachten Sie die Details in der Spalte Kommentare). | |
> | Welche Office-Bereitstellung-Technologie wird verwendet <br>in Ihrer Organisation? | <input type="checkbox">MSI-DATEI <br/> <input type="checkbox">Klick-und-los | |
> | Was sind die zulässigen und mobile unterstützt <br>Plattformen verwendet? <br/>Wählen Sie alle zutreffenden an. | <input type="checkbox">Windows <br/> <input type="checkbox"> Mobil <br/> <input type="checkbox">iOS <br/> <input type="checkbox">Android (engl.) <br/> <input type="checkbox">Andere (Beachten Sie die Details in der Spalte Kommentare). | |
> | Wie werden mobile Geräte bereitgestellt? <br/>Wählen Sie alle zutreffenden an. | <input type="checkbox">Unternehmens-Geräte <br/> <input type="checkbox">Schalten Sie Ihr eigenes Gerät | |
> | Welche Geräte Benutzer führen Sie derzeit verwenden für den Zugriff auf <br>Sprach- und Dienste <br>(Telefone, Headsets, Telefone, Video)? | | |

## <a name="operations"></a>Betrieb

Verwenden Sie in der folgenden Tabelle, um die Details der betriebliche Aspekte der Umgebung zu erfassen.

> | Frage | Antwort | Kommentare |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Was ist das Modell Ihres Vorgänge für den Lync Server, <br>Skype für Business Server oder Office 365-Bereitstellung <br>heute? | | |
> | Sie können die aktuelle Anordnung von Unterstützung für beschreiben <br>Lync Server, Skype für Business Server oder Office 365? | | |
> | Wenn Sie für mehrere Länder oder Regionen bereitstellen, <br>jedes Land/Region verfügt über einen eigenen IT / Telefonie <br>die Verwendung mit Mitarbeitern oder wird dies zentral werden verwaltet? | <input type="checkbox">Regionale Betrieb und support <br/> <input type="checkbox">Zentralisierte Betrieb und support | |
> | Befolgen Sie die [Qualität Methodik aufrufen](quality-of-experience-review-guide.md)? | <input type="checkbox">"Ja" <br/> <input type="checkbox">Nein | |
> | Haben Sie eine einzelne Person zugewiesen oder Teams die <br>Belohnungen Qualität-Rolle für die Plattform für die Zusammenarbeit <br>verwendet? | <input type="checkbox">"Ja" <br/> <input type="checkbox">Nein ||
> | Wie überwachen Sie die Lync Server, Skype für <br>Business Server oder Office 365 Bereitstellung? | | |
> | Treten Probleme mit der Anrufqualität auf? | <input type="checkbox">"Ja"<br/> <input type="checkbox">Nein | |
> | Wie und wann Sie bieten Schulungen für Ihre <br>Helpdesk auf neue Dienste und Funktionen? | | |

## <a name="adoption-and-readiness"></a>Übernahme- und Bereitschaft

Erfassen Sie mithilfe der folgenden Tabelle den aktuellen Status der Einführung und Bereitschaft in Ihrer Organisation.

> | Frage | Antwort | Kommentare |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Was ist Ihre aktuelle aktiven Nutzung des <br>Skype für Unternehmen? | ___ % aktive Benutzer insgesamt im Vergleich zu aktivierte Benutzer | |
> | Wie ist Ihre Organisation geeignet <br>Skype für Unternehmen? | Einzelunterhaltungen <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Instant Messaging <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Aufrufen <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Freigabe<br> Besprechungen <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Konferenzen<br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Freigabe<br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Aufrufen| |
> | Verfügt Ihre Organisation eine Benutzerakzeptanz <br>und Änderungsmanagement Team? | <input type="checkbox">"Ja"<br/> <input type="checkbox">Nein | |
> | Wie messen Sie derzeit für die Technologie Erfolg <br>Einführungen gern Skype für Unternehmen? | | |
> | Wie viel Prozent der Ihre Benutzerbasis würden Sie sagen hat <br>eingeführt Skype für Unternehmen? | | |
> | Wie ist die Einstellung der Benutzer zu Skype for Business? | <input type="checkbox">Eine gute <br/> <input type="checkbox">Neutral <br/> <input type="checkbox">Ungültige | |
> | Die am besten beschreibt der Einführung <br>Strategie für Ihre Skype für Unternehmen verwendet <br>Bereitstellung? | <input type="checkbox">Eine große: e-Mail-Kampagne mit <br>&nbsp;&nbsp; &nbsp;Links zu Schulungen <br/> <input type="checkbox">Erweitert: Eine große sowie eine Vielzahl <br>&nbsp;&nbsp; &nbsp;zur Förderung des Bekanntheitsgrads Kampagnen (Poster, <br>&nbsp;&nbsp; &nbsp;Ereignisse, Champions) und Schulung <br>&nbsp;&nbsp; &nbsp;(Videos, Benutzerhandbücher, persönlicher) <br/> <input type="checkbox">Zugeschnitten: Erweitert, plus die zielorientierten <br>&nbsp;&nbsp; &nbsp;messaging und Schulung nach Rolle <br/> <input type="checkbox">Andere <br>&nbsp;&nbsp; &nbsp;(Beachten Sie die Details in der Spalte Kommentare). | |

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt</td><td><ul><li>Wer wird für die Durchführung einer Analyse der Umgebung zuständig sein?</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Als Nächstes</td><td><ul><li>Dokumentieren Sie die Ergebnisse der Bewertung Umgebung.</li></ul></td></tr>
</table>

Nachdem Sie Ihre Umgebung bewerten, mit dem nächsten Schritt fortfahren: [Prepare Ihr Netzwerk](upgrade-prepare-environment-prepare-network.md).