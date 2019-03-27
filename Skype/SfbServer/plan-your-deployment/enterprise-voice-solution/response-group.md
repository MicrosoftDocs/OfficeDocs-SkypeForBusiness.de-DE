---
title: Plan für die Anwendung "Reaktionsgruppe" in Skype für Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: Planen von reaktionsgruppen in Skype für Business Server Enterprise-VoIP, ermöglicht Ihnen die Anrufrouting für Benutzergruppen einrichten. Es konfiguriert, was mit nicht zugewiesenen Telefonnummern in Ihren Organisationen passiert und beinhaltet Audiodateianforderungen.
ms.openlocfilehash: 68a693715739d58488e134934416790641dd091e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894402"
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server"></a>Plan für die Anwendung "Reaktionsgruppe" in Skype für Business Server

Planen von reaktionsgruppen in Skype für Business Server Enterprise-VoIP, ermöglicht Ihnen die Anrufrouting für Benutzergruppen einrichten. Es konfiguriert, was mit nicht zugewiesenen Telefonnummern in Ihren Organisationen passiert und beinhaltet Audiodateianforderungen.

Wenn Ihre Organisation Personengruppen, die beantwortet und bestimmte Arten von Anrufen zu verwalten verfügt, können wie für Kundendienst, einen internen Helpdesk oder allgemeine Telefonsupport für eine Abteilung Sie die Anwendung "Reaktionsgruppe" zum Verwalten von diese Arten von Anrufen bereitstellen. Die Reaktionsgruppe Anwendung leitet und eingehende Anrufe an die Warteschlange speziell dafür vorgesehenen Personen, die als Agents bezeichnet werden. Können Sie erhöhen die Verwendung von Telefon-Supports und verringern den Aufwand für die Ausführung dieser Dienste mithilfe von reaktionsgruppen.

Wenn ein Anrufer eine Reaktionsgruppe anruft, wird der Anruf basierend auf einem Sammelanschluss oder den interaktiven Sprachantworten des Anrufers an einen Agent weitergeleitet. Die Anwendung "Reaktionsgruppe" verwendet Standardantwort Gruppe Routingmethoden, um den Anruf dem nächsten verfügbaren Vertreter weiterzuleiten. Die Methoden zur Anrufweiterleitung umfassen serielles, Longest-Idle-, paralleles, Roundrobin- sowie das neue Routing über die Telefonzentrale (hier werden bei einem eingehenden Anruf alle Agents gleichzeitig angerufen, unabhängig von ihrem aktuellen Anwesenheitsstatus).

Wenn keine Agents verfügbar sind, wird der Anruf in einer Warteschleife platziert, bis ein Agent verfügbar ist. Wenn sich ein Anrufer in der Warteschleife befindet, wird Musik wiedergegeben, bis ein verfügbarer Agent den Anruf entgegennimmt. Wenn die Warteschleife belegt ist oder für einen Anruf ein Timeout auftritt, während er sich in der Warteschleife befindet, kann für den Anrufer eine Nachricht wiedergegeben werden und anschließend wird der Anrufer entweder getrennt oder an ein anderes Ziel wie beispielsweise eine andere Telefonnummer oder Voicemail übergeben. Wenn ein Agent den Anruf entgegennimmt, kann dem Anrufer abhängig davon, wie der Administrator die Reaktionsgruppe konfiguriert, die Identität des Agents angezeigt werden. Bei Agents kann es sich um formelle Agents handeln, die sich bei der Gruppe anmelden müssen, bevor sie Anrufe an die Gruppe entgegennehmen können, oder um informelle Agents, die sich nicht bei der Gruppe an- und abmelden müssen, um Anrufe zu beantworten.

> [!NOTE]
> Nur lokale Benutzer können Agents sein. Wenn ein Agent lokal zu online verschoben wurde, werden nicht reaktionsgruppenanrufe, Vertreter weitergeleitet.

> [!NOTE]
> Die Anwendung "Reaktionsgruppe" verwendet einen internen Dienst, namens Übereinstimmung zu machen, um Anrufe in die Warteschlange und verfügbare Agents zu suchen. Jeder Computer, der die Anwendung "Reaktionsgruppe" wird ausgeführt wird, den matchmakingdienst, aber jeweils ein matchmakingdienst pro Pool aktiv ist die anderen sind passiv. Wenn bei einem ungeplanten Ausfall der aktive matchmakingdienst nicht mehr verfügbar ist, wird einer der passiven matchmakingdienste aktiv. Die Anwendung "Reaktionsgruppe" versucht, die dafür sorgen, Anrufrouting und queuing wird ohne Unterbrechung fortgesetzt. Wenn eine Übereinstimmung tätigen Dienstwechsel, werden alle Anrufe, die zum Zeitpunkt durchgestellt werden verloren. Beispielsweise ist der Übergang aufgrund der Front-End-Server ausfallen, alle Anrufe, die von dem aktiven matchmakingdienst auf, die derzeit behandelt wird sind Front-End-Server auch verloren.

## <a name="response-group-workflows"></a>Workflows für Reaktionsgruppen

Ein Workflow definiert, wie mit einem Anruf ab dem Läuten des Telefons bis zur Annahme des Anrufs verfahren wird. Der Workflow gibt die Warteschleife zum Halten des Anrufs an und legt die Routingmethode für Sammelanschlüsse oder die Fragen und Antworten für interaktive Reaktionsgruppen fest. Ein Workflow definiert außerdem Einstellungen wie die Willkommensnachricht, Wartemusik, Geschäftszeiten und Feiertage.

> [!NOTE]
> Vor dem Erstellen eines Workflows müssen Sie zuerst Agent-Gruppen und Warteschleifen erstellen, die vom Workflow verwendet werden sollen.

## <a name="management-of-response-groups"></a>Verwaltung von Reaktionsgruppen

Zwei Verwaltungsrollen stehen für die Verwaltung von reaktionsgruppen in Skype für Business Server,: Antwort Gruppenleiter und Antwort Gruppe Administrator. Reaktionsgruppenadministratoren können keinen Aspekt der alle reaktionsgruppen verwalten. Reaktionsgruppenmanager können nur bestimmte Aspekte verwalten, und nur für die Antwort, die gruppiert sie besitzen. Die Rolle Manager helfen Ihnen die Verwaltung der Kosten senken, da Sie die begrenzte Verantwortung für spezifische reaktionsgruppen keinem Benutzer delegieren können, die für Enterprise Voice aktiviert ist. Beachten Sie, dass ein Benutzer eine Antwort Gruppenmanager und einer Antwort Gruppe Administrator sein kann.

Um die Rolle Manager zu unterstützen, verwendet reaktionsgruppenanwendung einen **Workflowtyp** des verwaltet. In der folgenden Tabelle werden die verwalteten und nicht verwalteten Reaktionsgruppen beschrieben.

**Verwaltete und nicht verwaltete Reaktionsgruppen**

|**Reaktionsgruppentyp**|**Beschreibung**|
|:-----|:-----|
|Nicht verwaltet  <br/> | Nicht verwalteten Reaktionsgruppen ist kein Manager zugewiesen. Die Antwort Gruppe Administratoren mit Leserechten können diese reaktionsgruppen konfigurieren. <br/>  Mehrere nicht verwaltete Reaktionsgruppen können eine Warteschleife oder Agentgruppe gemeinsam verwenden. <br/>  Wenn Sie reaktionsgruppen von einer früheren Version zu Skype für Business Server migrieren, wird der Typ nicht verwaltet festgelegt. <br/> |
|Verwaltet  <br/> | Reaktionsgruppenadministratoren können keinen Aspekt der verwaltete reaktionsgruppen konfigurieren. <br/>  Reaktionsgruppenmanager nicht anzeigen oder Ändern von reaktionsgruppen, die ihnen nicht explizit zugewiesen sind. <br/>  Reaktionsgruppenmanager können nur einige Einstellungen der reaktionsgruppen konfigurieren, die ihnen explizit zugewiesen sind. <br/>  Verwaltete Reaktionsgruppen können keine Warteschleifen oder Agentgruppen gemeinsam mit anderen Reaktionsgruppen, weder mit verwalteten noch nicht verwalteten, verwenden. <br/> |

In der folgenden Tabelle werden die Aktionen beschrieben, die Reaktionsgruppen-Manager und der ihnen zugewiesenen reaktionsgruppen kann nicht ausgeführt werden können.

**Funktionen der Reaktionsgruppenmanager**

|**Konfiguration von:**|**Erstellen, Löschen, Konfigurieren von:**|**Nicht möglich:**|
|:-----|:-----|:-----|
| Agents <br/>  Willkommensnachrichten <br/>  Antwort Gruppenname <br/>  Beschreibung <br/>  Anzeigenummer <br/>  Geschäftszeiten <br/>  Wartemusik <br/>  Status (aktiv/inaktiv) <br/>  Workflows für Sammelanschlüsse oder für Interaktive Sprachantwort (Interactive Voice Response, IVR) <br/> | Agentgruppen <br/>  Warteschleifen <br/>  Feiertagssätze <br/> | Erstellen oder Löschen beliebiger Workflowtypen <br/>  Ändern grundlegender Reaktionsgruppeneinstellungen wie **SIP-URI**, **Telefonnummer** oder **Workflowtyp**.  <br/> |

Reaktionsgruppen-Manager können die folgenden Tools verwenden, um ihnen zugewiesenen reaktionsgruppen verwalten.

- Skype for Business Server-Systemsteuerung

    > [!NOTE]
    > Reaktionsgruppenmanager können nur reaktionsgruppeneinstellungen mit diesem Tool verwalten. Andere Skype für Business Server-Einstellungen sind nicht verfügbar für Manager.

- Konfigurationstool für Reaktionsgruppen

- Skype for Business Server-Verwaltungsshell

Reaktionsgruppe skaliert gut auf Abteilungsebene oder arbeitsgruppenumgebungen (Weitere Informationen hierzu finden Sie unter [Kapazitätsplanung für Reaktionsgruppen](https://technet.microsoft.com/library/a2459a69-1f45-4f2f-bca5-d4f442708e44.aspx)) und in vollständig neuen telefoninstallationen bereitgestellt werden können. Eingehende Anrufe aus der Enterprise-VoIP-Bereitstellung und aus dem örtlichen Telefonnetz unterstützt. Agents können Skype für Geschäftskunden, Lync 2013, Lync 2010, Lync 2010 Attendant und Lync Phone Edition die Anrufe an sie weitergeleitet.

## <a name="deployment-and-requirements"></a>Bereitstellung und Anforderungen

Die Anwendung "Reaktionsgruppe" wird automatisch aktiviert, bei der Bereitstellung von Enterprise-VoIP.

### <a name="hardware-and-software-requirements"></a>Hardware- und Softwareanforderungen

Die Anwendung "Reaktionsgruppe" hat die dieselben hardwareanforderungen sowie die betriebssystemanforderungen und die erforderliche Software als Front-End-Server.

Bei Verwendung von Windows Media Audio (WMA)-Dateien für die Reaktionsgruppe Musik und Ankündigungen müssen alle Front-End-Server oder Standard Edition-Server, auf denen die Anwendung "Reaktionsgruppe" ausgeführt werden die Windows Media Format-Laufzeitkomponente für Windows-Server installiert haben. Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server 2012 R2. Windows Media Format-Laufzeitkomponente ist für Windows Server 2008 R2 als Teil des Windows Desktop Experience installiert.

Reaktionsgruppe verwendet zur Unterstützung von Sprachsynthese und die Spracherkennung **Language packs** . Diese Sprachtechnologien werden zum Konfigurieren von Nachrichten verwendet, beispielsweise für die Willkommensnachricht oder für andere Ansagen sowie für Fragen und Antworten der interaktiven Sprachantwort (Interactive Voice Response, IVR). Standardmäßig unterstützt die 26 Sprachpakete installiert werden, wenn Sie Skype für Business Server bereitstellen.

### <a name="port-requirements"></a>Portanforderungen

Die Anwendung "Reaktionsgruppe" werden die folgenden Ports verwendet:

- **Port 5071** für SIP-überwachungsanforderungen verwendet

- **Port 8404** für die Kommunikation

    > [!NOTE]
    > Dieser Port wird für den matchmakingdienst verwendet und ist erforderlich, wenn die Anwendung "Reaktionsgruppe" in einem Pool bereitgestellt wird, das mehr als einem Front-End-Server verfügt.

   > [!NOTE]
   > Diese Ports sind Standardeinstellungen, die Sie mit dem Cmdlet **Set-CsApplicationServer** ändern können. Ausführliche Informationen zu diesem Cmdlet finden Sie unter der Skype Business Server-Verwaltungsshell-Dokumentation.

### <a name="audio-file-requirements"></a>Anforderungen für Audiodateien

Reaktionsgruppe Anwendung unterstützt WAV-Dateiformat und Windows Media-Audiodatei (WMA) format für reaktionsgruppennachrichten, wartemusik oder interaktive Antwort (IVR) Fragen.

Das Windows Media audio-Dateiformat erfordert, dass die Windows Media Format-Laufzeitkomponente auf Front-End-Servern mit Windows Server 2008 R2 und Windows Server 2008 installiert ist. Nähere Informationen dazu finden Sie weiter oben in diesem Abschnitt unter „Softwareanforderungen“.

#### <a name="supported-wave-file-formats"></a>Unterstützte WAV-Dateiformate

WAV-Dateien müssen folgenden Anforderungen entsprechen:

- 8- oder 16-Bit-Datei

- LPCM- (Linear Pulse Code Modulation), A-Law- oder µ-Law-Format

- Mono oder Stereo

- Maximal 4 MB

Um die beste Leistung zu erzielen, wird eine WAV-Datei mit den Werten 16 kHz, Mono, 16 Bit empfohlen.

#### <a name="supported-windows-media-audio-file-formats"></a>Unterstützte WMA-Dateiformate

Bei Verwendung einer WMA-Datei sollten Sie niedrige Bitraten verwenden und die Leistung Ihres Systems überprüfen, wenn dieses ausgelastet ist.

Sie können Microsoft Expression Encoder 4 verwenden, um eine Datei in das WMA-Format zu konvertieren. Informationen zum Herunterladen von Expression Encoder 4 finden Sie unter [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843).

### <a name="response-group-configuration-tool-requirements"></a>Anforderungen des Konfigurationstools für Reaktionsgruppen

Das Konfigurationstool für Reaktionsgruppen unterstützt die Kombinationen von Betriebssystemen und Webbrowsern, die in der folgenden Tabelle beschrieben.

> [!NOTE]
> 32-Bit- und 64-Bit-Versionen des jeweiligen Betriebssystems werden unterstützt. Für Internet Explorer werden nur 32-Bit-Versionen unterstützt.

**Unterstützte Betriebssysteme und Webbrowser**

|**Betriebssystem**|**Webbrowser**|
|:-----|:-----|
|Windows Vista mit Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (einheitlicher Modus)  <br/> Internet Explorer 9 (einheitlicher Modus)  <br/> |
|Windows 7  <br/> Windows 7 mit Service Pack 1  <br/> |Internet Explorer 8 (einheitlicher Modus)  <br/> Internet Explorer 9 (einheitlicher Modus)  <br/> |
|Windows Server 2008 mit Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (einheitlicher Modus)  <br/> Internet Explorer 9 (einheitlicher Modus)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 mit Service Pack 1  <br/> |Internet Explorer 8 (einheitlicher Modus)  <br/> Internet Explorer 9 (einheitlicher Modus)  <br/> |
|Windows Server 2012  <br/> ||
|Windows Server 2012 R2  <br/> ||

### <a name="response-group-agent-console"></a>Agentkonsole für Reaktionsgruppen

Die Agentkonsole unterstützt die in der folgenden Tabelle aufgeführten Kombinationen aus Betriebssystemen und Webbrowsern.

> [!NOTE]
> 32-Bit- und 64-Bit-Versionen des jeweiligen Betriebssystems werden unterstützt. Für Internet Explorer werden nur 32-Bit-Versionen unterstützt.

**Unterstützte Betriebssysteme und Webbrowser**

|**Betriebssystem**|**Webbrowser**|
|:-----|:-----|
|Windows Vista mit Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (einheitlicher Modus)  <br/> Internet Explorer 9 (einheitlicher Modus)  <br/> |
|Windows 7  <br/> Windows 7 mit Service Pack 1  <br/> |Internet Explorer 8 (einheitlicher Modus)  <br/> Internet Explorer 9 (einheitlicher Modus)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2008 mit Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (einheitlicher Modus)  <br/> Internet Explorer 9 (einheitlicher Modus)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 mit Service Pack 1  <br/> |Internet Explorer 8 (einheitlicher Modus)  <br/> Internet Explorer 9 (einheitlicher Modus)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2012  <br/> |
|Windows Server 2012 R2  <br/> |

## <a name="client-support"></a>Clientunterstützung

Die Anwendung "Reaktionsgruppe" unterstützt die folgenden Clients:

- Skype für Business-Desktopclient

- Lync 2013-desktop-client

- Lync 2010-Desktopclient

- Lync 2010-Vermittlung

- Office Communications Server 2007 R2 Attendant

- Lync Phone Edition

> [!NOTE]
> Die Anwendung "Reaktionsgruppe" wird nicht auf mobilen Lync-Clients unterstützt.

Welcher Client, den Sie verwenden können, hängt von den Typ des Benutzers "Reaktionsgruppe", die Sie:

- **Anrufer** können eine Reaktionsgruppe über einen der zuvor aufgeführten Clients und unter Verwendung eines Standardtelefons über das Festnetz anrufen.

- **Informelle agents** (Agents, die nicht an- und wieder abmelden ihren Gruppen Signieren Anrufe annehmen) können Anrufe mit Attendant, Lync oder Lync Phone Edition entgegennehmen. Informelle Agents werden bei Skype für Business Server Anmeldung mithilfe einer dieser Clients automatisch in ihren Gruppen angemeldet.

- **Formelle agents** (Agents, die die an- und wieder abmelden ihren Gruppen und Abmelden müssen Anrufe annehmen) können Anrufe annehmen, durch Verwendung von Skype für Unternehmen und Zugreifen auf den Agent-Konsole über das Menü oder mit Attendant und Zugreifen auf den Agent-Konsole direkt in Internet Explorer.

## <a name="capacity-planning"></a>Kapazitätsplanung

Die folgende Tabelle beschreibt das Reaktionsgruppe Benutzermodell, das Sie als Grundlage für Anforderungen an die kapazitätsplanung verwenden können.

> [!NOTE]
> Bei den Zahlen in der folgenden Tabelle wird davon ausgegangen, dass Sie 16-kHz-, Mono-, 16-Bit-WAV-Dateien für alle Audiodateien für Reaktionsgruppen verwenden. Wenn Sie andere Dateiformate, z. B. Windows Media Audio (WMA), einsetzen, können die Zahlen abweichen.

> [!IMPORTANT]
> Bedenken Sie bei der Kapazitätsplanung für die Notfallwiederherstellung, dass jeder Pool eines Poolpaars in der Lage sein sollte, die Arbeitslasten für alle Reaktionsgruppen in beiden Pools zu verarbeiten.

**Benutzermodell für Reaktionsgruppen**

|**Metrik**|**Pro Enterprise Edition-Pool <br/> (mit 8 Front-End-Servern)**|**Pro Standard Edition-Server**|
|:-----|:-----|:-----|
|Eingehende Anrufe pro Sekunde  <br/> |16  <br/> |2  <br/> |
|Gleichzeitige mit interaktiver Sprachantwort (IVR) oder Wartemusik (MoH) verbundene Anrufe  <br/> |480  <br/> |60  <br/> |
|Gleichzeitige anonyme Sitzungen (ohne Chat)  <br/> |224  <br/> |28  <br/> |
|Gleichzeitige anonyme Sitzungen (mit Chat)  <br/> |64  <br/> |8  <br/> |
|Aktive Agents (formell und informell)  <br/> |2400  <br/> |2400  <br/> |
|Anzahl der Sammelanschlüsse  <br/> |800  <br/> |800  <br/> |
|Anzahl der IVR-Gruppen (Verwendung der Spracherkennung)  <br/> |400  <br/> |400  <br/> |


