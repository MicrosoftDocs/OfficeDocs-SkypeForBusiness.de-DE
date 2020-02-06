---
title: Hardware-und Softwareanforderungen für Konferenzen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Informationen zu den Hardware-und Softwareanforderungen für Konferenzen in Skype for Business Server zu erhalten.'
ms.openlocfilehash: 0d09e0e85e7059e0a761b2822f963765751623e0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815983"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>Hardware-und Softwareanforderungen für Konferenzen in Skype for Business Server

**Zusammenfassung:** In diesem Thema finden Sie Informationen zu den Hardware-und Softwareanforderungen für Konferenzen in Skype for Business Server.

In diesem Abschnitt werden die Hardware-und Softwareanforderungen für Webkonferenzen, Audio-und Videokonferenzen (A/V), Einwahlkonferenzen und Instant Messaging (im)-Konferenzen beschrieben. Alle Konferenzfunktionen werden auf Front-End-Servern ausgeführt. Es gibt zusätzliche Anforderungen für verschiedene Konferenztypen, wie im folgenden Diagramm dargestellt.

Wenn Sie beispielsweise Einwahlkonferenzen zulassen möchten, müssen Sie einen Vermittlungs Server und ein Gateway zum Herstellen einer Verbindung mit dem öffentlichen Telefonnetz (PSTN) bereitstellen. Wenn Sie Webkonferenzen zulassen möchten, müssen Sie sicherstellen, dass Skype for Business Server eine Verbindung mit einem Office Web Apps-Server herstellen kann. Wenn Sie externen Benutzern die Teilnahme an den Konferenzen ermöglichen möchten, müssen Sie einen Edgeserver bereitstellen.

**Funktionen und Systemanforderungen für Konferenzen**

![Konferenzkomponenten](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 Weitere Informationen zu Topologie Überlegungen finden Sie unter [Planen der Konferenz Topologie für Skype for Business Server](conferencing-topology.md).

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>Hardware- und Softwareanforderungen an den Front-End-Server

Da Webkonferenzen, A/V-Konferenzen, Einwahlkonferenzen und Chat Konferenzen alle mit dem Front-End-Server kombiniert sind, sind die Server Hardware-und Softwareanforderungen identisch mit den Front-End-Servern. Details zu diesen Anforderungen finden Sie unter [Server Anforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) und [Umgebungsanforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) oder [Server Anforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).

## <a name="requirements-for-web-conferencing"></a>Anforderungen für Webkonferenzen

Wenn Sie sich für die Bereitstellung von Webkonferenzfunktionen entschieden haben, müssen Sie Folgendes planen:

- Zugriff auf den Dateispeicher, der zum Speichern von Webkonferenzinhalten verwendet wird.

- Integration mit dem Office Web App-Server. Dies ist für die Freigabe von PowerPoint-Dateien während einer Konferenz erforderlich.

### <a name="file-store"></a>Dateispeicher

Der Skype for Business Server-Webkonferenzdienst speichert während Besprechungen im Dateispeicher freigegebene Inhalte. Als Teil der Bereitstellung müssen Sie eine Dateifreigabe angeben, die als Dateispeicher für den Standard Edition-Server oder den Enterprise Edition-Front-End-Pool verwendet werden soll. Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben. Weitere Informationen finden Sie unter [Erstellen einer Dateifreigabe in Skype for Business Server](../../deploy/install/create-a-file-share.md). Der Webkonferenzdienst verschlüsselt die Inhalte vor dem Speichern im Dateispeicher.

Skype for Business Server unterstützt die Verwendung von Dateifreigaben entweder im Direct Attached Storage (das) oder in einem SAN (Storage Area Network), einschließlich DFS (Distributed File System), und auf einem redundanten Array von unabhängigen Datenträgern (RAID) für Dateispeicher. Nachdem der Skype for Business Server-Bereitstellungs-Assistent den Speicherort der Dateifreigabe definiert hat, erstellt Skype for Business Server eine Ordnerstruktur innerhalb der Dateifreigabe ähnlich wie:

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - DataConf

Der Webkonferenzdienst speichert dann Inhalte wie z. B. PowerPoint-Folien, Whiteboards, Umfragen und Anhänge in den Ordnern „CollabContent“ und „CollabMetadata“, die sich wiederum im Ordner „WebServices“ befinden.

### <a name="office-web-apps-server"></a>Office Web Apps-Server

Um Webkonferenzfunktionen verwenden zu können, müssen Sie Office Web Apps Server installieren und Skype for Business Server für die Kommunikation mit Office Web Apps Server konfigurieren.

Office Web Apps Server sollte auf einem eigenständigen Computer installiert sein, auf dem Skype for Business Server, SQL Server oder eine andere Serveranwendung nicht ausgeführt wird. (Auf diesem Computer darf keine Office-Version installiert sein.) Auf jedem Computer, auf dem Office Web Apps-Server ausgeführt wird, muss auch eine bestimmte Softwaregruppe installiert sein (einschließlich .NET Framework 4,5 und Windows PowerShell 3,0). Diese Anforderungen sowie Informationen zum Konfigurieren von Zertifikaten und Internet Informationsdienste (IIS) werden ausführlich auf der [Microsoft Office Web Apps-Bereitstellungswebsite](https://go.microsoft.com/fwlink/p/?linkid=257525)erläutert.

Informationen zum Konfigurieren von Skype for Business Server für die Zusammenarbeit mit Office Web Apps Server finden Sie unter [Konfigurieren der Integration in Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).

## <a name="requirements-for-audio-and-video-conferencing"></a>Systemvoraussetzungen für Audio- und Videokonferenzen

Zum Planen von A/V-Konferenzen müssen Sie die erforderliche Netzwerkbandbreite für den Typ der Konferenzmedien kennen, die in Ihrer Organisation verwendet werden. Dies könnten z. B. Audio, Video und Panoramavideo sein. Eine zu geringe Netzwerkbandbreite kann zu einem stark beeinträchtigten Benutzererlebnis führen.

Weitere Informationen zur Kapazitätsplanung für Audio- und Videoinhalte auf Konferenzen finden Sie unter [Plan network requirements for Skype for Business](../../plan-your-deployment/network-requirements/network-requirements.md)

Für die Verwaltung der von A/V-Konferenzen verwendeten Netzwerkbandbreite können Sie die Anrufsteuerung (CAC) verwenden. Dies ist für eingeschränkte Netzwerke wichtig, beispielsweise bei Verbindungen mit beschränkter Bandbreite zwischen Zentrale und Niederlassungen. Einzelheiten hierzu finden Sie unter [Planen der Anrufsteuerung in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).

Bei Bereitstellung der Audiokonferenzfunktion in Ihrem Netzwerk benötigen Ihre Benutzer Audiogeräte (z. B. Headsets), um an einer Audiokonferenz teilzunehmen. Wenn Sie Videokonferenzen bereitstellen, benötigen die Benutzer Videogeräte, wie Webcams. Sowohl für Audio- als auch Videokonferenzen sollten Sie sich über die Bereitstellung der Geräte und mögliche Benutzerschulungen Gedanken machen. Weitere Informationen finden Sie unter [Planen von Clients und Geräten](../../plan-your-deployment/clients-and-devices/clients-and-devices.md). Microsoft empfiehlt für alle Gerätetypen die Verwendung von UC-Geräten (Unified Communications), die von Microsoft zertifiziert wurden, um eine optimale Benutzererfahrung sicherzustellen. Details zu UC-zertifizierten Geräten finden Sie unter [Telefone und Geräte für Skype for Business](https://go.microsoft.com/fwlink/?LinkId=619916).

## <a name="requirements-for-dial-in-conferencing"></a>Systemvoraussetzungen für Einwahlkonferenzen

Einwahlkonferenzen sind ein optionales Feature der Skype for Business Server-Konferenz Arbeitsauslastung, die eine Vielzahl von Komponenten umfasst. Einige der Komponenten gelten speziell für Einwahlkonferenzen und einige sind Enterprise-VoIP-Komponenten. In diesem Abschnitt werden die Anforderungen für die Komponenten beschrieben, die für Einwahlkonferenzen benötigt werden. Details zu den Anforderungen des Vermittlungsservers und des PSTN-Gateways (Public Switched Telephone Network) finden Sie unter [Vermittlungsserver Komponente in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) und [Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md).

### <a name="required-components"></a>Erforderliche Komponenten

Sie müssen die folgenden Skype for Business Server-Komponenten installieren, bevor Sie Einwahlkonferenzen konfigurieren können:

- Unified Communications-Anwendungsdienst (auch nur Anwendungsdienst genannt)

- Konferenzzentrale

- Konferenzankündigungsanwendung

- Webseite mit Einstellungen für Einwahlkonferenzen

- Mindestens ein Vermittlungsserver und ein PSTN-Gateway

Für Einwahlkonferenzen, Anwendungsdienst, Konferenz Aufsichts Anwendung und Konferenz Ankündigungs Anwendung gelten dieselben Betriebssystemanforderungen wie für Front-End-Server. Weitere Einzelheiten finden Sie in [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

Die Anwendung für die Conferencing Attendant-Anwendung und die Konferenzankündigung erfordern, dass Windows Media Format Runtime auf Front-End-Servern installiert ist. Die Windows Media Format-Laufzeitkomponente ist für die Wiedergabe von WMA-Dateien (Windows Media Audio) erforderlich, die für Wartemusik, aufgezeichnete Namen und Ansagen verwendet werden. Wenn Sie unter Windows Server 2012 oder Windows Server 2012 R2 installieren (was wir empfehlen), müssen Sie Microsoft Media Foundation installieren, um die Windows Media-Format Laufzeit zu erhalten. Wenn Sie auf einer älteren Version als Windows Server 2012 installieren, müssen Sie sicherstellen, dass Windows Desktop Experience installiert ist, damit Sie die Windows Media Format-Laufzeitkomponente erhalten.

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>Audiodateianforderungen für Einwahlkonferenzen

Skype for Business Server unterstützt keine Anpassung von Sprachansagen und Musik für Einwahlkonferenzen. Wenn Sie jedoch eine starke geschäftliche Anforderung haben, die erfordert, dass Sie die standardmäßigen Audiodateien ändern, lesen Sie den Microsoft Knowledge Base-Artikel 961177, [Anleitung zum Anpassen von Sprachansagen oder Musikdateien für Einwahlkonferenzen](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177).

Sie können auch das Verwaltungsdienstprogramm für [benutzerdefinierte Sprachansagen für Microsoft lync Server Conferencing](https://go.microsoft.com/fwlink/p/?LinkId=396880) verwenden, das es Administratoren ermöglicht, die standardmäßigen Sprachaufforderungen zu ersetzen, die verwendet werden, wenn ein Telefon Anrufer eine Skype for Business-Besprechung mit benutzerdefinierten Ansagen annimmt, um eine andere Besprechungs Eingabe zu ermöglichen. Die benutzerdefinierten Sprachansagen können entweder auf einem Enterprise-oder Standard Edition-Server installiert werden.

Anwendung für die Conferencing Attendant-Anwendung und Konferenzankündigung gelten für die folgenden Voraussetzungen für Musik in Wartestellung, aufgezeichnete Namen und Audio-Ansagedateien:

- WMA-Dateiformat (Windows Media Audio)

- 16-Bit mono

- Konstante Bitrate (Constant Bit Rate), 48 KBit/s, 2 Durchläufe

- Sprachpegel: -24 dB

### <a name="user-requirements-for-dial-in-conferencing"></a>Benutzeranforderungen für Einwahlkonferenzen

Dem Konto eines Einwahlkonferenzbenutzers muss eine eindeutige Rufnummer oder Durchwahl zugewiesen sein. Diese Anforderung unterstützt die Authentifizierung während der Einwahlkonferenz. Enterprise-Benutzer (also Benutzer mit den Anmeldeinformationen für Active Directory-Domänendienste und Skype for Business Server-Konten in Ihrer Organisation) geben Ihre Telefonnummer (oder Durchwahl) und eine persönliche Identifikationsnummer (PIN) ein, um sich in Konferenzen einzuwählen, ein authentifizierter Benutzer.

## <a name="port-requirements-for-conferencing"></a>Portanforderungen für Konferenzen

Um die Konferenzfunktionen nutzen zu können, ist es für Skype for Business Server erforderlich, dass bestimmte Ports geöffnet sind. In der folgenden Tabelle sind die Portanforderungen für Konferenzen dargestellt. Ausführliche Informationen zu den Portanforderungen finden Sie unter [Port-und Protokollanforderungen für Server](../../plan-your-deployment/network-requirements/ports-and-protocols.md).

**Erforderliche Serverports**


|**Serverrolle**|**Name des Diensts**|**Port**|**Protokoll**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|
|Front-End-Server  <br/> |Skype for Business Server-Chat Konferenzdienst  <br/> |5062  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für Instant Messaging-Konferenzen verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server-Webkonferenzdienst  <br/> |8057  <br/> |TCP (TLS)  <br/> |Wird zum Überwachen von PSOM-Verbindungen (Persistent Shared Object Model) vom Client verwendet.  <br/> |
|Front-End-Server  <br/> |Kompatibilitätsdienst für Skype for Business Server Web Conferencing  <br/> |8058  <br/> |TCP (TLS)  <br/> |Wird verwendet, um auf Persistent Shared Object Model (PSOM)-Verbindungen über den Live Meeting-Client und frühere Versionen von Skype for Business Server zu lauschen.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server-Audio/Video Konferenzdienst  <br/> |5063  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für A/V-Konferenzen (Audio/Video) verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server-Audio/Video Konferenzdienst  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Für Videokonferenzen verwendeter Medienportbereich.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server Conferencing Attendant Service (Einwahlkonferenzen)  <br/> |5064  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für Einwahlkonferenzen verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server Conferencing Attendant Service (Einwahlkonferenzen)  <br/> |5072  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für Attendant (Dial in Conferencing) verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server-Anwendungsfreigabe Dienst  <br/> |5065  <br/> |TCP  <br/> |Wird für eingehende SIP-Überwachungsanforderungen für die Anwendungsfreigabe verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server-Anwendungsfreigabe Dienst  <br/> |49152-65535  <br/> |TCP  <br/> |Für die Anwendungsfreigabe verwendeter Medienportbereich.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server-Konferenzankündigungsdienst  <br/> |5073  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für den Skype for Business Server-Konferenzankündigungsdienst (für Einwahlkonferenzen) verwendet.  <br/> |
|Alle internen Server  <br/> |Verschiedene  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |Für Audiokonferenzen auf allen internen Servern verwendeter Medienportbereich. Wird von allen Servern verwendet, die Audio beenden: Front-End-Server (für den Skype for Business Server-Konferenz Aufsichtsdienst, Skype for Business Server-Konferenzankündigungsdienst und Skype for Business Server-Audio/Video Konferenzdienst) und Vermittlungs Server.  <br/> |
|Office Web Apps-Server  <br/> ||443  <br/> ||Wird von Skype for Business Server verwendet, um eine Verbindung mit Office Web Apps Server herzustellen.  <br/> |

**Erforderliche Client Anschlüsse**


|**Port**|**Protokoll**|**Hinweise**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |Wird für externen Benutzerzugriff auf Webkonferenzsitzungen verwendet.  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |Wird für externen Benutzerzugriff auf A/V-Sitzungen und -Mediendaten verwendet (TCP).  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |Wird für externen Benutzerzugriff auf A/V-Sitzungen und -Mediendaten verwendet (UDP).  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |Audioportbereich (mindestens 20 Ports erforderlich).  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |Videoportbereich (mindestens 20 Ports erforderlich).  <br/> |
|1024-65535\*  <br/> |TCP  <br/> |Anwendungsfreigabe.  <br/> |


