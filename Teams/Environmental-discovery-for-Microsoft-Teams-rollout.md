---
title: Umweltkompatibilität – Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: So führen Sie eine detaillierte Umgebungsermittlung durch, während Sie Ihre Reise von Skype for Business zu Microsoft Teams planen.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 348a0e615f5ef876bfdd62b71adb30f6bf242dd6
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562604"
---
# <a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Umgebungsermittlung für ein Microsoft Teams-Rollout

Die Ermittlung ist einer der ersten, wichtigsten Schritte, die Sie bei der Planung Ihrer Reise zu Microsoft Teams ausführen.

Sie führen eine detaillierte Ermittlung Ihrer Umgebung durch, um den aktuellen Zustand besser zu verstehen und etwaige Schwierigkeiten oder – noch weiter – mögliche Blockierer für die Ausführung Ihres Teams-Rollouts aufzudecken.

## <a name="discovery-questionnaire"></a>Ermittlungsfragebogen

Der folgende Beispielfragebogen führt Sie durch eine Reihe von Fragen, um zu bestätigen, dass Ihre Organisation für die erfolgreiche Einführung von Audiokonferenzen und Telefonsystem mit Anrufplänen in Teams bereit ist.

Alle Angelegenheiten im Zusammenhang mit Ihrer vorhandenen Infrastruktur für die Zusammenarbeit und Microsoft 365 oder Office 365 Organisation, Netzwerk, Endpunkte, Vorgänge sowie Einführung und Bereitschaft sind teil des Fragebogens zur Ermittlung der Umgebung.

Der Fragebogen ist in mehrere Abschnitte unterteilt, um die Bereitschaft Ihrer Organisation für Ihre Teams-Bereitstellung in mehreren wichtigen Bereichen zu bestätigen. Arbeiten Sie mit Ihrem Projektteam zusammen, um die angeforderten Informationen so detailliert wie möglich bereitzustellen, um Ihre Planungsaktivitäten zu erleichtern.

> [!TIP]
> Sie können beginnen, indem Sie den Fragebogen in ein Microsoft Word-Dokument kopieren. Versuchen Sie, alle Fragen zu beantworten und alle Details zu erfassen, während Sie navigieren.

### <a name="project-team"></a>Projektteam

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
> | Leads für Geschäftsbereiche | | | |

## <a name="microsoft-365-or-office-365-organization-details"></a>Microsoft 365- oder Office 365 Organisationsdetails

Es wird dringend empfohlen, dass Sie während der Arbeit mit diesem Fragebogen über eine aktive Microsoft 365- oder Office 365-Organisation verfügen. Wenn Sie eine Microsoft 365- oder Office 365 Organisation noch nicht aktiviert oder konfiguriert haben, lesen Sie ["Planen der Einrichtung von Microsoft 365 Business](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)".

Verwenden Sie die folgende Tabelle, um Informationen zur Microsoft 365- oder Office 365-Organisation zu erfassen.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Beachten Sie die Microsoft 365-Produktion<br/>oder Office 365 Name und ID der Organisation<br/>in der Spalte "Antwort". Wenn Sie mehr haben<br/>als ein Mandant, der<br/>Ihre Organisation, notieren Sie sich alle IDs. | Mandantenname: <br/>Mandanten-ID:| |
> | In welchen Regionen werden die Mandanten bereitgestellt?| | |
> | Beachten Sie den Typ dieser Microsoft 365- oder <br/>Office 365 Mandanten. Sind sie multitenant? <br/>oder dediziert? | <input type="checkbox"> Mehrinstanzenfähig<br/> <input type="checkbox"> Gewidmet | |
> | Welche Microsoft Online-Produkte werden zurzeit verwendet? <br/>Beachten Sie, wie viele Benutzer für die einzelnen Benutzer aktiviert sind. <br/>-Dienst in der Spalte "Kommentare". | <input type="checkbox"> Microsoft Teams <br/> <input type="checkbox">Skype for Business <br/>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox"> SharePoint Online <br/> <input type="checkbox">OneDrive for Business <br/> <input type="checkbox"> Yammer <br/> <input type="checkbox"> Andere| |
> | Welche Lizenzstufe ist für Skype für aktiviert? <br/>Business Online-Benutzer? | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 | Die Anzahl der Benutzer <br/>für jede SKU: |
> | Was ist die aktuelle Active Directory-Gesamtstruktur? <br/>Funktionsebene in der Umgebung? <br/>Wenn mehr als eine Gesamtstruktur vorhanden ist, beachten Sie die Details <br/>in der Spalte "Kommentare". | <input type="checkbox"> Windows Server 2000 <br/> <input type="checkbox"> Windows Server 2003 <br/> <input type="checkbox"> Windows Server 2008<br/> <input type="checkbox"> Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | Was verwenden Sie für das Verzeichnis? <br/>Synchronisierung heute? |<input type="checkbox"> Keine Synchronisierung (nur Cloud) <br/> <input type="checkbox"> Azure Active Directory <br/>&nbsp;&nbsp; &nbsp; Verbinden <br/> <input type="checkbox"> Andere (Geben Sie im <br/>&nbsp;&nbsp; &nbsp; Spalte "Kommentare".)| |
> | Ist zurzeit eine Partneridentität bereitgestellt? <br/>(Active Directory-Verbunddienste (AD FS) oder <br/>Drittanbieter) | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Wenn Sie verbundidentität verwenden, was ist die <br/>Verbundinfrastruktur? | <input type="checkbox"> Windows 2008 R2 AD FS <br/> <input type="checkbox"> Windows 2012 AD FS <br/> <input type="checkbox"> Windows 2012 R2 AD FS <br/> <input type="checkbox"> Windows 2016 AD FS <br/> <input type="checkbox"> Drittanbieterverbund <br/>&nbsp;&nbsp; &nbsp;Gateway (Beachten Sie die Details <br/>&nbsp;&nbsp; &nbsp;in der Spalte "Kommentare".) | |
> | Wenn Sie derzeit ein aktives Microsoft 365 verwalten<br/>oder Office 365 Mandant ist die SMTP/SIP-Domäne von <br/>Ihre benutzerbezogenen Benutzer, die dem Mandanten zugeordnet sind? | <input type="checkbox"> Nv – Keine Microsoft 365 oder<br/>&nbsp;&nbsp; &nbsp;Office 365 Mandant vorhanden <br/> <input type="checkbox"> Nein, SMTP/SIP der Benutzer <br/>&nbsp;&nbsp; &nbsp;Domäne ist nicht zugeordnet <br/>&nbsp;&nbsp; &nbsp;mit beliebigen Mandanten in <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 oder Office 365<br/> <input type="checkbox"> Ja, SMTP/SIP der Benutzer <br/>&nbsp;&nbsp; &nbsp;Domäne zugeordnet ist <br/>&nbsp;&nbsp; &nbsp;mit einem vorhandenen Mandanten in <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 oder Office 365 | |
> | Stimmen Benutzer-UPNs mit ihrer primären SMTP-Adresse überein? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein <br/> <input type="checkbox"> Uneinheitlich | |

## <a name="existing-collaboration-platform-summary"></a>Zusammenfassung der vorhandenen Plattform für die Zusammenarbeit

Verwenden Sie die folgende Tabelle, um Informationen zu Ihrer vorhandenen Plattformbereitstellung für die Zusammenarbeit zu erfassen.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Ist Microsoft Teams bereitgestellt? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Ist Skype for Business bereitgestellt? <br/>Stellen Sie für lokale und hybride Bereitstellungen sicher, dass <br/>Sie beachten die Version und das kumulative Update (CU) <br/>Details in der Spalte "Kommentare". | <input type="checkbox"> Ja, Microsoft 365 oder <br/>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox"> Ja, hybrid (mit <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 oder <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> Ja, lokal <br/> <input type="checkbox"> Ja, online, dediziert <br/>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> Ja, gehostet, dediziert <br/>&nbsp;&nbsp; &nbsp;(Drittanbieter) <br/> <input type="checkbox"> Ja, gehostet, freigegeben <br/>&nbsp;&nbsp; &nbsp;(Drittanbieter) <br/> <input type="checkbox"> Nein, andere | |
> | Ist Exchange bereitgestellt? <br/>Stellen Sie für lokale und hybride Bereitstellungen sicher, dass <br/>die Versions- und CU-Details in den Kommentaren notieren <br/>Spalte. | <input type="checkbox"> Ja, Microsoft 365 <br/> <input type="checkbox"> Ja, hybrid (mit <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 oder <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> Ja, lokal <br/> <input type="checkbox"> Ja, online, dediziert <br/>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> Ja, gehostet, dediziert <br/>&nbsp;&nbsp; &nbsp;(Drittanbieter) <br/> <input type="checkbox"> Ja, gehostet, freigegeben <br/>&nbsp;&nbsp; &nbsp;(Drittanbieter) <br/> <input type="checkbox"> Nein, andere | |
> | Ist SharePoint bereitgestellt? <br/>Stellen Sie für lokale und hybride Bereitstellungen sicher, dass <br/>die Versions- und CU-Details in den Kommentaren notieren <br/>Spalte. | <input type="checkbox"> Ja, Microsoft 365 <br/> <input type="checkbox"> Ja, hybrid (mit <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 oder <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> Ja, lokal <br/> <input type="checkbox"> Ja, online, dediziert <br/>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> Ja, gehostet, dediziert <br/>&nbsp;&nbsp; &nbsp;(Drittanbieter) <br/> <input type="checkbox"> Ja, gehostet, freigegeben <br/>&nbsp;&nbsp; &nbsp;(Drittanbieter) <br/> <input type="checkbox"> Nein, andere | |
> | Wird OneDrive for Business bereitgestellt? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Sind andere Plattformen von Drittanbietern bereitgestellt? <br/>und heute in Gebrauch? Wenn ja, notieren Sie sich die Anzahl der Benutzer von <br/>diese Plattformen und die Nutzungsdetails im <br/>Kommentarspalte. | <input type="checkbox"> Cisco Webex <br/> <input type="checkbox"> Slack <br/> <input type="checkbox"> Andere (Geben Sie im <br/>&nbsp;&nbsp; &nbsp; Spalte "Kommentare".) | Anzahl der Benutzer: <br/>Details:|
> | Planen Sie, Benutzer von diesen Drittanbietern zu verschieben? <br/>Plattformen für Teams? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Was ist die aktuelle Telefonie- und Konferenzlösung? <br/>der Nutzer, die in den Geltungsbereich dieser Initiative fallen? | | |
> | Verfügen Sie über [SBC,die Direct Routing unterstützen](./direct-routing-plan.md#supported-session-border-controllers-sbcs) ? <br/>für Ihre Büros, die im Rahmen dieser Initiative stehen? Wenn ja,<br/>beachten Sie die Details in der Spalte "Kommentare".| <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein ||

## <a name="collaboration-platform-deployment-details"></a>Details zur Bereitstellung der Plattform für die Zusammenarbeit

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (falls zutreffend)

Erfassen Sie ggf. die Details Ihrer Teams-Bereitstellung mithilfe der nachstehenden Beispieltabelle. Wenn Sie Teams nicht bereitgestellt haben, überspringen Sie diesen Abschnitt.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Welche Benutzertypen sind für Microsoft Teams aktiviert? | <input type="checkbox"> Alle Benutzer in der Organisation <br/> <input type="checkbox"> Bestimmte Benutzer/Benutzergruppen <br/>&nbsp;&nbsp; &nbsp;(Geben Sie in der Spalte "Kommentare" an.) ||
> | Welche Teams-Features und -Modalitäten werden verwendet? | <input type="checkbox"> Kanalbasierte Unterhaltungen <br/> <input type="checkbox"> Privater Chat <br/> <input type="checkbox"> Gastzugriff <br/> <input type="checkbox"> Kanalbesprechungen <br/> <input type="checkbox"> Private Besprechungen <br/> <input type="checkbox"> Private Anrufe <br/> <input type="checkbox"> Ad-hoc-Kanal-Meetup <br/> <input type="checkbox"> Videos in Besprechungen <br/> <input type="checkbox"> Bildschirmfreigabe in Besprechungen <br/> <input type="checkbox"> Audiokonferenzen <br/><input type="checkbox"> Anwendungen (Apps)<br/> &nbsp;&nbsp; &nbsp;<input type="checkbox"> Registerkarten<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Bots <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Steckverbinder<br/><input type="checkbox"> Benutzerdefinierte Cloudspeicherintegration <br/>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google <br/>&nbsp;&nbsp; &nbsp; Drive, Egnyte <br/> <input type="checkbox"> Kanal-E-Mail-Integration <br/> <input type="checkbox"> Other (Specify in the Comments column.) | |
> | Welche Anwendungen haben Sie in Teams bereitgestellt? | | |
> | Haben Sie Funktionen von Microsoft Teams ausdrücklich gesperrt? <br/>Wenn ja, notieren Sie sich die Details in der Spalte "Kommentare". | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein ||
> | Welche Microsoft Teams-Clients werden verwendet? | <input type="checkbox"> Web <br/> <input type="checkbox"> Fenster <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> Linux <br/>  <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Windows Mobile | |
> | Wer verfügt über Berechtigungen zum Erstellen von Teams? | <input type="checkbox"> Jeder in der Organisation <br/>&nbsp;&nbsp; &nbsp;(Dies ist die Standardeinstellung) <br/> <input type="checkbox"> Bestimmte Personen <br/>&nbsp;&nbsp; &nbsp;(Geben Sie in der Spalte "Kommentare" an.) | |
> | Verwenden Sie Sicherheits- und Compliance-Funktionen in Microsoft Teams? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online (falls zutreffend)

Erfassen Sie ggf. die Details Ihrer Skype for Business Onlinebereitstellung mithilfe der nachstehenden Beispieltabelle. Wenn Sie Skype for Business Onlinebereitstellung nicht bereitgestellt haben, überspringen Sie diesen Abschnitt.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Welche Benutzertypen sind für Skype aktiviert? <br/>für Business Online? | <input type="checkbox"> Alle Benutzer in der Organisation <br/> <input type="checkbox"> Bestimmte Benutzer/Benutzergruppen <br/>&nbsp;&nbsp; &nbsp;(Geben Sie in der Spalte "Kommentare" an.) | |
> | Welche Modalitäten und Features sind derzeit? <br/>in Gebrauch heute? | <input type="checkbox"> Chat und Anwesenheit (Chat/P)<br/> <input type="checkbox"> Conferencing <br/> <input type="checkbox"> Föderation <br/> <input type="checkbox"> Besprechungsaufzeichnung <br/> <input type="checkbox"> Microsoft-Audiokonferenzen <br/> <input type="checkbox"> Audiokonferenzen von Drittanbietern (Hinweis)<br/>&nbsp;&nbsp; &nbsp;die Details in der Spalte "Kommentare".) <br/> <input type="checkbox"> Anrufpläne (früher PSTN-Anrufe) <br/> <input type="checkbox"> Automatische Organisatorische Telefonzentralen <br/> <input type="checkbox"> Anrufwarteschleifen | |
> | Haben Sie skype for ausdrücklich blockiert? <br/>Business Online-Funktionen? <br/>Wenn ja, notieren Sie sich die Details in der Spalte "Kommentare". | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Welche Methode verwenden Oder planen Sie für <br/>Verbinden des Telefonsystems (vormals Cloud PBX) mit <br/>das PSTN? <br/>Wählen Sie alle zutreffenden Optionen aus. | <input type="checkbox"> Anrufpläne (früher PSTN-Anrufe) <br/> <input type="checkbox"> Lokale PSTN-Konnektivität <br/>&nbsp;&nbsp; &nbsp;(Nutzung vorhandener Skype for-Elemente <br/>&nbsp;&nbsp; &nbsp; Business 2015 oder Lync Server <br/>&nbsp;&nbsp; &nbsp;Bereitstellung 2013) <br/> <input type="checkbox"> Lokale PSTN-Konnektivität <br/>&nbsp;&nbsp; &nbsp;(mit Cloud Connector) | |
> | Haben Sie Telefonnummern zu Microsoft portiert? <br/>Dies gilt für Anrufpläne und Audio <br/>Konferenzfeatures. | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype for Business lokal (falls zutreffend)

Erfassen Sie ggf. die Details Ihrer Skype for Business Bereitstellung mithilfe der nachstehenden Beispieltabelle. Wenn Sie Skype for Business lokal nicht bereitgestellt haben, überspringen Sie diesen Abschnitt.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Welche Versionen von Lync oder Skype for Business <br/> werden derzeit lokal bereitgestellt? | <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019 <br/><input type="checkbox">Skype for Business Cloud Connector <br/>&nbsp;&nbsp; &nbsp; Edition | |
> | Ist eine hybride Bereitstellung mit Skype for Business Online konfiguriert? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Wird diese Umgebung von einem Dritten gehostet und verwaltet? <br/>Partei? Wenn ja, notieren Sie sich die Details im <br/>Kommentarspalte. | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Welche Modalitäten und Features werden derzeit verwendet? <br/>Heute? | <input type="checkbox"> Chat und Anwesenheit (Chat/P) <br/> <input type="checkbox"> Conferencing <br/> <input type="checkbox"> Föderation <br/> <input type="checkbox"> Besprechungsaufzeichnung <br/> <input type="checkbox"> Beständiger Chat/ Gruppenchat <br/> <input type="checkbox"> Microsoft-Audiokonferenzen <br/>&nbsp;&nbsp; &nbsp;(vormals Dial in Conferencing) auf Ihrem <br/>&nbsp;&nbsp; &nbsp;lokalen Lync Server oder <br/>&nbsp;&nbsp; &nbsp;Skype for Business Bereitstellung <br/> <input type="checkbox"> Audiokonferenzen von Drittanbietern <br/>&nbsp;&nbsp; &nbsp;(Beachten Sie die Details in den Kommentaren <br/>&nbsp;&nbsp; &nbsp;Spalte.) <br/> <input type="checkbox">Enterprise-VoIP lokale Verwendung <br/>&nbsp; &nbsp; &nbsp;PSTN-Konnektivität <br/> <input type="checkbox"> Anrufpläne (früher PSTN-Anrufe) über <br/>&nbsp;&nbsp; &nbsp; Hybrid mit Skype for Business Online | |
> | Welche Edgeserverversionen sind bereitgestellt? | <input type="checkbox"> Office Communications Server 2007 "R1" <br/> <input type="checkbox"> Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019| |
> | Haben Sie Lync oder Skype for Business Edge? <br/>in mehreren Rechenzentren bereitgestellt? <br/>Wenn ja, notieren Sie sich die Details in der Spalte "Kommentare". | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Wählen Sie Dienste aus, die Ihre Edgerolle heute bereitstellt. | <input type="checkbox"> Externer Benutzerzugriff (Unternehmensbenutzer) <br/> <input type="checkbox"> Remotebenutzerzugriff (anonym) <br/>&nbsp;&nbsp; &nbsp;Externe Besprechungsteilnehmer) <br/> <input type="checkbox"> Föderation <br/> <input type="checkbox"> Medienrelay | |
> | Welche der folgenden Sprachanruffeatures haben Sie? <br/>sind derzeit Abhängigkeiten von? <br/>Beachten Sie alle zusätzlichen Abhängigkeiten in den Kommentaren. <br/>Spalte. | <input type="checkbox"> Beschäftigt-Optionen <br/> <input type="checkbox"> Parken von Anrufen <br/> <input type="checkbox"> Anrufannahme oder Gruppenanrufannahme <br/> <input type="checkbox"> Telefone für gemeinsame Bereiche oder "hot desking" <br/> <input type="checkbox"> Reaktionsgruppen oder Sammelanschlüsse <br/> <input type="checkbox"> Gemeinsame Liniendarstellung <br/> <input type="checkbox"> Privatleitung <br/> <input type="checkbox"> Voicemail <br/> <input type="checkbox"> Anrufen per Arbeit <br/> <input type="checkbox"> Notfall- oder Informationsnummern <br/>&nbsp;&nbsp; &nbsp;(911, 811, 411) <br/> <input type="checkbox"> Durchwahl <br/> <input type="checkbox"> Automatische Telefonzentrale <br/> <input type="checkbox"> Abonnentenzugriff <br/> <input type="checkbox"> Analoge Geräte <br/> <input type="checkbox"> Fax <br/> <input type="checkbox"> Maskieren oder Ändern der Anrufer-ID <br/> <input type="checkbox"> Standortbasiertes Routing <br/> <input type="checkbox"> Kostensparendes Routing <br/> <input type="checkbox"> Aufzugstelefone | |

## <a name="networking-and-access-to-microsoft-365-and-office-365-services"></a>Netzwerk und Zugriff auf Microsoft 365- und Office 365-Dienste

Verwenden Sie die folgende Tabelle, um die Netzwerkdetails Ihrer Organisation zu erfassen und wie Ihre Benutzer mit Microsoft 365 und Office 365 Diensten verbunden sind (oder werden).

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Vorgehensweise (oder wie wird) die Benutzer im Bereich der Migration <br/>Auf Teams zugreifen, wenn sie sich im Büro befinden? <br/>Wählen Sie alle zutreffenden Optionen aus. | <input type="checkbox"> Routing-NAT-Verbindung <br/> <input type="checkbox"> Proxyserver <br/> <input type="checkbox"> Öffentliche Wi-Fi <br/> <input type="checkbox"> Verwaltete (nicht öffentliche) Wi-Fi <br/> <input type="checkbox"> ExpressRoute <br/>&nbsp;&nbsp; &nbsp;(Microsoft-Peering) ||
> | Wenn der Zugriff auf Microsoft 365 oder Office 365 über eine<br/>Proxyserver, gibt es eine Möglichkeit, den Proxy zu umgehen? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Wird ExpressRoute zurzeit genutzt? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein <br/> <input type="checkbox"> Nein, aber es wird geplant | |
> | Haben Sie eine Bewertung der Netzwerkbereitschaft durchgeführt? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Sind Benutzer erforderlich, um ein VPN beim Herstellen einer Verbindung zu verwenden? <br/>Unternehmensressourcen remote? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Wenn ein VPN verwendet wird, kann Teams-Datenverkehr von <br/>das VPN für den direkten Zugriff auf Microsoft 365 und Office 365 Services? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Unterstützt Ihr Netzwerk QoS? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Können Sie den Audio- und Videodatenverkehr in Teams priorisieren? <br/>um ein qualitativ hochwertiges Erlebnis zu fördern? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Haben alle Standorte in einer Region einen Internetausgang? <br/>oder ist der Internetausgang für die gesamte Region zentral? | <input type="checkbox"> Regionaler Zugang zum Internet <br/> <input type="checkbox"> Zentralisierter Zugriff auf die <br/>&nbsp;&nbsp; &nbsp;Internet | |

## <a name="endpoints"></a>Endpunkte

Verwenden Sie die folgende Tabelle, um die Details der verwendeten Clients und Endpunkte zu erfassen.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Welches Desktopbetriebssystem verwenden die Benutzer? | <input type="checkbox"> Windows XP <br/> <input type="checkbox"> Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox"> Mac (Geben Sie die Version in der Spalte "Kommentare" an.) <br/> <input type="checkbox"> Linux (Geben Sie die Verteilung in der Spalte "Kommentare" an.) <br/><input type="checkbox"> Sonstiges (Beachten Sie die Details in der Spalte "Kommentare".) | |
> | Welche Version von Microsoft Office wird bereitgestellt? <br/>auf diese Geräte? | <input type="checkbox"> Office 2003 <br/> <input type="checkbox"> Office 2007 <br/> <input type="checkbox"> Office 2010 <br/> <input type="checkbox"> Office 2013 <br/> <input type="checkbox"> Office 2016 <br/> <input type="checkbox">Office für Mac 2011 <br/> <input type="checkbox">Office für Mac 2016 <br/> <input type="checkbox"> Sonstiges (Beachten Sie die Details in der Spalte "Kommentare".) | |
> | Welche Office-Bereitstellungstechnologie verwendet wird <br/>in Ihrer Organisation? | <input type="checkbox"> MSI <br/> <input type="checkbox"> Klick-und-Los | |
> | Was sind die zulässigen und unterstützten Mobilen? <br/>verwendete Plattformen? <br/>Wählen Sie alle zutreffenden Optionen aus. | <input type="checkbox"> Fenster <br/> <input type="checkbox"> Mobil <br/> <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Sonstiges (Beachten Sie die Details in der Spalte "Kommentare".) | |
> | Wie werden mobile Geräte bereitgestellt? <br/>Wählen Sie alle zutreffenden Optionen aus. | <input type="checkbox"> Unternehmensgeräte <br/> <input type="checkbox"> Bringen Sie Ihr eigenes Gerät mit | |
> | Welche Geräte verwenden Benutzer derzeit für den Zugriff? <br/>Sprach- und Konferenzdienste <br/>(Handys, Headsets, Telefone, Video)? | | |

## <a name="operations"></a>Vorgänge

Verwenden Sie die folgende Tabelle, um die Details der betrieblichen Aspekte Ihrer Umgebung zu erfassen.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Was ist Ihr Betriebsmodell für Ihren Lync Server? <br/>Skype for Business Server, Microsoft 365-Bereitstellung, <br/>oder Office 365 bereitstellung heute? | | |
> | Können Sie die aktuelle Supportanordnung für <br/>Lync Server, Skype for Business Server, Microsoft 365, <br/>oder Office 365? | | |
> | Wenn Sie die Bereitstellung in mehreren Ländern oder Regionen durchführen, <br/>verfügt jedes Land/jede Region über eine eigene IT/Telefonie <br/>personal to work with, or will this be managed zentral? | <input type="checkbox"> Regionale Operationen und Unterstützung <br/> <input type="checkbox"> Zentralisierte Vorgänge und Support | |
> | Wenden Sie die Methodik für Anrufqualität an? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Haben Sie eine Einzelperson oder ein Team dem <br/>Rolle des Qualitätspioniers für die Plattform für die Zusammenarbeit <br/>in Gebrauch? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein ||
> | Wie überwachen Sie Ihren Lync Server, Skype for <br/>Business Server, Microsoft 365-Bereitstellung oder <br/>Office 365 Bereitstellung? | | |
> | Treten Probleme mit der Anrufqualität auf? | <input type="checkbox"> Ja<br/> <input type="checkbox"> Nein | |
> | Wie und wann bieten Sie Schulungen für Ihre <br/>Helpdesk zu neuen Diensten und Funktionen? | | |

## <a name="adoption-and-readiness"></a>Einführung und Bereitschaft

Erfassen Sie mithilfe der folgenden Tabelle den aktuellen Status der Einführung und Bereitschaft in Ihrer Organisation.

>
> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Was ist Ihre aktuelle aktive Nutzung von <br/>Skype for Business? | **__** % gesamtzahl der aktiven Benutzer im Vergleich zu aktivierten Benutzern | |
> | Wie verwendet Ihre Organisation <br/>Skype for Business? | Einzelunterhaltungen <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Chat <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Aufrufen <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Teilens<br/> Besprechungen <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Conferencing<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Teilens<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Aufrufen | |
> | Verfügt Ihre Organisation über eine Benutzerakzeptanz? <br/>und Change Management-Team? | <input type="checkbox"> Ja<br/> <input type="checkbox"> Nein | |
> | Wie messen Sie derzeit den Technologieerfolg? <br/>Rollouts wie Skype for Business? | | |
> | Welchen Prozentsatz Ihrer Benutzerbasis würden Sie sagen? <br/>Skype for Business angenommen? | | |
> | Wie ist die Einstellung der Benutzer zu Skype for Business? | <input type="checkbox"> Gut <br/> <input type="checkbox"> Neutral <br/> <input type="checkbox"> Schlecht | |
> | Welche der folgenden Aussagen beschreibt das Rollout am besten <br/>Strategie, die für Ihre Skype for Business verwendet wird <br/>Einsatz? | <input type="checkbox"> Breite Reichweite: E-Mail-Kampagne mit <br/>&nbsp;&nbsp; &nbsp;Links zu Schulungen <br/> <input type="checkbox"> Erweitert: Breite Reichweite plus Vielfalt <br/>&nbsp;&nbsp; &nbsp;von Sensibilisierungskampagnen (Poster, <br/>&nbsp;&nbsp; &nbsp;Veranstaltungen, Champions) und Schulungen <br/>&nbsp;&nbsp; &nbsp;(Videos, Benutzerhandbücher, persönlich) <br/> <input type="checkbox"> Maßgeschneidert: Erweitert und gezielt <br/>&nbsp;&nbsp; &nbsp;Messaging und Schulungen nach Persona <br/> <input type="checkbox"> Andere <br/>&nbsp;&nbsp; &nbsp;(Beachten Sie die Details in der Spalte "Kommentare".) | |
