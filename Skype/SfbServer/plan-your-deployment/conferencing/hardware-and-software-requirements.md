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
localization_priority: Normal
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: 'Zusammenfassung: In diesem Thema erfahren Sie mehr über die Hardware- und Softwareanforderungen für Konferenzen in Skype for Business Server.'
ms.openlocfilehash: 59ad84cd0f4445709b236baecafeeab240e6ea65
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814015"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>Hardware- und Softwareanforderungen für Konferenzen in Skype for Business Server

**Zusammenfassung:** In diesem Thema erfahren Sie mehr über die Hardware- und Softwareanforderungen für Konferenzen in Skype for Business Server.

In diesem Abschnitt werden die Hardware- und Softwareanforderungen für Webkonferenzen, Audio- und Videokonferenzen (A/V), Einwahlkonferenzen und Chatkonferenzen beschrieben. Alle Konferenzfunktionen werden auf Front-End-Servern ausgeführt. Es gibt zusätzliche Anforderungen für verschiedene Arten von Konferenzen, wie im folgenden Diagramm dargestellt.

Wenn Sie beispielsweise Einwahlkonferenzen zulassen möchten, müssen Sie einen Vermittlungsserver und ein Gateway für die Verbindung mit dem Telefonnetz (Public Switched Telephone Network, PSTN) bereitstellen. Wenn Sie Webkonferenzen zulassen möchten, müssen Sie sicherstellen, dass Skype for Business Server eine Verbindung mit einem Office Web Apps Server herstellen kann. Wenn Sie externen Benutzern die Teilnahme an Konferenzen ermöglichen möchten, müssen Sie einen Edgeserver bereitstellen.

**Konferenzfunktionen und -anforderungen**

![Konferenzkomponenten](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 Weitere Informationen zu Überlegungen zur Topologie finden Sie unter [Plan your conferencing topology for Skype for Business Server](conferencing-topology.md).

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>Hardware- und Softwareanforderungen für Front-End-Server

Da Webkonferenzen, A/V-Konferenzen, Einwahlkonferenzen und Telefonkonferenzen alle mit dem Front-End-Server ausgeführt werden, entsprechen die Hardware- und Softwareanforderungen des Servers den Anforderungen der Front-End-Server. Weitere Informationen zu diesen Anforderungen finden Sie unter ["Serveranforderungen für Skype for Business Server 2015"](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) und ["Environmental requirements for Skype for Business Server 2015"](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) oder ["Server requirements for Skype for Business Server 2019".](../../../SfBServer2019/plan/system-requirements.md)

## <a name="requirements-for-web-conferencing"></a>Anforderungen für Webkonferenzen

Wenn Sie sich für die Bereitstellung von Webkonferenzfunktionen entschieden haben, müssen Sie Folgendes planen:

- Zugriff auf den Dateispeicher, der zum Speichern von Webkonferenzinhalten verwendet wird.

- Integration in Office Web Apps Server, die erforderlich ist, um während einer Konferenz die PowerPoint-Dateien gemeinsam nutzen zu können.

### <a name="file-store"></a>Dateispeicher

Der Skype for Business Server-Webkonferenzdienst speichert Inhalte, die während Besprechungen freigegeben wurden, im Dateispeicher. Im Rahmen der Bereitstellung müssen Sie eine Dateifreigabe angeben, die als Dateispeicher für den Standard Edition-Server oder Front-End-Pool der Enterprise Edition verwendet werden soll. Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben. Weitere Informationen finden Sie unter [Erstellen einer Dateifreigabe in Skype for Business Server](../../deploy/install/create-a-file-share.md). Der Webkonferenzdienst verschlüsselt die Inhalte vor dem Speichern im Dateispeicher.

Skype for Business Server unterstützt die Verwendung von Dateifreigaben entweder für das DAS (Direct Attached Storage) oder ein Storage Area Network (SAN), einschließlich DFS (Distributed File System), und für Dateispeicher auf einem redundanten Array von unabhängigen Datenträgern (RAID). Nachdem der Skype for Business Server -Bereitstellungs-Assistent den Speicherort der Dateifreigabe definiert hat, erstellt Skype for Business Server eine Ordnerstruktur innerhalb der Dateifreigabe ähnlich der:

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - DataConf

Der Webkonferenzdienst speichert dann Inhalte wie z. B. PowerPoint-Folien, Whiteboards, Umfragen und Anhänge in den Ordnern "CollabContent" und "CollabMetadata", die sich wiederum im Ordner "WebServices" befinden.

### <a name="office-web-apps-server"></a>Office Web Apps-Server

Um Webkonferenzfunktionen verwenden zu können, müssen Sie Office Web Apps Server installieren und Skype for Business Server für die Kommunikation mit Office Web Apps Server konfigurieren.

Office Web Apps Server sollte auf einem eigenständigen Computer installiert werden, auf dem skype for Business Server, SQL Server oder eine andere Serveranwendung nicht ausgeführt wird. (Auf diesem Computer darf keine Version von Office installiert sein.) Auf jedem Computer, auf dem Office Web Apps Server ausgeführt wird, muss auch eine bestimmte Software installiert sein (einschließlich .NET Framework 4.5 und Windows PowerShell 3.0). Diese Anforderungen sowie Informationen zum Konfigurieren von Zertifikaten und Internetinformationsdienste (Internet Information Services, IIS) werden auf der Website für die Microsoft Office [Web Apps Deployment ausführlich erläutert.](https://go.microsoft.com/fwlink/p/?linkid=257525)

Informationen zum Konfigurieren von Skype for Business Server für die Zusammenarbeit mit Office Web Apps Server finden Sie unter "Konfigurieren der Integration [mit Office Web Apps Server in Skype for Business Server".](../../deploy/deploy-conferencing/office-web-app-server.md)

## <a name="requirements-for-audio-and-video-conferencing"></a>Anforderungen für Audio- und Videokonferenzen

Zum Planen von A/V-Konferenzen müssen Sie die erforderliche Netzwerkbandbreite für den Typ der Konferenzmedien kennen, die in Ihrer Organisation verwendet werden. Dies kann Audio, Video und Panoramavideo umfassen. Ohne ausreichende Netzwerkbandbreite kann die Benutzererfahrung stark beeinträchtigt werden.

Informationen zur Planung der Audio- und Videokapazität für Konferenzen finden Sie unter "Planen der [Netzwerkanforderungen für Skype for Business".](../../plan-your-deployment/network-requirements/network-requirements.md)

Sie können die Anrufsteuerung verwenden, um die von A/V-Konferenzen verwendete Netzwerkbandbreite zu verwalten. Dies ist wichtig für eingeschränkte Netzwerke, z. B. Verbindungen mit eingeschränkter Bandbreite zwischen zentralen und Zweigstellenstandorten. Weitere Informationen finden Sie unter [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).

Wenn Sie Audiokonferenzen in Ihrem Netzwerk bereitstellen, benötigen Ihre Benutzer Audiogeräte wie Headsets, um an einer Audiokonferenz teilzunehmen. Wenn Sie Videokonferenzen bereitstellen, müssen Sie Videogeräte wie Webcams für Benutzer bereitstellen. Bei Audio- und Videogeräten sind gerätebereitstellung und Benutzerschulungen wichtige Schritte, die Sie berücksichtigen sollten. Weitere Informationen finden Sie unter ["Planen von Clients und Geräten".](../../plan-your-deployment/clients-and-devices/clients-and-devices.md) Microsoft empfiehlt die Verwendung von Unified Communications (UC)-Geräten, die von Microsoft für alle Gerätetypen zertifiziert wurden, um eine optimale Benutzererfahrung zu gewährleisten. Details zu UC-zertifizierten Geräten finden Sie unter [Telefone und Geräte für Skype for Business](https://go.microsoft.com/fwlink/?LinkId=619916).

## <a name="requirements-for-dial-in-conferencing"></a>Anforderungen für Einwahlkonferenzen

Einwahlkonferenzen sind eine optionale Funktion der Skype for Business Server-Konferenzarbeitsauslastung, die eine Vielzahl von Komponenten umfasst. Einige der Komponenten sind spezifisch für Einwahlkonferenzen, andere sind Enterprise-VoIP Komponenten. In diesem Abschnitt werden die Anforderungen für die Komponenten beschrieben, die für Einwahlkonferenzen erforderlich sind. Weitere Informationen zu den Anforderungen für Vermittlungsserver und PstN-Gateways finden Sie unter ["Vermittlungsserverkomponente" in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) und bereitstellen eines Vermittlungsservers im [Topologie-Generator in Skype for Business Server.](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)

### <a name="required-components"></a>Erforderliche Komponenten

Sie müssen die folgenden Skype for Business Server-Komponenten installieren, bevor Sie Einwahlkonferenzen konfigurieren können:

- Unified Communications-Anwendungsdienst (auch nur Anwendungsdienst genannt)

- Konferenzzentrale

- Konferenzankündigungsanwendung

- Webseite mit Einstellungen für Einwahlkonferenzen

- Mindestens ein Vermittlungsserver und mindestens ein PSTN-Gateway

Für Einwahlkonferenzen, Anwendungsdienst, Anwendung für die Konferenztelefon attendant und Konferenzankündigungsanwendung gelten dieselben Betriebssystemanforderungen wie für Front-End-Server. Weitere Informationen finden Sie unter ["Serveranforderungen für Skype for Business Server 2015".](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)

Für die Konferenz attendant-Anwendung und die Konferenzankündigungsanwendung muss die Windows Media Format Runtime auf Front-End-Servern installiert sein. Die Windows Media Format Runtime ist für die Wiedergabe von Windows Media Audio (WMA)-Dateien erforderlich, die für Wartemusik, aufgezeichnete Namen und Ansforderungen verwendet werden. Wenn Sie auf Windows Server 2012 oder Windows Server 2012 R2 installieren (was empfohlen wird), müssen Sie Microsoft Media Foundation installieren, um windows Media Format Runtime zu erhalten. Wenn Sie vor Windows 2012 auf einer beliebigen Version von Windows Server installieren, müssen Sie sicherstellen, dass die Windows Desktop Experience installiert ist, um die Windows Media Format Runtime zu erhalten.

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>Audiodateianforderungen für Einwahlkonferenzen

Skype for Business Server unterstützt keine Anpassung von Sprachanrufen und Musik für Einwahlkonferenzen. Wenn Sie jedoch eine starke geschäftliche Notwendigkeit haben, die es erfordert, die Standardaudiodateien zu [](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177)ändern, lesen Sie den Microsoft Knowledge Base-Artikel 961177, wie Sie Sprachanrufe oder Musikdateien für Einwahlaudiokonferenzen anpassen.

Sie können auch das Verwaltungsprogramm für benutzerdefinierte Sprachanrufe der [Microsoft Lync Server-Konferenz attendant](https://go.microsoft.com/fwlink/p/?LinkId=396880) verwenden, mit dem Administratoren die Standardtelefonanrufe ersetzen können, die verwendet werden, wenn ein Anrufer einer Skype for Business-Besprechung mit benutzerdefinierten Ansaufforderungen beitritt, um eine andere Besprechungseingabeerfahrung zu ermöglichen. Die benutzerdefinierten Sprachanrufe können auf einem Enterprise- oder Standard Edition-Server installiert werden.

Für die Konferenz attendant-Anwendung und die Konferenzankündigungsanwendung gelten die folgenden Anforderungen für wartemusik, aufgezeichnete Namen und Audioansagendateien:

- WMA-Dateiformat (Windows Media Audio)

- 16-Bit mono

- Konstante Bitrate (Constant Bit Rate), 48 KBit/s, 2 Durchläufe

- Sprachpegel: -24 DB

### <a name="user-requirements-for-dial-in-conferencing"></a>Benutzeranforderungen für Einwahlkonferenzen

Dem Konto eines Einwahlkonferenzbenutzers muss eine eindeutige Rufnummer oder Durchwahl zugewiesen sein. Diese Anforderung unterstützt die Authentifizierung während der Einwahlkonferenz. Unternehmensbenutzer (d. h. Benutzer mit Active Directory Domain Services-Anmeldeinformationen und Skype for Business Server-Konten in Ihrer Organisation) geben ihre Telefonnummer (oder Durchwahl) und eine persönliche Identifikationsnummer (PIN) ein, um sich als authentifizierter Benutzer in Konferenzen einwählen zu können.

## <a name="port-requirements-for-conferencing"></a>Portanforderungen für Konferenzen

Um die Konferenzfunktionen verwenden zu können, erfordert Skype for Business Server, dass bestimmte Ports geöffnet sind. In der folgenden Tabelle sind die Portanforderungen für Konferenzen aufgeführt. Weitere Informationen zu allen Portanforderungen finden Sie unter [Port- und Protokollanforderungen für Server.](../../plan-your-deployment/network-requirements/ports-and-protocols.md)

**Erforderliche Serverports**


|**Serverrolle**|**Dienstname**|**Port**|**Protocol**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|
|Front-End-Server  <br/> |Skype for Business Server-Chatkonferenzdienst  <br/> |5062  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für Chatkonferenzen verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server-Webkonferenzdienst  <br/> |8057  <br/> |TCP (TLS)  <br/> |Wird zum Abhören von Verbindungen des beständigen freigegebenen Objektmodells (Persistent Shared Object Model, PSOM) vom Client verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server Web Conferencing Compatibility service  <br/> |8058  <br/> |TCP (TLS)  <br/> |Wird zum Abhören von Verbindungen des beständigen freigegebenen Objektmodells (Persistent Shared Object Model, PSOM) vom Live Meeting-Client und früheren Versionen von Skype for Business Server verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server Audio/Video-Konferenzdienst  <br/> |5063  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für Audio-/Videokonferenzen (A/V) verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server Audio/Video-Konferenzdienst  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Für Videokonferenzen verwendeter Medienportbereich.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server Conferencing Attendant service (Dial-in conferencing)  <br/> |5064  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für Einwahlkonferenzen verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server Conferencing Attendant service (Dial-in conferencing)  <br/> |5072  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für die Telefon attendant (Einwahlkonferenzen) verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server-Anwendungsfreigabedienst  <br/> |5065  <br/> |TCP  <br/> |Wird für eingehende SIP-Abhöranforderungen für die Anwendungsfreigabe verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server-Anwendungsfreigabedienst  <br/> |49152-65535  <br/> |TCP  <br/> |Für die Anwendungsfreigabe verwendeter Medienportbereich.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server Conferencing Announcement Service  <br/> |5073  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für den Skype for Business Server-Konferenzankündigungsdienst (d. h. für Einwahlkonferenzen) verwendet.  <br/> |
|Alle internen Server  <br/> |Verschiedene  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |Für Audiokonferenzen auf allen internen Servern verwendeter Medienportbereich. Wird von allen Servern verwendet, die Audio beenden: Front-End-Server (für skype for Business Server-Konferenz attendant-Dienst, Skype for Business Server-Konferenzankündigungsdienst und Skype for Business Server-Audio-/Videokonferenzdienst) und Vermittlungsserver.  <br/> |
|Office Web Apps Server  <br/> ||443  <br/> ||Wird von Skype for Business Server verwendet, um eine Verbindung mit Office Web Apps Server herzustellen.  <br/> |

**Erforderliche Clientports**


|**Port**|**Protocol**|**Notizen**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |Wird für den Externen Benutzerzugriff auf Webkonferenzsitzungen verwendet.  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |Wird für den Externen Benutzerzugriff auf A/V-Sitzungen und Medien (TCP) verwendet.  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |Wird für den externen Benutzerzugriff auf A/V-Sitzungen und Medien (UDP) verwendet.  <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |Audioportbereich (mindestens 20 Ports erforderlich)  <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |Videoportbereich (mindestens 20 Ports erforderlich).  <br/> |
|1024-65535 \*  <br/> |TCP  <br/> |Anwendungsfreigabe.  <br/> |


