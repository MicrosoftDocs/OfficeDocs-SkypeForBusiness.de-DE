---
title: Planen der Reaktiongruppenanwendung in Skype for Business Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: Planen von Reaktionsgruppen in Skype for Business Server Enterprise-VoIP, mit der Sie das Anrufrouting für Benutzergruppen einrichten können. Umfasst Audiodateianforderungen.
ms.openlocfilehash: 5abf043531079e8eef707b8cdfc4efe70f8be4bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813475"
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server"></a>Planen der Reaktiongruppenanwendung in Skype for Business Server

Planen von Reaktionsgruppen in Skype for Business Server Enterprise-VoIP, mit der Sie das Anrufrouting für Benutzergruppen einrichten können. Umfasst Audiodateianforderungen.

Wenn Ihre Organisation über Gruppen von Personen verfügt, die bestimmte Arten von Anrufen beantworten und verwalten, z. B. für den Kundendienst, ein internes Helpdesk oder allgemeinen Telefonsupport für eine Abteilung, können Sie die Reaktionsgruppenanwendung bereitstellen, um diese Anruftypen zu verwalten. Die Reaktiongruppenanwendung leitet eingehende Anrufe an bestimmte Personen weiter, die als Agenten bezeichnet werden, und leitet sie in die Warteschlange ein. Sie können die Nutzung von Telefonsupportdiensten erhöhen und den Mehraufwand für die Ausführung dieser Dienste mithilfe von Reaktionsgruppen reduzieren.

Wenn ein Anrufer eine Reaktionsgruppe anruft, wird der Anruf basierend auf einem Sammelanschluss oder den interaktiven Sprachantworten des Anrufers an einen Agent weitergeleitet. Die Reaktiongruppenanwendung verwendet standardmäßige Routingmethoden für Reaktionsgruppe, um den Anruf an den nächsten verfügbaren Agent weiter zu routen. Unterstützte Anrufroutingmethoden umfassen serielles, längstes Leerlauf-, Parallel-, Roundrobin- und Telefonanrufrouting (d. h. alle Agents werden unabhängig von ihrer aktuellen Anwesenheit für jeden eingehenden Anruf gleichzeitig angerufen).

Wenn keine Agents verfügbar sind, wird der Anruf in einer Warteschleife platziert, bis ein Agent verfügbar ist. Wenn sich ein Anrufer in der Warteschleife befindet, wird Musik wiedergegeben, bis ein verfügbarer Agent den Anruf entgegennimmt. Wenn die Warteschleife voll ist oder bei einem Anruf in der Warteschleife ein Zeit geben kann, hört der Anrufer möglicherweise eine Nachricht und wird dann entweder getrennt oder an ein anderes Ziel übermittelt, z. B. eine andere Telefonnummer oder Voicemail. Wenn ein Agent den Anruf entgegennimmt, kann dem Anrufer abhängig davon, wie der Administrator die Reaktionsgruppe konfiguriert, die Identität des Agents angezeigt werden. Bei Agents kann es sich um formelle Agents handeln, die sich bei der Gruppe anmelden müssen, bevor Sie Anrufe an die Gruppe entgegennehmen können, oder um informelle Agents, die sich nicht bei der Gruppe an- und abmelden müssen, um Anrufe zu beantworten.

> [!NOTE]
> Nur lokale Benutzer können Agents sein. Wenn ein Agent von einer lokalen zu einer Onlinebereitstellung verschoben wird, werden Reaktionsgruppenanrufe nicht an diesen Agent weitergeleitet.

> [!NOTE]
> Die Reaktiongruppenanwendung verwendet einen internen Dienst namens "Match Making", um Anrufe in die Warteschlange zu stellen und nach verfügbaren Agents zu suchen. Auf jedem Computer, auf dem die Reaktiongruppenanwendung ausgeführt wird, wird der Match Making-Dienst ausgeführt, aber jeweils ist nur ein Match Making-Dienst pro Pool aktiv– die anderen sind passiv. Wenn der aktive Match Making-Dienst während eines ungeplanten Ausfalls nicht mehr verfügbar ist, wird einer der passiven Match Making-Dienste aktiviert. Die Reaktiongruppenanwendung tut ihr Bestes, um sicherzustellen, dass anrufrouting and queuing unterbrechungsfrei fortgesetzt wird. Wenn jedoch ein Match Making -Dienstübergang stattfindet, gehen alle Anrufe verloren, die zu diesem Zeitpunkt übertragen werden. Wenn der Übergang z. B. auf den Front-End-Server zurück geht, gehen alle Anrufe, die derzeit vom aktiven Match Making Service auf diesem Front-End-Server verarbeitet werden, ebenfalls verloren.

## <a name="response-group-workflows"></a>Workflows für Reaktionsgruppe

Ein Workflow definiert, wie mit einem Anruf ab dem Läuten des Telefons bis zur Annahme des Anrufs verfahren wird. Der Workflow gibt die Warteschleife zum Halten des Anrufs an und legt die Routingmethode für Sammelanschlüsse oder die Fragen und Antworten für interaktive Reaktionsgruppen fest. Ein Workflow definiert außerdem Einstellungen wie die Willkommensnachricht, Wartemusik, Geschäftszeiten und Feiertage.

> [!NOTE]
> Vor dem Erstellen eines Workflows müssen Sie zuerst Agentgruppen und Warteschleifen erstellen, die vom Workflow verwendet werden sollen.

## <a name="management-of-response-groups"></a>Verwaltung von Reaktionsgruppen

In Skype for Business Server stehen zwei Verwaltungsrollen für die Verwaltung von Reaktionsgruppen zur Verfügung: Reaktionsgruppenmanager und Reaktionsgruppenadministrator. Reaktionsgruppeadministratoren können jeden Aspekt jeder Reaktionsgruppe verwalten. Reaktionsgruppenmanager können nur bestimmte Aspekte verwalten und nur für die Reaktionsgruppen, die sie besitzen. Die Rolle "Manager" kann Ihnen helfen, Ihre Verwaltungskosten zu senken, da Sie begrenzte Zuständigkeiten für bestimmte Reaktionsgruppen an alle Benutzer delegieren können, die für die Enterprise-VoIP. Beachten Sie, dass ein Benutzer sowohl reaktionsgruppenleiter als auch reaktionsgruppenadministrator sein kann.

Zur Aufnahme der Rolle "Manager" verwendet die Reaktiongruppenanwendung einen **Workflowtyp** "Verwaltet" oder "Nicht verwaltet". In der folgenden Tabelle werden die verwalteten und nicht verwalteten Reaktionsgruppen beschrieben.

**Verwaltete und nicht verwaltete Reaktionsgruppen**

|**Reaktionsgruppentyp**|**Beschreibung**|
|:-----|:-----|
|Nicht verwaltet  <br/> | Nicht verwalteten Reaktionsgruppen ist kein Manager zugewiesen. Nur der Reaktionsgruppenadministrator kann diese Reaktionsgruppen konfigurieren. <br/>  Mehrere nicht verwaltete Reaktionsgruppen können eine Warteschleife oder Agentgruppe gemeinsam verwenden. <br/>  Wenn Sie Reaktionsgruppen von einer früheren Version zu Skype for Business Server migrieren, wird der Typ auf "Nicht verwaltet" festgelegt. <br/> |
|Verwaltet  <br/> | Reaktionsgruppenadministratoren können jeden Aspekt verwalteter Reaktionsgruppen konfigurieren. <br/>  Reaktionsgruppenmanager können keine Reaktionsgruppen anzeigen oder ändern, die ihnen nicht explizit zugewiesen sind. <br/>  Reaktionsgruppenmanager können nur einige Einstellungen für die Reaktionsgruppen konfigurieren, die ihnen explizit zugewiesen sind. <br/>  Verwaltete Reaktionsgruppen können keine Warteschleifen oder Agentgruppen gemeinsam mit anderen Reaktionsgruppen, weder mit verwalteten noch nicht verwalteten, verwenden. <br/> |

In der folgenden Tabelle werden die Aktionen beschrieben, die Reaktionsgruppenmanager für die ihnen zugewiesenen Reaktionsgruppen ausführen können und nicht.

**Funktionen der Reaktionsgruppenmanager**

|**Konfiguration von:**|**Erstellen, Löschen, Konfigurieren von:**|**Kann nicht:**|
|:-----|:-----|:-----|
| Agents <br/>  Willkommensnachrichten <br/>  Name der Reaktionsgruppe <br/>  Beschreibung <br/>  Anzeigenummer <br/>  Geschäftszeiten <br/>  Wartemusik <br/>  Status (aktiv/inaktiv) <br/>  Workflows für Sammelanschlüsse oder für Interaktive Sprachantwort (Interactive Voice Response, IVR) <br/> | Agentgruppen <br/>  Warteschlangen <br/>  Feiertagssätze <br/> | Erstellen oder Löschen beliebiger Workflowtypen <br/>  Ändern grundlegender Reaktionsgruppeneinstellungen, wie: **SIP-URI**, **Telefonnummer** oder **Workflowtyp**.  <br/> |

Reaktionsgruppenmanager können die folgenden Tools verwenden, um ihre festgelegten Reaktionsgruppen zu verwalten.

- Skype for Business Server-Systemsteuerung

    > [!NOTE]
    > Reaktiongruppenmanager können reaktionsgruppeneinstellungen nur mit diesem Tool verwalten. Andere Skype for Business Server-Einstellungen sind für Manager nicht verfügbar.

- Reaktiongruppenkonfigurationstool

- Skype for Business Server-Verwaltungsshell

Reaktionsgruppe kann gut auf Abteilungs- oder Arbeitsgruppenumgebungen skaliert werden (weitere Informationen finden Sie unter Kapazitätsplanung für [Reaktionsgruppe)](https://technet.microsoft.com/library/a2459a69-1f45-4f2f-bca5-d4f442708e44.aspx)und kann in völlig neuen Telefonieinstallationen bereitgestellt werden. Es unterstützt eingehende Anrufe aus der Enterprise-VoIP und aus dem lokalen Netzbetreibernetzwerk. Agents können Skype for Business, Lync 2013, Lync 2010, Lync 2010 Attendant oder Lync Phone Edition verwenden, um die an sie gerouteten Anrufe entgegen zu nehmen.

## <a name="deployment-and-requirements"></a>Bereitstellung und Anforderungen

Die Reaktiongruppenanwendung wird automatisch aktiviert, wenn Sie Enterprise-VoIP.

### <a name="hardware-and-software-requirements"></a>Hardware- und Softwareanforderungen

Für die Reaktionsgruppe gelten dieselben Hardwareanforderungen, Betriebssystemanforderungen und Softwarevoraussetzungen wie für Front-End-Server.

Wenn Sie Windows Media Audio (.wma)-Dateien für Reaktionsgruppe Musik und Ansagen verwenden, muss auf allen Front-End-Servern oder Standard Editions-Servern, auf denen die Reaktionsgruppe ausgeführt wird, die Windows Media Format Runtime für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server 2012 R2 installiert sein. For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.

Reaktionsgruppe verwendet **Sprachpakete zur** Unterstützung von Text-zu-Sprache und Spracherkennung. Diese Sprachtechnologien werden zum Konfigurieren von Nachrichten verwendet, beispielsweise für die Willkommensnachricht oder für andere Ansagen sowie für Fragen und Antworten der interaktiven Sprachantwort (Interactive Voice Response, IVR). Standardmäßig werden die 26 unterstützten Sprachpakete installiert, wenn Sie Skype for Business Server bereitstellen.

### <a name="port-requirements"></a>Portanforderungen

Die Reaktiongruppenanwendung verwendet die folgenden Ports:

- **Port 5071**   für SIP-Abhöranforderungen

- **Port 8404 für**   die Kommunikation zwischen Den Servern

    > [!NOTE]
    > Dieser Port wird für den Match Making Service verwendet und ist erforderlich, wenn die Reaktionsgruppe in einem Pool bereitgestellt wird, der über mehrere Front-End-Server verfügt.

   > [!NOTE]
   > Diese Ports sind Standardeinstellungen, die Sie mit dem Cmdlet **Set-CsApplicationServer** ändern können. Ausführliche Informationen zu diesem Cmdlet finden Sie in der Dokumentation zur Skype for Business Server-Verwaltungsshell.

### <a name="audio-file-requirements"></a>Anforderungen für Audiodateien

Die Reaktiongruppenanwendung unterstützt das Wav-Dateiformat (Wave) und das Windows Media Audio (WMA)-Dateiformat für Reaktionsgruppe-Nachrichten, Wartemusik oder Interaktive Sprachantwort (Interactive Voice Response, IVR).

Für das Windows Media-Audiodateiformat muss die Windows Media Format Runtime auf Front-End-Servern mit Windows Server 2008 R2 Windows Server 2008 installiert sein. Weitere Informationen finden Sie unter "Softwareanforderungen" weiter oben in diesem Abschnitt.

#### <a name="supported-wave-file-formats"></a>Unterstützte WAV-Dateiformate

Alle Wavedateien müssen die folgenden Anforderungen erfüllen:

- 8-Bit- oder 16-Bit-Datei

- LPCM- (Linear Pulse Code Modulation), A-Law- oder µ-Law-Format

- Mono oder Stereo

- 4 MB oder weniger

Für eine optimale Leistung bei Wavedateien wird eine Mono-WAV-Datei mit 16 kHz und 16 Bit empfohlen.

#### <a name="supported-windows-media-audio-file-formats"></a>Unterstützte WMA-Dateiformate

Wenn Sie eine Windows Media-Audiodatei verwenden, sollten Sie niedrige Bitraten verwenden und die Leistung Des Systems unter Last überprüfen.

Sie können Microsoft Expression Encoder 4 verwenden, um einen Datei in das WMA-Format zu konvertieren. Informationen zum Herunterladen von Expression Encoder 4 finden Sie unter [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843) .

### <a name="response-group-configuration-tool-requirements"></a>Anforderungen des Reaktiongruppenkonfigurationstools

Das Reaktiongruppenkonfigurationstool unterstützt die in der folgenden Tabelle beschriebenen Kombinationen von Betriebssystemen und Webbrowsern.

> [!NOTE]
> 32-Bit- oder 64-Bit-Versionen der Betriebssysteme werden unterstützt. Nur 32-Bit-Versionen von Internet Explorer werden unterstützt.

**Unterstützte Betriebssysteme und Webbrowser**

|**Betriebssystem**|**Webbrowser**|
|:-----|:-----|
|Windows Vista mit Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (nativer Modus)  <br/> Internet Explorer 9 (nativer Modus)  <br/> |
|Windows 7  <br/> Windows 7 mit Service Pack 1  <br/> |Internet Explorer 8 (nativer Modus)  <br/> Internet Explorer 9 (nativer Modus)  <br/> |
|Windows Server 2008 mit Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (nativer Modus)  <br/> Internet Explorer 9 (nativer Modus)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 mit Service Pack 1  <br/> |Internet Explorer 8 (nativer Modus)  <br/> Internet Explorer 9 (nativer Modus)  <br/> |
|Windows Server 2012  <br/> ||
|Windows Server 2012 R2  <br/> ||

### <a name="response-group-agent-console"></a>Response Group Agent Console

Die Agentkonsole unterstützt die in der folgenden Tabelle beschriebenen Kombinationen von Betriebssystemen und Webbrowsern.

> [!NOTE]
> 32-Bit- oder 64-Bit-Versionen der Betriebssysteme werden unterstützt. Nur 32-Bit-Versionen von Internet Explorer werden unterstützt.

**Unterstützte Betriebssysteme und Webbrowser**

|**Betriebssystem**|**Webbrowser**|
|:-----|:-----|
|Windows Vista mit Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (nativer Modus)  <br/> Internet Explorer 9 (nativer Modus)  <br/> |
|Windows 7  <br/> Windows 7 mit Service Pack 1  <br/> |Internet Explorer 8 (nativer Modus)  <br/> Internet Explorer 9 (nativer Modus)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2008 mit Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (nativer Modus)  <br/> Internet Explorer 9 (nativer Modus)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 mit Service Pack 1  <br/> |Internet Explorer 8 (nativer Modus)  <br/> Internet Explorer 9 (nativer Modus)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2012  <br/> |
|Windows Server 2012 R2  <br/> |

## <a name="client-support"></a>Clientunterstützung

Die Reaktiongruppenanwendung unterstützt die folgenden Clients:

- Skype for Business-Desktopclient

- Lync 2013-Desktopclient

- Lync 2010-Desktopclient

- Lync 2010 Attendant

- Office Communications Server 2007 R2 Attendant

- Lync Phone Edition

> [!NOTE]
> Die Reaktiongruppenanwendung wird auf mobilen Lync-Clients nicht unterstützt.

Der spezifische Client, den Sie verwenden können, hängt vom Typ des Reaktionsgruppebenutzers ab, den Sie sind:

- **Anrufer** können eine Reaktionsgruppe über einen der zuvor aufgeführten Clients und unter Verwendung eines Standardtelefons über das Festnetz anrufen.

- **Informelle Agents** (Agents, die sich nicht bei ihren Gruppen anmelden und sich abmelden, um Anrufe zu akzeptieren) können Anrufe mithilfe von Attendant, Lync oder Lync Phone Edition annehmen. Informelle Agents werden automatisch bei ihren Gruppen angemeldet, wenn sie sich mit einem dieser Clients bei Skype for Business Server anmelden.

- **Formelle** Agents (Agents, die sich bei ihren Gruppen an- und abmelden müssen, um Anrufe zu akzeptieren) können Anrufe annehmen, indem sie Skype for Business verwenden und über das Menüelement auf die Agentkonsole zugreifen, oder indem sie die Telefon attendant verwenden und direkt über Internet Explorer auf die Agentkonsole zugreifen.

## <a name="capacity-planning"></a>Kapazitätsplanung

In der folgenden Tabelle wird das Benutzermodell der Reaktionsgruppe beschrieben, das Sie als Grundlage für die Kapazitätsplanungsanforderungen verwenden können.

> [!NOTE]
> Bei den Zahlen in der folgenden Tabelle wird davon ausgegangen, dass Sie 16-kHz-, Mono-, 16-Bit-WAV-Dateien für alle Audiodateien für Reaktionsgruppen verwenden. Wenn Sie andere Dateiformate, z. B. Windows Media Audio (WMA), einsetzen, können die Zahlen abweichen.

> [!IMPORTANT]
> Bedenken Sie bei der Kapazitätsplanung für die Notfallwiederherstellung, dass jeder Pool eines Poolpaars in der Lage sein sollte, die Arbeitslasten für alle Reaktionsgruppen in beiden Pools zu verarbeiten.

**Benutzermodell für Reaktionsgruppen**

|**Metrik**|**Pro Enterprise Edition-Pool  <br/> (mit 8 Front-End-Servern)**|**Pro Standard Edition-Server**|
|:-----|:-----|:-----|
|Eingehende Anrufe pro Sekunde  <br/> |16   <br/> |2   <br/> |
|Gleichzeitige mit interaktiver Sprachantwort (IVR) oder Wartemusik (MoH) verbundene Anrufe  <br/> |480  <br/> |60  <br/> |
|Gleichzeitige anonyme Sitzungen (ohne Instant Messaging)  <br/> |224  <br/> |28  <br/> |
|Gleichzeitige anonyme Sitzungen (mit Instant Messaging)  <br/> |64  <br/> |8   <br/> |
|Aktive Agents (formell und informell)  <br/> |2400  <br/> |2400  <br/> |
|Anzahl der Sammelanschlüsse  <br/> |800  <br/> |800  <br/> |
|Anzahl der IVR-Gruppen (Verwendung der Spracherkennung)  <br/> |400  <br/> |400  <br/> |


