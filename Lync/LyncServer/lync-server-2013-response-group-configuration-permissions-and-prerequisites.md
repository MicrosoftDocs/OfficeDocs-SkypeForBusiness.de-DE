---
title: 'Lync Server 2013: Konfigurations Berechtigungen und-Voraussetzungen für Reaktionsgruppen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9712d196f485c51d720245903739387befb49dd3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a>Berechtigungen und Voraussetzungen für die Reaktionsgruppen Konfiguration in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-05_

Reaktionsgruppen sind eine Enterprise-VoIP-Funktion für die Anrufverwaltung. In diesem Thema wird beschrieben, welche Voraussetzungen erfüllt sein müssen, bevor Sie Reaktionsgruppen konfigurieren können, und welche Administratoranmeldeinformationen und Berechtigungen Sie zum Ausführen der Konfigurationsaufgaben benötigen.

In diesem Abschnitt wird davon ausgegangen, dass Sie die für Reaktionsgruppen relevanten Abschnitte in der Planungsdokumentation gelesen haben. Ausführliche Informationen finden Sie unter [Planning for Call Management Features in lync Server 2013](lync-server-2013-planning-for-call-management-features.md) in der Planungsdokumentation.

<div>

## <a name="configuration-tools-and-administrative-roles"></a>Konfigurationstools und Administratorrollen

Sie können Reaktionsgruppen mithilfe der folgenden Verwaltungstools konfigurieren:

  - Lync Server-Systemsteuerung

  - Reaktionsgruppen-Konfigurations Tool

  - Lync Server-Verwaltungsshell

Für die Konfiguration von Reaktionsgruppen müssen Sie über mindestens eine der folgenden Administratorrollen verfügen:


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Active Directory-Sicherheitsgruppe (1)</strong></p></td>
<td><p>Erstellen eines Workflows</p></td>
<td><p>Zuweisen eines Managers</p></td>
<td><p>Erstellen/Zuweisen von Agents und Warteschlangen</p></td>
<td><p>Erstellen/Verwalten von Feiertagen und Geschäftszeiten</p></td>
<td><p>Workflow aktivieren/deaktivieren</p></td>
<td><p>Workflow konfigurieren (IVR-Gruppe oder Sammelanschlüsse)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsResponseGroupAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rolle csresponsegroupmanager</strong></p></td>
<td> </td>
<td><p>√ (2)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsVoiceAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsServerAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="even">
<td><p><strong>CsAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsViewOnlyAdministrator</strong></p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>(1)</STRONG> ein Active Directory-Domänendienste-Benutzerobjekt muss ein Mitglied der angegebenen Active Directory Sicherheitsgruppe aufgeführt sein. Ein Administrator oder ein anderes delegiertes Active Directory Gruppenmitglied mit den entsprechenden Berechtigungen zum Hinzufügen von Benutzern zu einer Sicherheitsgruppe (beispielsweise Administrator, Kontooperatoren) muss der aufgelisteten Sicherheitsgruppe oder Gruppe ein Benutzerobjekt hinzufügen, damit der Benutzer Führen Sie die aufgeführten Funktionen aus. <STRONG>(2)</STRONG> nur für Workflows, die von der CsResponseGroupAdministrator dem Rolle csresponsegroupmanager zugewiesen wurden. <STRONG>(3)</STRONG> ein Reaktionsgruppen-Manager kann einem Workflow, den der aktuelle Manager bereits verwaltet, ein weiteres Mitglied von Rolle csresponsegroupmanager zuweisen. <STRONG>(4)</STRONG> CsViewOnlyAdministrator kann nur das Verb "Get" lync Server-Verwaltungsshell-Cmdlets ausführen.



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a>Konfigurationsvoraussetzungen für Reaktionsgruppen

Für Reaktionsgruppen sind die folgenden Komponenten erforderlich:

  - Anwendungsdienst

  - Reaktionsgruppenanwendung

  - Sprachpakete

  - Dateispeicher (für Audiodateien)

  - Webdienste (umfasst das Konfigurations Tool für Reaktionsgruppen und die Konsole für die Anmeldung und Abmeldung der Agents)

All diese Komponenten werden bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert.

Möglicherweise müssen Sie vor dem Konfigurieren der Reaktionsgruppe die folgenden Aufgaben ausführen:

  - Aktivieren Sie Benutzer für lync Server 2013 und Enterprise-VoIP.

  - Ändern einer Konfigurationsdatei für FIPS-Konformität (Federal Information Processing Standards).

  - Ändern der Datenbanksortierung für die Unterstützung von Yi-, Meng- und Zang-Zeichen für Warteschleifen- und Agentgruppennamen.

<div>

## <a name="enabling-users"></a>Aktivieren von Benutzern

Der erste Schritt beim Konfigurieren der Reaktionsgruppe ist das Erstellen von Agentengruppen. Bevor Sie eine Agentgruppe erstellen können, müssen Sie die Benutzer aktivieren, die als Agents für die Reaktionsgruppe für lync Server 2013 und Enterprise-VoIP verwendet werden sollen. Das Aktivieren von Benutzern für lync Server 2013 ist normalerweise ein Schritt in der Enterprise Edition-Server-oder Standard Edition-Server-Bereitstellung. Ausführliche Informationen zum Aktivieren von Benutzern für lync Server 2013 finden Sie unter [deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Das Aktivieren von Benutzern für Enterprise-VoIP ist im Allgemeinen ein Schritt, der bei der Bereitstellung von Enterprise-VoIP ausgeführt wird. Ausführliche Informationen finden Sie unter [Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).

</div>

<div>

## <a name="complying-with-fips-requirements"></a>Erfüllen von FIPS-Anforderungen

Dieser Abschnitt ist nur relevant, wenn Ihre Organisation FIPS-Konformität (Federal Information Processing Standards) sicherstellen muss.

Zur Einhaltung von FIPS müssen Sie die Datei "Web.config" auf Anwendungsebene nach der Installation der Webdienste ändern, um einen anderen Kryptografiealgorithmus zu verwenden. Sie müssen angeben, dass ASP.NET zur Verarbeitung von Anzeigestatusdaten den 3DES-Algorithmus (Triple Data Encryption Standard) verwendet. Für den Reaktionsgruppenanwendung gilt diese Anforderung für das Reaktionsgruppen-Konfigurations Tool und die Agent-Anmelde-und-Abmelde Konsole. Ausführliche Informationen zu dieser Anforderung finden Sie im [http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183)Microsoft Knowledge Base-Artikel 911722, "möglicherweise erhalten Sie eine Fehlermeldung, wenn Sie auf ASP.NET-Webseiten zugreifen, für die ViewState aktiviert ist, nachdem Sie ein Upgrade von ASP.NET 1,1 auf ASP.NET 2,0 durchführen".

Führen Sie zum Ändern der Datei "Web.config" die folgenden Schritte aus:

1.  Öffnen Sie in einem Text-Editor (z. B. Editor) die Datei "Web.config" auf Anwendungsebene.

2.  Suchen Sie in der Datei "Internet. config `<system.web>` " nach dem Abschnitt.

3.  Fügen Sie im `<machineKey>` `<system.web>` Abschnitt den folgenden Abschnitt hinzu:
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  Speichern Sie die Datei "Web.config".

5.  Starten Sie den Internet Information Services (IIS) Dienst neu, indem Sie den folgenden Befehl an einer Eingabeaufforderung ausführen:
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a>Unterstützen von Yi-, Meng- und Zang-Zeichen

Dieser Abschnitt ist nur relevant, wenn Ihre Organisation Yi-, Meng- oder Zang-Zeichen unterstützen muss.

<div>


> [!NOTE]  
> Informationen dazu, was die Yi-, Meng-und Zang-Zeichen sind und warum Sie für Ihre Bereitstellung wichtig sein können, finden Sie in den Informationen <A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>zu den GB18030-Zeichensätzen.



</div>

Um Yi-, Meng- oder Zang-Zeichen zu unterstützen, müssen Sie die Sortierung für die Rgsconfig-Datenbank ändern. Ändern Sie die Sortierung der Spalte **Name** in den folgenden Tabellen der einzelnen Rgsconfig-Datenbanken:

  - dbo. AgentGroups

  - dbo. BusinessHours

  - dbo. HolidaySets

  - dbo. Warteschlangen

  - dbo. Workflows

Verwenden Sie für SQL Server 2008 R2 und SQL Server 2012 die Sortierung\_Latin\_General 100 (Accent Sensitive). Bei Verwendung dieser Sortierung wird die Groß-/Kleinschreibung bei Objektnamen nicht beachtet.

Die Sortierung kann über Microsoft SQL Server Management Studio geändert werden. Ausführliche Informationen zur Verwendung dieses Tools finden Sie unter "Using SQL Server Management Studio" [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184)unter. Führen Sie die folgenden Schritte aus, um die Sortierung zu ändern:

1.  Stellen Sie sicher, dass SQL Server Management Studio zum Zulassen von Änderungen konfiguriert ist, für die Tabellen neu erstellt werden müssen. Ausführliche Informationen finden Sie unter "speichern (nicht zulässig)" im [http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186). Ausführliche Informationen zum Festlegen einer Spaltensortierung finden Sie unter "Vorgehensweise: Festlegen der Spaltensortierung (Visual Database [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185)Tools)" unter.

2.  Stellen Sie unter Verwendung von Microsoft SQL Server Management Studio eine Verbindung mit der Rgsconfig-Datenbank her.

3.  Wechseln Sie in der Rgsconfig-Datenbank zu der Tabelle, die geändert werden soll, klicken Sie mit der rechten Maustaste auf die Tabelle, und klicken Sie auf **Entwerfen**.

4.  Ändern Sie die Sortierung der Spalte **Name**, und speichern Sie die Tabelle.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

