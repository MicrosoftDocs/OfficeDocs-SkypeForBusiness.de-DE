---
title: Bereitstellungsprozess für Reaktionsgruppe in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: Bereitstellungsprozess und Schritte für Reaktionsgruppe in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: b1a29c4f43deb260987492e0731b740500bff87e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103501"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>Bereitstellungsprozess für Reaktionsgruppe in Skype for Business

Bereitstellungsprozess und Schritte für Reaktionsgruppe in Skype for Business Server Enterprise-VoIP.

Die Reaktionsgruppe ist ein Enterprise-VoIP, das eingehende Anrufe an Gruppen von Personen, sogenannte Agents, z. B. einen Helpdesk oder einen Kundendienstschalter, weiter leitet und in die Warteschlange einreiht.

Die erforderlichen Komponenten für Reaktionsgruppen werden bei der Bereitstellung von Enterprise-VoIP automatisch auf dem Front-End-Server oder Standard Edition-Server installiert und aktiviert. Zur Bereitstellung der Reaktionsgruppenfunktion für Benutzer müssen Sie Agentgruppen, dann Warteschleifen und anschließend Workflows konfigurieren. Darüber hinaus kann ein Reaktionsgruppenadministrator die Konfiguration eines vorhandenen Workflows an einen Reaktionsgruppen-Manager delegieren, der dann den Workflow und die zugehörigen Agentgruppen und Warteschlangen ändern und neu konfigurieren kann.

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
> **(1)** Ein Active Directory Domain Services-Benutzerobjekt muss Mitglied der angegebenen Active Directory-Sicherheitsgruppe sein. Ein Administrator oder ein anderes delegiertes Active Directory-Gruppenmitglied mit den entsprechenden Berechtigungen zum Hinzufügen von Benutzern zu einer Sicherheitsgruppe (z. B. Administrator, Kontooperatoren) muss der aufgeführten Sicherheitsgruppe oder -gruppe ein Benutzerobjekt hinzufügen, damit der Benutzer die aufgeführten Funktionen ausführen kann. **(2)** Nur für Workflows, die der CsResponseGroupAdministrator dem CsResponseGroupManager zugewiesen hat. **(3)** Ein Reaktionsgruppen-Manager kann einem Workflow, den der aktuelle Manager bereits verwaltet, ein anderes Mitglied von CsResponseGroupManager zuweisen. **(4)** CsViewOnlyAdministrator kann nur Verb "Get"-Cmdlets ausführen.

## <a name="response-group-configuration-prerequisites"></a>Konfigurationsvoraussetzungen für Reaktionsgruppen

Für Reaktionsgruppen sind die folgenden Komponenten erforderlich:

- Anwendungsdienst

- Reaktionsgruppenanwendung

- Sprachpakete

- Dateispeicher (für Audiodateien)

- Webdienste (umfasst das Reaktionsgruppe-Konfigurationstool und die Anmelde- und Abmeldekonsole der Agents)

All diese Komponenten werden bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert.

Möglicherweise müssen Sie die folgenden Aufgaben ausführen, bevor Sie die Reaktionsgruppe konfigurieren:

- Aktivieren Sie Benutzer für Lync Server 2013 und Enterprise-VoIP.

- Ändern einer Konfigurationsdatei für FIPS-Konformität (Federal Information Processing Standards).

- Ändern der Datenbanksortierung für die Unterstützung von Yi-, Meng- und Zang-Zeichen für Warteschleifen- und Agentgruppennamen.

### <a name="enabling-users"></a>Aktivieren von Benutzern

Der erste Schritt beim Konfigurieren der Reaktionsgruppe besteht im Erstellen von Agentgruppen. Bevor Sie eine Agentgruppe erstellen können, müssen Sie die Benutzer aktivieren, die Agents für Reaktionsgruppe für Skype for Business und Enterprise-VoIP. Das Aktivieren von Benutzern für Skype for Business ist in der Regel ein Schritt in der Enterprise Edition-Server- oder Standard Edition-Serverbereitstellung. Weitere Informationen zum Aktivieren von Benutzern für Skype for Business finden Sie unter [Enable or Disable Users for Lync Server 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server). Das Aktivieren von Benutzern für Enterprise-VoIP ist im Allgemeinen ein Schritt, der bei der Bereitstellung von Enterprise-VoIP ausgeführt wird. Weitere Informationen finden Sie [unter Enable users for Enterprise-VoIP in Skype for Business Server](enable-users-for-enterprise-voice.md).

### <a name="complying-with-fips-requirements"></a>Erfüllen von FIPS-Anforderungen

Dieser Abschnitt ist nur relevant, wenn Ihre Organisation FIPS-Konformität (Federal Information Processing Standards) sicherstellen muss.

Zur Einhaltung von FIPS müssen Sie die Datei "Web.config" auf Anwendungsebene nach der Installation der Webdienste ändern, um einen anderen Kryptografiealgorithmus zu verwenden. Sie müssen angeben, dass ASP.NET zur Verarbeitung von Anzeigestatusdaten den 3DES-Algorithmus (Triple Data Encryption Standard) verwendet. Für die Reaktionsgruppeanwendung gilt diese Anforderung für das Reaktionsgruppe-Konfigurationstool und die Agent-Anmelde- und Abmeldekonsole. Weitere Informationen zu dieser Anforderung finden Sie im Microsoft Knowledge Base-Artikel 911722: "Sie erhalten möglicherweise eine Fehlermeldung, wenn Sie auf ASP.NET Webseiten zugreifen, für die ViewState aktiviert ist, nachdem Sie ein Upgrade von ASP.NET 1.1 auf ASP.NET 2.0 durchführen", unter [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183) .

Führen Sie zum Ändern der Datei "Web.config" die folgenden Schritte aus:

1. Öffnen Sie in einem Text-Editor (z. B. Editor) die Datei "Web.config" auf Anwendungsebene.

2. Suchen Sie in der Web.config nach dem  `<system.web>` Abschnitt.

3. Fügen Sie im  `<machineKey>` Abschnitt den folgenden Abschnitt `<system.web>` hinzu:

   ```xml
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. Speichern Sie die Datei "Web.config".

5. Starten Sie den Internetinformationsdienstedienst neu, indem Sie den folgenden Befehl an einer Eingabeaufforderung ausführen:

   ```console
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>Unterstützen von Yi-, Meng- und Zang-Zeichen

Dieser Abschnitt ist nur relevant, wenn Ihre Organisation Yi-, Meng- oder Zang-Zeichen unterstützen muss.

> [!NOTE]
> Informationen dazu, was die Zeichen Yi, Meng und Zang sind und warum sie für Ihre Bereitstellung wichtig sein können, finden Sie in den Informationen zu den GB18030-Zeichensätzen. [https://go.microsoft.com/fwlink/p/?linkId=240223](/previous-versions/sql/sql-server-2008-r2/ms180991(v=sql.105))

Um Yi-, Meng- oder Zang-Zeichen zu unterstützen, müssen Sie die Sortierung für die Rgsconfig-Datenbank ändern. Ändern Sie die Sortierung der Spalte **Name** in den folgenden Tabellen der einzelnen Rgsconfig-Datenbanken:

- dbo. AgentGroups

- dbo. BusinessHours

- dbo. HolidaySets

- dbo. Warteschlangen

- dbo. Workflows

Verwenden SQL Server 2008 R2 und SQL Server 2012 die sortierung Latin_General_100 (Accent Sensitive). Bei Verwendung dieser Sortierung wird die Groß-/Kleinschreibung bei Objektnamen nicht beachtet.

Die Sortierung kann über Microsoft SQL Server Management Studio geändert werden. Weitere Informationen zur Verwendung dieses Tools finden Sie unter ["Verwenden SQL Server Management Studio"](/sql/ssms/sql-server-management-studio-ssms). Führen Sie die folgenden Schritte aus, um die Sortierung zu ändern:

1. Stellen Sie sicher, dass SQL Server Management Studio zum Zulassen von Änderungen konfiguriert ist, für die Tabellen neu erstellt werden müssen. Weitere Informationen finden Sie [unter "Dialogfeld Speichern (Nicht zulässig) "](/sql/ssms/visual-db-tools/save-not-permitted-dialog-box). Weitere Informationen zum Festlegen einer Spaltensortierung finden Sie unter ["How to: Set Column Collation (Visual Database Tools)"](/previous-versions/sql/sql-server-2008-r2/ms187473(v=sql.105)).

2. Stellen Sie unter Verwendung von Microsoft SQL Server Management Studio eine Verbindung mit der Rgsconfig-Datenbank her.

3. Wechseln Sie in der Rgsconfig-Datenbank zu der Tabelle, die geändert werden soll, klicken Sie mit der rechten Maustaste auf die Tabelle, und klicken Sie auf **Entwerfen**.

4. Ändern Sie die Sortierung der Spalte **Name**, und speichern Sie die Tabelle.

## <a name="response-group-deployment-steps"></a>Schritte zur Reaktionsgruppe-Bereitstellung

**Prozess zur Bereitstellung von Reaktionsgruppen**

|**Phase**|**Schritte**|**Berechtigungen**|**Bereitstellungsdokumentation**|
|:-----|:-----|:-----|:-----|
|Aktivieren von Benutzern für Skype for Business und Enterprise-VoIP  <br/> |Aktivieren Sie Benutzer, die Agents für Skype for Business und Enterprise-VoIP. Benutzer müssen aktiviert sein, bevor Sie sie Agentgruppen hinzufügen können. In der Regel sind Benutzer während der Enterprise Edition- oder Standard Edition-Serverbereitstellung für Skype for Business aktiviert. Benutzer sind während der Enterprise-VoIP für Enterprise-VoIP aktiviert.  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Aktivieren oder Deaktivieren von Benutzern für Lync Server 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server) <br/> [Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server](enable-users-for-enterprise-voice.md) <br/> |
|Erstellen und Konfigurieren von Reaktionsgruppen, die aus Agentgruppen, Warteschlangen und Workflows bestehen  <br/> |1. Verwenden Sie die Skype for Business Server-Systemsteuerung oder die Skype for Business Server-Verwaltungsshell, um die folgenden Schritte zu tun:  <br/> a. Erstellen und Konfigurieren von Agentgruppen  <br/> b. Erstellen und Konfigurieren von Warteschlangen  <br/> 2. Verwenden Sie optional skype for Business Server Management Shell, um vordefinierte Reaktionsgruppe Geschäftszeiten und Feiertage zu erstellen.  <br/> 3. Verwenden Sie das Reaktionsgruppenkonfigurationstool oder die Skype for Business Server-Verwaltungsshell, um Workflows (Sammelaufrufgruppen oder Anrufflüsse für interaktive Sprachantworten) zu erstellen, einschließlich benutzerdefinierter Reaktionszeiten und Feiertage.  <br/> Sie können über die Skype for Business Server-Systemsteuerung auf das Reaktionsgruppeskonfigurationstool zugreifen.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[Erstellen von Agentgruppen für Reaktionsgruppen](/previous-versions/office/lync-server-2013/lync-server-2013-create-response-group-agent-groups) <br/> [Erstellen von Warteschleifen für Reaktionsgruppen](/previous-versions/office/lync-server-2013/lync-server-2013-create-response-group-queues) <br/> [(Optional) Definieren der Geschäftszeiten der Reaktionsgruppe in Skype for Business](optional-define-response-group-business-hours.md) <br/> [(Optional) Definieren von Feiertagssätzen für Reaktionsgruppe in Skype for Business](optional-define-response-group-holiday-sets.md) <br/> [Entwerfen und Erstellen von Reaktionsgruppeworkflows in Skype for Business](designing-and-creating-response-group-workflows.md) <br/> |
|(Optional) Anpassen der Einstellungen auf Anwendungsebene  <br/> |Verwenden Sie die Skype for Business Server-Verwaltungsshell, um die Standardkonfiguration für die Wartemusik, die Standardaudiodatei für die Wartemusik, die Agent-Ringback-Kulanzfrist und die Anrufkontextkonfiguration anzupassen.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Verwalten von Reaktionsgruppeseinstellungen auf Anwendungsebene in Skype for Business](managing-application-level-response-group-settings.md) <br/> |
|(Optional) Delegieren der Verwaltung von Reaktionsgruppen  <br/> |Weisen Sie Benutzern die Rolle CsResponseGroupManager zu, um die Konfiguration von Reaktionsgruppen zu delegieren. Reaktionsgruppenmanager können dann die ihnen zugewiesenen Reaktionsgruppen konfigurieren.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Planen der rollenbasierten Zugriffssteuerung](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control) <br/> |
|Überprüfen der Reaktionsgruppenbereitstellung  <br/> |Führen Sie Testanrufe bei den Sammelanschlüssen und IVR-Workflows durch, um sicherzustellen, dass die Konfiguration wie erwartet funktioniert.  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>Übersicht über Workflowerstellungsszenarien

Beim Erstellen von Workflows stehen zwei mögliche Szenarien zur Verfügung:

- **Der Administrator erstellt und konfiguriert den Workflow**: Das Mitglied der Rolle "CsResponseGroupAdministrator" (oder einer gleichwertigen Rolle) erstellt und aktiviert den Workflow und alle Elemente im Workflow, z. B. die Agentgruppen, Warteschlangen, Feiertage und Geschäftszeiten, Wartemusik usw.

- **Der Administrator erstellt den Workflow und der Manager konfiguriert die Optionen**: Das Mitglied der Rolle "CsResponseGroupAdministrator" (oder einer gleichwertigen Rolle) definiert den primären SIP-URI und den Anzeigenamen, weist Mitglieder der Rolle "CsResponseGroupManager" zu, wählt eine Warteschlange aus und aktiviert den Workflow. Das CsResponseGroupManager-Mitglied kann sich dann anmelden und die Konfiguration des Workflows bearbeiten, indem es Agentgruppen erstellt und die Gruppe ebenfalls der Warteschlange zuweist und die Telefonnummer, Feiertage und Geschäftszeiten, Wartemusik usw. konfiguriert.

    > [!NOTE]
    > Wenn Sie einen verwalteten Workflow erstellen möchten, müssen Sie den Workflow als aktiv erstellen. Nach dem Speichern eines aktiven, verwalteten Workflows können Sie den Workflow ändern und deaktivieren.