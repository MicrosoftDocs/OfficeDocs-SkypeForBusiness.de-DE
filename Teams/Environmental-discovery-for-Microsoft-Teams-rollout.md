---
title: Umweltkompatibilität – Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: Hier erfahren Sie, wie Sie eine detaillierte Umweltermittlung durchführen, während Sie Ihre Reise von Skype for Business Microsoft Teams.
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
ms.openlocfilehash: fdaafeb9042f8b76b40c797109740af5c93ef077
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635049"
---
# <a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Umgebungsermittlung für Microsoft Teams Einführung

Entdecken ist einer der ersten wichtigen Schritte, die Sie bei der Planung Ihrer Reise zu Microsoft Teams.

Sie führen eine ausführliche Ermittlung Ihrer Umgebung durch, um deren aktuellen Status besser zu verstehen und um etwaige Schwierigkeiten oder – noch weiter – mögliche Blocker bei der Durchführung Ihres Rollouts Ihres Teams auf dem Teams können.

## <a name="discovery-questionnaire"></a>Discovery-Fragebogen

Der folgende Beispiel-Fragebogen führt Sie durch eine Reihe von Fragen, um zu bestätigen, dass Ihre Organisation für den erfolgreichen Rollout von Audiokonferenzen und Telefonsystem mit Anrufplanfunktionen in Teams.

Alle Fragen im Zusammenhang mit Ihrer vorhandenen Zusammenarbeitsinfrastruktur und Microsoft 365- oder Office 365-Organisation, Netzwerken, Endpunkten, Vorgängen sowie Akzeptanz und Bereitschaft sind teil des Fragebogens zur Umweltermittlung.

Der Fragebogen ist in mehrere Abschnitte unterteilt, um die Bereitschaft Ihrer Organisation für Ihre Teams Bereitstellung in mehreren Hauptbereichen zu bestätigen. Arbeiten Sie mit Ihrem Projektteam zusammen, um die angeforderten Informationen mit so viel Details wie möglich zur Verfügung zu stellen, um Ihre Planungsaktivitäten zu vereinfachen.

> [!TIP]
> Sie können beginnen, indem Sie den Fragebogen in ein Dokument Microsoft Word kopieren. Versuchen Sie, alle Fragen zu beantworten und alle Details zu erfassen, während Sie durch die Daten gehen.

### <a name="project-team"></a>Project-Team

Erfassen Sie detaillierte Informationen zu den wichtigsten Projektbeteiligten Ihres Teams Rolloutprojekts. Beachten Sie, dass eine Person im gesamten Projekt mehrere Rollen spielen kann.

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

## <a name="microsoft-365-or-office-365-organization-details"></a>Microsoft 365 oder Office 365 Organisationsdetails

Wir empfehlen dringend, während des Ausfüllens dieses Fragebogens über Microsoft 365 oder Office 365 Organisation zu verfügen. Wenn Sie eine Organisation für Microsoft 365 oder Office 365 noch nicht aktiviert oder konfiguriert haben, lesen Sie Planen Des Setups von [Microsoft 365 Business.](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)

Verwenden Sie die folgende Tabelle, um Informationen über die Organisation Microsoft 365 oder Office 365 erfassen.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Beachten Sie die Microsoft 365<br/>oder Office 365 und ID der Organisation<br/>in der Spalte Antwort aus. Wenn Sie mehr<br/>mehr als ein Mandant zugeordnet ist<br/>Ihrer Organisation alle IDs an. | Tenant Name: <br/>Mandanten-ID:| |
> | In welchen Regionen werden die Mandanten bereitgestellt?| | |
> | Notieren Sie sich den Typ dieser Microsoft 365 oder <br/>Office 365 Mandanten. Sind sie multitenant? <br/>oder De dedicated? | <input type="checkbox"> Multitenant<br/> <input type="checkbox"> De dedicated | |
> | Welche Microsoft Online-Produkte werden zurzeit verwendet? <br/>Beachten Sie die Anzahl der aktivierten Benutzer für jedes <br/>in der Spalte Kommentare. | <input type="checkbox">Microsoft Teams <br/> <input type="checkbox">Skype for Business <br/>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive for Business <br/> <input type="checkbox">Yammer <br/> <input type="checkbox"> Sonstiges| |
> | Für welche Lizenzebene ist die Skype aktiviert? <br/>Business Online-Benutzer? | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 | Die Anzahl der Benutzer <br/>für jede SKU: |
> | Was ist die aktuelle Active Directory-Gesamtstruktur? <br/>Funktionsebene in der Umgebung? <br/>Wenn es mehrere Gesamtstrukturen gibt, beachten Sie die Details. <br/>in der Spalte Kommentare. | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | Was verwenden Sie für das Verzeichnis? <br/>Synchronisierung heute? |<input type="checkbox"> Keine Synchronisierung (nur Cloud) <br/> <input type="checkbox">Azure Active Directory <br/>&nbsp;&nbsp; &nbsp; Verbinden <br/> <input type="checkbox"> Sonstiges (Geben Sie im <br/>&nbsp;&nbsp; &nbsp; Spalte Kommentare.)| |
> | Ist zurzeit eine Partneridentität bereitgestellt? <br/>(Active Directory-Verbunddienste oder <br/>Drittanbieter) | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Wenn Sie Verbundidentität verwenden, was ist die <br/>Verbundinfrastruktur? | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox"> Drittanbieterverbund <br/>&nbsp;&nbsp; &nbsp; Gateway (Details anzeigen) <br/>&nbsp;&nbsp; &nbsp; in der Spalte Kommentare.) | |
> | Wenn aktuell ein aktives Microsoft 365<br/>oder Office 365-Mandant ist die SMTP/SIP-Domäne von <br/>die dem Mandanten zugeordneten Zielbenutzer? | <input type="checkbox">N/A – Keine Microsoft 365 oder<br/>&nbsp;&nbsp; &nbsp; Office 365-Mandant an Ort und Stelle <br/> <input type="checkbox"> Nein, SMTP/SIP der Benutzer <br/>&nbsp;&nbsp; &nbsp; Domäne ist nicht zugeordnet <br/>&nbsp;&nbsp; &nbsp; mit beliebigen Mandanten in <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 oder Office 365<br/> <input type="checkbox"> Ja, SMTP/SIP der Benutzer <br/>&nbsp;&nbsp; &nbsp; Domäne zugeordnet ist <br/>&nbsp;&nbsp; &nbsp; mit einem vorhandenen Mandanten in <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 oder Office 365 | |
> | Entsprechen Benutzer-UPNs ihrer primären SMTP-Adresse? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein <br/> <input type="checkbox"> Inkonsistent | |

## <a name="existing-collaboration-platform-summary"></a>Vorhandene Zusammenfassung der Zusammenarbeitsplattform

Verwenden Sie die folgende Tabelle, um Informationen zu Ihrer vorhandenen Plattform für die Zusammenarbeit zu erfassen.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Ist Microsoft Teams bereitgestellt? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Ist Skype for Business bereitgestellt? <br/>Stellen Sie bei lokalen und Hybridbereitstellungen sicher, dass <br/>beachten Sie die Version und das kumulative Update (CU) <br/>details in the Comments column. | <input type="checkbox">Ja, Microsoft 365 oder <br/>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox"> Ja, Hybrid (mit <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 oder <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Ja, lokal <br/> <input type="checkbox"> Ja, online, de dedicated <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Ja, gehostet, de dedicated <br/>&nbsp;&nbsp; &nbsp; (Drittanbieter) <br/> <input type="checkbox"> Ja, gehostet, geteilt <br/>&nbsp;&nbsp; &nbsp; (Drittanbieter) <br/> <input type="checkbox"> Nein, andere | |
> | Ist Exchange bereitgestellt? <br/>Stellen Sie bei lokalen und Hybridbereitstellungen sicher, dass <br/>die Versions- und CU-Details in den Kommentaren <br/>aus. | <input type="checkbox">Ja, Microsoft 365 <br/> <input type="checkbox"> Ja, Hybrid (mit <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 oder <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Ja, lokal <br/> <input type="checkbox"> Ja, online, de dedicated <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Ja, gehostet, de dedicated <br/>&nbsp;&nbsp; &nbsp; (Drittanbieter) <br/> <input type="checkbox"> Ja, gehostet, geteilt <br/>&nbsp;&nbsp; &nbsp; (Drittanbieter) <br/> <input type="checkbox"> Nein, andere | |
> | Ist SharePoint bereitgestellt? <br/>Stellen Sie bei lokalen und Hybridbereitstellungen sicher, dass <br/>die Versions- und CU-Details in den Kommentaren <br/>aus. | <input type="checkbox">Ja, Microsoft 365 <br/> <input type="checkbox"> Ja, Hybrid (mit <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 oder <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Ja, lokal <br/> <input type="checkbox"> Ja, online, de dedicated <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Ja, gehostet, de dedicated <br/>&nbsp;&nbsp; &nbsp; (Drittanbieter) <br/> <input type="checkbox"> Ja, gehostet, geteilt <br/>&nbsp;&nbsp; &nbsp; (Drittanbieter) <br/> <input type="checkbox"> Nein, andere | |
> | Ist OneDrive for Business bereitgestellt? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Haben Sie andere Plattformen von Drittanbietern bereitgestellt? <br/>und heute noch in Verwendung? Beachten Sie in diesem Falls die Anzahl der Benutzer von <br/>und die Nutzungsdetails im <br/>Spalte Kommentare. | <input type="checkbox"> Cisco WebEx <br/> <input type="checkbox"> Pufferzeit <br/> <input type="checkbox"> Sonstiges (Geben Sie im <br/>&nbsp;&nbsp; &nbsp; Spalte Kommentare.) | Anzahl der Benutzer: <br/>Details:|
> | Planen Sie, Benutzer von diesen Drittanbietern zu verschieben? <br/>plattformen zu Teams? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Was ist die aktuelle Telefonie- und Konferenzlösung? <br/>der Benutzer, die im Rahmen dieser Initiative liegen? | | |
> | Verfügen Sie über [SBC,die Direct Routing](./direct-routing-plan.md#supported-session-border-controllers-sbcs) unterstützen? <br/>für Ihre Büros, die im Rahmen dieser Initiative liegen? Wenn Ja,<br/>beachten Sie die Details in der Spalte Kommentare.| <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein ||

## <a name="collaboration-platform-deployment-details"></a>Details zur Bereitstellung der Zusammenarbeitsplattform

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (falls zutreffend)

Erfassen Sie ggf. die Details Ihrer Teams mithilfe der folgenden Beispieltabelle. Wenn Sie noch keine Bereitstellungs-Teams, überspringen Sie diesen Abschnitt.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Welche Benutzertypen sind für Microsoft Teams aktiviert? | <input type="checkbox"> Alle Benutzer in der Organisation <br/> <input type="checkbox"> Bestimmte Benutzer/Benutzergruppen <br/>&nbsp;&nbsp; &nbsp; (Geben Sie in der Spalte Kommentare an.) ||
> | Welche Teams und Modalitäten werden verwendet? | <input type="checkbox"> Kanalbasierte Unterhaltungen <br/> <input type="checkbox"> Privater Chat <br/> <input type="checkbox"> Gastzugriff <br/> <input type="checkbox"> Kanalbesprechungen <br/> <input type="checkbox"> Private Besprechungen <br/> <input type="checkbox"> Private Anrufe <br/> <input type="checkbox"> Ad-hoc-Kanal-Meetup <br/> <input type="checkbox"> Videos in Besprechungen <br/> <input type="checkbox"> Bildschirmfreigabe in Besprechungen <br/> <input type="checkbox"> Audiokonferenzen <br/><input type="checkbox"> Anwendungen (Apps)<br/> &nbsp;&nbsp; &nbsp;<input type="checkbox"> Registerkarten<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Bots <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Verbinder<br/><input type="checkbox"> Integration von benutzerdefiniertem Cloudspeicher <br/>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google <br/>&nbsp;&nbsp; &nbsp; Drive, Egnyte <br/> <input type="checkbox"> Kanal-E-Mail-Integration <br/> <input type="checkbox"> Sonstige (Geben Sie in der Spalte Kommentare an.) | |
> | Welche Anwendungen haben Sie auf ihrer Teams? | | |
> | Haben Sie Funktionen von Microsoft Teams ausdrücklich gesperrt? <br/>Wenn Ja, notieren Sie sich die Details in der Spalte Kommentare. | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein ||
> | Welche Microsoft Teams-Clients werden verwendet? | <input type="checkbox"> Web <br/> <input type="checkbox">Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> Linux <br/>  <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox">Windows Mobil | |
> | Wer verfügt über Berechtigungen zum Erstellen von Teams? | <input type="checkbox"> Jeder in der Organisation <br/>&nbsp;&nbsp; &nbsp; (Dies ist die Standardeinstellung.) <br/> <input type="checkbox"> Bestimmte Personen <br/>&nbsp;&nbsp; &nbsp; (Geben Sie in der Spalte Kommentare an.) | |
> | Verwenden Sie Sicherheits- und Compliance-Funktionen in Microsoft Teams? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online (falls zutreffend)

Erfassen Sie ggf. die Details Ihrer online Skype for Business, indem Sie die nachstehende Beispieltabelle verwenden. Wenn Sie die Onlinebereitstellung noch Skype for Business haben, überspringen Sie diesen Abschnitt.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Welche Arten von Benutzern sind für die Skype <br/>for Business Online? | <input type="checkbox"> Alle Benutzer in der Organisation <br/> <input type="checkbox"> Bestimmte Benutzer/Benutzergruppen <br/>&nbsp;&nbsp; &nbsp; (Geben Sie in der Spalte Kommentare an.) | |
> | Welche Modalitäten und Features sind derzeit <br/>wird heute verwendet? | <input type="checkbox"> Chatnachrichten und Anwesenheit (Chat/P)<br/> <input type="checkbox"> Konferenzen <br/> <input type="checkbox"> Verbund <br/> <input type="checkbox"> Besprechungsaufzeichnung <br/> <input type="checkbox"> Microsoft Audio Conferencing <br/> <input type="checkbox"> Drittanbieter-Audiokonferenzen (Hinweis<br/>&nbsp;&nbsp; &nbsp; die Details in der Spalte Kommentare.) <br/> <input type="checkbox"> Anrufpläne (früher PSTN-Anrufe) <br/> <input type="checkbox"> Automatische Organisations-Attendants <br/> <input type="checkbox"> Anrufwarteschleifen | |
> | Haben Sie speziell alle E-Skype für <br/>Business Online-Funktionen? <br/>Wenn Ja, notieren Sie sich die Details in der Spalte Kommentare. | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Welche Methode verwenden Sie, oder planen Sie für <br/>verbinden Telefonsystem (früher Cloud PBX) mit <br/>PSTN? <br/>Wählen Sie alle anzuwendende Option aus. | <input type="checkbox"> Anrufpläne (früher PSTN-Anrufe) <br/> <input type="checkbox"> Lokale PSTN-Anbindung <br/>&nbsp;&nbsp; &nbsp; (nutzen Sie vorhandene Skype für <br/>&nbsp;&nbsp; &nbsp; Business 2015 oder Lync Server <br/>&nbsp;&nbsp; &nbsp; 2013-Bereitstellung) <br/> <input type="checkbox"> Lokale PSTN-Anbindung <br/>&nbsp;&nbsp; &nbsp; (mit Cloud Connector) | |
> | Haben Sie Telefonnummern zu Microsoft portiert? <br/>Dies gilt für Anrufpläne und Audio <br/>Konferenzfeatures. | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype for Business lokal (falls zutreffend)

Erfassen Sie ggf. die Details Ihrer Skype for Business, indem Sie die folgende Beispieltabelle verwenden. Wenn Sie die Bereitstellung nicht lokal Skype for Business, überspringen Sie diesen Abschnitt.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Welche Versionen von Lync oder Skype for Business <br/> sind derzeit lokal bereitgestellt? | <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019 <br/><input type="checkbox">Skype for Business Cloud Connector <br/>&nbsp;&nbsp; &nbsp; Edition | |
> | Ist eine hybride Bereitstellung mit Skype for Business Online konfiguriert? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Wird diese Umgebung von einem dritten gehostet und verwaltet? <br/>Party? Falls ja, notieren Sie sich die Details im <br/>Spalte Kommentare. | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Welche Modalitäten und Features werden derzeit verwendet? <br/>heute? | <input type="checkbox"> Chatnachrichten und Anwesenheit (Chat/P) <br/> <input type="checkbox"> Konferenzen <br/> <input type="checkbox"> Verbund <br/> <input type="checkbox"> Besprechungsaufzeichnung <br/> <input type="checkbox"> Beständiger Chat/Gruppenchat <br/> <input type="checkbox"> Microsoft Audio Conferencing <br/>&nbsp;&nbsp; &nbsp; (ehemals Dial in Conferencing, Einwahlkonferenzen) auf Ihrer <br/>&nbsp;&nbsp; &nbsp; lokalen Lync Server oder <br/>&nbsp;&nbsp; &nbsp; Skype for Business-Bereitstellung <br/> <input type="checkbox"> Drittanbieter für Audiokonferenzen <br/>&nbsp;&nbsp; &nbsp; (Details finden Sie in den Kommentaren <br/>&nbsp;&nbsp; &nbsp; Spalte.) <br/> <input type="checkbox">Enterprise-VoIP mit der lokalen <br/>&nbsp; &nbsp; &nbsp;PSTN-Konnektivität <br/> <input type="checkbox"> Anrufpläne (früher PSTN-Anrufe) über <br/>&nbsp;&nbsp; &nbsp; Hybrid mit Skype for Business Online | |
> | Welche Edgeserverversionen sind bereitgestellt? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019| |
> | Haben Sie Lync oder Skype for Business Edge? <br/>in mehreren Rechenzentren bereitgestellt? <br/>Wenn Ja, notieren Sie sich die Details in der Spalte Kommentare. | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Wählen Sie Dienste aus, die Ihre Edge-Rolle heute bietet. | <input type="checkbox"> Externer Benutzerzugriff (Unternehmensbenutzer) <br/> <input type="checkbox"> Remotebenutzerzugriff (anonym) <br/>&nbsp;&nbsp; &nbsp; externe Besprechungsteilnehmer) <br/> <input type="checkbox"> Verbund <br/> <input type="checkbox"> Media Relay | |
> | Welche der folgenden Sprachanruffunktionen haben Sie? <br/>bestehen derzeit Abhängigkeiten? <br/>Beachten Sie alle zusätzlichen Abhängigkeiten im Kommentar <br/>aus. | <input type="checkbox"> Beschäftigt-Optionen <br/> <input type="checkbox"> Parken von Anrufen <br/> <input type="checkbox"> Abholen von Anrufen oder Gruppenanrufen <br/> <input type="checkbox"> Telefone in der Nähe oder "Hot-King" <br/> <input type="checkbox"> Reaktionsgruppen oder Sammelsuchegruppen <br/> <input type="checkbox"> Darstellung einer freigegebenen Linie <br/> <input type="checkbox"> Privatleitung <br/> <input type="checkbox"> Voicemail <br/> <input type="checkbox"> Anrufen über die Arbeit <br/> <input type="checkbox"> Notfall- oder Informationsnummern <br/>&nbsp;&nbsp; &nbsp; (911, 811, 411) <br/> <input type="checkbox"> Durchwahlwahl <br/> <input type="checkbox"> automatische Telefonzentrale <br/> <input type="checkbox"> Abonnentenzugriff <br/> <input type="checkbox"> Analoge Geräte <br/> <input type="checkbox"> Fax <br/> <input type="checkbox"> Maskieren oder Ändern der Anrufer-ID <br/> <input type="checkbox"> Standortbasiertes Routing <br/> <input type="checkbox"> Kostengünstiges Routing <br/> <input type="checkbox"> Fahrstuhltelefone | |

## <a name="networking-and-access-to-microsoft-365-and-office-365-services"></a>Netzwerk und Zugriff auf Microsoft 365 und Office 365 Dienste

Verwenden Sie die folgende Tabelle, um die Netzwerkdetails Ihrer Organisation sowie die Art und Weise zu erfassen, wie Ihre Benutzer mit Microsoft 365 und Office 365 verbunden sind.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Wie (oder wie) werden die Benutzer im Gültigkeitsbereich der Migration <br/>Auf Teams, wenn sie im Büro sind? <br/>Wählen Sie alle anzuwendende Option aus. | <input type="checkbox"> Routed NAT connection <br/> <input type="checkbox"> Proxyserver <br/> <input type="checkbox"> Öffentliche Wi-Fi <br/> <input type="checkbox"> Verwaltete (nicht öffentliche) Wi-Fi <br/> <input type="checkbox"> ExpressRoute <br/>&nbsp;&nbsp; &nbsp; (Microsoft-Peering) ||
> | Wenn der Zugriff auf Microsoft 365-Office 365 über eine<br/>Proxyserver gibt es eine Möglichkeit, den Proxy zu umgehen? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Wird ExpressRoute zurzeit genutzt? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein <br/> <input type="checkbox"> Nein, aber es wird geplant | |
> | Haben Sie eine Netzwerkbereitschaftsbewertung durchgeführt? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Müssen Benutzer beim Herstellen einer Verbindung ein VPN verwenden? <br/>Unternehmensressourcen remote? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Wenn ein VPN verwendet wird, kann Teams-Datenverkehr von <br/>VPN für den direkten Zugriff Microsoft 365 und Office 365 Dienste? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Unterstützt Ihr Netzwerk QoS? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Können Sie den Audio- Teams- und Videodatenverkehr priorisieren? <br/>um ein qualitativ hochwertiges Erlebnis zu ermöglichen? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Alle Standorte innerhalb einer Region verfügen über einen Internetanschluss, <br/>oder ist der Internet-Ausgangsbereich für die gesamte Region zentralisiert? | <input type="checkbox"> Regionaler Zugriff auf das Internet <br/> <input type="checkbox"> Zentralisierter Zugriff auf die <br/>&nbsp;&nbsp; &nbsp; Internet | |

## <a name="endpoints"></a>Endpunkte

Verwenden Sie die folgende Tabelle, um die Details der verwendeten Clients und Endpunkte zu erfassen.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Welches Desktopbetriebssystem verwenden die Benutzer? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox"> Mac (Geben Sie die Version in der Spalte Kommentare an.) <br/> <input type="checkbox"> Linux (Geben Sie die Verteilung in der Spalte Kommentare an.) <br/><input type="checkbox"> Sonstige (Beachten Sie die Details in der Spalte Kommentare.) | |
> | Welche Version des Microsoft Office bereitgestellt wird <br/>auf diese Geräte zugreifen? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office für Mac 2011 <br/> <input type="checkbox">Office für Mac 2016 <br/> <input type="checkbox"> Sonstige (Beachten Sie die Details in der Spalte Kommentare.) | |
> | Welche Office verwendet wird <br/>in Ihrer Organisation? | <input type="checkbox"> MSI <br/> <input type="checkbox"> Klick-und-Ausführen | |
> | Welche mobilen Geräte sind zulässig und unterstützt? <br/>verwendet werden? <br/>Wählen Sie alle anzuwendende Option aus. | <input type="checkbox">Windows <br/> <input type="checkbox"> Mobil <br/> <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Sonstige (Beachten Sie die Details in der Spalte Kommentare.) | |
> | Wie werden mobile Geräte bereitgestellt? <br/>Wählen Sie alle anzuwendende Option aus. | <input type="checkbox"> Unternehmensgeräte <br/> <input type="checkbox"> Mit ihrem eigenen Gerät | |
> | Auf welche Geräte greifen Benutzer derzeit zu? <br/>Sprach- und Konferenzdienste <br/>(Handsets, Headsets, Smartphones, Video)? | | |

## <a name="operations"></a>Vorgänge

Verwenden Sie die folgende Tabelle, um die Details der betriebsbereiten Aspekte Ihrer Umgebung zu erfassen.

> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Wie sieht Ihr Betriebsmodell für Lync Server aus, <br/>Skype for Business Server, Microsoft 365 Bereitstellung, <br/>oder Office 365 noch heute bereitstellung? | | |
> | Gliederung der aktuellen Supportanordnung für <br/>Lync Server, Skype for Business Server, Microsoft 365, <br/>oder Office 365? | | |
> | Wenn Sie Ihre Bereitstellung in mehreren Ländern oder Regionen <br/>verfügt jedes Land/jede Region über eine eigene IT/Telefonie <br/>mitarbeiter für die Zusammenarbeit, oder wird dies zentral verwaltet? | <input type="checkbox"> Regionale Vorgänge und Support <br/> <input type="checkbox"> Zentrale Vorgänge und Unterstützung | |
> | Wenden Sie die Methodik für Anrufqualität an? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein | |
> | Haben Sie eine Person oder ein Team der <br/>Rolle "Quality Champion" für die Zusammenarbeitsplattform <br/>wird verwendet? | <input type="checkbox"> Ja <br/> <input type="checkbox"> Nein ||
> | Wie überwachen Sie Ihren Lync-Server, Skype für <br/>Business Server, Microsoft 365 Bereitstellung oder <br/>Office 365 Bereitstellung? | | |
> | Treten Probleme mit der Anrufqualität auf? | <input type="checkbox"> Ja<br/> <input type="checkbox"> Nein | |
> | Wie und wann bieten Sie Schulungen für Ihre <br/>Helpdesk zu neuen Diensten und Funktionen? | | |

## <a name="adoption-and-readiness"></a>Verbreitung und Bereitschaft

Erfassen Sie mithilfe der folgenden Tabelle den aktuellen Status der Einführung und Bereitschaft in Ihrer Organisation.

>
> | Frage | Antwort | Kommentare |
> |---|---|---|
> | Wie wird Ihre aktuelle aktive Nutzung von <br/>Skype for Business? | **__** % Gesamtzahl aktiver Benutzer im Vergleich zu aktivierten Benutzern | |
> | Wie verwendet Ihre Organisation <br/>Skype for Business? | Einzelunterhaltungen <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Imit <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Anrufe <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Freigabe<br/> Besprechungen <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Konferenzen<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Freigabe<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Anrufe | |
> | Verfügt Ihre Organisation über eine Benutzeradzeptanz? <br/>und Managementteam ändern? | <input type="checkbox"> Ja<br/> <input type="checkbox"> Nein | |
> | Wie messen Sie derzeit den Erfolg für Technologie? <br/>Rollouts wie Skype for Business? | | |
> | Welchen Prozentsatz Ihrer Benutzerbasis würden Sie sagen, hat <br/>übernommen Skype for Business? | | |
> | Wie ist die Einstellung der Benutzer zu Skype for Business? | <input type="checkbox"> Gut <br/> <input type="checkbox"> Neutral <br/> <input type="checkbox"> Schlecht | |
> | Welche der folgenden Informationen beschreibt am besten das Rollout <br/>strategie für Ihre Skype for Business <br/>Bereitstellung? | <input type="checkbox"> Umfassende Reichweite: E-Mail-Kampagne mit <br/>&nbsp;&nbsp; &nbsp; Links zu Schulungen <br/> <input type="checkbox"> Erweitert: Breite Reichweite und vielfältiges Angebot <br/>&nbsp;&nbsp; &nbsp; von Bewusstseinskampagnen (Postern, <br/>&nbsp;&nbsp; &nbsp; Events, Champions) und Schulungen <br/>&nbsp;&nbsp; &nbsp; (Videos, Benutzerhandbücher, persönlich) <br/> <input type="checkbox"> Tailored: Expanded, plus targeted <br/>&nbsp;&nbsp; &nbsp; Messaging und Schulung nach Persona <br/> <input type="checkbox"> Sonstiges <br/>&nbsp;&nbsp; &nbsp; (Beachten Sie die Details in der Spalte Kommentare.) | |
