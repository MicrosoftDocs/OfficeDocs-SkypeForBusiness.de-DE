---
title: Bereitstellungsprozess für Reaktionsgruppen in Skype für Unternehmen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: Bereitstellungsprozess und Schritte für die Reaktionsgruppe in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 83438ec17bd78a60afbc08a1c72ef84469218652
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897935"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>Bereitstellungsprozess für Reaktionsgruppen in Skype für Unternehmen

Bereitstellungsprozess und Schritte für die Reaktionsgruppe in Skype für Business Server Enterprise-VoIP.

Reaktionsgruppe ist eine Enterprise-VoIP-Funktion, die die Warteschlange umleitet und eingehende Anrufe an eine Gruppe von Personen, die Agents, wie ein Helpdesk oder den Kundendienst aufgerufen.

Die Komponenten, die Antwort Gruppe benötigt werden installiert und aktiviert automatisch auf dem Front-End-Server oder Standard Edition-Server, bei der Bereitstellung von Enterprise-VoIP. Response Group für Benutzer zur Verfügung zu stellen, müssen Sie agentgruppen, Warteschlangen und dann Workflows konfigurieren. Darüber hinaus können eine Antwort Gruppe Administrator Konfiguration eines vorhandenen Workflows zu einer Antwort Gruppe Manager delegieren, die dann ändern und konfigurieren den Workflow und die zugehörigen agentgruppen und Warteschleifen können.

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
> **(1)** ein Active Directory Domain Services User-Objekt muss ein Mitglied der angegebenen Active Directory-Sicherheitsgruppe aufgeführt. Ein Administrator oder anderen delegierten Mitglied der Active Directory-Gruppe mit den entsprechenden Berechtigungen zum Hinzufügen von Benutzern zu einer Sicherheitsgruppe (beispielsweise "Administrator", "Konten-Operatoren") muss ein User-Objekt können die aufgelisteten Sicherheitsgruppe oder einer Gruppe für den Benutzer hinzufügen. Führen Sie die Funktionen aufgelistet. **(2)** nur für Workflows, die die CsResponseGroupAdministrator der CsResponseGroupManager zugewiesen hat. **(3)** eine Antwort Gruppenleiter können ein anderes Mitglied CsResponseGroupManager eines Workflows zuweisen, die der aktuelle Manager bereits verwaltet. **(4)** CsViewOnlyAdministrator kann nur Verb Get-Cmdlets ausführen.

## <a name="response-group-configuration-prerequisites"></a>Konfigurationsvoraussetzungen für Reaktionsgruppen

Reaktionsgruppe sind die folgenden Komponenten erforderlich:

- Anwendungsdienst

- Reaktionsgruppenanwendung

- Sprachpakete

- Dateispeicher (für Audiodateien)

- Webdienste (einschließlich der Reaktionsgruppen-Konfigurationstool und der Agents an- und Abmeldung Konsole)

All diese Komponenten werden standardmäßig installiert, bei der Bereitstellung von Enterprise-VoIP.

Sie müssen möglicherweise die folgenden Aufgaben ausführen, vor dem Konfigurieren von Reaktionsgruppen:

- Aktivieren von Benutzern für Lync Server 2013 und Enterprise-VoIP.

- Ändern einer Konfigurationsdatei für FIPS-Konformität (Federal Information Processing Standards).

- Ändern der Datenbanksortierung für die Unterstützung von Yi-, Meng- und Zang-Zeichen für Warteschleifen- und Agentgruppennamen.

### <a name="enabling-users"></a>Aktivieren von Benutzern

Der erste Schritt beim Konfigurieren von Reaktionsgruppen wird zum Erstellen von Agent-Gruppen. Bevor Sie eine agentgruppe erstellen können, müssen Sie die Benutzer aktivieren, die Agents für Reaktionsgruppen für Skype für Unternehmen und Enterprise-VoIP festgelegt werden soll. Aktivieren von Benutzern für Skype für Unternehmen ist in der Regel ein Schritt in der Enterprise Edition-Server oder Standard Edition-Server-Bereitstellung. Ausführliche Informationen zum Aktivieren von Benutzern für Skype für Unternehmen finden Sie unter [Enable or Disable Users for Lync Server 2013 Preview](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx). Aktivieren von Benutzern für Enterprise-VoIP ist in der Regel ein Schritt in der Enterprise-VoIP-Bereitstellung. Weitere Informationen hierzu finden Sie unter [Aktivieren von Benutzern für Enterprise-VoIP in Skype für Business Server](enable-users-for-enterprise-voice.md).

### <a name="complying-with-fips-requirements"></a>Erfüllen von FIPS-Anforderungen

Dieser Abschnitt ist nur relevant, wenn Ihre Organisation FIPS-Konformität (Federal Information Processing Standards) sicherstellen muss.

Zur Einhaltung von FIPS müssen Sie die Datei „Web.config“ auf Anwendungsebene nach der Installation der Webdienste ändern, um einen anderen Kryptografiealgorithmus zu verwenden. Sie müssen angeben, dass ASP.NET zur Verarbeitung von Anzeigestatusdaten den 3DES-Algorithmus (Triple Data Encryption Standard) verwendet. Dies betrifft für die Anwendung "Reaktionsgruppe" aus der Reaktionsgruppen-Konfigurationstool und die an- und Abmeldung Agent-Konsole. Ausführliche Informationen zu dieser Anforderung finden Sie im Microsoft Knowledge Base-Artikel 911722, "möglicherweise eine Fehlermeldung beim Zugriff auf ASP.NET Webseiten, die Ansichtszustand aktiviert nach der Aktualisierung von ASP.NET 1.1 in ASP.NET 2.0," unter [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183).

Führen Sie zum Ändern der Datei „Web.config“ die folgenden Schritte aus:

1. Öffnen Sie in einem Text-Editor (z. B. Editor) die Datei „Web.config“ auf Anwendungsebene.

2. Suchen Sie in der Datei Web.config die `<system.web>` Abschnitt.

3. Fügen Sie die folgenden `<machineKey>` Abschnitt aus, um in die `<system.web>` Abschnitt:

   ```
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. Speichern Sie die Datei „Web.config“.

5. Starten Sie den Dienst Internetinformationsdienste (Internet Information Services, IIS), durch den folgenden Befehl an der Befehlszeile ausführen:

   ```
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>Unterstützen von Yi-, Meng- und Zang-Zeichen

Dieser Abschnitt ist nur relevant, wenn Ihre Organisation Yi-, Meng- oder Zang-Zeichen unterstützen muss.

> [!NOTE]
> Informationen Was sind die Yi-, Meng- und Zang-Zeichen und warum sie für Ihre Bereitstellung wichtig sein können, finden Sie die Informationen auf die Zeichensätze GB18030 [https://go.microsoft.com/fwlink/p/?linkId=240223](https://go.microsoft.com/fwlink/p/?linkId=240223).

Um Yi-, Meng- oder Zang-Zeichen zu unterstützen, müssen Sie die Sortierung für die Rgsconfig-Datenbank ändern. Ändern Sie die Sortierung der Spalte **Name** in den folgenden Tabellen der einzelnen Rgsconfig-Datenbanken:

- dbo.AgentGroups

- dbo.BusinessHours

- dbo.HolidaySets

- dbo.Queues

- dbo.Workflows

Für SQL Server 2008 R2 und SQL Server 2012 verwenden die Latin_General_100 (Accent-Sensitive) Sortierung. Bei Verwendung dieser Sortierung wird die Groß-/Kleinschreibung bei Objektnamen nicht beachtet.

Die Sortierung kann über Microsoft SQL Server Management Studio geändert werden. Weitere Informationen zur Verwendung dieses Tools finden Sie unter ["Verwenden von SQL Server Management Studio"](https://go.microsoft.com/fwlink/p/?linkId=196184). Führen Sie die folgenden Schritte aus, um die Sortierung zu ändern:

1. Stellen Sie sicher, dass SQL Server Management Studio zum Zulassen von Änderungen konfiguriert ist, für die Tabellen neu erstellt werden müssen. Weitere Informationen hierzu finden Sie unter ["(nicht zulässig) speichern im Dialogfeld"](https://go.microsoft.com/fwlink/p/?linkId=196186). Ausführliche Informationen zum Festlegen einer Spalte Sortierung, finden Sie unter ["How to: Set-Spalte Sortierung (Visual Database Tools)"](https://go.microsoft.com/fwlink/p/?linkId=196185).

2. Stellen Sie unter Verwendung von Microsoft SQL Server Management Studio eine Verbindung mit der Rgsconfig-Datenbank her.

3. Wechseln Sie in der Rgsconfig-Datenbank zu der Tabelle, die geändert werden soll, klicken Sie mit der rechten Maustaste auf die Tabelle und klicken Sie auf **Entwerfen**.

4. Ändern Sie die Sortierung der Spalte **Name** und speichern Sie die Tabelle.

## <a name="response-group-deployment-steps"></a>Schritte zur Bereitstellung von Reaktionsgruppen

**Prozess zur Bereitstellung von Reaktionsgruppen**

|**Phase**|**Schritte**|**Berechtigungen**|**Bereitstellungsdokumentation**|
|:-----|:-----|:-----|:-----|
|Aktivieren von Benutzern für Skype für Unternehmen und für Enterprise-VoIP  <br/> |Aktivieren von Benutzern, die Agents für Skype für Unternehmen und Enterprise-VoIP. Benutzer müssen aktiviert sein, damit sie Agentgruppen hinzugefügt werden können. Benutzer werden in der Regel während der Enterprise Edition oder Standard Edition-Server-Bereitstellung für Skype für Unternehmen aktiviert. Benutzer werden während der Bereitstellung von Enterprise-VoIP für Enterprise Voice aktiviert.  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Enable or Disable Users for Lync Server 2013 Preview](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx) <br/> [Aktivieren von Benutzern für Enterprise-VoIP in Skype für Business Server](enable-users-for-enterprise-voice.md) <br/> |
|Erstellen und Konfigurieren von Reaktionsgruppen, die aus Agentgruppen, Warteschlangen und Workflows bestehen  <br/> |1. verwenden Sie die Skype für Business Server-Systemsteuerung oder Skype für Business Server-Verwaltungsshell folgende Aktionen ausführen:  <br/> a. Erstellen und Konfigurieren von Agentgruppen  <br/> b. Erstellen und Konfigurieren von Warteschlangen  <br/> 2. optional, verwenden Sie Skype für Business Server-Verwaltungsshell, um vordefinierte Antwort Geschäftszeiten und Feiertage erstellen.  <br/> 3. verwenden das Konfigurationstool für Reaktionsgruppen oder Skype für Business Server-Verwaltungsshell zum Erstellen von Workflows (Sammelanschlüsse oder interaktive Sprachantwort (IVR) Anruf), einschließlich der benutzerdefinierten Antwort Geschäftszeiten und Feiertage.  <br/> Sie können das Konfigurationstool für Reaktionsgruppen über Skype Business Server-Systemsteuerung zugreifen.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[Create Response Group Agent Groups](https://technet.microsoft.com/library/2a80de17-ead0-46e8-8a27-7a4e233dbde0.aspx) <br/> [Create Response Group Queues](https://technet.microsoft.com/library/49cb86c7-2cfd-4a53-8408-d407475174ed.aspx) <br/> [(Optional) Reaktionsgruppe Definieren von Geschäftszeiten in Skype für Unternehmen](optional-define-response-group-business-hours.md) <br/> [(Optional) Definieren von Reaktionsgruppe feiertagssätze in Skype für Unternehmen](optional-define-response-group-holiday-sets.md) <br/> [Entwerfen und Erstellen von Antwort Gruppe Workflows in Skype für Unternehmen](designing-and-creating-response-group-workflows.md) <br/> |
|(Optional) Anpassen der Einstellungen auf Anwendungsebene  <br/> |Verwenden Sie Skype für Business Server-Verwaltungsshell, um die Standardkonfiguration für die Musik halten, die standardmäßige Musik halten Audiodatei, die Agents bei Kulanzfrist und der anrufkontextkonfiguration anzupassen.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Verwalten von reaktionsgruppeneinstellungen auf Anwendungsebene in Skype für Unternehmen](managing-application-level-response-group-settings.md) <br/> |
|(Optional) Delegieren der Verwaltung von Reaktionsgruppen  <br/> |Zuweisen von Benutzern die Rolle CsResponseGroupManager zum Delegieren der Konfiguration von reaktionsgruppen. Reaktionsgruppenmanager können Sie die ihnen zugewiesenen reaktionsgruppen konfigurieren.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Planning for Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) <br/> |
|Überprüfen der Reaktionsgruppenbereitstellung  <br/> |Führen Sie Testanrufe bei den Sammelanschlüssen und IVR-Workflows durch, um sicherzustellen, dass die Konfiguration wie erwartet funktioniert.  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>Übersicht über Szenarios zur Erstellung von Workflows

Beim Erstellen von Workflows stehen zwei mögliche Szenarien zur Verfügung:

- **Der Administrator erstellt und konfiguriert den Workflow**: Das Mitglied der Rolle „CsResponseGroupAdministrator“ (oder einer gleichwertigen Rolle) erstellt und aktiviert den Workflow und alle Elemente im Workflow, z. B. die Agentgruppen, Warteschleifen, Feiertage und Geschäftszeiten, Wartemusik usw.

- **Der Administrator erstellt den Workflow und der Manager konfiguriert die Optionen**: Das Mitglied der Rolle „CsResponseGroupAdministrator“ (oder einer gleichwertigen Rolle) definiert den primären SIP-URI und den Anzeigenamen, weist Mitglieder der Rolle „CsResponseGroupManager“ zu, wählt eine Warteschleife aus und aktiviert den Workflow. Das CsResponseGroupManager-Mitglied kann sich dann anmelden und die Konfiguration des Workflows bearbeiten, indem es Agentgruppen erstellt und die Gruppe ebenfalls der Warteschleife zuweist und die Telefonnummer, Feiertage und Geschäftszeiten, Wartemusik usw. konfiguriert.

    > [!NOTE]
    > Wenn Sie einen verwalteten Workflow erstellen möchten, müssen Sie den Workflow als aktiv erstellen. Nach dem Speichern eines aktiven, verwalteten Workflows können Sie den Workflow ändern und deaktivieren.


