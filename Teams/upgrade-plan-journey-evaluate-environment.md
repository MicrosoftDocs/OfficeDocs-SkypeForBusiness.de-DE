---
title: Microsoft Teams-Upgrade | Umgebungs Bewertung, Ermittlungs Fragen
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Verwenden Sie diese Anleitung, um sich über die Anforderungen für eine ordnungsgemäße Bewertung Ihrer aktuellen Umgebung für ein Upgrade auf Teams zu informieren.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d73c40ee6a2ebe906a6a3ca66dbb430b843c6eeb
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706925"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a>Auswerten Ihrer Umgebung vor dem Upgrade auf Teams

![Diagramm zum Upgrade von Fahrten mit Hervorhebung der technischen Bereitschaftsstufe](media/upgrade-banner-tech-readiness.png "Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der technischen Bereitschaftsstufe liegt")

Dieser Artikel ist Bestandteil der Phase „Technische Bereitschaft“ Ihrer Upgrade-Strategie, einer Aktivität, die Sie parallel zur Phase „Benutzerbereitschaft“ durchführen. Bevor Sie fortfahren, bestätigen Sie, dass Sie diese Aktivitäten aus vorherigen Phasen abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](https://aka.ms/SkypetoTeams-Scope)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

In diesem Artikel finden Sie eine Übersicht über die Anforderungen für die ordnungsgemäße Auswertung Ihrer aktuellen Umgebung für das Funktionieren von Teams. Durch Auswertung Ihrer Umgebung ermitteln Sie Risiken und Anforderungen, die sich auf die gesamte Bereitstellung auswirken. Wenn Sie diese Elemente vorher identifizieren, können Sie Ihre Planung anpassen, um den Erfolg zu steigern.

## <a name="introduction-to-the-discovery-questionnaire"></a>Einführung in den Such Fragebogen

Um Ihre objektiven Hauptergebnisse (OKRs) zu erreichen, haben Sie zuvor wichtige Dienst Entscheidungen getroffen. Der nächste Schritt besteht darin, eine Umgebungs Ermittlung durchzuführen, um alle Aspekte in Bezug auf Ihre IT-Infrastruktur, Netzwerke und Vorgänge zu bewerten, um zu bestätigen, dass Ihre Organisation zur Implementierung der Lösung bereit ist. Die Ermittlung ist einer der ersten wichtigen Schritte, die Sie bei der Planung Ihrer Reise zu Teams Unternehmen. Umgebungs Ermittlung muss eine Netzwerk Readiness-Bewertung umfassen, um sicherzustellen, dass Ihr Netzwerk das Upgrade auf Teams unterstützenkann. Sie führen eine detaillierte Ermittlung Ihrer Umgebung durch, um den aktuellen Zustand besser zu verstehen und etwaige Schwierigkeiten oder – noch wichtiger – mögliche Blockierungen für die Ausführung Ihres Teams-Rollouts zu erkennen.

Sie erkennen technische Risiken als Teil einer Evaluierung der Umweltverträglichkeitsprüfung und Akzeptanz Bereitschaft an und entwickeln einen Minderungsplan für jedes erkannte Risiko. Sie sollten diese Informationen in das risikoregister aufnehmen.

Alle Fragen im Zusammenhang mit Ihrer vorhandenen Infrastruktur für die Zusammenarbeit und der Office 365-Mandanten,-Netzwerke,-Endpunkte,-Vorgänge sowie-Einführung und-Bereitschaft sind Teil des Fragebogens zur Umwelt Ermittlung. Der Fragebogen ist in mehrere Abschnitte unterteilt, um die Bereitstellung Ihrer Organisation für Ihre Teams in mehreren wichtigen Bereichen zu bestätigen. Arbeiten Sie mit Ihrem Projektteam zusammen, um die gewünschten Informationen so detailliert wie möglich zur Verfügung zu stellen, um Ihre Planungsaktivitäten zu vereinfachen.

> [!TIP]
> Sie können zunächst den Fragebogen in ein Microsoft Word-Dokument kopieren. Versuchen Sie, alle Fragen zu beantworten und alle Details während des Navigierens zu erfassen.

## <a name="project-team"></a>Projektteam

Stellen Sie sicher, dass Sie die richtigen Personen für Ihr Projektteam aktiviert haben. Überprüfen Sie die Schritte, die Sie unter eintragen [ihrer Projekt stakekholders](upgrade-enlist-stakeholders.md)abgeschlossen haben.

## <a name="office-365-tenant-details"></a>Office 365-Mandanten Details

Wir empfehlen dringend, dass Sie über einen Active Office 365-Mandanten verfügen, während Sie mit diesem Fragebogen arbeiten. Wenn Sie noch keinen Office 365-Mandanten aktiviert oder konfiguriert haben, lesen Sie [Planen des Setups von Office 365 for Business](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645).

Verwenden Sie die folgende Tabelle, um Informationen zum Office 365-Mandanten zu erfassen.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Notieren Sie den Office 365-Produktions Mandanten <br>Name und ID in der Spalte "Antwort" <br/>Wenn Sie mehr als einen Mandanten haben <br>mit Ihrer Organisation verknüpft ist, <br>Beachten Sie alle IDs. | Mandanten Name: <br/>Mandanten-ID:| |
> | In welchen Regionen werden die Mandanten bereitgestellt?| | |
> | Sind diese Mandanten Office 365 Multitenant oder <br>Dedizierte? | <input type="checkbox">Multitenant<br/> <input type="checkbox">Dedizierte | |
> | Welche Microsoft Online-Produkte werden zurzeit verwendet? <br/>Notieren Sie sich die Anzahl der Benutzer, die für jeden aktiviert sind <br>Dienst in der Spalte "Kommentare". | <input type="checkbox">Microsoft Teams <br/> <input type="checkbox">Skype for Business <br>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive for Business <br/> <input type="checkbox">Jammern <br/> <input type="checkbox">Anderen| |
> | Welche Lizenzstufe ist für Skype aktiviert <br>Business Online-Benutzer? | <input type="checkbox">E1/G1 <br/> <input type="checkbox">E2/G2 <br/> <input type="checkbox">E3/G3 <br/> <input type="checkbox">E4/G4 E5 <br/> <input type="checkbox">Standalone | Die Anzahl der Benutzer <br>für jede SKU: |
> | Was ist die aktuelle Active Directory-Gesamtstruktur? <br>Funktionsebene in der Umgebung? <br/>Wenn es mehr als eine Gesamtstruktur gibt, notieren Sie sich die Details. <br>in der Spalte Kommentare. | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | Was verwenden Sie für das Verzeichnis? <br>Synchronisierung heute? |<input type="checkbox">Keine Synchronisierung (nur Cloud) <br/> <input type="checkbox">Azure Active Directory <br>&nbsp;&nbsp; &nbsp;Verbinden <br/> <input type="checkbox">Sonstiges (geben Sie im <br>&nbsp;&nbsp; Spalte "Kommentare" &nbsp;.)| |
> | Ist zurzeit eine Partneridentität bereitgestellt? <br/>(Active Directory-Verbunddienste oder <br>Drittanbieter) | <input type="checkbox">Ja <br/> <input type="checkbox">Nein | |
> | Wenn Sie die Verbundidentität verwenden, was ist die <br>Verbundinfrastruktur? | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox">Drittanbieter-Föderation <br>&nbsp;&nbsp; &nbsp;Gateway <br>&nbsp;&nbsp; (Beachten Sie die &nbsp;Details im <br>&nbsp;&nbsp; Spalte "Kommentare" &nbsp;.) | |
> | Wenn Sie derzeit ein Active Office 365 verwalten <br>Mandant ist die SMTP/SIP-Domäne Ihres <br>mit dem Mandanten verknüpfte, gezielte Benutzer? | <input type="checkbox">N/A – kein Office 365 <br>&nbsp;&nbsp; &nbsp;und Stelle <br/> <input type="checkbox">Nein, SMTP/SIP der Benutzer <br>&nbsp;&nbsp; &nbsp; <br>&nbsp;&nbsp; &nbsp; <br>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox">Ja, SMTP/SIP der Benutzer <br>&nbsp;&nbsp; &nbsp; <br>&nbsp;&nbsp; &nbsp;Mandanten <br>&nbsp;&nbsp; &nbsp; | |
> | Entsprechen Benutzer-UPNs ihrer primären SMTP-Adresse? | <input type="checkbox">Ja <br/> <input type="checkbox">Nein <br/> <input type="checkbox">Uneinheitlich | |

## <a name="existing-collaboration-platform-summary"></a>Zusammenfassung der vorhandenen Zusammenarbeitsplattform

Verwenden Sie die folgende Tabelle, um Informationen zu Ihrer vorhandenen Bereitstellungsplattform für die Zusammenarbeit zu erfassen.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Ist Microsoft Teams bereitgestellt? | <input type="checkbox">Ja <br/> <input type="checkbox">Nein | |
> | Ist Skype for Business bereitgestellt? <br/>Stellen Sie bei lokalen und hybridbereitstellungen sicher, dass <br>Notieren Sie sich die Version und das kumulative Update (Cu). <br>Details in der Spalte "Kommentare". | <input type="checkbox">Ja, Office 365 <br/> <input type="checkbox">Ja, Hybrid (mit Office 365) <br/> <input type="checkbox">Ja, lokal <br/> <input type="checkbox">Ja, Online, dediziert <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Ja, gehostet, dediziert <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Ja, gehostet, freigegeben (Drittanbieter) <br/> <input type="checkbox">Nein, andere | |
> | Ist Exchange bereitgestellt? <br/>Stellen Sie bei lokalen und hybridbereitstellungen sicher, dass <br>Notieren Sie sich die Versions-und Cu-Details in den Kommentaren. <br>Spalte. | <input type="checkbox">Ja, Office 365 <br/> <input type="checkbox">Ja, Hybrid (mit Office 365) <br/> <input type="checkbox">Ja, lokal <br/> <input type="checkbox">Ja, Online, dediziert <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Ja, gehostet, dediziert <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Ja, gehostet, freigegeben <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Nein, andere | |
> | Ist SharePoint bereitgestellt? <br/>Stellen Sie bei lokalen und hybridbereitstellungen sicher, dass <br>Notieren Sie sich die Versions-und Cu-Details in den Kommentaren. <br>Spalte. | <input type="checkbox">Ja, Office 365 <br/> <input type="checkbox">Ja, Hybrid (mit Office 365) <br/> <input type="checkbox">Ja, lokal <br/> <input type="checkbox">Ja, Online, dediziert <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Ja, gehostet, dediziert <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Ja, gehostet, freigegeben <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Nein, andere | |
> | Ist Office 365 OneDrive for Business bereitgestellt? | <input type="checkbox">Ja <br/> <input type="checkbox">Nein | |
> | Sind andere Plattformen von Drittanbietern bereitgestellt? <br>und wird heute verwendet? Wenn ja, notieren Sie sich die Anzahl der Benutzer von <br>Diese Plattformen und die Nutzungsdetails in den Kommentaren <br>Spalte. | <input type="checkbox">Cisco WebEx <br/> <input type="checkbox">Pufferzeit <br/> <input type="checkbox">Sonstiges (in den Kommentaren angeben <br>&nbsp;&nbsp; &nbsp; | Anzahl der Benutzer: <br/>Details|
> | Planen Sie das Verschieben von Benutzern von diesen Drittanbietern <br>Plattformen für Teams? | <input type="checkbox">Ja <br/> <input type="checkbox">Nein | |
> | Was ist die aktuelle Lösung für Telefonie und Konferenzen? <br>der Benutzer, die im Bereich dieser Initiative arbeiten? | | |
> | Verfügen Sie über [SBCS, die das direkt Routing](direct-routing-plan.md#supported-session-border-controllers-sbcs) für Ihre Office-Abteilungen unterstützen, die für diese Initiative in den Anwendungsbereich fallen? <br>Wenn ja, notieren Sie sich die Details in der Spalte Kommentare.| <input type="checkbox">Ja <br/> <input type="checkbox">Nein ||

## <a name="collaboration-platform-deployment-details"></a>Bereitstellungsdetails für die Zusammenarbeitsplattform

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (falls zutreffend)

Erfassen Sie die Details Ihrer Teams-Bereitstellung, falls zutreffend, mithilfe der folgenden Beispieltabelle. Wenn Sie keine Teams bereitgestellt haben, überspringen Sie diesen Abschnitt.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Welche Benutzertypen sind für Microsoft Teams aktiviert? | <input type="checkbox">Alle Benutzer in der Organisation <br/> <input type="checkbox">Bestimmte Benutzer/Benutzergruppen <br>&nbsp;&nbsp; (In der Spalte Kommentare &nbsp;angeben) ||
> | Welche Teams-Features und-Modalitäten werden verwendet? | <input type="checkbox">Kanalbasierte Unterhaltungen <br/> <input type="checkbox">Privater Chat <br/> <input type="checkbox">Gastzugriff <br/> <input type="checkbox">Kanal Besprechungen <br/> <input type="checkbox">Private Besprechungen <br/> <input type="checkbox">Private Anrufe <br/> <input type="checkbox">Meetup zum Ad-hoc-Kanal <br/> <input type="checkbox">Videos in Besprechungen <br/> <input type="checkbox">Bildschirmübertragung in Besprechungen <br/> <input type="checkbox">Audiokonferenzen <br/><input type="checkbox">Anwendungen (Apps)<br> &nbsp;&nbsp; &nbsp; Tabstopps <input type="checkbox"><br>&nbsp;&nbsp; Bots &nbsp; <input type="checkbox"> <br>&nbsp;&nbsp; Verbinder &nbsp; <input type="checkbox"><br><input type="checkbox">Benutzerdefinierte Cloud-Speicherintegration <br>&nbsp;&nbsp; (Box, Dropbox, Freigabe Datei, Google &nbsp; Drive) <br/> <input type="checkbox">Kanal-e-Mail-Integration <br/> <input type="checkbox">Sonstiges (in der Spalte Kommentare angeben.) | |
> | Welche Anwendungen haben Sie für Teams bereitgestellt? | | |
> | Haben Sie Funktionen von Microsoft Teams ausdrücklich gesperrt? <br/>Wenn ja, notieren Sie sich die Details in der Spalte Kommentare. | <input type="checkbox">Ja <br/> <input type="checkbox">Nein ||
> | Welche Microsoft Teams-Clients werden verwendet? | <input type="checkbox">Web <br/> <input type="checkbox">Windows <br/> <input type="checkbox">Mac <br/> <input type="checkbox">IOS <br/> <input type="checkbox">Android <br/> <input type="checkbox">Windows Mobile | |
> | Wer verfügt über Berechtigungen zum Erstellen von Teams? | <input type="checkbox">Jeder in der Organisation <br>&nbsp;&nbsp; (Dies ist die Standard &nbsp;Einstellung) <br/> <input type="checkbox">Bestimmte Personen <br>&nbsp;&nbsp; (Geben Sie in der Spalte Kommentare an &nbsp;.) | |
> | Verwenden Sie Sicherheits- und Compliance-Funktionen in Microsoft Teams? | <input type="checkbox">Ja <br/> <input type="checkbox">Nein | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online (falls zutreffend)

Erfassen Sie die Details Ihrer Skype for Business Online-Bereitstellung, falls zutreffend, mithilfe der folgenden Beispieltabelle. Wenn Sie die Bereitstellung von Skype for Business Online nicht bereitgestellt haben, überspringen Sie diesen Abschnitt.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Welche Arten von Benutzern sind für Skype aktiviert? <br>für Business Online? | <input type="checkbox">Alle Benutzer in der Organisation <br/> <input type="checkbox">Bestimmte Benutzer/Benutzergruppen <br>&nbsp;&nbsp; (In der Spalte Kommentare &nbsp;angeben) | |
> | Welche Modalitäten und Funktionen sind derzeit <br>in Verwendung heute? | <input type="checkbox">Sofortnachrichten und Anwesenheitsinformationen (im/P)<br/> <input type="checkbox">Sitzungen <br/> <input type="checkbox">Verbund <br/> <input type="checkbox">Besprechungsaufzeichnung <br/> <input type="checkbox">Microsoft-Audiokonferenzen <br/> <input type="checkbox">Audiokonferenzen von Drittanbietern <br>&nbsp;&nbsp; (Beachten Sie die Details in der Spalte Kommentare &nbsp;.) <br/> <input type="checkbox">Anrufpläne (ehemals PSTN-Anrufe) <br/> <input type="checkbox">Automatische Organisations Betreuer <br/> <input type="checkbox">Anrufwarteschlangen | |
> | Haben Sie Skype ausdrücklich blockiert? <br>Business Online-Funktionen? <br>Wenn ja, notieren Sie sich die Details in der Spalte Kommentare. | <input type="checkbox">Ja <br/> <input type="checkbox">Nein | |
> | Welche Methode verwenden oder planen Sie, um <br>Verbinden Sie das Telefon System (ehemals Cloud PBX) mit <br>das PSTN? <br/>Wählen Sie alle zutreffenden aus. | <input type="checkbox">Anrufpläne (ehemals PSTN-Anrufe) <br/> <input type="checkbox">Lokale PSTN-Konnektivität (nutzt vorhandene <br>&nbsp;&nbsp; Skype for Business 2015 oder lync &nbsp;Server 2013 <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Lokale PSTN-Konnektivität (mithilfe von Cloud Connector) | |
> | Haben Sie Telefonnummern zu Microsoft portiert? <br/>Dies gilt für Anrufpläne und Audio <br>Konferenzfeatures | <input type="checkbox">Ja <br/> <input type="checkbox">Nein | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype for Business lokal (falls zutreffend)

Erfassen Sie die Details Ihrer Skype for Business-Bereitstellung, falls zutreffend, mithilfe der folgenden Beispieltabelle. Wenn Sie Skype for Business nicht lokal bereitgestellt haben, überspringen Sie diesen Abschnitt.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Welche Versionen von lync oder Skype for Business derzeit <br>sind lokal bereitgestellt? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019 <br/> <input type="checkbox">Skype for Business Cloud Connector Edition | |
> | Ist eine hybride Bereitstellung mit Skype for Business Online konfiguriert? | <input type="checkbox">Ja <br/> <input type="checkbox">Nein | |
> | Wird diese Umgebung von einem Drittanbieter gehostet und verwaltet? <br/>Wenn ja, notieren Sie sich die Details in der Spalte Kommentare. | <input type="checkbox">Ja <br/> <input type="checkbox">Nein | |
> | Welche Modalitäten und Funktionen werden derzeit verwendet? <br>heute? | <input type="checkbox">Sofortnachrichten und Anwesenheitsinformationen (im/P) <br/> <input type="checkbox">Sitzungen <br/> <input type="checkbox">Verbund <br/> <input type="checkbox">Besprechungsaufzeichnung <br/> <input type="checkbox">Beständiger Chat/Gruppen-Chat <br/> <input type="checkbox">Microsoft-Audiokonferenzen <br>&nbsp;&nbsp; (vormals Dial in Conferencing) &nbsp;auf Ihrem <br>&nbsp;&nbsp; &nbsp;Server oder <br>&nbsp;&nbsp; Bereitstellung von Skype &nbsp;for Business <br/> <input type="checkbox">Audiokonferenzen von Drittanbietern <br>&nbsp;&nbsp; (Beachten Sie die Details in der Spalte Kommentare &nbsp;). <br/> <input type="checkbox">Enterprise-VoIP mit lokalem PSTN <br>&nbsp;&nbsp; &nbsp;Konnektivität <br/> <input type="checkbox">Anrufpläne (ehemals PSTN-Anrufe) über <br>&nbsp;&nbsp; Hybrid mit Skype for &nbsp;Business Online | |
> | Welche Edgeserverversionen sind bereitgestellt? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019 | |
> | Haben Sie lync oder Skype for Business Edge bereitgestellt? <br>in mehr als ein Rechenzentrum? <br/>Wenn ja, notieren Sie sich die Details in der Spalte Kommentare. | <input type="checkbox">Ja <br/> <input type="checkbox">Nein | |
> | Wählen Sie Dienste aus, die von ihrer Edge-Rolle heute bereitgestellt werden. | <input type="checkbox">Zugriff auf externe Benutzer (Unternehmensbenutzer) <br/> <input type="checkbox">Zugriff durch Remote Benutzer (anonym extern <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Verbund <br/> <input type="checkbox">Medien Relay | |
> | Welche der folgenden Sprachanruf Funktionen haben Sie <br>sind zurzeit Abhängigkeiten vorhanden? <br/>Beachten Sie alle weiteren Abhängigkeiten in den Kommentaren. <br>Spalte. | <input type="checkbox">Optionen für "beschäftigt" <br/> <input type="checkbox">Park anrufen <br/> <input type="checkbox">Anruf Abholung oder Gruppenanruf Abholung <br/> <input type="checkbox">Telefone im öffentlichen Bereich oder "Hot Desking" <br/> <input type="checkbox">Reaktionsgruppen oder Sammelanschlüsse <br/> <input type="checkbox">Darstellung der freigegebenen Zeile <br/> <input type="checkbox">Privatleitung <br/> <input type="checkbox">Voicemail <br/> <input type="checkbox">Anruf über die Arbeit <br/> <input type="checkbox">Notfall-oder Informations Nummern <br>&nbsp;&nbsp; (911, 811, &nbsp;411) <br/> <input type="checkbox">Durchwahl Wahl <br/> <input type="checkbox">Automatische Telefonzentrale <br/> <input type="checkbox">Teilnehmerzugriff <br/> <input type="checkbox">Analoge Geräte <br/> <input type="checkbox">Fax <br/> <input type="checkbox">Anrufer-ID-Maskierung oder-Änderung <br/> <input type="checkbox">Standortbasiertes Routing <br/> <input type="checkbox">Kostengünstigstes Routing <br/> <input type="checkbox">Aufzugs Telefone | |

## <a name="networking-and-access-to-office-365-services"></a>Netzwerk und Zugriff auf Office 365-Dienste

Verwenden Sie die folgende Tabelle, um die Netzwerkdetails Ihrer Organisation zu erfassen und zu erfahren, wie Ihre Benutzer mit Office 365-Diensten verbunden sind (oder werden).

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Wie (oder wie werden) die Benutzer im Bereich für die Migration <br>Access Teams, wenn Sie im Büro sind? <br/>Wählen Sie alle zutreffenden aus. | <input type="checkbox">Weitergeleitete NAT-Verbindung <br/> <input type="checkbox">Proxy Server <br/> <input type="checkbox">Öffentliches Wi-Fi <br/> <input type="checkbox">Verwaltetes (nicht öffentliches) Wi-Fi <br/> <input type="checkbox">Express Route (Microsoft Peering) ||
> | Wenn der Zugriff auf Office 365 über einen Proxy Server erfolgt, gibt es <br>gibt es eine Möglichkeit, den Proxy zu umgehen? | <input type="checkbox">Ja <br/> <input type="checkbox">Nein | |
> | Wird ExpressRoute zurzeit genutzt? | <input type="checkbox">Ja <br/> <input type="checkbox">Nein <br/> <input type="checkbox">Nein, aber es ist geplant. | |
> | Haben Sie eine Netzwerk Bereitschafts Beurteilung durchgeführt? | <input type="checkbox">Ja <br/> <input type="checkbox">Nein | |
> | Sind Benutzer für die Verwendung eines VPNs beim Herstellen einer Verbindung erforderlich <br>Unternehmensressourcen Remote? | <input type="checkbox">Ja <br/> <input type="checkbox">Nein | |
> | Wenn ein VPN verwendet wird, kann der Datenverkehr von Teams ausgeschlossen werden. <br>das VPN für den direkten Zugriff auf Office 365-Dienste? | <input type="checkbox">Ja <br/> <input type="checkbox">Nein | |
> | Unterstützt Ihr Netzwerk QoS? | <input type="checkbox">Ja <br/> <input type="checkbox">Nein | |
> | Können Sie den Team-Audio-und Videoverkehr priorisieren <br>um eine hohe Qualität zu erzielen? | <input type="checkbox">Ja <br/> <input type="checkbox">Nein | |
> | Verfügen alle Standorte innerhalb einer Region über einen Internet Ausstieg, <br>oder ist der Internet Ausstieg für die gesamte Region zentralisiert? | <input type="checkbox">Regionaler Zugriff auf das Internet <br/> <input type="checkbox">Zentralisierter Zugriff auf das Internet | |

## <a name="endpoints"></a>Endpunkte

Verwenden Sie die folgende Tabelle, um die Details der verwendeten Clients und Endpunkte zu erfassen.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Welches Desktopbetriebssystem verwenden die Benutzer? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox">Mac (geben Sie die Version in der Spalte Kommentare an.) <br/> <input type="checkbox">Linux (geben Sie die Verteilung in der Spalte Kommentare an.) <br/> <input type="checkbox">Sonstiges (Notieren Sie sich die Details in der Spalte Kommentare.) | |
> | Welche Version von Microsoft Office bereitgestellt wird <br>zu diesen Geräten? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office für Mac 2011 <br/> <input type="checkbox">Office für Mac 2016 <br/> <input type="checkbox">Sonstiges (Notieren Sie sich die Details in der Spalte Kommentare.) | |
> | Welche Office-Bereitstellungstechnologie wird verwendet <br>in Ihrer Organisation? | <input type="checkbox">MSI <br/> <input type="checkbox">Klick-und-Los | |
> | Was sind die zulässigen und unterstützten Mobiltelefone? <br>verwendete Plattformen? <br/>Wählen Sie alle zutreffenden aus. | <input type="checkbox">Windows <br/> <input type="checkbox">Mobile <br/> <input type="checkbox">IOS <br/> <input type="checkbox">Android <br/> <input type="checkbox">Sonstiges (Notieren Sie sich die Details in der Spalte Kommentare.) | |
> | Wie werden mobile Geräte bereitgestellt? <br/>Wählen Sie alle zutreffenden aus. | <input type="checkbox">Unternehmensgeräte <br/> <input type="checkbox">Bringen Sie Ihr eigenes Gerät | |
> | Welche Geräte verwenden Benutzer derzeit für den Zugriff auf <br>Sprach-und Konferenzdienste <br>(Handsets, Headsets, Telefone, Video)? | | |

## <a name="operations"></a>Vorgänge

Verwenden Sie die folgende Tabelle, um die Details der betrieblichen Aspekte Ihrer Umgebung zu erfassen.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Was ist Ihr Betriebsmodell für Ihren lync-Server? <br>Skype for Business Server-oder Office 365-Bereitstellung <br>heute? | | |
> | Können Sie die aktuelle Support-Vereinbarung für <br>Lync Server, Skype for Business Server oder Office 365? | | |
> | Wenn Sie in mehreren Ländern oder Regionen bereitstellen, <br>hat jedes Land/jede Region seine eigene IT/Telefonie <br>Mitarbeiter, mit denen Sie arbeiten können, oder wird diese zentral verwaltet? | <input type="checkbox">Regionaler Betrieb und Support <br/> <input type="checkbox">Zentralisierte Vorgänge und Support | |
> | Verfolgen Sie die [Methode zur Anrufqualität](quality-of-experience-review-guide.md)? | <input type="checkbox">Ja <br/> <input type="checkbox">Nein | |
> | Haben Sie eine Person oder ein Team dem <br>Quality Champion-Rolle für die Plattform für die Zusammenarbeit <br>in Verwendung? | <input type="checkbox">Ja <br/> <input type="checkbox">Nein ||
> | Wie können Sie Ihren lync-Server überwachen, Skype für <br>Business Server oder Office 365-Bereitstellung? | | |
> | Treten Probleme mit der Anrufqualität auf? | <input type="checkbox">Ja<br/> <input type="checkbox">Nein | |
> | Wie und wann stellen Sie Schulungen für Ihre <br>Helpdesk zu neuen Diensten und Funktionen? | | |

## <a name="adoption-and-readiness"></a>Annahme und Bereitschaft

Erfassen Sie mithilfe der folgenden Tabelle den aktuellen Status der Einführung und Bereitschaft in Ihrer Organisation.

>
> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Was ist Ihre aktuelle aktive Nutzung von <br>Skype for Business? | **__** % Gesamtanzahl der aktiven Benutzer im Vergleich zu aktivierten Benutzern | |
> | Wie verwendet Ihre Organisation <br>Skype for Business? | Einzelunterhaltungen <br>&nbsp;&nbsp; Im &nbsp; <input type="checkbox"> <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> <br>&nbsp;&nbsp; Freigabe &nbsp; <input type="checkbox"><br> Besprechungen <br>&nbsp;&nbsp; Konferenzen &nbsp; <input type="checkbox"><br>&nbsp;&nbsp; Freigabe &nbsp; <input type="checkbox"><br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> | |
> | Verfügt Ihre Organisation über eine Benutzerakzeptanz <br>und das Change Management-Team? | <input type="checkbox">Ja<br/> <input type="checkbox">Nein | |
> | Wie Messen Sie den Erfolg für Technologie aktuell? <br>Rollouts wie Skype for Business? | | |
> | Wie viel Prozent ihrer Nutzerbasis würden Sie sagen? <br>haben Sie Skype for Business angenommen? | | |
> | Wie ist die Einstellung der Benutzer zu Skype for Business? | <input type="checkbox">Gute <br/> <input type="checkbox">Neutral <br/> <input type="checkbox">Schlechte | |
> | Welche der folgenden Aussagen beschreibt am besten den Rollout <br>Strategie für Ihre Skype for Business-Anwendung <br>Bereitstellungs? | <input type="checkbox">Breite Reichweite: e-Mail-Kampagne mit <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Erweitert: breite Reichweite und eine Vielzahl <br>&nbsp;&nbsp; Sensibilisierungskampagnen (Plakate &nbsp;, <br>&nbsp;&nbsp; Events, Champions) &nbsp;und Schulung <br>&nbsp;&nbsp; (Videos, Nutzerleitfäden, in &nbsp;Person) <br/> <input type="checkbox">Zugeschnitten: erweitert, plus gezielt <br>&nbsp;&nbsp; &nbsp;nach Persona <br/> <input type="checkbox">Anderen <br>&nbsp;&nbsp; (Beachten Sie die Details in der Spalte Kommentare &nbsp;.) | |

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Entscheidungspunkt</td><td><ul><li>Wer ist für das Ausfüllen einer Umgebungs Bewertung verantwortlich?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Nächster Schritt</td><td><ul><li>Dokumentieren Sie die Ergebnisse der Umgebungs Bewertung.</li></ul></td></tr>
</table>

Nachdem Sie Ihre Umgebung ausgewertet haben, fahren Sie mit dem nächsten Schritt fort: [Vorbereiten Ihres Netzwerks](prepare-network.md).
