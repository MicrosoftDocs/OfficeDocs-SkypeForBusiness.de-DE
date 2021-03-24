---
title: Umweltkompatibilität – Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: So führen Sie eine detaillierte Umgebungserkennung durch, während Sie Ihre Reise von Skype for Business zu Microsoft Teams planen.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 50c6845eabb56ea270e6eafa699fbba57d0639e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105251"
---
<a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Umgebungserkennung für ein Microsoft Teams-Rollout
===================================================

Discovery ist einer der ersten, wichtigsten Schritte, die Sie bei der Planung Ihrer Reise zu Microsoft Teams ausführen.

Sie führen eine detaillierte Erkennung Ihrer Umgebung durch, um den aktuellen Zustand besser zu verstehen und mögliche Schwierigkeiten oder – noch weiter – mögliche Blocker für die Ausführung Ihres Teams-Rollouts zu entdecken.

## <a name="discovery-questionnaire"></a>Ermittlungsfragebogen

Der nachstehende Beispielfragebogen führt Sie durch eine Reihe von Fragen, um zu bestätigen, dass Ihre Organisation bereit für den erfolgreichen Rollout von Audiokonferenzen und Telefonsystem mit Anrufplänen in Teams ist.

Alle Fragen im Zusammenhang mit Ihrer vorhandenen Zusammenarbeitsinfrastruktur und Microsoft 365- oder Office 365-Organisation, Netzwerken, Endpunkten, Vorgängen sowie der Einführung und Bereitschaft sind Teil des Fragebogens zur Umweltermittlung.

Der Fragebogen ist in mehrere Abschnitte unterteilt, um die Bereitschaft Ihrer Organisation für Ihre Teams-Bereitstellung in mehreren wichtigen Bereichen zu bestätigen. Arbeiten Sie mit Ihrem Projektteam zusammen, um die angeforderten Informationen so detailliert wie möglich zur Verfügung zu stellen, um Ihre Planungsaktivitäten zu erleichtern.

> [!TIP]
> Sie können den Fragebogen zunächst in ein Microsoft Word-Dokument kopieren. Versuchen Sie, alle Fragen zu beantworten und alle Details zu erfassen, während Sie sich bewegen.

<a name="project-team"></a>Projektteam
---

Erfassen Sie detaillierte Informationen zu den wichtigsten Projektbeteiligten Ihres Teams-Rolloutprojekts. Beachten Sie, dass eine Person im gesamten Projekt mehrere Rollen spielen kann.

> | Rolle | Name, E-Mail-Adresse, Telefonnummer | Ort, Zeitzone | Kommentare |
> |---|---|---|---|
> | Befürworter aus der Führungsebene | | | |
> | Projektleiter | | | |
> | Leiter/Architekt für Zusammenarbeit | | | |
> | Berater | | | |
> | Projektmanager | | | |
> | Spezialist für Change Management/Einführung | | | |
> | Netzwerkleiter | | | |
> | Leiter der Sicherheit | | | |
> | Telefonieleiter | | | |
> | Desktopleiter | | | |
> | Support-/Helpdeskleiter | | | |
> | Bereitstellungsleiter | | | |
> | Leiter des Kundendiensts | | | |
> | Einrichtungsleiter | | | |
> | Leiter des Videoteams | | | |
> | Leads für Geschäftseinheiten | | | |

<a name="microsoft-365-or-office-365-organization-details"></a>Microsoft 365- oder Office 365-Organisationsdetails
---

Wir empfehlen dringend, dass Sie während der Arbeit mit diesem Fragebogen über eine aktive Microsoft 365- oder Office 365-Organisation verfügen. Wenn Sie eine Microsoft 365- oder Office 365-Organisation noch nicht aktiviert oder konfiguriert haben, lesen Sie Planen Ihrer Einrichtung [von Microsoft 365 Business.](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)

Verwenden Sie die folgende Tabelle, um Informationen zur Microsoft 365- oder Office 365-Organisation zu erfassen.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Beachten Sie die Produktion von Microsoft 365<br/>oder Office 365-Organisationsname und -ID<br/>in der Spalte Antwort. Wenn Sie mehr<br/>als ein mandant zugeordnet ist<br/>beachten Sie alle IDs. | Name des Mandanten: <br/>Mandanten-ID:| |
> | In welchen Regionen werden die Mandanten bereitgestellt?| | |
> | Beachten Sie den Typ dieser Microsoft 365- oder <br/>Office 365-Mandanten. Sind sie multitenant <br/>oder Dedicated? | <input type="checkbox"> Multitenant<br/> <input type="checkbox"> Dedizierte | |
> | Welche Microsoft Online-Produkte werden zurzeit verwendet? <br/>Notieren Sie sich die Anzahl der Benutzer, die für die einzelnen Benutzer aktiviert sind. <br/>in der Spalte Kommentare. | <input type="checkbox"> Microsoft Teams <br/> <input type="checkbox"> Skype for Business <br/>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox"> Exchange Online <br/> <input type="checkbox"> SharePoint Online <br/> <input type="checkbox"> OneDrive for Business <br/> <input type="checkbox"> Yammer <br/> <input type="checkbox"> Sonstige| |
> | Welche Lizenzstufe ist für Skype aktiviert? <br/>Business Online-Benutzer? | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 | Die Anzahl der Benutzer <br/>für jede SKU: |
> | Was ist die aktuelle Active Directory-Gesamtstruktur? <br/>Funktionsebene in der Umgebung? <br/>Wenn es mehrere Gesamtstrukturen gibt, beachten Sie die Details <br/>in der Spalte Kommentare. | <input type="checkbox"> Windows Server 2000 <br/> <input type="checkbox"> Windows Server 2003 <br/> <input type="checkbox"> Windows Server 2008<br/> <input type="checkbox"> Windows Server 2008 R2 <br/> <input type="checkbox"> Windows Server 2012 <br/> <input type="checkbox"> Windows Server 2012 R2 <br/> <input type="checkbox"> Windows Server 2016| |
> | Was verwenden Sie für das Verzeichnis? <br/>Synchronisierung heute? |<input type="checkbox"> Keine Synchronisierung (nur Cloud) <br/> <input type="checkbox"> Azure Active Directory <br/>&nbsp;&nbsp; &nbsp; Verbinden <br/> <input type="checkbox"> Sonstiges (Geben Sie im <br/>&nbsp;&nbsp; &nbsp; Spalte "Kommentare".)| |
> | Ist zurzeit eine Partneridentität bereitgestellt? <br/>(Active Directory Federation Services oder <br/>Drittanbieter) | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Wenn Sie eine Verbundidentität verwenden, <br/>Verbundinfrastruktur? | <input type="checkbox"> Windows 2008 R2 AD FS <br/> <input type="checkbox"> Windows 2012 AD FS <br/> <input type="checkbox"> Windows 2012 R2 AD FS <br/> <input type="checkbox"> Windows 2016 AD FS <br/> <input type="checkbox"> Drittanbieterverbund <br/>&nbsp;&nbsp; &nbsp; Gateway (Beachten Sie die Details <br/>&nbsp;&nbsp; &nbsp; in der Spalte Kommentare.) | |
> | Wenn Sie derzeit ein aktives Microsoft 365<br/>oder Office 365-Mandant ist die SMTP/SIP-Domäne von <br/>Ihre zielorientierten Benutzer, die dem Mandanten zugeordnet sind? | <input type="checkbox"> N/A – Kein Microsoft 365 oder<br/>&nbsp;&nbsp; &nbsp; Office 365-Mandant an Ort und Stelle <br/> <input type="checkbox"> Nein, SMTP/SIP der Benutzer <br/>&nbsp;&nbsp; &nbsp; Domäne ist nicht zugeordnet <br/>&nbsp;&nbsp; &nbsp; mit beliebigen Mandanten in <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 oder Office 365<br/> <input type="checkbox"> Ja, SMTP/SIP der Benutzer <br/>&nbsp;&nbsp; &nbsp; Domäne ist zugeordnet <br/>&nbsp;&nbsp; &nbsp; mit einem vorhandenen Mandanten in <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 oder Office 365 | |
> | Entsprechen Benutzer-UPNs ihrer primären SMTP-Adresse? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein <br/> <input type="checkbox"> Inkonsistent | |

<a name="existing-collaboration-platform-summary"></a>Zusammenfassung der vorhandenen Zusammenarbeitsplattform
---

Verwenden Sie die folgende Tabelle, um Informationen zur vorhandenen Bereitstellung der Zusammenarbeitsplattform zu erfassen.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Ist Microsoft Teams bereitgestellt? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Ist Skype for Business bereitgestellt? <br/>Stellen Sie bei lokalen und hybriden Bereitstellungen sicher, dass <br/>beachten Sie die Version und das kumulative Update (CU) <br/>details in the Comments column. | <input type="checkbox"> Ja, Microsoft 365 oder <br/>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox"> Ja, Hybrid (mit <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 oder <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Ja, lokal <br/> <input type="checkbox"> Ja, online, dedizierte <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Ja, gehostet, dedizierte <br/>&nbsp;&nbsp; &nbsp; (Dritter) <br/> <input type="checkbox"> Ja, gehostet, freigegeben <br/>&nbsp;&nbsp; &nbsp; (Dritter) <br/> <input type="checkbox"> Nein, andere | |
> | Ist Exchange bereitgestellt? <br/>Stellen Sie bei lokalen und hybriden Bereitstellungen sicher, dass <br/>sie die Versions- und CU-Details in den Kommentaren <br/>spalte. | <input type="checkbox"> Ja, Microsoft 365 <br/> <input type="checkbox"> Ja, Hybrid (mit <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 oder <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Ja, lokal <br/> <input type="checkbox"> Ja, online, dedizierte <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Ja, gehostet, dedizierte <br/>&nbsp;&nbsp; &nbsp; (Dritter) <br/> <input type="checkbox"> Ja, gehostet, freigegeben <br/>&nbsp;&nbsp; &nbsp; (Dritter) <br/> <input type="checkbox"> Nein, andere | |
> | Ist SharePoint bereitgestellt? <br/>Stellen Sie bei lokalen und hybriden Bereitstellungen sicher, dass <br/>sie die Versions- und CU-Details in den Kommentaren <br/>spalte. | <input type="checkbox"> Ja, Microsoft 365 <br/> <input type="checkbox"> Ja, Hybrid (mit <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 oder <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Ja, lokal <br/> <input type="checkbox"> Ja, online, dedizierte <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Ja, gehostet, dedizierte <br/>&nbsp;&nbsp; &nbsp; (Dritter) <br/> <input type="checkbox"> Ja, gehostet, freigegeben <br/>&nbsp;&nbsp; &nbsp; (Dritter) <br/> <input type="checkbox"> Nein, andere | |
> | Ist OneDrive for Business bereitgestellt? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Sind andere Plattformen von Drittanbietern bereitgestellt? <br/>und heute in Gebrauch? Wenn ja, notieren Sie sich die Anzahl der Benutzer von <br/>und die Nutzungsdetails im <br/>Spalte "Kommentare". | <input type="checkbox"> Cisco WebEx <br/> <input type="checkbox"> Pufferzeit <br/> <input type="checkbox"> Sonstiges (Geben Sie im <br/>&nbsp;&nbsp; &nbsp; Spalte "Kommentare".) | Anzahl der Benutzer: <br/>Details:|
> | Planen Sie, Benutzer von diesen Drittanbietern zu verschieben? <br/>Plattformen zu Teams? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Was ist die aktuelle Telefonie- und Konferenzlösung? <br/>der Benutzer, die sich im Rahmen dieser Initiative befinden? | | |
> | Verfügen Sie über [SBC-Server, die Direct Routing](./direct-routing-plan.md#supported-session-border-controllers-sbcs) unterstützen <br/>für Ihre Büros, die sich im Rahmen dieser Initiative befinden? Wenn Ja,<br/>Beachten Sie die Details in der Spalte Kommentare.| <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein ||

<a name="collaboration-platform-deployment-details"></a>Bereitstellungsdetails für die Zusammenarbeitsplattform
---

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (falls zutreffend)

Erfassen Sie ggf. die Details Ihrer Teams-Bereitstellung mithilfe der nachstehenden Beispieltabelle. Wenn Sie Teams noch nicht bereitgestellt haben, überspringen Sie diesen Abschnitt.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Welche Benutzertypen sind für Microsoft Teams aktiviert? | <input type="checkbox"> Alle Benutzer in der Organisation <br/> <input type="checkbox"> Bestimmte Benutzer/Benutzergruppen <br/>&nbsp;&nbsp; &nbsp; (Geben Sie in der Spalte Kommentare an.) ||
> | Welche Features und Modalitäten von Teams werden verwendet? | <input type="checkbox"> Kanalbasierte Unterhaltungen <br/> <input type="checkbox"> Privater Chat <br/> <input type="checkbox"> Gastzugriff <br/> <input type="checkbox"> Kanalbesprechungen <br/> <input type="checkbox"> Private Besprechungen <br/> <input type="checkbox"> Private Anrufe <br/> <input type="checkbox"> Ad-hoc-Kanalbetreff <br/> <input type="checkbox"> Videos in Besprechungen <br/> <input type="checkbox"> Bildschirmfreigabe in Besprechungen <br/> <input type="checkbox"> Audiokonferenzen <br/><input type="checkbox"> Anwendungen (Apps)<br/> &nbsp;&nbsp; &nbsp;<input type="checkbox"> Registerkarten<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Bots <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Connectors<br/><input type="checkbox"> Benutzerdefinierte Cloudspeicherintegration <br/>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google <br/>&nbsp;&nbsp; &nbsp; Laufwerk, Egnyte <br/> <input type="checkbox"> Kanal-E-Mail-Integration <br/> <input type="checkbox"> Sonstige (Geben Sie in der Spalte Kommentare an.) | |
> | Welche Anwendungen haben Sie in Teams bereitgestellt? | | |
> | Haben Sie Funktionen von Microsoft Teams ausdrücklich gesperrt? <br/>Wenn Ja, notieren Sie sich die Details in der Spalte Kommentare. | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein ||
> | Welche Microsoft Teams-Clients werden verwendet? | <input type="checkbox"> Web <br/> <input type="checkbox"> Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> Linux <br/>  <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Windows Mobile | |
> | Wer verfügt über Berechtigungen zum Erstellen von Teams? | <input type="checkbox"> Jeder in der Organisation <br/>&nbsp;&nbsp; &nbsp; (Dies ist die Standardeinstellung) <br/> <input type="checkbox"> Bestimmte Personen <br/>&nbsp;&nbsp; &nbsp; (Geben Sie in der Spalte Kommentare an.) | |
> | Verwenden Sie Sicherheits- und Compliance-Funktionen in Microsoft Teams? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online (falls zutreffend)

Erfassen Sie ggf. die Details Ihrer Skype for Business Online-Bereitstellung mithilfe der nachstehenden Beispieltabelle. Wenn Sie die Skype for Business Online-Bereitstellung noch nicht bereitgestellt haben, überspringen Sie diesen Abschnitt.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Welche Benutzertypen sind für Skype aktiviert? <br/>für Business Online? | <input type="checkbox"> Alle Benutzer in der Organisation <br/> <input type="checkbox"> Bestimmte Benutzer/Benutzergruppen <br/>&nbsp;&nbsp; &nbsp; (Geben Sie in der Spalte Kommentare an.) | |
> | Welche Modalitäten und Features derzeit sind <br/>die heute verwendet werden? | <input type="checkbox"> Chatnachrichten und Anwesenheitsnachrichten (Chat/P)<br/> <input type="checkbox"> Konferenzen <br/> <input type="checkbox"> Verbund <br/> <input type="checkbox"> Besprechungsaufzeichnung <br/> <input type="checkbox"> Microsoft Audio Conferencing <br/> <input type="checkbox"> Audiokonferenzen von Drittanbietern (Hinweis<br/>&nbsp;&nbsp; &nbsp; die Details in der Spalte Kommentare.) <br/> <input type="checkbox"> Anrufpläne (früher PSTN-Anrufe) <br/> <input type="checkbox"> Automatische Organisationswarten <br/> <input type="checkbox"> Anrufwarteschlangen | |
> | Haben Sie skype für <br/>Business Online-Funktionen? <br/>Wenn Ja, notieren Sie sich die Details in der Spalte Kommentare. | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Welche Methode verwenden Oder planen Sie für <br/>Telefonsystem (vorige Cloud PBX) mit <br/>pstN? <br/>Wählen Sie alle anwendbaren Aus- und Auswähler aus. | <input type="checkbox"> Anrufpläne (früher PSTN-Anrufe) <br/> <input type="checkbox"> Lokale PSTN-Konnektivität <br/>&nbsp;&nbsp; &nbsp; (verwenden Sie vorhandene Skype für <br/>&nbsp;&nbsp; &nbsp; Business 2015 oder Lync Server <br/>&nbsp;&nbsp; &nbsp; 2013-Bereitstellung) <br/> <input type="checkbox"> Lokale PSTN-Konnektivität <br/>&nbsp;&nbsp; &nbsp; (mit Cloud Connector) | |
> | Haben Sie Telefonnummern zu Microsoft portiert? <br/>Dies gilt für Anrufpläne und Audio <br/>Konferenzfeatures. | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype for Business lokal (falls zutreffend)

Erfassen Sie ggf. die Details Ihrer Skype for Business-Bereitstellung mithilfe der nachstehenden Beispieltabelle. Wenn Sie Skype for Business nicht lokal bereitgestellt haben, überspringen Sie diesen Abschnitt.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Welche Versionen von Lync oder Skype for Business <br/> werden derzeit lokal bereitgestellt? | <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox"> Skype for Business Server 2015 <br/> <input type="checkbox"> Skype for Business Server 2019 <br/><input type="checkbox"> Skype for Business Cloud Connector <br/>&nbsp;&nbsp; &nbsp; Edition | |
> | Ist eine hybride Bereitstellung mit Skype for Business Online konfiguriert? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Wird diese Umgebung von einem dritten <br/>Party? Wenn Ja, notieren Sie sich die Details im <br/>Spalte "Kommentare". | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Welche Modalitäten und Features derzeit verwendet werden <br/>heute? | <input type="checkbox"> Chatnachrichten und Anwesenheitsnachrichten (Chat/P) <br/> <input type="checkbox"> Konferenzen <br/> <input type="checkbox"> Verbund <br/> <input type="checkbox"> Besprechungsaufzeichnung <br/> <input type="checkbox"> Beständiger Chat / Gruppenchat <br/> <input type="checkbox"> Microsoft Audio Conferencing <br/>&nbsp;&nbsp; &nbsp; (voriges Einwählen von Konferenzen) auf Ihrem <br/>&nbsp;&nbsp; &nbsp; lokalen Lync Server oder <br/>&nbsp;&nbsp; &nbsp; Skype for Business-Bereitstellung <br/> <input type="checkbox"> Audiokonferenzen von Drittanbietern <br/>&nbsp;&nbsp; &nbsp; (Beachten Sie die Details in den Kommentaren <br/>&nbsp;&nbsp; &nbsp; Spalte.) <br/> <input type="checkbox"> Enterprise-VoIP lokale Verwendung <br/>&nbsp; &nbsp; &nbsp;PSTN-Konnektivität <br/> <input type="checkbox"> Anrufpläne (früher PSTN-Anrufe) über <br/>&nbsp;&nbsp; &nbsp; Hybrid mit Skype for Business Online | |
> | Welche Edgeserverversionen sind bereitgestellt? | <input type="checkbox"> Office Communications Server 2007 "R1" <br/> <input type="checkbox"> Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox"> Skype for Business Server 2015 <br/> <input type="checkbox"> Skype for Business Server 2019| |
> | Haben Sie Lync oder Skype for Business Edge? <br/>in mehr als einem Rechenzentrum bereitgestellt? <br/>Wenn Ja, notieren Sie sich die Details in der Spalte Kommentare. | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Wählen Sie Dienste aus, die Ihre Edge-Rolle heute bietet. | <input type="checkbox"> Zugriff externer Benutzer (Unternehmensbenutzer) <br/> <input type="checkbox"> Remotebenutzerzugriff (anonym) <br/>&nbsp;&nbsp; &nbsp; externe Besprechungsteilnehmer) <br/> <input type="checkbox"> Verbund <br/> <input type="checkbox"> Medienrelais | |
> | Welche der folgenden Sprachanruffeatures <br/>sind derzeit Abhängigkeiten von? <br/>Beachten Sie alle zusätzlichen Abhängigkeiten in den Kommentaren <br/>spalte. | <input type="checkbox"> Beschäftigt-Optionen <br/> <input type="checkbox"> Anrufpark <br/> <input type="checkbox"> Anrufabholung oder Gruppenanrufabholung <br/> <input type="checkbox"> Telefone im allgemeinen Bereich oder "Hot Desking" <br/> <input type="checkbox"> Reaktionsgruppen oder Sammelgruppen <br/> <input type="checkbox"> Darstellung einer freigegebenen Zeile <br/> <input type="checkbox"> Private Zeile <br/> <input type="checkbox"> Voicemail <br/> <input type="checkbox"> Anrufen über die Arbeit <br/> <input type="checkbox"> Notfall- oder Informationsnummern <br/>&nbsp;&nbsp; &nbsp; (911, 811, 411) <br/> <input type="checkbox"> Erweiterungswahl <br/> <input type="checkbox"> automatische Telefonzentrale <br/> <input type="checkbox"> Abonnentenzugriff <br/> <input type="checkbox"> Analoge Geräte <br/> <input type="checkbox"> Fax <br/> <input type="checkbox"> Maskierung oder Änderung der Anrufer-ID <br/> <input type="checkbox"> Standortbasiertes Routing <br/> <input type="checkbox"> Kostengünstiges Routing <br/> <input type="checkbox"> Lifttelefone | |

<a name="networking-and-access-to-microsoft-365-and-office-365-services"></a>Netzwerk und Zugriff auf Microsoft 365- und Office 365-Dienste
---

Verwenden Sie die folgende Tabelle, um die Netzwerkdetails Ihrer Organisation zu erfassen und zu erfassen, wie Ihre Benutzer mit Microsoft 365- und Office 365-Diensten verbunden sind (oder werden).

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Wie (oder wie wird) die Benutzer im Migrationsbereich <br/>Sie auf Teams zugreifen, wenn sie sich im Büro auf dem Büro begnen? <br/>Wählen Sie alle anwendbaren Aus- und Auswähler aus. | <input type="checkbox"> Routeierte NAT-Verbindung <br/> <input type="checkbox"> Proxyserver <br/> <input type="checkbox"> Öffentliche Wi-Fi <br/> <input type="checkbox"> Verwaltete (nicht öffentliche) Wi-Fi <br/> <input type="checkbox"> ExpressRoute <br/>&nbsp;&nbsp; &nbsp; (Microsoft-Peering) ||
> | Wenn der Zugriff auf Microsoft 365 oder Office 365 über eine<br/>gibt es eine Möglichkeit, den Proxy zu umgehen? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Wird ExpressRoute zurzeit genutzt? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein <br/> <input type="checkbox"> Nein, aber es wird geplant | |
> | Haben Sie eine Netzwerkbereitschaftsbeurteilung durchgeführt? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Müssen Benutzer ein VPN verwenden, wenn sie eine Verbindung mit <br/>Unternehmensressourcen remote? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Wenn ein VPN verwendet wird, kann der Teams-Datenverkehr aus <br/>das VPN für den direkten Zugriff auf Microsoft 365- und Office 365-Dienste? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Unterstützt Ihr Netzwerk QoS? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Können Sie den Audio- und Videodatenverkehr von Teams priorisieren? <br/>um eine hohe Qualität zu gewährleisten? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Haben alle Speicherorte in einer Region einen Internetanschluss, <br/>oder ist der Internetanschluss für die gesamte Region zentralisiert? | <input type="checkbox"> Regionaler Zugriff auf das Internet <br/> <input type="checkbox"> Zentraler Zugriff auf die <br/>&nbsp;&nbsp; &nbsp; Internet | |

<a name="endpoints"></a>Endpunkte
---

Verwenden Sie die folgende Tabelle, um die Details der verwendeten Clients und Endpunkte zu erfassen.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Welches Desktopbetriebssystem verwenden die Benutzer? | <input type="checkbox"> Windows XP <br/> <input type="checkbox"> Windows 7 <br/> <input type="checkbox"> Windows 8 <br/> <input type="checkbox"> Windows 10 <br/> <input type="checkbox"> Mac (Geben Sie die Version in der Spalte Kommentare an.) <br/> <input type="checkbox"> Linux (Geben Sie die Verteilung in der Spalte Kommentare an.) <br/><input type="checkbox"> Sonstiges (Beachten Sie die Details in der Spalte Kommentare.) | |
> | Welche Version von Microsoft Office bereitgestellt wird <br/>auf diese Geräte? | <input type="checkbox"> Office 2003 <br/> <input type="checkbox"> Office 2007 <br/> <input type="checkbox"> Office 2010 <br/> <input type="checkbox"> Office 2013 <br/> <input type="checkbox"> Office 2016 <br/> <input type="checkbox"> Office für Mac 2011 <br/> <input type="checkbox"> Office für Mac 2016 <br/> <input type="checkbox"> Sonstiges (Beachten Sie die Details in der Spalte Kommentare.) | |
> | Welche Office-Bereitstellungstechnologie verwendet wird <br/>in Ihrer Organisation? | <input type="checkbox"> MSI <br/> <input type="checkbox"> Klick-und-Ausführen | |
> | Was sind die zulässigen und unterstützten Mobilgeräte? <br/>Plattformen verwendet werden? <br/>Wählen Sie alle anwendbaren Aus- und Auswähler aus. | <input type="checkbox"> Windows <br/> <input type="checkbox"> Mobile <br/> <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Sonstiges (Beachten Sie die Details in der Spalte Kommentare.) | |
> | Wie werden mobile Geräte bereitgestellt? <br/>Wählen Sie alle anwendbaren Aus- und Auswähler aus. | <input type="checkbox"> Unternehmensgeräte <br/> <input type="checkbox"> Eigenes Gerät mitbringen | |
> | Welche Geräte verwenden Benutzer derzeit für den Zugriff <br/>Sprach- und Konferenzdienste <br/>(Mobiltelefone, Headsets, Telefone, Video)? | | |

<a name="operations"></a>Vorgänge
---

Verwenden Sie die folgende Tabelle, um die Details der betrieblichen Aspekte Ihrer Umgebung zu erfassen.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Was ist Ihr Betriebsmodell für Ihren Lync Server, <br/>Skype for Business Server, Microsoft 365-Bereitstellung, <br/>oder office 365-Bereitstellung heute? | | |
> | Können Sie die aktuelle Supportanordnung für <br/>Lync Server, Skype for Business Server, Microsoft 365, <br/>oder Office 365? | | |
> | Wenn Sie in mehreren Ländern oder Regionen bereitstellen, <br/>verfügt jedes Land/jede Region über eine eigene IT/Telefonie <br/>mitarbeiter, mit dem Sie zusammenarbeiten können, oder wird dies zentral verwaltet? | <input type="checkbox"> Regionale Vorgänge und Support <br/> <input type="checkbox"> Zentrale Vorgänge und Support | |
> | Wenden Sie die Methodik für Anrufqualität an? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Haben Sie eine Person oder ein Team dem <br/>Rolle des Qualitätsmeisters für die Zusammenarbeitsplattform <br/>in Verwendung? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein ||
> | Wie überwachen Sie Ihren Lync Server, Skype für <br/>Business Server, Microsoft 365-Bereitstellung oder <br/>Office 365-Bereitstellung? | | |
> | Treten Probleme mit der Anrufqualität auf? | <input type="checkbox"> Ja<br/> <input type="checkbox"> Nein | |
> | Wie und wann bieten Sie Schulungen für Ihre <br/>Helpdesk zu neuen Diensten und Funktionen? | | |

<a name="adoption-and-readiness"></a>Einführung und Bereitschaft
---

Erfassen Sie mithilfe der folgenden Tabelle den aktuellen Status der Einführung und Bereitschaft in Ihrer Organisation.

>
> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Was ist Ihre aktuelle aktive Nutzung von <br/>Skype for Business? | **__** % der aktiven Benutzer insgesamt im Vergleich zu aktivierten Benutzern | |
> | Wie wird Ihre Organisation verwendet? <br/>Skype for Business? | Einzelunterhaltungen <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Imit <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Anrufe <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Freigabe<br/> Besprechungen <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Konferenzen<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Freigabe<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Anrufe | |
> | Verfügt Ihre Organisation über eine Benutzeradzeptanz <br/>und Änderungsverwaltungsteam? | <input type="checkbox"> Ja<br/> <input type="checkbox"> Nein | |
> | Wie messen Sie derzeit den Erfolg für Technologie? <br/>Rollouts wie Skype for Business? | | |
> | Welchen Prozentsatz Ihrer Benutzerbasis würden Sie sagen? <br/>Skype for Business übernommen? | | |
> | Wie ist die Einstellung der Benutzer zu Skype for Business? | <input type="checkbox"> Gut <br/> <input type="checkbox"> Neutral <br/> <input type="checkbox"> Schlecht | |
> | Welche der folgenden Informationen beschreibt am besten das Rollout <br/>Für Skype for Business verwendete Strategie <br/>Bereitstellung? | <input type="checkbox"> Breite Reichweite: E-Mail-Kampagne mit <br/>&nbsp;&nbsp; &nbsp; Links zu Schulungen <br/> <input type="checkbox"> Erweitert: Breite Reichweite und eine Vielzahl <br/>&nbsp;&nbsp; &nbsp; von Bewusstseinskampagnen (Poster, <br/>&nbsp;&nbsp; &nbsp; Events, Champions) und Schulungen <br/>&nbsp;&nbsp; &nbsp; (Videos, Benutzerhandbücher, persönlich) <br/> <input type="checkbox"> Maßgeschneidert: Erweitert, plus gezielt <br/>&nbsp;&nbsp; &nbsp; Messaging und Schulung nach Persona <br/> <input type="checkbox"> Sonstige <br/>&nbsp;&nbsp; &nbsp; (Beachten Sie die Details in der Spalte Kommentare.) | |