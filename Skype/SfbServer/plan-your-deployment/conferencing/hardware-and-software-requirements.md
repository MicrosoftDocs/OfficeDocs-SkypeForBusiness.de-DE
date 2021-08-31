---
title: Hardware- und Softwareanforderungen für Konferenzen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: 'Zusammenfassung: Lesen Sie dieses Thema, um mehr über die Hardware- und Softwareanforderungen für Konferenzen in Skype for Business Server zu erfahren.'
ms.openlocfilehash: bfc449abc2e01676a412fc0ead85eeae12aa2610
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733534"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>Hardware- und Softwareanforderungen für Konferenzen in Skype for Business Server

**Zusammenfassung:** Lesen Sie dieses Thema, um mehr über die Hardware- und Softwareanforderungen für Konferenzen in Skype for Business Server zu erfahren.

In diesem Abschnitt werden die Hardware- und Softwareanforderungen für Webkonferenzen, Audio- und Videokonferenzen (A/V), Einwahlkonferenzen und Chatkonferenzen beschrieben. Alle Konferenzfunktionen werden auf Front-End-Servern ausgeführt. Es gibt zusätzliche Anforderungen für verschiedene Konferenztypen, wie im folgenden Diagramm dargestellt.

Wenn Sie beispielsweise Einwahlkonferenzen zulassen möchten, müssen Sie einen Vermittlungsserver und ein Gateway für die Verbindung mit dem Telefonfestnetz (Public Switched Telephone Network, PSTN) bereitstellen. Wenn Sie Webkonferenzen zulassen möchten, müssen Sie sicherstellen, dass Skype for Business Server eine Verbindung mit einem Office Web Apps-Server herstellen können. Wenn Sie externen Benutzern die Teilnahme an Konferenzen gestatten möchten, müssen Sie einen Edgeserver bereitstellen.

**Konferenzfunktionen und -anforderungen**

![Konferenzkomponenten.](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 Weitere Informationen zu Topologieüberlegungen finden Sie unter [Planen der Konferenztopologie für Skype for Business Server.](conferencing-topology.md)

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>Hardware- und Softwareanforderungen für Front-End-Server

Da Webkonferenzen, A/V-Konferenzen, Einwahlkonferenzen und Chatkonferenzen alle mit dem Front-End-Server verbunden sind, sind die Hardware- und Softwareanforderungen des Servers die gleichen wie für die Front-End-Server. Ausführliche Informationen zu diesen Anforderungen finden Sie unter [server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and Environmental requirements for Skype for Business Server [2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).

## <a name="requirements-for-web-conferencing"></a>Anforderungen für Webkonferenzen

Wenn Sie sich für die Bereitstellung von Webkonferenzfunktionen entschieden haben, müssen Sie Folgendes planen:

- Zugriff auf den Dateispeicher, der zum Speichern von Webkonferenzinhalten verwendet wird.

- Integration in Office Web Apps-Server, was erforderlich ist, um PowerPoint Dateien während einer Konferenz freizugeben.

### <a name="file-store"></a>Dateispeicher

Der Skype for Business Server Webkonferenzdienst speichert Inhalte, die während Besprechungen freigegeben wurden, im Dateispeicher. Im Rahmen der Bereitstellung müssen Sie eine Dateifreigabe angeben, die als Dateispeicher für den Standard Edition Server oder Enterprise Edition Front-End-Pool verwendet werden soll. Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben. Weitere Informationen finden Sie unter [Erstellen einer Dateifreigabe in Skype for Business Server](../../deploy/install/create-a-file-share.md). Der Webkonferenzdienst verschlüsselt die Inhalte vor dem Speichern im Dateispeicher.

Skype for Business Server unterstützt die Verwendung von Dateifreigaben auf direct Attached Storage (DAS) oder einem Speicherbereichsnetzwerk (SAN), einschließlich dfs (Distributed File System) und auf einem redundanten Array unabhängiger Datenträger (RAID) für Dateispeicher. Nachdem der Skype for Business Server Bereitstellungs-Assistent den Speicherort der Dateifreigabe definiert hat, erstellt Skype for Business Server eine Ordnerstruktur innerhalb der Dateifreigabe, ähnlich wie:

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - DataConf

Der Webkonferenzdienst speichert dann Inhalte wie z. B. PowerPoint-Folien, Whiteboards, Umfragen und Anhänge in den Ordnern "CollabContent" und "CollabMetadata", die sich wiederum im Ordner "WebServices" befinden.

### <a name="office-web-apps-server"></a>Office Web Apps-Server

Um Webkonferenzfunktionen verwenden zu können, müssen Sie Office Web Apps-Server installieren und Skype for Business Server für die Kommunikation mit Office Web Apps Server konfigurieren.

Office Web Apps Server sollte auf einem eigenständigen Computer installiert werden, auf dem Skype for Business Server, SQL Server oder keine andere Serveranwendung ausgeführt wird. (Auf diesem Computer darf keine Version von Office installiert sein.) Auf jedem Computer, auf dem Office Web Apps-Server ausgeführt wird, muss auch eine bestimmte Softwaregruppe installiert sein (einschließlich .NET Framework 4.5 und Windows PowerShell 3.0). Diese Anforderungen sowie Informationen zum Konfigurieren von Zertifikaten und Internetinformationsdienste (IIS) werden auf der [Microsoft Office Web Apps-Bereitstellungswebsite](/webappsserver/deploy-the-infrastructure-office-web-apps-server)ausführlich erläutert.

Informationen zum Konfigurieren von Skype for Business Server für die Verwendung mit Office Web Apps Server finden Sie unter Konfigurieren der [Integration mit Office Web Apps Server in Skype for Business Server.](../../deploy/deploy-conferencing/office-web-app-server.md)

## <a name="requirements-for-audio-and-video-conferencing"></a>Anforderungen für Audio- und Videokonferenzen

Zum Planen von A/V-Konferenzen müssen Sie die erforderliche Netzwerkbandbreite für den Typ der Konferenzmedien kennen, die in Ihrer Organisation verwendet werden. Dies kann Audio-, Video- und Panoramavideos umfassen. Ohne ausreichende Netzwerkbandbreite kann die Benutzererfahrung stark beeinträchtigt werden.

Informationen zur Planung der Audio- und Videokapazität für Konferenzen finden Sie unter Planen der [Netzwerkanforderungen für Skype for Business.](../../plan-your-deployment/network-requirements/network-requirements.md)

Sie können die Anrufsteuerung (Call Admission Control, CAC) verwenden, um die von A/V-Konferenzen verwendete Netzwerkbandbreite zu verwalten. Dies ist wichtig für eingeschränkte Netzwerke, z. B. Verbindungen mit begrenzter Bandbreite zwischen zentralen standorten und Zweigstellen. Ausführliche Informationen finden Sie unter [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).

Wenn Sie Audiokonferenzen in Ihrem Netzwerk bereitstellen, benötigen Ihre Benutzer Audiogeräte wie Headsets, um an einer Audiokonferenz teilzunehmen. Wenn Sie Videokonferenzen bereitstellen, müssen Sie Videogeräte wie Webcams für Benutzer bereitstellen. Für Audio- und Videogeräte sind gerätebereitstellung und Benutzerschulungen wichtige Schritte, die Sie berücksichtigen sollten. Weitere Informationen finden Sie unter [Planen von Clients und Geräten.](../../plan-your-deployment/clients-and-devices/clients-and-devices.md) Microsoft empfiehlt die Verwendung von Unified Communications (UC)-Geräten, die von Microsoft für alle Gerätetypen zertifiziert sind, um eine optimale Benutzererfahrung sicherzustellen. Ausführliche Informationen zu UC-zertifizierten Geräten finden Sie unter [Telefone und Geräte für Skype for Business](../../../SfbPartnerCertification/certification/devices-ip-phones.md).

## <a name="requirements-for-dial-in-conferencing"></a>Anforderungen für Einwahlkonferenzen

Einwahlkonferenzen sind ein optionales Feature der Skype for Business Server Konferenzarbeitsauslastung, die eine Vielzahl von Komponenten umfasst. Einige der Komponenten sind spezifisch für Einwahlkonferenzen, andere Enterprise-VoIP Komponenten. In diesem Abschnitt werden die Anforderungen für die Komponenten beschrieben, die für Einwahlkonferenzen erforderlich sind. Ausführliche Informationen zu den Anforderungen des Vermittlungsservers und des PSTN-Gateways finden Sie unter ["Vermittlungsserverkomponente" in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) und [Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype for Business Server.](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)

### <a name="required-components"></a>Erforderliche Komponenten

Sie müssen die folgenden Skype for Business Server Komponenten installieren, bevor Sie Einwahlkonferenzen konfigurieren können:

- Unified Communications-Anwendungsdienst (auch nur Anwendungsdienst genannt)

- Konferenzzentrale

- Konferenzankündigungsanwendung

- Webseite mit Einstellungen für Einwahlkonferenzen

- Mindestens ein Vermittlungsserver und mindestens ein PSTN-Gateway

Für Einwahlkonferenzen, Anwendungsdienst, Konferenzzentralenanwendung und Konferenzankündigungsanwendung die gleichen Betriebssystemanforderungen wie Front-End-Server haben. Ausführliche Informationen finden Sie unter [server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

Konferenzzentralenanwendung und Konferenzankündigungsanwendung erfordern, dass Windows Media Format Runtime auf Front-End-Servern installiert ist. Windows Die Medienformatlaufzeit ist erforderlich, um Windows WMA-Dateien (Media Audio) wiederzugeben, die für Wartemusik, aufgezeichnete Namen und Eingabeaufforderungen verwendet werden. Wenn Sie auf Windows Server 2012 oder Windows Server 2012 R2 installieren (was wir empfehlen), müssen Sie Microsoft Media Foundation installieren, um Windows Media Format Runtime zu erhalten. Wenn Sie vor Windows 2012 auf einer beliebigen Version von Windows Server installieren, müssen Sie sicherstellen, dass die Windows Desktopdarstellung installiert ist, um Windows Media Format Runtime abzurufen.

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>Audiodateianforderungen für Einwahlkonferenzen

Skype for Business Server unterstützt keine Anpassung von Sprachansagen und Musik für Einwahlkonferenzen. Wenn Sie jedoch eine starke geschäftliche Notwendigkeit haben, die erfordert, dass Sie die Standardaudiodateien ändern müssen, lesen Sie den Microsoft Knowledge Base-Artikel 961177, wie Sie [Sprachansagen oder Musikdateien für Einwahlaudiokonferenzen anpassen.](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177)

Sie können auch das [Verwaltungsprogramm "Microsoft Lync Server Konferenzzentrale Custom Voice Prompts"](https://go.microsoft.com/fwlink/p/?LinkId=396880) verwenden, mit dem Administratoren die Standard-Sprachansagen ersetzen können, die verwendet werden, wenn ein Telefonanrufer an einer Skype for Business Besprechung teilnimmt, durch benutzerdefinierte Eingabeaufforderungen, um eine andere Besprechungseintragsoberfläche bereitzustellen. Die benutzerdefinierten Sprachansagen können auf einem Enterprise oder Standard Edition Server installiert werden.

für Konferenzzentralenanwendung und Konferenzankündigungsanwendung gelten die folgenden Anforderungen für Wartemusik, aufgezeichnete Namen und Audioansagendateien:

- WMA-Dateiformat (Windows Media Audio)

- 16-Bit mono

- Konstante Bitrate (Constant Bit Rate), 48 KBit/s, 2 Durchläufe

- Sprachpegel: -24 DB

### <a name="user-requirements-for-dial-in-conferencing"></a>Benutzeranforderungen für Einwahlkonferenzen

Dem Konto eines Einwahlkonferenzbenutzers muss eine eindeutige Rufnummer oder Durchwahl zugewiesen sein. Diese Anforderung unterstützt die Authentifizierung während der Einwahlkonferenz. Enterprise Benutzer (d. h. Benutzer mit Active Directory Domain Services-Anmeldeinformationen und Skype for Business Server Konten innerhalb Ihrer Organisation) geben ihre Telefonnummer (oder Erweiterung) und eine persönliche Identifikationsnummer (PIN) ein, um sich als authentifizierter Benutzer bei Konferenzen einwählen.

## <a name="port-requirements-for-conferencing"></a>Portanforderungen für Konferenzen

Um die Konferenzfunktionen verwenden zu können, müssen Skype for Business Server bestimmte Ports öffnen. In der folgenden Tabelle sind die Portanforderungen für Konferenzen aufgeführt. Ausführliche Informationen zu allen Portanforderungen finden Sie unter [Port- und Protokollanforderungen für Server.](../../plan-your-deployment/network-requirements/ports-and-protocols.md)

**Erforderliche Serverports**


|**Serverrolle**|**Dienstname**|**Port**|**Protocol**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|
|Front-End-Server  <br/> |Skype for Business Server Chatkonferenzdienst  <br/> |5062  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für Chatkonferenzen verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server Webkonferenzdienst  <br/> |8057  <br/> |TCP (TLS)  <br/> |Wird zum Überwachen von PSOM-Verbindungen (Persistent Shared Object Model) vom Client verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server Webkonferenzkompatibilitätsdienst  <br/> |8058  <br/> |TCP (TLS)  <br/> |Wird zum Überwachen von PSOM-Verbindungen (Persistent Shared Object Model) vom Live Meeting-Client und früheren Versionen von Skype for Business Server verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server Audio-/Videokonferenzdienst  <br/> |5063  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für Audio-/Videokonferenzen (A/V) verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server Audio-/Videokonferenzdienst  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Für Videokonferenzen verwendeter Medienportbereich.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server Konferenzzentrale Dienst (Einwahlkonferenzen)  <br/> |5064  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für Einwahlkonferenzen verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server Konferenzzentrale Dienst (Einwahlkonferenzen)  <br/> |5072  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für die Telefonzentrale (Einwahlkonferenzen) verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server Anwendungsfreigabedienst  <br/> |5065  <br/> |TCP  <br/> |Wird für eingehende SIP-Überwachungsanforderungen für die Anwendungsfreigabe verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server Anwendungsfreigabedienst  <br/> |49152-65535  <br/> |TCP  <br/> |Für die Anwendungsfreigabe verwendeter Medienportbereich.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server Konferenzankündigung Dienst  <br/> |5073  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für den Skype for Business Server Konferenzankündigung Dienst (d. b. für Einwahlkonferenzen) verwendet.  <br/> |
|Alle internen Server  <br/> |Verschiedene  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |Für Audiokonferenzen auf allen internen Servern verwendeter Medienportbereich. Wird von allen Servern verwendet, die Audio beenden: Front-End-Server (für Skype for Business Server Konferenzzentrale-Dienst, Skype for Business Server Konferenzankündigung-Dienst und Skype for Business Server Audio-/Videokonferenzdienst) und Vermittlungsserver.  <br/> |
|Office Web Apps-Server  <br/> ||443  <br/> ||Wird von Skype for Business Server zum Herstellen einer Verbindung mit Office Web Apps-Server verwendet.  <br/> |

**Erforderliche Clientports**


|**Port**|**Protocol**|**Hinweise**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |Wird für den Zugriff externer Benutzer auf Webkonferenzsitzungen verwendet.  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |Wird für den Zugriff externer Benutzer auf A/V-Sitzungen und -Medien (TCP) verwendet.  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |Wird für den Zugriff externer Benutzer auf A/V-Sitzungen und Medien (UDP) verwendet.  <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |Audioportbereich (mindestens 20 Ports erforderlich)  <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |Videoportbereich (mindestens 20 Ports erforderlich).  <br/> |
|1024-65535 \*  <br/> |TCP  <br/> |Anwendungsfreigabe.  <br/> |