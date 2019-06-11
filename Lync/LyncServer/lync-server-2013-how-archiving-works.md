---
title: 'Lync Server 2013: Funktionsweise der Archivierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: How Archiving works
ms:assetid: 536a52a9-cfb7-4392-9620-ffc5b319b31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204900(v=OCS.15)
ms:contentKeyID: 48184174
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 097b40ef4194a618c090e0d67f73583d6aa427b3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-archiving-works-in-lync-server-2013"></a>Funktionsweise der Archivierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-04_

Die lync Server 2013-Archivierung bietet Optionen, die Ihnen helfen, Ihre Compliance-Anforderungen zu erfüllen. Wenn Sie diese so implementieren und verwalten möchten, dass Sie die Anforderungen Ihrer Organisation am besten erfüllt, sollten Sie Folgendes verstehen:

  - Welche Informationen archiviert werden können

  - So aktivieren und deaktivieren Sie die Archivierung in Ihrer Bereitstellung.

  - Die Archivierungsoptionen, die Sie konfigurieren können, um zu steuern, wie die Archivierung implementiert wird.

<div>

## <a name="what-information-can-be-archived"></a>Welche Informationen können archiviert werden?

Die folgenden Inhaltstypen können archiviert werden:

  - Peer-zu-Peer-Chatnachrichten

  - Konferenzen (Besprechungen), die Teil von Chatsitzungen mit mehreren Teilnehmern sind

  - Konferenzinhalte, einschließlich hochgeladener Inhalte (z. B. Handzettel) sowie ereignisbezogener Inhalte (z. B. Beitritt zu/Verlassen einer Konferenz, Hochladen/Freigeben von Inhalten oder Änderungen in der Sichtbarkeit)

  - Whiteboards und Abstimmungen für alle Teilnehmer im Rahmen einer Konferenz

Die folgenden Inhaltstypen werden nicht archiviert:

  - Peer-to-Peer-Dateiübertragungen

  - Audio-/Videoinhalte für Peer-zu-Peer-Chatnachrichten und -konferenzen

  - Desktop- und Anwendungsfreigaben für Peer-zu-Peer-Chatnachrichten und -konferenzen

Lync Server archiviert auch keine beständigen Chat Unterhaltungen. Zum Archivieren beständiger Chat Unterhaltungen müssen Sie den Kompatibilitätsdienst aktivieren und konfigurieren, bei dem es sich um eine Komponente handelt, die mit dem persistenten Chat Server von Microsoft lync Server 2013 bereitgestellt werden kann. Ausführliche Informationen finden Sie unter Planen des beständigen [Chat Servers in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation.

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a>Wie beginne ich mit der Verwendung der Archivierung?

Die Archivierung wird automatisch auf jedem Front-End-Server installiert, wenn Sie den Server bereitstellen, aber die Archivierung wird erst nach der Konfiguration aktiviert. Wie Sie es konfigurieren, hängt davon ab, wie Sie die Archivierung bereitstellen:

  - **Archivierung mithilfe der Microsoft Exchange-Integration** Wenn Sie über Benutzer verfügen, die sich in Exchange 2013 befinden und deren Postfächer in einem in-situ-Speicher abgelegt wurden, können Sie die Option zum Integrieren des lync Server 2013-Speichers in den Exchange-Speicher auswählen. Wenn Sie die Option Microsoft Exchange-Integration auswählen, verwenden Sie Exchange 2013-Richtlinien und-Konfigurationen, um die Archivierung von lync Server 2013-Daten für diese Benutzer zu steuern.

  - **Archivierung mit lync Server-Archivierungsdatenbanken.** Wenn Sie über Benutzer verfügen, die nicht in Exchange 2013 sind oder deren Postfächer nicht in einem Speicherplatz gespeichert sind, oder wenn Sie die Microsoft Exchange-Integration nicht für einen oder alle Benutzer in Ihrer Bereitstellung verwenden möchten, können Sie die lync Server-Archivierungsdatenbanken mithilfe von SQL Server bereitstellen.  zum Speichern von Archivierungsdaten für diese Benutzer. In diesem Fall bestimmen lync Server 2013-Archivierungsrichtlinien und-Konfigurationen, ob die Archivierung aktiviert ist und wie Sie implementiert wird. Wenn Sie lync Server 2013 verwenden möchten, müssen Sie der Topologie die entsprechenden SQL Server-Datenbanken hinzufügen und die Topologie veröffentlichen.

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a>Archivierungs Setup bei Verwendung der Microsoft Exchange-Integration

Wenn sich Ihre Benutzer in Exchange 2013 befinden und ihre Postfächer in einem in-situ-Speicher abgelegt wurden, können Sie die **Microsoft Exchange-Integrations** Option (wie weiter unten in diesem Abschnitt beschrieben) zum Archivieren von lync Server 2013 für diese Benutzer auswählen und dann Steuern Archivierung für diese Benutzer durch Angabe von Exchange in-situ-Speicherrichtlinien und-Einstellungen sowie von lync Server-Konfigurationen, um Folgendes zu steuern:

  - Ob Sie Chat, Konferenz oder beides archivieren möchten.

  - Gibt an, ob der kritische Modus für Ihre lync Server-Bereitstellung implementiert werden soll.

  - Auswahl der Microsoft Exchange-Integrations Option, um Exchange 2013 für die Speicherung archivierter Daten zu verwenden.

Diese lync Server 2013-Archivierungs Konfigurationsoptionen werden weiter unten in diesem Abschnitt beschrieben. Informationen zum Konfigurieren von Exchange-in-situ-Speicherrichtlinien und-Einstellungen zur Unterstützung der Archivierung finden Sie in der Exchange 2013-Produktdokumentation.

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a>Archivierungs Setup bei Verwendung des lync Server-Archivierungsdaten Bank Speichers

Wenn Sie die lync Server-Archivierungsdatenbanken (mithilfe von SQL Server-Datenbanken) zum Archivieren von Daten für alle Benutzer in Ihrer Bereitstellung verwenden möchten, können Sie die lync Server-Archivierungsrichtlinien konfigurieren, um zu steuern, ob die Archivierung für diese Benutzer aktiviert ist. In jeder Archivierungsrichtlinie können Sie die Archivierung für eine oder beide der folgenden Optionen aktivieren oder deaktivieren:

  - Interne Kommunikation

  - Externe Kommunikation

Standardmäßig ist die Archivierung für die interne Kommunikation oder die externe Kommunikation in einer lync Server-Archivierungsrichtlinie nicht aktiviert. Sie aktivieren und deaktivieren die Kommunikation mit der lync Server 2013-Systemsteuerung oder mithilfe von Cmdlets in der lync Server 2013-Verwaltungsshell.

Die Archivierungsrichtlinien für lync Server 2013 umfassen die folgenden:

  - **Globale Archivierungsrichtlinie** Hierbei handelt es sich um die standardmäßige Archivierungsrichtlinie, die auf die gesamte Bereitstellung angewendet wird. Sie wird beim Bereitstellen von lync Server 2013 erstellt und deaktiviert standardmäßig die Archivierung für die interne und externe Kommunikation. Sie können diese Richtlinie nicht löschen. Wenn Sie die Option "Löschen" auswählen, wird die globale Richtlinie auf die Standardeinstellungen zurückgesetzt.

  - **Website Archivierungsrichtlinie** Optional können Sie die Archivierung für eine oder mehrere bestimmte Websites aktivieren oder deaktivieren, indem Sie eine Archivierungsrichtlinie auf Websiteebene für die Website erstellen und konfigurieren. Wenn Sie eine Archivierungsrichtlinie auf Websiteebene erstellen, ist die Archivierung standardmäßig nicht aktiviert. Sie können alle von Ihnen erstellten Archivierungsrichtlinien auf Websiteebene löschen. Eine Archivierungsrichtlinie auf Websiteebene setzt die globale Richtlinie außer Kraft, allerdings nur für die in der Richtlinie angegebene Website. Wenn Sie beispielsweise die Archivierung für die interne und externe Kommunikation in ihrer globalen Richtlinie aktivieren und eine Website Richtlinie erstellen, in der Sie die Archivierung für die externe Kommunikation deaktivieren, wird nur die interne Kommunikation für diese Website archiviert.

  - **Richtlinie für die Benutzer Archivierung** Optional können Sie die Archivierung für einen oder mehrere bestimmte Benutzer und Benutzergruppen aktivieren oder deaktivieren, indem Sie eine Archivierungsrichtlinie auf Benutzerebene für die angegebenen Benutzer und Benutzergruppen erstellen, konfigurieren und anwenden. Wenn Sie eine Archivierungsrichtlinie auf Benutzerebene erstellen, ist die Archivierung standardmäßig nicht aktiviert. Sie können alle von Ihnen erstellten Archivierungsrichtlinien auf Benutzerebene löschen, und Sie können festlegen, für welche Benutzer und Benutzergruppen die Archivierungsrichtlinie gelten soll. Eine Archivierungsrichtlinie auf Benutzerebene setzt die globale Richtlinie und alle Website Richtlinien außer Kraft, allerdings nur für die Benutzer und Benutzergruppen, auf die die Richtlinie angewendet wird. Wenn Sie beispielsweise die Archivierung für die interne und externe Kommunikation in ihrer globalen Richtlinie deaktivieren, erstellen Sie eine Richtlinie auf Websiteebene, in der Sie die Archivierung für die interne und externe Kommunikation aktivieren, und erstellen Sie dann eine Richtlinie auf Benutzerebene, in der Sie deaktivieren. Archivierung für die externe Kommunikation würden die Kommunikationen sowohl für die externe als auch für die interne Kommunikation für alle Websitebenutzer archiviert, mit der Ausnahme, dass für die Benutzer, für die Sie die Richtlinie auf Benutzerebene anwenden, nur die interne Kommunikation archiviert werden würde.

Details zum Einrichten von anfänglichen Archivierungsrichtlinien beim Bereitstellen der Archivierung finden Sie unter [Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md) in der Bereitstellungsdokumentation. Details zur Verwendung von Archivierungsrichtlinien zum Aktivieren und Deaktivieren der Kommunikation nach der Bereitstellung finden Sie unter [Verwalten der Archivierung interner und externer Kommunikation in lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in der Betriebsdokumentation.

<div>


> [!NOTE]  
> Wenn Sie sowohl lync Server 2013-Archivierungsdatenbanken implementieren als auch die Microsoft Exchange-Integration aktivieren, setzen Exchange 2013-Richtlinien die lync Server-Archivierungsrichtlinien außer Kraft, allerdings nur für Benutzer, die sich in Exchange 2013 befinden und ihre Postfächer in den Wartezustand versetzt wurden. . Die lync-Archivierung hängt nur von der Microsoft Exchange-Richtlinie für den in-situ-Speicher ab.



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a>Welche Optionen habe ich für die Konfiguration der Archivierung?

Neben der Verwendung von Richtlinien und zum Aktivieren und Deaktivieren der Archivierung stehen Ihnen weitere Archivierungsoptionen zur Verfügung, die für die gesamte Bereitstellung und optional für bestimmte Websites und Pools konfiguriert werden können. Sie steuern die meisten Archivierungsoptionen mithilfe einer oder mehrerer Archivierungs Konfigurationen, die in der lync Server 2013-Systemsteuerung zur Verfügung stehen, aber auch eine weitere Option, die nur für die Konfiguration mit der lync Server 2013-Verwaltungsshell zur Verfügung steht.

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a>In der lync Server 2013-Systemsteuerung verfügbare Archivierungs Konfigurationsoptionen

Jede Archivierungskonfiguration bietet die folgenden Optionen:

Die Konfiguration auf globaler Ebene wird automatisch erstellt, wenn Sie die Archivierung bereitstellen, und Sie können konfiguriert, aber nicht gelöscht werden. Wenn Sie die Option zum Löschen der globalen Konfiguration auswählen, werden die Einstellungen auf die Standardwerte zurückgesetzt. Sie können mehrere Website-und Poolkonfigurationen erstellen, die zusammen mit der globalen Konfiguration Archivierungseinstellungen steuern. Für die globale Konfiguration sowie für jede Website-und Poolkonfiguration stehen Ihnen die folgenden Optionen zur Verfügung:

  - Deaktivieren Sie die Archivierung, aktivieren Sie die Archivierung nur für Instant Messaging (im), oder aktivieren Sie die Archivierung von Chats und Konferenzen.

  - Konfigurieren Sie den kritischen Modus, um Chat-und Konferenzsitzungen im Fall eines lync-Server Fehlers zu blockieren. Folgende Fehler können auftreten:
    
      - **Im**. Ein Problem mit dem lync Server-Speicherdienst In diesem Fall ist der Chat für Benutzer blockiert, die für die Archivierung aktiviert sind.
    
      - **Konferenz**. Fehler können eine nicht verfügbare Dateifreigabe oder ein Problem mit dem Speicherdienst sein. In diesem Fall werden aktiven Konferenzen, die beim Auftreten des Fehlers im Pool gehostet werden, in den eingeschränkten Modus umgeschaltet und neue Konferenzen können nicht aktiviert werden.
    
    Chatnachrichten und Konferenzen werden nach dem Beheben des Fehlers automatisch wiederhergestellt.

  - Geben Sie die Verwendung der Integration von Microsoft Exchange Server 2013 zur Verwendung von Exchange 2013 für die Speicherung archivierter Daten an, anstatt separate SQL Server-Datenbanken für die Speicherung von lync Server 2013-Archivierungsdaten einzurichten.

  - Konfigurieren von Löschoptionen für archivierte Daten Dies umfasst die Angabe, wann archivierte Daten gelöscht werden sollen, wobei es sich um eine der folgenden Optionen handeln kann:
    
      - Nach einer bestimmten Anzahl von Tagen, die Sie angeben
    
      - Nachdem die Archivierungsdaten exportiert wurden (einschließlich der Daten, die in Exchange hochgeladen wurden, wenn Sie die Microsoft Exchange-Integration aktivieren).
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie die Microsoft Exchange-Integration aktivieren, wird das Bereinigen für Benutzer, die sich in Exchange 2013 befinden, und ihre Postfächer, die in-situ-Speicher abgelegt werden, von Exchange gesteuert. Die einzige Qualifikation ist für Konferenz Dateien, die auf der lync Server-Dateifreigabe gespeichert sind. Diese Dateien werden von der Dateifreigabe nur bereinigt, nachdem die Dateien exportiert (in Exchange hochgeladen) wurden, wenn Sie die Option zum Löschen von Daten nach dem Exportieren der Archivierungsdaten oder nach der angegebenen maximalen Anzahl von Tagen auswählen, wenn Sie eine maximale Anzahl von Tagen angeben. Tage für die Aufbewahrung.

    
    </div>

Standardmäßig sind keine Archivierungsoptionen aktiviert. Sie können Archivierungs Konfigurationen mithilfe der lync Server 2013-Systemsteuerung verwalten.

Sie können die folgenden Archivierungs Konfigurationen angeben:

  - **Globale Archivierungskonfiguration**. Hierbei handelt es sich um die standardmäßige Archivierungskonfiguration, die auf die gesamte Bereitstellung angewendet wird. Sie wird erstellt, wenn Sie lync Server 2013 bereitstellen und die Archivierungsfunktionalität standardmäßig nicht aktiviert. Sie können die globale Konfiguration ändern, aber nicht löschen. Wenn Sie die Option Löschen für die Konfiguration auswählen, wird die globale Konfiguration auf die Standardeinstellungen zurückgesetzt.

  - **Website Archivierungskonfiguration**. Optional können Sie die Archivierung für eine oder mehrere bestimmte Websites konfigurieren, indem Sie eine Archivierungskonfiguration auf Websiteebene für eine einzelne Website erstellen und konfigurieren. Eine Archivierungskonfiguration auf Websiteebene ist nur verfügbar, wenn Sie Sie erstellt haben. Sie können jede Archivierungskonfiguration auf Websiteebene ändern oder löschen. Eine Archivierungskonfiguration auf Websiteebene setzt die globale Konfiguration außer Kraft, allerdings nur für die Website, die in der Konfiguration auf Websiteebene angegeben ist. Wenn Sie beispielsweise die Archivierung nur für Chatnachrichten in ihrer globalen Konfiguration aktivieren und eine Websitekonfiguration erstellen, in der Sie die Archivierung sowohl für Chats als auch für Konferenzen aktivieren, werden Konferenzen nur für die Website und nicht für den Rest Ihrer Organisation archiviert.

  - **Pool Archivierungskonfiguration**. Optional können Sie Archivierungseinstellungen für ein oder mehrere bestimmte Pools angeben, indem Sie eine Konfiguration auf Poolebene für den einzelnen Pool erstellen und konfigurieren. Eine Archivierungskonfiguration auf Poolebene ist nur verfügbar, wenn Sie Sie erstellt haben. Sie können jede Archivierungskonfiguration auf Poolebene ändern und löschen. Eine Archivierungskonfiguration auf Poolebene überschreibt die globale Konfiguration und die von Ihnen möglicherweise erstellte Website Archivierungskonfiguration. Wenn Sie beispielsweise die Archivierung nur für Chatnachrichten in ihrer globalen Konfiguration aktivieren, erstellen Sie eine Konfiguration auf Websiteebene, in der Sie die Archivierung für Chats und Konferenzen für die Website aktivieren, und erstellen Sie dann eine Konfiguration auf Poolebene, in der Sie die Archivierung nur für Im werden die Kommunikationen sowohl für Chatnachrichten als auch für Konferenzen für alle Benutzer der Website archiviert, mit Ausnahme der Benutzer, die in dem Pool verwaltet werden, der in der Konfiguration auf Poolebene angegeben ist. Für alle anderen Benutzer in Ihrer Organisation wäre die Archivierung nur für Chatnachrichten aktiviert.

Details zum Einrichten von anfänglichen Archivierungs Konfigurationen beim Bereitstellen der Archivierung finden Sie unter [Konfigurieren von Archivierungsoptionen in lync Server 2013](lync-server-2013-configuring-archiving-options.md) in der Bereitstellungsdokumentation. Details zur Verwendung von Archivierungsrichtlinien zum Aktivieren und Deaktivieren der Kommunikation nach der Bereitstellung finden Sie unter [Verwalten von Archivierungs Konfigurationsoptionen in lync Server 2013 für Ihre Organisation, Websites und Pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in der Betriebsdokumentation.

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a>Nur in Windows PowerShell verfügbare Archivierungsoptionen

Mit der lync Server 2013-Verwaltungsshell können Sie Cmdlets verwenden, um Optionen zu implementieren, die in der Systemsteuerung von lync Server 2013 nicht zur Verfügung stehen. Zu den folgenden Optionen gehören:

  - **Archivieren Sie doppelte Nachrichten**. Ausführliche Informationen finden Sie unter [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) und [CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) in der Betriebsdokumentation.

  - **Exportieren von archivierten Daten** Ausführliche Informationen finden Sie unter [exportieren-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a>Wie kann ich auf archivierte Daten zugreifen?

Der Zugriff auf archivierte Daten ist abhängig davon, wo die Daten gespeichert wurden:

  - **Microsoft Exchange-Speicher**. Wenn Sie die Option für die Exchange-Integration auswählen, wird der Archivierungs Inhalt im Exchange 2013-Store für alle Benutzer abgelagert, die sich in Exchange 2013 befinden und deren Postfächer in-situ-Speicher abgelegt wurden. Archivierte Daten werden im Ordner "Wiederherstellbare Elemente" der Benutzerpostfächer gespeichert, der für Benutzer in der Regel nicht sichtbar ist und nur von Benutzern mit einer Exchange **Discovery-Verwaltungs** Rolle durchsucht werden kann. Exchange ermöglicht die Verbundsuche und-Erkennung zusammen mit SharePoint, wenn Sie bereitgestellt wird. Weitere Informationen zu Speicher, Aufbewahrung und Ermittlung der in Exchange gespeicherten Daten finden Sie in der Exchange 2013-und SharePoint-Dokumentation.

  - **Lync Server-Speicher**. Wenn Sie lync Server 2013-Archivierungsdatenbanken für die Speicherung von lync Server-Daten einrichten, stellt lync Server Archivierungs Inhalte in den lync Server-Archivierungsdatenbanken (SQL Server-Datenbanken) für alle Benutzer ein, die sich nicht in Exchange 2013 befinden und deren Postfächer nicht aktiviert wurden. In-situ-Speicher. This data is not searchable, but it can be exported to formats that are searchable using other tools. Ausführliche Informationen zum Exportieren von Daten, die in Archivierungsdatenbanken gespeichert sind, finden Sie unter [Exportieren von archivierten Daten aus lync Server 2013](lync-server-2013-exporting-archived-data.md) in der Betriebsdokumentation.

Weitere Informationen dazu, wie lync Server 2013 und Exchange 2013 zusammenarbeiten, finden Sie unter Unterstützung für [Exchange Server und SharePoint-Integration in lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in der Dokumentation zur Unterstützung.

</div>

</div>

<span> </span>

</div>

</div>

</div>

