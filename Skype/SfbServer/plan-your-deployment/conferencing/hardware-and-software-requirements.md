---
title: Hardware und Software-Anforderungen für Konferenzen in Skype für Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Informationen zu Hardware und Software-Anforderungen für Konferenzen in Skype für Business Server erhalten.'
ms.openlocfilehash: 3385395eb34e69fadcdce4ba4bf529a347a2979c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883928"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>Hardware und Software-Anforderungen für Konferenzen in Skype für Business Server

**Zusammenfassung:** Lesen Sie dieses Thema, um Informationen zu Hardware und Software-Anforderungen für Konferenzen in Skype für Business Server erhalten.

In diesem Abschnitt werden die Anforderungen für Hardware und Software für Webkonferenzen, audio und video (A / V) Konferenz-, einwahlkonferenzen und Konferenzen Sofortnachrichten (IM). Führen Sie alle Konferenzfunktionen auf Front-End-Servern. Es sind zusätzliche Anforderungen für unterschiedliche Arten von Konferenzen, wie in der folgenden Abbildung dargestellt.

Wenn Sie einwahlkonferenzen zulassen möchten, müssen Sie einen Vermittlungsserver und einem Gateway für die Verbindung mit dem öffentlichen Telefonfestnetz (PSTN) bereitstellen. Wenn Sie Webkonferenzen zulassen möchten, müssen Sie sicherstellen, dass Skype für Business Server mit einer Office Web Apps-Server verbinden kann. Wenn Sie externen Benutzern die Teilnahme an den Konferenzen ermöglichen möchten, müssen Sie einen Edgeserver bereitstellen.

**Funktionen und Systemanforderungen für Konferenzen**

![Konferenzkomponenten](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 Weitere Informationen zu Überlegungen zu finden Sie unter [Planen Ihrer konferenztopologie für Skype für Business Server](conferencing-topology.md).

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>Hardware- und Softwareanforderungen an den Front-End-Server

Da von Webkonferenzen, A / V-Konferenzen, einwahlkonferenzen und Instant Messaging-Konferenzen, werden alle mit dem Front-End-Server verbunden, werden die Anforderungen für Hardware und Software sind die gleichen wie für den Front-End-Servern. Ausführliche Informationen zu diesen Anforderungen finden Sie unter [Server-Anforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) und [umgebungsanforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) oder [Anforderungen für Skype für Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).

## <a name="requirements-for-web-conferencing"></a>Anforderungen für Webkonferenzen

Wenn Sie sich für die Bereitstellung von Webkonferenzfunktionen entschieden haben, müssen Sie Folgendes planen:

- Zugriff auf den Dateispeicher, der zum Speichern von Webkonferenzinhalten verwendet wird.

- Integration mit dem Office Web App-Server. Dies ist für die Freigabe von PowerPoint-Dateien während einer Konferenz erforderlich.

### <a name="file-store"></a>Dateispeicher

Die Skype für Business Server Webkonferenzdienst speichert während einer Besprechung in den Dateispeicher freigegebenen Inhalt. Im Rahmen der Bereitstellung müssen Sie eine Dateifreigabe als den Dateispeicher für den Standard Edition-Server oder Enterprise Edition-Front-End-Pool zu verwendenden angeben. Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben. Weitere Informationen finden Sie unter [Erstellen einer Dateifreigabe in Skype für Business Server](../../deploy/install/create-a-file-share.md). Der Webkonferenzdienst verschlüsselt die Inhalte vor dem Speichern im Dateispeicher.

Skype für Business Server unterstützt, die Verwendung von Dateifreigaben auf direct-attached Storage (DAS) oder ein Storage Area Network (SAN), einschließlich verteilten Dateisystem (DFS), und klicken Sie auf eine redundant Array of independent Disks (RAID) für Dateispeicher. Nachdem die Skype für Business Server-Bereitstellungs-Assistenten den Speicherort der Dateifreigabe definiert, erstellt Skype für Business Server eine Ordnerstruktur innerhalb der Dateifreigabe ähnelt:

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - DataConf

Der Webkonferenzdienst speichert dann Inhalte wie z. B. PowerPoint-Folien, Whiteboards, Umfragen und Anhänge in den Ordnern „CollabContent“ und „CollabMetadata“, die sich wiederum im Ordner „WebServices“ befinden.

### <a name="office-web-apps-server"></a>Office Web Apps-Server

Um die Webkonferenzfunktionen benötigt verwenden, müssen Sie Installieren von Office Web Apps Server und Skype für Business Server zur Kommunikation mit Office Web Apps Server konfigurieren.

Office Web Apps Server sollte auf einem eigenständigen Computer installiert werden, die nicht Skype Business Server, SQL Server oder einer anderen Serveranwendung ausgeführt wird. (Sie müssen keine Versionen von Office auf dem Computer installierten verfügen.) Einem beliebigen Computer zum Ausführen von Office Web Apps Server verwendet müssen außerdem die einen bestimmten Satz von Software (einschließlich .NET Framework 4.5 und Windows PowerShell 3.0) installiert. Diese Anforderungen, zusammen mit Informationen zum Konfigurieren von Zertifikaten und (Internet Information Services, IIS) werden in der [Website Microsoft Office Web Apps-Bereitstellung](https://go.microsoft.com/fwlink/p/?linkid=257525)ausführlich erläutert.

Informationen zur Konfiguration von Skype für Business Server mit Office Web Apps Server arbeiten finden Sie unter [Konfigurieren der Integration mit Office Web Apps Server in Skype für Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).

## <a name="requirements-for-audio-and-video-conferencing"></a>Systemvoraussetzungen für Audio- und Videokonferenzen

Zum Planen von A/V-Konferenzen müssen Sie die erforderliche Netzwerkbandbreite für den Typ der Konferenzmedien kennen, die in Ihrer Organisation verwendet werden. Dies könnten z. B. Audio, Video und Panoramavideo sein. Eine zu geringe Netzwerkbandbreite kann zu einem stark beeinträchtigten Benutzererlebnis führen.

Weitere Informationen zur Kapazitätsplanung für Audio- und Videoinhalte auf Konferenzen finden Sie unter [Plan network requirements for Skype for Business](../../plan-your-deployment/network-requirements/network-requirements.md)

Für die Verwaltung der von A/V-Konferenzen verwendeten Netzwerkbandbreite können Sie die Anrufsteuerung (CAC) verwenden. Dies ist für eingeschränkte Netzwerke wichtig, beispielsweise bei Verbindungen mit beschränkter Bandbreite zwischen Zentrale und Niederlassungen. Weitere Informationen hierzu finden Sie unter [Planen für die anrufsteuerung in Skype für Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).

Bei Bereitstellung der Audiokonferenzfunktion in Ihrem Netzwerk benötigen Ihre Benutzer Audiogeräte (z. B. Headsets), um an einer Audiokonferenz teilzunehmen. Wenn Sie Videokonferenzen bereitstellen, benötigen die Benutzer Videogeräte, wie Webcams. Sowohl für Audio- als auch Videokonferenzen sollten Sie sich über die Bereitstellung der Geräte und mögliche Benutzerschulungen Gedanken machen. Weitere Informationen finden Sie unter [Planen von Clients und Geräten](../../plan-your-deployment/clients-and-devices/clients-and-devices.md). Microsoft empfiehlt für alle Gerätetypen die Verwendung von UC-Geräten (Unified Communications), die von Microsoft zertifiziert wurden, um eine optimale Benutzererfahrung sicherzustellen. Informationen zu zertifizierten UC-Geräten finden Sie unter [Telefone und Geräte für Skype für Unternehmen](https://go.microsoft.com/fwlink/?LinkId=619916).

## <a name="requirements-for-dial-in-conferencing"></a>Systemvoraussetzungen für Einwahlkonferenzen

Einwahlkonferenzen ist eine optionale Funktion von der Skype für Business Server die konferenzarbeitslast, die eine Vielzahl von Komponenten enthält. Einige der Komponenten sind spezifisch für einwahlkonferenzen und einige Komponenten von Enterprise-VoIP. Dieser Abschnitt beschreibt die Anforderungen für die Komponenten, die für einwahlkonferenzen erforderlich sind. Ausführliche Informationen zu Vermittlungsserver und das Telefonfestnetz (PSTN) Gateway netzwerkanforderungen finden Sie unter [Mediation Server Component in Skype für Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) und [Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype für Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md).

### <a name="required-components"></a>Erforderliche Komponenten

Sie müssen die folgenden Skype für Business Server-Komponenten installieren, bevor Sie einwahlkonferenzen konfigurieren können:

- Unified Communications Application Service (UCAS) (called the Application service)

- Konferenzzentrale

- Konferenzankündigungsanwendung

- Webseite mit Einstellungen für Einwahlkonferenzen

- Mindestens ein Vermittlungsserver und ein PSTN-Gateway

Müssen Sie für einwahlkonferenzen, -Anwendungsdienst, konferenzzentrale und Konferenzankündigungsdienst-Anwendung die gleichen betriebssystemanforderungen als Front-End-Server. Weitere Einzelheiten finden Sie in [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

Die Anwendung Konferenzzentrale und Konferenzankündigungsdienst Anwendung erfordern, dass Windows Media Format-Laufzeitkomponente auf Front-End-Servern installiert ist. Die Windows Media Format-Laufzeitkomponente ist für die Wiedergabe von WMA-Dateien (Windows Media Audio) erforderlich, die für Wartemusik, aufgezeichnete Namen und Ansagen verwendet werden. Wenn Sie auf Windows Server 2012 oder Windows Server 2012 R2 (die empfohlen) installieren, müssen Sie installieren Microsoft Media Foundation Wenn Windows Media Format-Laufzeitkomponente erhalten möchten. Wenn Sie auf einer älteren Version als Windows Server 2012 installieren, müssen Sie sicherstellen, dass Windows Desktop Experience installiert ist, damit Sie die Windows Media Format-Laufzeitkomponente erhalten.

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>Audiodateianforderungen für Einwahlkonferenzen

Skype für Business Server unterstützt keine Anpassung von Ansagen und Musik für einwahlkonferenzen. Allerdings Sie starken geschäftlicher verfügen, die Sie zum Ändern der Standard-Audiodateien erforderlich sind, finden Sie unter Microsoft Knowledge Base-Artikel 961177 [zum Anpassen von Ansagen oder Musikdateien für Einwahl - Audiokonferenzen](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177).

Sie können auch das Hilfsprogramm [Microsoft Lync Server Conferencing Attendant Custom VoIP Prompts](https://go.microsoft.com/fwlink/p/?LinkId=396880) Management verwenden, das ermöglicht Administratoren, ersetzen Sie die standardmäßigen Ansagen verwendet, wenn ein Anrufer Telefon einen Skype für Business-Besprechung mit benutzerdefinierten Ansagen Beitritt Bereitstellen eine andere Besprechung Eintrag auftreten. Die benutzerdefinierte Ansagen können auf eine Enterprise oder Standard Edition-Server installiert werden.

Die Anwendung Konferenzzentrale und Konferenzankündigungsdienst Anwendung gelten folgende Anforderungen für die Musik in der Warteschleife, aufgezeichneten Namen und Dateien mit audioansagen:

- WMA-Dateiformat (Windows Media Audio)

- 16-Bit mono

- Konstante Bitrate (Constant Bit Rate), 48 KBit/s, 2 Durchläufe

- Sprachpegel: -24 dB

### <a name="user-requirements-for-dial-in-conferencing"></a>Benutzeranforderungen für Einwahlkonferenzen

Dem Konto eines Einwahlkonferenzbenutzers muss eine eindeutige Rufnummer oder Durchwahl zugewiesen sein. Diese Anforderung unterstützt die Authentifizierung während der Einwahlkonferenz. Unternehmensbenutzer (d. h., Benutzer mit Active Directory-Domänendienste-Anmeldeinformationen und Skype für Business Server-Konten in Ihrer Organisation) Geben Sie ihre Telefonnummer ein (oder die Erweiterung) und eine persönliche Identifikationsnummer (PIN) in Konferenzen als einwählen ein authentifizierter Benutzer.

## <a name="port-requirements-for-conferencing"></a>Portanforderungen für Konferenzen

Um die Konferenzfeatures verwenden, erfordert Skype für Business Server an, dass bestimmte Ports geöffnet sind. In der folgenden Tabelle sind die Portanforderungen für Konferenzen dargestellt. Ausführliche Informationen zu allen Port finden Sie unter [Ports und Protokolle-Anforderungen für Server](../../plan-your-deployment/network-requirements/ports-and-protocols.md).

**Erforderliche Serverports**


|**Serverrolle**|**Name des Diensts**|**Port**|**Protokoll**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|
|Front-End-Server  <br/> |Skype für Business Server Sofortnachrichten-Konferenzdienst  <br/> |5062  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für Instant Messaging-Konferenzen verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server-Webkonferenzdienst  <br/> |8057  <br/> |TCP (TLS)  <br/> |Wird zum Überwachen von PSOM-Verbindungen (Persistent Shared Object Model) vom Client verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Webkonferenzkompatibilität von Business Server-Dienst  <br/> |8058  <br/> |TCP (TLS)  <br/> |Wird zum Persistent Shared Object Model (PSOM) Verbindungen vom Live Meeting-Client und von früheren Versionen von Skype für Business Server verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server a/v-Konferenzdienst  <br/> |5063  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für A/V-Konferenzen (Audio/Video) verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server a/v-Konferenzdienst  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Für Videokonferenzen verwendeter Medienportbereich.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server-konferenzzentralendienst (einwahlkonferenzen)  <br/> |5064  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für Einwahlkonferenzen verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server-konferenzzentralendienst (einwahlkonferenzen)  <br/> |5072  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für Attendant (einwahlkonferenzen) verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server-anwendungsfreigabedienst  <br/> |5065  <br/> |TCP  <br/> |Wird für eingehende SIP-Überwachungsanforderungen für die Anwendungsfreigabe verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server-anwendungsfreigabedienst  <br/> |49152-65535  <br/> |TCP  <br/> |Für die Anwendungsfreigabe verwendeter Medienportbereich.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server-konferenzankündigungsdienst  <br/> |5073  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für die Skype für Business Server-konferenzankündigungsdienst verwendet (d. h., für einwahlkonferenzen).  <br/> |
|Alle internen Server  <br/> |Verschiedene  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |Für Audiokonferenzen auf allen internen Servern verwendeter Medienportbereich. Von allen Servern, die beendet Audio verwendet: Front-End-Servern (für Skype für Business Server-konferenzzentralendienst, Skype für Business Server-konferenzankündigungsdienst und Skype für Business Server a/v-Konferenzdienst), und Vermittlungsserver.  <br/> |
|Office Web Apps-Server  <br/> ||443  <br/> ||Verbindung mit Office Web Apps Server verwendet durch Skype für Business Server.  <br/> |

**Erforderliche Clientports**


|**Port**|**Protokoll**|**Hinweise**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |Wird für externen Benutzerzugriff auf Webkonferenzsitzungen verwendet.  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |Wird für externen Benutzerzugriff auf A/V-Sitzungen und -Mediendaten verwendet (TCP).  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |Wird für externen Benutzerzugriff auf A/V-Sitzungen und -Mediendaten verwendet (UDP).  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |Audioportbereich (mindestens 20 Ports erforderlich).  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |Videoportbereich (mindestens 20 Ports erforderlich).  <br/> |
|1024-65535\*  <br/> |TCP  <br/> |Anwendungsfreigabe.  <br/> |


