---
title: Planen der Reaktionsgruppenanwendung in Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: Planung von Reaktionsgruppen in Skype for Business Server Enterprise-VoIP, mit der Sie Anrufweiterleitung für Benutzergruppen einrichten können. Umfasst Audiodateianforderungen.
ms.openlocfilehash: c7a34b63cfd01e8958c85f459415e3830d0eb235
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392407"
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server"></a>Planen der Reaktionsgruppenanwendung in Skype for Business Server

Planung von Reaktionsgruppen in Skype for Business Server Enterprise-VoIP, mit der Sie Anrufweiterleitung für Benutzergruppen einrichten können. Umfasst Audiodateianforderungen.

Wenn Ihre Organisation über Gruppen von Personen verfügt, die bestimmte Arten von Anrufen annehmen und verwalten, z. B. für den Kundendienst, ein internes Helpdesk oder allgemeine Telefonunterstützung für eine Abteilung, können Sie die Reaktionsgruppenanwendung bereitstellen, um diese Arten von Anrufen zu verwalten. Die Reaktionsgruppenanwendung leitet eingehende Anrufe an bestimmte Personen, die als Agents bezeichnet werden, weiter und stellt sie in die Warteschlange. Sie können die Verwendung von Telefonsupportdiensten erhöhen und den Mehraufwand für die Ausführung dieser Dienste mithilfe von Reaktionsgruppen reduzieren.

Wenn ein Anrufer eine Reaktionsgruppe anruft, wird der Anruf basierend auf einem Sammelanschluss oder den interaktiven Sprachantworten des Anrufers an einen Agent weitergeleitet. Die Reaktionsgruppenanwendung verwendet standardmäßige Routingmethoden für Reaktionsgruppen, um den Anruf an den nächsten verfügbaren Agent weiterzuleiten. Zu den unterstützten Anrufweiterleitungsmethoden gehören serielles, längstes Leerlauf-, Parallel-, Roundrobin- und Attendant-Routing (das heißt, alle Agents werden für jeden eingehenden Anruf gleichzeitig aufgerufen, unabhängig von ihrer aktuellen Anwesenheit).

Wenn keine Agents verfügbar sind, wird der Anruf in einer Warteschleife platziert, bis ein Agent verfügbar ist. Wenn sich ein Anrufer in der Warteschleife befindet, wird Musik wiedergegeben, bis ein verfügbarer Agent den Anruf entgegennimmt. Wenn die Warteschleife voll ist oder wenn der Anruf in der Warteschleife einen Zeitüberschreitung aufweist, hört der Anrufer möglicherweise eine Nachricht und wird entweder getrennt oder an ein anderes Ziel weitergeleitet, z. B. eine andere Telefonnummer oder Voicemail. Wenn ein Agent den Anruf entgegennimmt, kann dem Anrufer abhängig davon, wie der Administrator die Reaktionsgruppe konfiguriert, die Identität des Agents angezeigt werden. Bei Agents kann es sich um formelle Agents handeln, die sich bei der Gruppe anmelden müssen, bevor Sie Anrufe an die Gruppe entgegennehmen können, oder um informelle Agents, die sich nicht bei der Gruppe an- und abmelden müssen, um Anrufe zu beantworten.

> [!NOTE]
> Nur lokale Benutzer können Agents sein. Wenn ein Agent von einer lokalen zu einer Onlinebereitstellung verschoben wird, werden Reaktionsgruppenanrufe nicht an diesen Agent weitergeleitet.

> [!NOTE]
> Die Reaktionsgruppenanwendung verwendet einen internen Dienst namens "Match Making", um Anrufe in die Warteschlange zu stellen und verfügbare Agents zu finden. Jeder Computer, auf dem die Reaktionsgruppenanwendung ausgeführt wird, führt den Match Making-Dienst aus, aber nur ein Match Making-Dienst pro Pool ist zu einem zeitpunkt aktiv – die anderen sind passiv. Wenn der aktive Match Making-Dienst während eines ungeplanten Ausfalls nicht mehr verfügbar ist, wird einer der passiven Match Making-Dienste aktiv. Die Reaktionsgruppenanwendung bietet ihr Bestes, um sicherzustellen, dass Anrufweiterleitung und Warteschlangen unterbrechungsfrei fortgesetzt werden. Wenn jedoch ein Übergang zum Match Making-Dienst erfolgt, gehen alle Anrufe verloren, die sich zu diesem Zeitpunkt in der Übertragung befinden. Wenn der Übergang beispielsweise darauf zurückzuführen ist, dass der Front-End-Server abläuft, gehen auch alle Anrufe verloren, die derzeit vom aktiven Match Making-Dienst auf diesem Front-End-Server verarbeitet werden.

## <a name="response-group-workflows"></a>Workflows für Reaktionsgruppen

Ein Workflow definiert, wie mit einem Anruf ab dem Läuten des Telefons bis zur Annahme des Anrufs verfahren wird. Der Workflow gibt die Warteschleife zum Halten des Anrufs an und legt die Routingmethode für Sammelanschlüsse oder die Fragen und Antworten für interaktive Reaktionsgruppen fest. Ein Workflow definiert außerdem Einstellungen wie die Willkommensnachricht, Wartemusik, Geschäftszeiten und Feiertage.

> [!NOTE]
> Vor dem Erstellen eines Workflows müssen Sie zuerst Agentgruppen und Warteschleifen erstellen, die vom Workflow verwendet werden sollen.

## <a name="management-of-response-groups"></a>Verwaltung von Reaktionsgruppen

In Skype for Business Server stehen zwei Verwaltungsrollen für die Verwaltung von Reaktionsgruppen zur Verfügung: Reaktionsgruppen-Manager und Reaktionsgruppenadministrator. Reaktionsgruppenadministratoren können jeden Aspekt jeder Reaktionsgruppe verwalten. Reaktionsgruppenmanager können nur bestimmte Aspekte und nur für die Reaktionsgruppen verwalten, die sie besitzen. Die Managerrolle kann Ihnen helfen, Ihre Verwaltungskosten zu senken, da Sie begrenzte Zuständigkeiten für bestimmte Reaktionsgruppen an jeden Benutzer delegieren können, der für Enterprise-VoIP aktiviert ist. Beachten Sie, dass ein Benutzer sowohl ein Reaktionsgruppen-Manager als auch ein Reaktionsgruppenadministrator sein kann.

Um der Managerrolle gerecht zu werden, verwendet die Reaktionsgruppenanwendung einen **Workflowtyp** "Verwaltet" oder "Nicht verwaltet". In der folgenden Tabelle werden die verwalteten und nicht verwalteten Reaktionsgruppen beschrieben.

**Verwaltete und nicht verwaltete Reaktionsgruppen**

|**Reaktionsgruppentyp**|**Beschreibung**|
|:-----|:-----|
|Nicht verwaltet  <br/> | Nicht verwalteten Reaktionsgruppen ist kein Manager zugewiesen. Nur der Reaktionsgruppenadministrator kann diese Reaktionsgruppen konfigurieren. <br/>  Mehrere nicht verwaltete Reaktionsgruppen können eine Warteschleife oder Agentgruppe gemeinsam verwenden. <br/>  Wenn Sie Reaktionsgruppen von einer früheren Version zu Skype for Business Server migrieren, wird der Typ auf "Nicht verwaltet" festgelegt. <br/> |
|Verwaltet  <br/> | Reaktionsgruppenadministratoren können jeden Aspekt verwalteter Reaktionsgruppen konfigurieren. <br/>  Reaktionsgruppenmanager können keine Reaktionsgruppen anzeigen oder ändern, die ihnen nicht explizit zugewiesen sind. <br/>  Reaktionsgruppenmanager können nur einige Einstellungen für die Reaktionsgruppen konfigurieren, die ihnen explizit zugewiesen sind. <br/>  Verwaltete Reaktionsgruppen können keine Warteschleifen oder Agentgruppen gemeinsam mit anderen Reaktionsgruppen, weder mit verwalteten noch nicht verwalteten, verwenden. <br/> |

In der folgenden Tabelle werden die Aktionen beschrieben, die Reaktionsgruppenmanager für die ihnen zugewiesenen Reaktionsgruppen ausführen können und können.

**Funktionen der Reaktionsgruppenmanager**

|**Konfiguration von:**|**Erstellen, Löschen, Konfigurieren von:**|**Kann nicht:**|
|:-----|:-----|:-----|
| Agents <br/>  Willkommensnachrichten <br/>  Name der Reaktionsgruppe <br/>  Beschreibung <br/>  Anzeigenummer <br/>  Geschäftszeiten <br/>  Wartemusik <br/>  Status (aktiv/inaktiv) <br/>  Workflows für Sammelanschlüsse oder für Interaktive Sprachantwort (Interactive Voice Response, IVR) <br/> | Agentgruppen <br/>  Warteschlangen <br/>  Feiertagssätze <br/> | Erstellen oder Löschen beliebiger Workflowtypen <br/>  Ändern grundlegender Reaktionsgruppeneinstellungen, wie: **SIP-URI**, **Telefonnummer** oder **Workflowtyp**.  <br/> |

Reaktionsgruppenmanager können die folgenden Tools verwenden, um ihre festgelegten Reaktionsgruppen zu verwalten.

- Skype for Business Server-Systemsteuerung

    > [!NOTE]
    > Reaktionsgruppenmanager können Reaktionsgruppeneinstellungen nur mit diesem Tool verwalten. Andere Skype for Business Server-Einstellungen sind für Manager nicht verfügbar.

- Konfigurationstool für Reaktionsgruppen

- Skype for Business Server-Verwaltungsshell

Reaktionsgruppen können gut auf Abteilungs- oder Arbeitsgruppenumgebungen skaliert werden (ausführliche Informationen finden Sie unter [Kapazitätsplanung für Reaktionsgruppen](/previous-versions/office/lync-server-2013/lync-server-2013-capacity-planning-for-response-group)) und können in völlig neuen Telefonieinstallationen bereitgestellt werden. Es unterstützt eingehende Anrufe aus der Enterprise-VoIP-Bereitstellung und aus dem lokalen Netzbetreibernetzwerk. Agents können Skype for Business, Lync 2013, Lync 2010, Lync 2010 Attendant oder Lync Telefon Edition verwenden, um die an sie weitergeleiteten Anrufe zu tätigen.

## <a name="deployment-and-requirements"></a>Bereitstellung und Anforderungen

Die Reaktionsgruppenanwendung wird automatisch aktiviert, wenn Sie Enterprise-VoIP bereitstellen.

### <a name="hardware-and-software-requirements"></a>Hardware- und Softwareanforderungen

Die Reaktionsgruppenanwendung hat die gleichen Hardwareanforderungen, Betriebssystemanforderungen und Softwarevoraussetzungen wie Front-End-Server.

Wenn Sie Windows Medienaudiodateien (WMA) für Reaktionsgruppenmusik und Ankündigungen verwenden, muss auf allen Front-End-Servern oder Standardeditionsservern, auf denen die Reaktionsgruppenanwendung ausgeführt wird, die Windows Media Format Runtime für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server 2012 R2. For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.

Reaktionsgruppe verwendet **Sprachpakete** zur Unterstützung von Text-zu-Sprache und Spracherkennung. Diese Sprachtechnologien werden zum Konfigurieren von Nachrichten verwendet, beispielsweise für die Willkommensnachricht oder für andere Ansagen sowie für Fragen und Antworten der interaktiven Sprachantwort (Interactive Voice Response, IVR). Standardmäßig werden die 26 unterstützten Sprachpakete installiert, wenn Sie Skype for Business Server bereitstellen.

### <a name="port-requirements"></a>Portanforderungen

Die Reaktionsgruppenanwendung verwendet die folgenden Ports:

- **Port 5071**   für SIP-Überwachungsanforderungen

- **Port 8404**   für die Kommunikation zwischen Servern

    > [!NOTE]
    > Dieser Port wird für den Match Making-Dienst verwendet und ist erforderlich, wenn die Reaktionsgruppenanwendung in einem Pool mit mehr als einem Front-End-Server bereitgestellt wird.

   > [!NOTE]
   > Diese Ports sind Standardeinstellungen, die Sie mit dem Cmdlet **Set-CsApplicationServer** ändern können. Ausführliche Informationen zu diesem Cmdlet finden Sie in der Dokumentation zur Skype for Business Server Verwaltungsshell.

### <a name="audio-file-requirements"></a>Anforderungen für Audiodateien

Die Reaktionsgruppenanwendung unterstützt das Wav-Dateiformat (Wave) und Windows WMA-Dateiformat (Media Audio) für Reaktionsgruppennachrichten, Wartemusik oder IVR-Fragen (Interactive Voice Response).

Das Windows Medienaudiodateiformat erfordert, dass die Windows Media Format Runtime auf Front-End-Servern installiert ist, auf denen Windows Server 2008 R2 und Windows Server 2008 ausgeführt wird. Weitere Informationen finden Sie weiter oben in diesem Abschnitt unter "Softwareanforderungen".

#### <a name="supported-wave-file-formats"></a>Unterstützte WAV-Dateiformate

Alle Wavedateien müssen die folgenden Anforderungen erfüllen:

- 8-Bit- oder 16-Bit-Datei

- LPCM- (Linear Pulse Code Modulation), A-Law- oder µ-Law-Format

- Mono oder Stereo

- 4 MB oder weniger

Für eine optimale Leistung bei Wavedateien wird eine Mono-WAV-Datei mit 16 kHz und 16 Bit empfohlen.

#### <a name="supported-windows-media-audio-file-formats"></a>Unterstützte WMA-Dateiformate

Wenn Sie eine Windows Medienaudiodatei verwenden, erwägen Sie die Verwendung niedriger Bitraten, und überprüfen Sie die Leistung Ihres Systems unter Last.

Sie können Microsoft Expression Encoder 4 verwenden, um einen Datei in das WMA-Format zu konvertieren. Informationen zum Herunterladen von Expression Encoder 4 finden Sie unter [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843).

### <a name="response-group-configuration-tool-requirements"></a>Konfigurationstoolanforderungen für Reaktionsgruppen

Das Konfigurationstool für Reaktionsgruppen unterstützt die Kombinationen aus Betriebssystemen und Webbrowsern, die in der folgenden Tabelle beschrieben sind.

> [!NOTE]
> 32-Bit- oder 64-Bit-Versionen der Betriebssysteme werden unterstützt. Es werden nur 32-Bit-Versionen von Internet Explorer unterstützt.

**Unterstützte Betriebssysteme und Webbrowser**

|**Betriebssystem**|**Webbrowser**|
|:-----|:-----|
|Windows Vista mit Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (nativer Modus)  <br/> Internet Explorer 9 (nativer Modus)  <br/> |
|Windows 7  <br/> Windows 7 mit Service Pack 1  <br/> |Internet Explorer 8 (nativer Modus)  <br/> Internet Explorer 9 (nativer Modus)  <br/> |
|Windows Server 2008 mit Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (nativer Modus)  <br/> Internet Explorer 9 (nativer Modus)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 mit Service Pack 1  <br/> |Internet Explorer 8 (nativer Modus)  <br/> Internet Explorer 9 (nativer Modus)  <br/> |
|Windows Server 2012  <br/> ||
|Windows Server 2012 R2  <br/> ||

### <a name="response-group-agent-console"></a>Reaktionsgruppen-Agent-Konsole

Die Agentkonsole unterstützt die Kombinationen aus Betriebssystemen und Webbrowsern, die in der folgenden Tabelle beschrieben werden.

> [!NOTE]
> 32-Bit- oder 64-Bit-Versionen der Betriebssysteme werden unterstützt. Es werden nur 32-Bit-Versionen von Internet Explorer unterstützt.

**Unterstützte Betriebssysteme und Webbrowser**

|**Betriebssystem**|**Webbrowser**|
|:-----|:-----|
|Windows Vista mit Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (nativer Modus)  <br/> Internet Explorer 9 (nativer Modus)  <br/> |
|Windows 7  <br/> Windows 7 mit Service Pack 1  <br/> |Internet Explorer 8 (nativer Modus)  <br/> Internet Explorer 9 (nativer Modus)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2008 mit Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (nativer Modus)  <br/> Internet Explorer 9 (nativer Modus)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 mit Service Pack 1  <br/> |Internet Explorer 8 (nativer Modus)  <br/> Internet Explorer 9 (nativer Modus)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2012  <br/> |
|Windows Server 2012 R2  <br/> |

## <a name="client-support"></a>Clientunterstützung

Die Reaktionsgruppenanwendung unterstützt die folgenden Clients:

- Skype for Business-Desktopclient

- Lync 2013-Desktopclient

- Lync 2010-Desktopclient

- Lync 2010 Attendant

- Office Communications Server 2007 R2 Attendant

- Lync Phone Edition

> [!NOTE]
> Die Reaktionsgruppenanwendung wird auf mobilen Lync-Clients nicht unterstützt.

Der spezifische Client, den Sie verwenden können, hängt vom Typ des Reaktionsgruppenbenutzers ab, der Sie sind:

- **Anrufer** können eine Reaktionsgruppe über einen der zuvor aufgeführten Clients und unter Verwendung eines Standardtelefons über das Festnetz anrufen.

- **Informelle Agents** (Agents, die sich nicht bei ihren Gruppen anmelden und sich nicht abmelden, um Anrufe entgegenzunehmen) können Anrufe über die Telefonzentrale, Lync oder Lync Telefon Edition annehmen. Informelle Agents werden automatisch bei ihren Gruppen angemeldet, wenn sie sich mit einem dieser Clients bei Skype for Business Server anmelden.

- **Formale Agents** (Agents, die sich bei ihren Gruppen anmelden müssen, um Anrufe entgegenzunehmen) können Anrufe annehmen, indem sie Skype for Business verwenden und über das Menüelement auf die Agentkonsole zugreifen oder indem sie die Telefonzentrale verwenden und direkt über Internet Explorer auf die Agentkonsole zugreifen.

## <a name="capacity-planning"></a>Kapazitätsplanung

In der folgenden Tabelle wird das Reaktionsgruppenbenutzermodell beschrieben, das Sie als Grundlage für die Anforderungen an die Kapazitätsplanung verwenden können.

> [!NOTE]
> Bei den Zahlen in der folgenden Tabelle wird davon ausgegangen, dass Sie 16-kHz-, Mono-, 16-Bit-WAV-Dateien für alle Audiodateien für Reaktionsgruppen verwenden. Wenn Sie andere Dateiformate, z. B. Windows Media Audio (WMA), einsetzen, können die Zahlen abweichen.

> [!IMPORTANT]
> Bedenken Sie bei der Kapazitätsplanung für die Notfallwiederherstellung, dass jeder Pool eines Poolpaars in der Lage sein sollte, die Arbeitslasten für alle Reaktionsgruppen in beiden Pools zu verarbeiten.

**Benutzermodell für Reaktionsgruppen**

|**Metrik**|**Pro Enterprise Edition Pool <br/> (mit 8 Front-End-Servern)**|**Pro Standard Edition-Server**|
|:-----|:-----|:-----|
|Eingehende Anrufe pro Sekunde  <br/> |16  <br/> |2  <br/> |
|Gleichzeitige mit interaktiver Sprachantwort (IVR) oder Wartemusik (MoH) verbundene Anrufe  <br/> |480  <br/> |60  <br/> |
|Gleichzeitige anonyme Sitzungen (ohne Instant Messaging)  <br/> |224  <br/> |28  <br/> |
|Gleichzeitige anonyme Sitzungen (mit Instant Messaging)  <br/> |64  <br/> |8   <br/> |
|Aktive Agents (formell und informell)  <br/> |2400  <br/> |2400  <br/> |
|Anzahl der Sammelanschlüsse  <br/> |800  <br/> |800  <br/> |
|Anzahl der IVR-Gruppen (Verwendung der Spracherkennung)  <br/> |400  <br/> |400  <br/> |