---
title: Planen der Antwortgruppen Anwendung in Skype for Business Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: Planen von Reaktionsgruppen in Skype for Business Server Enterprise Voice, mit der Sie Anrufweiterleitung für Benutzergruppen einrichten können. Es konfiguriert, was mit nicht zugewiesenen Telefonnummern in Ihren Organisationen passiert und beinhaltet Audiodateianforderungen.
ms.openlocfilehash: ec0bbe0e02fd7b4f027f8c2e57784c402aa0f039
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802485"
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server"></a>Planen der Antwortgruppen Anwendung in Skype for Business Server

Planen von Reaktionsgruppen in Skype for Business Server Enterprise Voice, mit der Sie Anrufweiterleitung für Benutzergruppen einrichten können. Es konfiguriert, was mit nicht zugewiesenen Telefonnummern in Ihren Organisationen passiert und beinhaltet Audiodateianforderungen.

Wenn Ihre Organisation über Gruppen von Personen verfügt, die bestimmte Anrufarten beantworten und verwalten, beispielsweise für den Kundendienst, einen internen Helpdesk oder allgemeinen Telefonsupport für eine Abteilung, können Sie die Anwendung zur Reaktionsgruppe bereitstellen, um diese Anrufarten zu verwalten. Die Antwortgruppen Anwendung leitet eingehende Anrufe an bezeichnete Personen weiter, die als Agents bezeichnet werden. Sie können die Nutzung von Telefonsupport Diensten erhöhen und den Aufwand für die Ausführung dieser Dienste mithilfe von Reaktionsgruppen reduzieren.

Wenn ein Anrufer eine Reaktionsgruppe anruft, wird der Anruf basierend auf einem Sammelanschluss oder den interaktiven Sprachantworten des Anrufers an einen Agent weitergeleitet. Die reaktionsgruppenanwendung verwendet standardmäßige Reaktionsgruppen-Routingmethoden, um den Anruf an den nächsten verfügbaren Agenten weiterzuleiten. Die Methoden zur Anrufweiterleitung umfassen serielles, Longest-Idle-, paralleles, Roundrobin- sowie das neue Routing über die Telefonzentrale (hier werden bei einem eingehenden Anruf alle Agents gleichzeitig angerufen, unabhängig von ihrem aktuellen Anwesenheitsstatus).

Wenn keine Agents verfügbar sind, wird der Anruf in einer Warteschleife platziert, bis ein Agent verfügbar ist. Wenn sich ein Anrufer in der Warteschleife befindet, wird Musik wiedergegeben, bis ein verfügbarer Agent den Anruf entgegennimmt. Wenn die Warteschleife belegt ist oder für einen Anruf ein Timeout auftritt, während er sich in der Warteschleife befindet, kann für den Anrufer eine Nachricht wiedergegeben werden und anschließend wird der Anrufer entweder getrennt oder an ein anderes Ziel wie beispielsweise eine andere Telefonnummer oder Voicemail übergeben. Wenn ein Agent den Anruf entgegennimmt, kann dem Anrufer abhängig davon, wie der Administrator die Reaktionsgruppe konfiguriert, die Identität des Agents angezeigt werden. Bei Agents kann es sich um formelle Agents handeln, die sich bei der Gruppe anmelden müssen, bevor sie Anrufe an die Gruppe entgegennehmen können, oder um informelle Agents, die sich nicht bei der Gruppe an- und abmelden müssen, um Anrufe zu beantworten.

> [!NOTE]
> Nur lokale Benutzer können Agents sein. Wenn ein Agent von lokal in Online verschoben wird, werden keine Antwortgruppen Aufrufe an diesen Agenten weitergeleitet.

> [!NOTE]
> Die Antwortgruppen Anwendung verwendet einen internen Dienst, der als Übereinstimmungs Erstellung bezeichnet wird, um Anrufe in die Warteschlange zu stellen und verfügbare Agents zu finden. Jeder Computer, auf dem die reaktionsgruppenanwendung ausgeführt wird, führt den Übereinstimmungs Dienst aus, aber es ist jeweils nur ein Übereinstimmungs Dienst pro Pool aktiv – die anderen sind passiv. Wenn der aktive Übereinstimmungs Dienst während eines ungeplanten Ausfalls nicht mehr verfügbar ist, wird einer der passiven Übereinstimmungs Dienste aktiviert. Die Response Group-Anwendung tut ihr Bestes, um sicherzustellen, dass Anrufweiterleitung und-Warteschlangen unterbrechungsfrei fortgesetzt werden. Wenn jedoch eine Übereinstimmung zum Dienst Übergang eintritt, gehen alle Anrufe, die zu diesem Zeitpunkt übertragen werden, verloren. Wenn der Übergang beispielsweise auf den Ausfall des Front-End-Servers zurückzuführen ist, gehen alle Anrufe, die derzeit vom aktiven Übereinstimmungs Dienst auf dem Front-End-Server abgewickelt werden, ebenfalls verloren.

## <a name="response-group-workflows"></a>Workflows für Reaktionsgruppen

Ein Workflow definiert, wie mit einem Anruf ab dem Läuten des Telefons bis zur Annahme des Anrufs verfahren wird. Der Workflow gibt die Warteschleife zum Halten des Anrufs an und legt die Routingmethode für Sammelanschlüsse oder die Fragen und Antworten für interaktive Reaktionsgruppen fest. Ein Workflow definiert außerdem Einstellungen wie die Willkommensnachricht, Wartemusik, Geschäftszeiten und Feiertage.

> [!NOTE]
> Vor dem Erstellen eines Workflows müssen Sie zuerst Agent-Gruppen und Warteschleifen erstellen, die vom Workflow verwendet werden sollen.

## <a name="management-of-response-groups"></a>Verwaltung von Reaktionsgruppen

In Skype for Business Server stehen zwei Verwaltungsrollen für die Verwaltung von Reaktionsgruppen zur Verfügung: Antwortgruppen-Manager und Antwortgruppen Administrator. Reaktionsgruppen Administratoren können alle Aspekte jeder Reaktionsgruppe verwalten. Antwortgruppen-Manager können nur bestimmte Aspekte verwalten, und zwar nur für die Antwortgruppen, die Sie besitzen. Die Manager-Rolle kann Ihnen dabei helfen, ihre Verwaltungskosten zu senken, da Sie begrenzte Zuständigkeiten für bestimmte Reaktionsgruppen an alle Benutzer delegieren können, die für Enterprise-VoIP aktiviert sind. Beachten Sie, dass ein Benutzer sowohl als Antwortgruppen-Manager als auch als Antwortgruppen Administrator fungieren kann.

Um der Rolle des Managers gerecht zu werden, verwendet die Antwortgruppen Anwendung einen **Workflowtyp** von Managed oder unmanaged. In der folgenden Tabelle werden die verwalteten und nicht verwalteten Reaktionsgruppen beschrieben.

**Verwaltete und nicht verwaltete Reaktionsgruppen**

|**Reaktionsgruppentyp**|**Beschreibung**|
|:-----|:-----|
|Nicht verwaltet  <br/> | Nicht verwalteten Reaktionsgruppen ist kein Manager zugewiesen. Diese Reaktionsgruppen können nur vom Administrator der Reaktionsgruppe konfiguriert werden. <br/>  Mehrere nicht verwaltete Reaktionsgruppen können eine Warteschleife oder Agentgruppe gemeinsam verwenden. <br/>  Wenn Sie Antwortgruppen aus einer früheren Version in Skype for Business Server migrieren, wird der Typ auf "nicht verwaltet" gesetzt. <br/> |
|Verwaltet  <br/> | Reaktionsgruppen Administratoren können alle Aspekte von verwalteten Reaktionsgruppen konfigurieren. <br/>  Reaktionsgruppen-Manager können keine Antwortgruppen anzeigen oder ändern, die Ihnen nicht explizit zugewiesen sind. <br/>  Reaktionsgruppen-Manager können nur einige Einstellungen für die Reaktionsgruppen konfigurieren, die Ihnen explizit zugewiesen sind. <br/>  Verwaltete Reaktionsgruppen können keine Warteschleifen oder Agentgruppen gemeinsam mit anderen Reaktionsgruppen, weder mit verwalteten noch nicht verwalteten, verwenden. <br/> |

In der folgenden Tabelle werden die Aktionen beschrieben, die von Reaktionsgruppen-Managern für die Ihnen zugewiesenen Antwortgruppen ausgeführt werden können.

**Funktionen der Reaktionsgruppenmanager**

|**Konfiguration von:**|**Erstellen, Löschen, Konfigurieren von:**|**Nicht möglich:**|
|:-----|:-----|:-----|
| Agents <br/>  Willkommensnachrichten <br/>  Name der Reaktionsgruppe <br/>  Beschreibung <br/>  Anzeigenummer <br/>  Geschäftszeiten <br/>  Wartemusik <br/>  Status (aktiv/inaktiv) <br/>  Workflows für Sammelanschlüsse oder für Interaktive Sprachantwort (Interactive Voice Response, IVR) <br/> | Agentgruppen <br/>  Warteschleifen <br/>  Feiertagssätze <br/> | Erstellen oder Löschen beliebiger Workflowtypen <br/>  Ändern grundlegender Reaktionsgruppeneinstellungen wie **SIP-URI**, **Telefonnummer** oder **Workflowtyp**.  <br/> |

Antwortgruppen-Manager können die folgenden Tools verwenden, um Ihre vorgesehenen Antwortgruppen zu verwalten.

- Skype for Business Server-Systemsteuerung

    > [!NOTE]
    > Antwortgruppen-Manager können mit diesem Tool nur Einstellungen für die Reaktionsgruppe verwalten. Andere Skype for Business Server-Einstellungen stehen Managern nicht zur Verfügung.

- Konfigurationstool für Reaktionsgruppen

- Skype for Business Server-Verwaltungsshell

Die Reaktionsgruppe eignet sich gut für Abteilungs-oder Arbeitsgruppenumgebungen (Details finden Sie unter [Kapazitätsplanung für Reaktionsgruppe](https://technet.microsoft.com/library/a2459a69-1f45-4f2f-bca5-d4f442708e44.aspx)) und können in völlig neuen Telefonieanlagen bereitgestellt werden. Sie unterstützt eingehende Anrufe von der Enterprise-VoIP-Bereitstellung und vom lokalen Netzbetreiber Netzwerk. Agents können Skype for Business, lync 2013, lync 2010, lync 2010 Attendant oder lync Phone Edition verwenden, um die an Sie weitergeleiteten Anrufe zu übernehmen.

## <a name="deployment-and-requirements"></a>Bereitstellung und Anforderungen

Die reaktionsgruppenanwendung wird automatisch aktiviert, wenn Sie Enterprise-VoIP bereitstellen.

### <a name="hardware-and-software-requirements"></a>Hardware- und Softwareanforderungen

Die reaktionsgruppenanwendung hat die gleichen Hardwareanforderungen, Betriebssystemanforderungen und Softwarevoraussetzungen wie Front-End-Server.

Wenn Sie Windows Media Audio (WMA)-Dateien für die Musik und Ankündigungen von Reaktionsgruppen verwenden, muss für alle Front-End-Server oder Standard Edition-Server, auf denen die reaktionsgruppenanwendung ausgeführt wird, die Windows Media-Format Laufzeit für Server unter Windows installiert sein. Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server 2012 R2. Für Windows Server 2008 R2 wird die Windows Media-Format Laufzeit als Teil der Windows-Desktop Oberfläche installiert.

Die Reaktionsgruppe verwendet **Sprachpakete** zur Unterstützung von Text-zu-Sprache und Spracherkennung. Diese Sprachtechnologien werden zum Konfigurieren von Nachrichten verwendet, beispielsweise für die Willkommensnachricht oder für andere Ansagen sowie für Fragen und Antworten der interaktiven Sprachantwort (Interactive Voice Response, IVR). Standardmäßig werden die 26 unterstützten Sprachpakete installiert, wenn Sie Skype for Business Server bereitstellen.

### <a name="port-requirements"></a>Portanforderungen

Die Antwortgruppen Anwendung verwendet die folgenden Ports:

- **Port 5071** für SIP-Abhör Anforderungen

- **Port 8404** für die Kommunikation zwischen Servern

    > [!NOTE]
    > Dieser Port wird für den Übereinstimmungs Dienst verwendet und ist erforderlich, wenn die reaktionsgruppenanwendung in einem Pool mit mehr als einem Front-End-Server bereitgestellt wird.

   > [!NOTE]
   > Diese Ports sind Standardeinstellungen, die Sie mit dem Cmdlet **Set-CsApplicationServer** ändern können. Details zu diesem Cmdlet finden Sie in der Dokumentation zur Skype for Business Server-Verwaltungsshell.

### <a name="audio-file-requirements"></a>Anforderungen für Audiodateien

Die Antwortgruppen Anwendung unterstützt das Wave-Dateiformat (WAV) und das Windows Media Audio-Dateiformat (WMA) für Reaktionsgruppen Nachrichten, Warteschleife-Musik oder IVR-Fragen (Interactive Voice Response).

Das Windows Media-Audiodateiformat setzt voraus, dass die Windows Media-Format Laufzeit auf Front-End-Servern mit Windows Server 2008 R2 und Windows Server 2008 installiert ist. Nähere Informationen dazu finden Sie weiter oben in diesem Abschnitt unter „Softwareanforderungen“.

#### <a name="supported-wave-file-formats"></a>Unterstützte WAV-Dateiformate

WAV-Dateien müssen folgenden Anforderungen entsprechen:

- 8- oder 16-Bit-Datei

- LPCM- (Linear Pulse Code Modulation), A-Law- oder µ-Law-Format

- Mono oder Stereo

- Maximal 4 MB

Um die beste Leistung zu erzielen, wird eine WAV-Datei mit den Werten 16 kHz, Mono, 16 Bit empfohlen.

#### <a name="supported-windows-media-audio-file-formats"></a>Unterstützte WMA-Dateiformate

Bei Verwendung einer WMA-Datei sollten Sie niedrige Bitraten verwenden und die Leistung Ihres Systems überprüfen, wenn dieses ausgelastet ist.

Sie können Microsoft Expression Encoder 4 verwenden, um eine Datei in das WMA-Format zu konvertieren. Informationen zum Herunterladen von Expression Encoder [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843)4 finden Sie unter.

### <a name="response-group-configuration-tool-requirements"></a>Anforderungen des Konfigurationstools für Reaktionsgruppen

Das Reaktionsgruppen-Konfigurations Tool unterstützt die in der folgenden Tabelle beschriebenen Kombinationen aus Betriebssystemen und Webbrowsern.

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

Die reaktionsgruppenanwendung unterstützt die folgenden Clients:

- Skype for Business-Desktop Client

- Lync 2013-Desktop Client

- Lync 2010-Desktop Client

- Lync 2010 Attendant

- Office Communications Server 2007 R2 Attendant

- Lync Phone Edition

> [!NOTE]
> Die Antwortgruppen Anwendung wird auf mobilen lync-Clients nicht unterstützt.

Der spezifische Client, den Sie verwenden können, hängt vom Typ des Reaktionsgruppen Benutzers ab:

- **Anrufer** können eine Reaktionsgruppe über einen der zuvor aufgeführten Clients und unter Verwendung eines Standardtelefons über das Festnetz anrufen.

- **Informelle Agents** (Agents, die sich nicht an-und abmelden, um Anrufe zu akzeptieren) können Anrufe über Attendant, lync oder lync Phone Edition annehmen. Informelle Agents werden bei der Anmeldung bei Skype for Business Server automatisch bei ihren Gruppen angemeldet, indem Sie einen dieser Clients verwenden.

- **Formelle Agents** (Agents, die sich an-und abmelden müssen, um Anrufe anzunehmen) können Anrufe über Skype for Business annehmen und über das Menüelement auf die Agentenkonsole zugreifen, oder indem Sie Attendant verwenden und direkt über Internet Explorer auf die Agentenkonsole zugreifen.

## <a name="capacity-planning"></a>Kapazitätsplanung

In der folgenden Tabelle wird das Benutzermodell der Reaktionsgruppe beschrieben, das Sie als Grundlage für die Kapazitäts Planungsanforderungen verwenden können.

> [!NOTE]
> Bei den Zahlen in der folgenden Tabelle wird davon ausgegangen, dass Sie 16-kHz-, Mono-, 16-Bit-WAV-Dateien für alle Audiodateien für Reaktionsgruppen verwenden. Wenn Sie andere Dateiformate, z. B. Windows Media Audio (WMA), einsetzen, können die Zahlen abweichen.

> [!IMPORTANT]
> Bedenken Sie bei der Kapazitätsplanung für die Notfallwiederherstellung, dass jeder Pool eines Poolpaars in der Lage sein sollte, die Arbeitslasten für alle Reaktionsgruppen in beiden Pools zu verarbeiten.

**Benutzermodell für Reaktionsgruppen**

|**Metrik**|**Pro Enterprise <br/> Edition-Pool (mit 8 Front-End-Servern)**|**Pro Standard Edition-Server**|
|:-----|:-----|:-----|
|Eingehende Anrufe pro Sekunde  <br/> |16  <br/> |2  <br/> |
|Gleichzeitige mit interaktiver Sprachantwort (IVR) oder Wartemusik (MoH) verbundene Anrufe  <br/> |480  <br/> |60  <br/> |
|Gleichzeitige anonyme Sitzungen (ohne Chat)  <br/> |224  <br/> |28  <br/> |
|Gleichzeitige anonyme Sitzungen (mit Chat)  <br/> |64  <br/> |8  <br/> |
|Aktive Agents (formell und informell)  <br/> |2400  <br/> |2400  <br/> |
|Anzahl der Sammelanschlüsse  <br/> |800  <br/> |800  <br/> |
|Anzahl der IVR-Gruppen (Verwendung der Spracherkennung)  <br/> |400  <br/> |400  <br/> |


