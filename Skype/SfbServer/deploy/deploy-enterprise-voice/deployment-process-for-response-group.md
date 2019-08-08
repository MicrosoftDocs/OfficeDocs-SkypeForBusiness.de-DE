---
title: Bereitstellungsprozess für die Reaktionsgruppe in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: Bereitstellungsprozess und Schritte für die Reaktionsgruppe in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: 12497d143f9ff5c7630f81db8f416e2f7c74d574
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233299"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>Bereitstellungsprozess für die Reaktionsgruppe in Skype for Business

Bereitstellungsprozess und Schritte für die Reaktionsgruppe in Skype for Business Server Enterprise-VoIP

Reaktionsgruppe ist ein Enterprise-VoIP-Feature, mit dem eingehende Anrufe an Personengruppen, so genannte Agenten, weitergeleitet und in die Warteschlange gestellt werden, beispielsweise ein Helpdesk oder ein Kundendienst Desk.

Die Komponenten, die von der Reaktionsgruppe benötigt werden, werden beim Bereitstellen von Enterprise-VoIP automatisch auf dem Front-End-Server oder Standard Edition-Server installiert und aktiviert. Um die Reaktionsgruppe für Benutzer verfügbar zu machen, müssen Sie Agentengruppen, dann Warteschlangen und dann Workflows konfigurieren. Darüber hinaus kann ein Antwortgruppen Administrator die Konfiguration eines vorhandenen Workflows an einen Reaktionsgruppen-Manager delegieren, der dann den Workflow und die zugehörigen Agentengruppen und-Warteschlangen ändern und neu konfigurieren kann.

Für die Konfiguration von Reaktionsgruppen müssen Sie über mindestens eine der folgenden Administratorrollen verfügen:

|**Active Directory-Sicherheitsgruppe (1)** <br/> |Erstellen eines Workflows  <br/> |Zuweisen eines Managers  <br/> |Erstellen/Zuweisen von Agents und Warteschlangen  <br/> |Erstellen/Verwalten von Feiertagen und Geschäftszeiten  <br/> |Workflow aktivieren/deaktivieren  <br/> |Workflow konfigurieren (IVR-Gruppe oder Sammelanschlüsse)  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**CsResponseGroupAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsResponseGroupManager** <br/> ||√(2)  <br/> |√(3)  <br/> |√(3)  <br/> |√(3)  <br/> |√(3)  <br/> |
|**CsVoiceAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsServerAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsViewOnlyAdministrator** <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |

> [!NOTE]
> **(1)** ein Active Directory-Domänendienste-Benutzerobjekt muss ein Mitglied der angegebenen Active Directory-Sicherheitsgruppe sein. Ein Administrator oder ein anderes delegiertes Active Directory-Gruppenmitglied mit den entsprechenden Berechtigungen zum Hinzufügen von Benutzern zu einer Sicherheitsgruppe (beispielsweise Administrator, Kontooperatoren) muss ein Benutzerobjekt zur aufgelisteten Sicherheitsgruppe oder Gruppe hinzufügen, damit der Benutzer Führen Sie die aufgelisteten Funktionen aus. **(2)** nur für Workflows, die der CsResponseGroupAdministrator dem CsResponseGroupManager zugewiesen hat. **(3)** ein Antwortgruppen-Manager kann einem Workflow, den der aktuelle Manager bereits verwaltet, ein weiteres Mitglied von CsResponseGroupManager zuweisen. **(4)** CsViewOnlyAdministrator kann nur Verb "Get"-Cmdlets ausführen.

## <a name="response-group-configuration-prerequisites"></a>Voraussetzungen für die Reaktionsgruppen Konfiguration

Für die Reaktionsgruppe sind die folgenden Komponenten erforderlich:

- Anwendungsdienst

- Reaktionsgruppenanwendung

- Sprachpakete

- Dateispeicher (für Audiodateien)

- Webdienste (umfasst das Konfigurations Tool für Reaktionsgruppen und die Anmelde-und Abmelde Konsole des Agents)

Alle diese Komponenten werden standardmäßig installiert, wenn Sie Enterprise-VoIP bereitstellen.

Möglicherweise müssen Sie die folgenden Aufgaben ausführen, bevor Sie die Reaktionsgruppe konfigurieren:

- Aktivieren von Benutzern für lync Server 2013 und Enterprise-VoIP

- Ändern einer Konfigurationsdatei für FIPS-Konformität (Federal Information Processing Standards).

- Ändern der Datenbanksortierung für die Unterstützung von Yi-, Meng- und Zang-Zeichen für Warteschleifen- und Agentgruppennamen.

### <a name="enabling-users"></a>Aktivieren von Benutzern

Der erste Schritt beim Konfigurieren der Reaktionsgruppe besteht im Erstellen von Agentengruppen. Bevor Sie eine Agentengruppe erstellen können, müssen Sie die Benutzer aktivieren, die Agents für die Reaktionsgruppe für Skype for Business und Enterprise-VoIP sein sollen. Das Aktivieren von Benutzern für Skype for Business ist in der Regel ein Schritt in der Enterprise Edition-Server-oder Standard Edition-Server Bereitstellung. Details zum Aktivieren von Benutzern für Skype for Business finden Sie unter [Aktivieren oder Deaktivieren von Benutzern für lync Server 2013 Preview](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx). Das Aktivieren von Benutzern für Enterprise-VoIP ist in der Regel ein Schritt in der Enterprise Voice-Bereitstellung Ausführliche Informationen finden Sie unter [Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server](enable-users-for-enterprise-voice.md).

### <a name="complying-with-fips-requirements"></a>Erfüllen von FIPS-Anforderungen

Dieser Abschnitt ist nur relevant, wenn Ihre Organisation FIPS-Konformität (Federal Information Processing Standards) sicherstellen muss.

Zur Einhaltung von FIPS müssen Sie die Datei „Web.config“ auf Anwendungsebene nach der Installation der Webdienste ändern, um einen anderen Kryptografiealgorithmus zu verwenden. Sie müssen angeben, dass ASP.NET zur Verarbeitung von Anzeigestatusdaten den 3DES-Algorithmus (Triple Data Encryption Standard) verwendet. Für die reaktionsgruppenanwendung gilt diese Anforderung für das Reaktionsgruppen-Konfigurations Tool und die Agent-Anmeldung und-Abmelde Konsole. Ausführliche Informationen zu dieser Anforderung finden Sie im [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183)Microsoft Knowledge Base-Artikel 911722, "möglicherweise erhalten Sie eine Fehlermeldung, wenn Sie auf ASP.NET-Webseiten zugreifen, bei denen ViewState nach dem Upgrade von ASP.NET 1,1 auf ASP.NET 2,0" aktiviert ist.

Führen Sie zum Ändern der Datei „Web.config“ die folgenden Schritte aus:

1. Öffnen Sie in einem Text-Editor (z. B. Editor) die Datei „Web.config“ auf Anwendungsebene.

2. Suchen Sie in der Datei Web. config nach `<system.web>` dem Abschnitt.

3. Fügen Sie im `<machineKey>` `<system.web>` Abschnitt den folgenden Abschnitt hinzu:

   ```
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. Speichern Sie die Datei „Web.config“.

5. Starten Sie den Dienst Internet Informationsdienste (IIS) neu, indem Sie an einer Eingabeaufforderung den folgenden Befehl ausführen:

   ```
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>Unterstützen von Yi-, Meng- und Zang-Zeichen

Dieser Abschnitt ist nur relevant, wenn Ihre Organisation Yi-, Meng- oder Zang-Zeichen unterstützen muss.

> [!NOTE]
> Informationen dazu, was die Zeichen Yi, Meng und Zang sind und warum Sie für Ihre Bereitstellung wichtig sein können, finden Sie in den Informationen zu den GB18030 [https://go.microsoft.com/fwlink/p/?linkId=240223](https://go.microsoft.com/fwlink/p/?linkId=240223)-Zeichensätzen.

Um Yi-, Meng- oder Zang-Zeichen zu unterstützen, müssen Sie die Sortierung für die Rgsconfig-Datenbank ändern. Ändern Sie die Sortierung der Spalte **Name** in den folgenden Tabellen der einzelnen Rgsconfig-Datenbanken:

- dbo.AgentGroups

- dbo.BusinessHours

- dbo.HolidaySets

- dbo.Queues

- dbo.Workflows

Verwenden Sie für SQL Server 2008 R2 und SQL Server 2012 die Latin_General_100 (Accent sensitiv)-Sortierung. Bei Verwendung dieser Sortierung wird die Groß-/Kleinschreibung bei Objektnamen nicht beachtet.

Die Sortierung kann über Microsoft SQL Server Management Studio geändert werden. Ausführliche Informationen zur Verwendung dieses Tools finden Sie unter ["Verwenden von SQL Server Management Studio"](https://go.microsoft.com/fwlink/p/?linkId=196184). Führen Sie die folgenden Schritte aus, um die Sortierung zu ändern:

1. Stellen Sie sicher, dass SQL Server Management Studio zum Zulassen von Änderungen konfiguriert ist, für die Tabellen neu erstellt werden müssen. Ausführliche Informationen finden Sie unter ["speichern (nicht zulässig)" (Dialog Feld)](https://go.microsoft.com/fwlink/p/?linkId=196186). Details zum Festlegen einer Spaltensortierung finden Sie unter ["so wird es gemacht: Festlegen der Spaltensortierung (Visual Database Tools)"](https://go.microsoft.com/fwlink/p/?linkId=196185).

2. Stellen Sie unter Verwendung von Microsoft SQL Server Management Studio eine Verbindung mit der Rgsconfig-Datenbank her.

3. Wechseln Sie in der Rgsconfig-Datenbank zu der Tabelle, die geändert werden soll, klicken Sie mit der rechten Maustaste auf die Tabelle und klicken Sie auf **Entwerfen**.

4. Ändern Sie die Sortierung der Spalte **Name** und speichern Sie die Tabelle.

## <a name="response-group-deployment-steps"></a>Schritte zur Bereitstellung von Reaktionsgruppen

**Prozess zur Bereitstellung von Reaktionsgruppen**

|**Phase**|**Schritte**|**Berechtigungen**|**Bereitstellungsdokumentation**|
|:-----|:-----|:-----|:-----|
|Aktivieren von Benutzern für Skype for Business und für Enterprise-VoIP  <br/> |Aktivieren Sie Benutzer, die Agents für Skype for Business und Enterprise-VoIP sind. Benutzer müssen aktiviert sein, damit sie Agentgruppen hinzugefügt werden können. In der Regel sind Benutzer während der Enterprise Edition-oder Standard Edition-Server Bereitstellung für Skype for Business aktiviert. Benutzer sind während der Enterprise-VoIP-Bereitstellung für Enterprise-VoIP aktiviert.  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Enable or Disable Users for Lync Server 2013 Preview](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx) <br/> [Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server](enable-users-for-enterprise-voice.md) <br/> |
|Erstellen und Konfigurieren von Reaktionsgruppen, die aus Agentgruppen, Warteschlangen und Workflows bestehen  <br/> |1. verwenden Sie das Skype for Business Server Control Panel oder die Skype for Business Server-Verwaltungsshell, um folgende Aktionen auszuführen:  <br/> a. Erstellen und Konfigurieren von Agentgruppen  <br/> b. Erstellen und Konfigurieren von Warteschlangen  <br/> 2. Optional können Sie mit der Skype for Business Server-Verwaltungsshell vordefinierte Geschäftszeiten und Feiertage in der Reaktionsgruppe erstellen.  <br/> 3. verwenden Sie das Reaktionsgruppen-Konfigurations Tool oder die Skype for Business Server-Verwaltungsshell zum Erstellen von Workflows (Sammelanschlüsse oder IVR-Anruf Bewegungen (Interactive Voice Response), einschließlich benutzerdefinierter Reaktionsgruppen-Geschäftszeiten und-Feiertage.  <br/> Sie können über die Skype for Business Server-Systemsteuerung auf das Tool für die Reaktionsgruppen Konfiguration zugreifen.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[Create Response Group Agent Groups](https://technet.microsoft.com/library/2a80de17-ead0-46e8-8a27-7a4e233dbde0.aspx) <br/> [Create Response Group Queues](https://technet.microsoft.com/library/49cb86c7-2cfd-4a53-8408-d407475174ed.aspx) <br/> [Optional Definieren der Geschäftszeiten der Reaktionsgruppe in Skype for Business](optional-define-response-group-business-hours.md) <br/> [Optional Definieren von Feiertagssätzen für Reaktionsgruppen in Skype for Business](optional-define-response-group-holiday-sets.md) <br/> [Entwerfen und Erstellen von Workflows für die Reaktionsgruppe in Skype for Business](designing-and-creating-response-group-workflows.md) <br/> |
|(Optional) Anpassen der Einstellungen auf Anwendungsebene  <br/> |Verwenden Sie die Skype for Business Server-Verwaltungsshell zum Anpassen der standardmäßigen Music-on-halten-Konfiguration, der standardmäßigen Music-on-halten-Audiodatei, des Kulanzzeitraums für den Agent-Rückruf und der Konfiguration des Anruf Kontexts.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Verwalten von Reaktionsgruppeneinstellungen auf Anwendungsebene in Skype for Business](managing-application-level-response-group-settings.md) <br/> |
|(Optional) Delegieren der Verwaltung von Reaktionsgruppen  <br/> |Weisen Sie Benutzern die CsResponseGroupManager-Rolle zu, um die Konfiguration von Reaktionsgruppen zu delegieren. Die Antwortgruppen-Manager können dann die Ihnen zugewiesenen Antwortgruppen konfigurieren.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Planning for Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) <br/> |
|Überprüfen der Reaktionsgruppenbereitstellung  <br/> |Führen Sie Testanrufe bei den Sammelanschlüssen und IVR-Workflows durch, um sicherzustellen, dass die Konfiguration wie erwartet funktioniert.  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>Übersicht über Szenarios zur Erstellung von Workflows

Beim Erstellen von Workflows stehen zwei mögliche Szenarien zur Verfügung:

- **Der Administrator erstellt und konfiguriert den Workflow**: Das Mitglied der Rolle „CsResponseGroupAdministrator“ (oder einer gleichwertigen Rolle) erstellt und aktiviert den Workflow und alle Elemente im Workflow, z. B. die Agentgruppen, Warteschleifen, Feiertage und Geschäftszeiten, Wartemusik usw.

- **Der Administrator erstellt den Workflow und der Manager konfiguriert die Optionen**: Das Mitglied der Rolle „CsResponseGroupAdministrator“ (oder einer gleichwertigen Rolle) definiert den primären SIP-URI und den Anzeigenamen, weist Mitglieder der Rolle „CsResponseGroupManager“ zu, wählt eine Warteschleife aus und aktiviert den Workflow. Das CsResponseGroupManager-Mitglied kann sich dann anmelden und die Konfiguration des Workflows bearbeiten, indem es Agentgruppen erstellt und die Gruppe ebenfalls der Warteschleife zuweist und die Telefonnummer, Feiertage und Geschäftszeiten, Wartemusik usw. konfiguriert.

    > [!NOTE]
    > Wenn Sie einen verwalteten Workflow erstellen möchten, müssen Sie den Workflow als aktiv erstellen. Nach dem Speichern eines aktiven, verwalteten Workflows können Sie den Workflow ändern und deaktivieren.


