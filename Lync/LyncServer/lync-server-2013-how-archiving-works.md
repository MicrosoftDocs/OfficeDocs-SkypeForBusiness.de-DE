---
title: 'Lync Server 2013: Funktionsweise der Archivierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Archiving works
ms:assetid: 536a52a9-cfb7-4392-9620-ffc5b319b31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204900(v=OCS.15)
ms:contentKeyID: 48184174
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bc6266cdf81f4462adf82c5878bcc47a6060fdf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-archiving-works-in-lync-server-2013"></a>Funktionsweise der Archivierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-04_

Lync Server 2013 Archivierung bietet Optionen, mit denen Sie Ihre Compliance-Anforderungen erfüllen können. Sie sollten Folgendes verstehen, um es so zu implementieren und zu warten, dass es den Anforderungen Ihrer Organisation am besten entspricht:

  - Welche Informationen können archiviert werden?

  - Wie kann die Archivierung in der Bereitstellung aktiviert bzw. deaktiviert werden?

  - Welche Archivierungsoptionen können konfiguriert werden, um die Implementierung der Archivierung zu steuern?

<div>

## <a name="what-information-can-be-archived"></a>Welche Informationen können archiviert werden?

Folgende Arten von Inhalt können archiviert werden:

  - Peer-zu-Peer-Sofortnachrichten

  - Konferenzen (Besprechungen), die Teil von Sofortnachrichtensitzungen mit mehreren Teilnehmern sind

  - Konferenzinhalte, einschließlich hochgeladener Inhalte (z. B. Handzettel) sowie ereignisbezogener Inhalte (z. B. Beitritt zu/Verlassen einer Konferenz, Hochladen/Freigeben von Inhalten oder Änderungen in der Sichtbarkeit)

  - Whiteboards und Abstimmungen für alle Teilnehmer im Rahmen einer Konferenz

Die folgenden Arten von Inhalt können nicht archiviert werden:

  - Peer-zu-Peer-Dateiübertragungen

  - Audio-/Videoinhalte für Peer-zu-Peer-Sofortnachrichten und -konferenzen

  - Desktop- und Anwendungsfreigaben für Peer-zu-Peer-Sofortnachrichten und -konferenzen

Lync Server archiviert auch keine beständigen Chat Unterhaltungen. Zum Archivieren von Unterhaltungen für beständigen Chat müssen Sie den Kompatibilitätsdienst aktivieren und konfigurieren, bei dem es sich um eine Komponente handelt, die mit Microsoft lync Server 2013 Server für beständigen Chat bereitgestellt werden kann. Ausführliche Informationen finden Sie unter [Planning for persistent Chat Server in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation.

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a>Wie kann ich mit der Archivierung beginnen?

Die Archivierung wird bei der Bereitstellung des Servers automatisch auf jedem Front-End-Server installiert. Zum Verwenden der Archivierung müssen Sie sie jedoch zunächst konfigurieren. Die Konfiguration der Archivierung ist dabei abhängig von Ihrer Bereitstellung:

  - **Archivierung mit Microsoft Exchange Integration.** Wenn Sie über Benutzer verfügen, die in Exchange 2013 verwaltet werden und deren Postfächer in einem Compliance-Archiv abgelegt wurden, können Sie die Option zum integrieren lync Server 2013 Speichers mit Exchange-Speicher auswählen. Wenn Sie die Option Microsoft Exchange Integration auswählen, verwenden Sie Exchange 2013 Richtlinien und Konfigurationen, um die Archivierung von lync Server 2013 Daten für diese Benutzer zu steuern.

  - **Archivierung mit lync Server Archivierungsdatenbanken.** Wenn Sie über Benutzer verfügen, die nicht in Exchange 2013 verwaltet werden oder deren Postfächer nicht in-situ-Speicher abgelegt wurden, oder wenn Sie Microsoft Exchange Integration nicht für einen oder alle Benutzer in Ihrer Bereitstellung verwenden möchten, können Sie lync Server Archivierungsdatenbanken mithilfe von SQL Server bereitstellen.  zum Speichern von Archivierungsdaten für diese Benutzer. In diesem Fall bestimmen lync Server 2013 Archivierungsrichtlinien und-Konfigurationen, ob die Archivierung aktiviert ist und wie Sie implementiert wird. Um lync Server 2013 verwenden zu können, müssen Sie die entsprechenden SQL Server Datenbanken zu Ihrer Topologie hinzufügen und die Topologie veröffentlichen.

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a>Archivierungs Setup bei Verwendung Microsoft Exchange Integration

Wenn Ihre Benutzer in Exchange 2013 verwaltet werden und ihre Postfächer in einem Compliance-Archiv abgelegt wurden, können Sie die Option **Microsoft Exchange Integration** (wie weiter unten in diesem Abschnitt beschrieben) zur Archivierung von lync Server 2013 für diese Benutzer auswählen und dann die Archivierung für diese Benutzer steuern, indem Sie die in-situ-Speicherrichtlinien und-Einstellungen von Exchange festlegen sowie lync Server Konfigurationen zur Steuerung der folgenden Schritte durchführen:

  - Zu archivierende Elemente (Sofortnachrichten, Konferenzen oder beides)

  - Gibt an, ob der kritische Modus für Ihre lync Server-Bereitstellung implementiert werden soll.

  - Auswahl der Option für die Microsoft Exchange Integration, um Exchange 2013 für die Speicherung archivierter Daten zu verwenden.

Diese lync Server 2013 Archivierungs Konfigurationsoptionen werden weiter unten in diesem Abschnitt beschrieben. Informationen zum Konfigurieren von Exchange in-situ-Speicherrichtlinien und-Einstellungen zur Unterstützung der Archivierung finden Sie in der Exchange 2013-Produktdokumentation.

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a>Einrichten der Archivierung bei Verwendung des Archivierungsdatenbankspeichers von Lync Server

Wenn Sie lync Server Archivierungsdatenbanken (mithilfe SQL Server Datenbanken) zum Archivieren von Daten für alle Benutzer in Ihrer Bereitstellung verwenden möchten, können Sie lync Server Archivierungsrichtlinien konfigurieren, um zu steuern, ob die Archivierung für diese Benutzer aktiviert ist. In jeder Archivierungsrichtlinie können Sie die Archivierung für eine oder beide der folgenden Optionen aktivieren oder deaktivieren:

  - Interne Kommunikation

  - Externe Kommunikation

Standardmäßig ist die Archivierung für die interne Kommunikation oder externe Kommunikation in einer lync Server Archivierungsrichtlinie nicht aktiviert. Sie können die Kommunikation mit lync Server 2013-Systemsteuerung oder mithilfe von Cmdlets in der lync Server 2013-Verwaltungsshell aktivieren und deaktivieren.

Lync Server 2013 Archivierungsrichtlinien umfassen Folgendes:

  - **Globale Archivierungsrichtlinie**. Dies ist die Standard Archivierungsrichtlinie und gilt für Ihre gesamte Bereitstellung. Sie wird erstellt, wenn Sie lync Server 2013 bereitstellen und standardmäßig die Archivierung für die interne und externe Kommunikation deaktiviert. Diese Richtlinie kann nicht gelöscht werden. Wenn Sie die Option Löschen auswählen, wird die globale Richtlinie auf die Standardeinstellungen zurückgesetzt.

  - **Standortarchivierungsrichtlinie**. Sie können auch die Archivierung für einen oder mehrere Standorte aktivieren oder deaktivieren. Dazu erstellen und konfigurieren Sie eine Archivierungsrichtlinie auf Standortebene für den bzw. die betreffenden Standorte. Wenn Sie eine Archivierungsrichtlinie auf Standortebene erstellen, ist die Archivierung zunächst deaktiviert. Alle Archivierungsrichtlinien auf Standortebene, die Sie erstellen, können auch wieder gelöscht werden. Eine Archivierungsrichtlinie auf Standortebene überschreibt die globale Richtlinie, allerdings nur für den in der Richtlinie angegebenen Standort. Wenn Sie beispielsweise die Archivierung für die interne und für die externe Kommunikation in Ihrer globalen Richtlinie aktivieren und eine Standortrichtlinie erstellen, in der die Archivierung für die externe Kommunikation deaktiviert ist, wird an diesem Standort nur die interne Kommunikation archiviert.

  - **Benutzerarchivierungsrichtlinie**. Sie können die Archivierung auch für bestimmte Benutzer oder Benutzergruppen aktivieren bzw. deaktivieren. Dazu erstellen, konfigurieren oder wenden Sie eine Archivierungsrichtlinie für die angegebenen Benutzer oder Benutzergruppen an. Wenn Sie eine Archivierungsrichtlinie auf Benutzerebene erstellen, ist die Archivierung standardmäßig nicht aktiviert. Alle Archivierungsrichtlinien auf Benutzerebene, die Sie erstellen, können auch wieder gelöscht werden. Außerdem können Sie die Benutzer oder Benutzergruppen ändern, auf die sich eine Archivierungsrichtlinie auswirkt. Die globale Richtlinie und alle Richtlinien auf Standortebene werden durch eine Archivierungsrichtlinie auf Benutzerebene überschrieben. Dies gilt jedoch nur für die Benutzer, die von der Richtlinie betroffen sind. Angenommen, Sie deaktivieren die Archivierung für die interne und für die externe Kommunikation in Ihrer globalen Richtlinie. Ferner erstellen Sie eine Richtlinie auf Standortebene, in der die Archivierung für die interne und für die externe Kommunikation aktiviert ist. Abschließend erstellen Sie eine Richtlinie auf Benutzerebene, in der Sie die Archivierung für die externe Kommunikation deaktivieren. In diesem Fall werden die externe und die interne Kommunikation für alle Standortbenutzer mit Ausnahme der Benutzer archiviert, auf die die Richtlinie auf Benutzerebene angewendet wird: Für diese Benutzer wird nur die interne Kommunikation archiviert.

Ausführliche Informationen zum Einrichten der anfänglichen Archivierungsrichtlinien beim Bereitstellen der Archivierung finden Sie unter [Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md) in der Bereitstellungsdokumentation. Ausführliche Informationen zur Verwendung von Archivierungsrichtlinien zur Aktivierung und Deaktivierung der Kommunikation nach der Bereitstellung finden Sie unter [Managing the Archiving of Internal and External Communications in lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in der Betriebsdokumentation.

<div>


> [!NOTE]  
> Wenn Sie sowohl lync Server 2013 Archivierungsdatenbanken implementieren als auch Microsoft Exchange Integration aktivieren, setzen Exchange 2013-Richtlinien lync Server Archivierungsrichtlinien außer Kraft, jedoch nur für Benutzer, die in Exchange 2013 verwaltet werden und ihre Postfächer in einem Compliance-Archiv platziert haben. . Die lync-Archivierung hängt nur von Microsoft Exchange in-situ-Aufbewahrungsrichtlinie ab.



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a>Welche Optionen stehen für die Konfiguration der Archivierung zur Verfügung?

Zusätzlich zur Verwendung von Richtlinien und zum Aktivieren und Deaktivieren der Archivierung stehen Ihnen andere Archivierungsoptionen zur Verfügung, die für die gesamte Bereitstellung und optional für bestimmte Standorte und Pools konfiguriert werden können. Sie können die meisten Archivierungsoptionen mit einer oder mehreren Archivierungs Konfigurationen steuern, die in lync Server 2013 Systemsteuerung zur Verfügung stehen, aber auch eine andere Option aufweisen, die nur für die Konfiguration mit lync Server 2013 Verwaltungsshell verfügbar ist.

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a>Konfigurationsoptionen für die Archivierung in der Systemsteuerung von Lync Server 2013

Jede Archivierungskonfiguration beinhaltet folgende Optionen:

Die Konfiguration auf globaler Ebene wird automatisch beim Bereitstellen der Archivierung erstellt. Sie kann angepasst, nicht jedoch gelöscht werden. Wenn Sie die Option zum Löschen der globalen Konfiguration auswählen, werden die Einstellungen auf die Standardwerte zurückgesetzt. Sie können mehrere Standort- und Poolkonfigurationen erstellen, die zusammen mit der globalen Konfiguration die Archivierungseinstellungen festlegen. Folgende Konfigurationsoptionen stehen für die globale Konfiguration sowie für die einzelnen Standort- und Poolkonfigurationen zur Verfügung:

  - Archivierung deaktivieren, Archivierung nur für Sofortnachrichten aktivieren oder Archivierung für Sofortnachrichten und Konferenzen aktivieren.

  - Konfigurieren des kritischen Modus zum Blockieren von Chat-und Konferenzsitzungen im Falle eines lync Server Fehlers Fehler können folgende Elemente betreffen:
    
      - **Im**. Ein Problem mit dem lync Server-Speicherdienst. In diesem Fall werden Sofortnachrichten für Benutzer blockiert, für die die Archivierung aktiviert wurde.
    
      - **Konferenzen**. Fehler können eine nicht verfügbare Dateifreigabe oder ein Problem mit dem Speicherdienst sein. In diesem Fall werden aktiven Konferenzen, die beim Auftreten des Fehlers im Pool gehostet werden, in den eingeschränkten Modus umgeschaltet, und neue Konferenzen können nicht aktiviert werden.
    
    Sofortnachrichten und Konferenzen werden nach dem Beheben des Fehlers automatisch wiederhergestellt.

  - Geben Sie an, wie Microsoft Exchange Server 2013 Integration verwendet werden soll, um Exchange 2013 für die Speicherung archivierter Daten zu verwenden, anstatt separate SQL Server-Datenbanken zum Speichern von lync Server 2013 Archivierungsdaten zu erstellen.

  - Optionen zum Löschen der archivierten Daten konfigurieren. Dabei muss auch angegeben werden, zu welchem Zeitpunkt archivierte Daten gelöscht werden sollen:
    
      - Nach einer bestimmten Anzahl von Tagen
    
      - Nach dem Exportieren der Archivierungsdaten (einschließlich der Daten, die in Exchange hochgeladen wurden, wenn Sie Microsoft Exchange Integration aktivieren).
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie Microsoft Exchange Integration aktivieren, wird die Bereinigung für Benutzer, die in Exchange 2013 verwaltet werden, und mit ihren Postfächern, die in Compliance-Archiv abgelegt werden, von Exchange gesteuert. Die einzige Qualifikation besteht für Konferenz Dateien, die auf der lync Server Dateifreigabe gespeichert sind. Diese Dateien werden erst nach dem Export der Dateien aus der Dateifreigabe gelöscht (in Exchange hochgeladen), wenn Sie die Option zum Löschen von Daten nach dem Exportieren der Archivierungsdaten oder nach der angegebenen maximalen Anzahl von Tagen auswählen, wenn Sie eine maximale Anzahl von Tage für die Aufbewahrung.

    
    </div>

Die Archivierungsoptionen sind standardmäßig nicht aktiviert. Sie können Archivierungs Konfigurationen mit lync Server 2013 Systemsteuerung verwalten.

Folgende Archivierungskonfigurationen können angegeben werden:

  - **Globale Archivierungskonfiguration**. Dies ist die Standard Archivierungskonfiguration und gilt für Ihre gesamte Bereitstellung. Sie wird erstellt, wenn Sie lync Server 2013 bereitstellen und standardmäßig keine Archivierungsfunktionen aktivieren. Sie können die globale Konfiguration ändern, aber nicht löschen. Wenn Sie die Option Löschen für die Konfiguration auswählen, wird die globale Konfiguration auf die Standardeinstellungen zurückgesetzt.

  - **Konfiguration für die Standortarchivierung**. Sie können die Archivierung auch für einen oder mehrere spezifische Standorte konfigurieren. Dazu erstellen und konfigurieren Sie eine Archivierungskonfiguration auf Standortebene für einen einzelnen Standort. Archivierungskonfigurationen auf Standortebene sind standardmäßig nicht vorhanden, sondern müssen explizit erstellt werden. Sie können jede Archivierungskonfiguration auf Standortebene bearbeiten oder löschen. Eine Archivierungskonfiguration auf Standortebene überschreibt die globale Konfiguration. Dies gilt jedoch nur für den in der Konfiguration auf Standortebene angegebenen Standort. Wenn Sie beispielsweise in der globalen Konfiguration die Archivierung nur für Sofortnachrichten aktiviert haben und eine Standortkonfiguration erstellen, in der zusätzlich die Archivierung für Konferenzen aktiviert wird, werden Konferenzen nur für den Standort, jedoch nicht für die übrigen Teile der Organisation archiviert.

  - **Konfiguration für die Poolarchivierung**. Sie können auch Archivierungseinstellungen für einen oder mehrere Pools angeben, indem Sie eine Konfiguration auf Poolebene für den jeweiligen Pool erstellen und anpassen. Archivierungskonfigurationen auf Poolebene sind standardmäßig nicht vorhanden, sondern müssen explizit erstellt werden. Sie können jede Archivierungskonfiguration auf Poolebene bearbeiten oder löschen. Eine Archivierungskonfiguration auf Poolebene überschreibt die globale Konfiguration sowie alle ggf. erstellten Archivierungskonfigurationen auf Standortebene. Angenommen, Sie haben die Archivierung nur für Sofortnachrichten in Ihrer globalen Konfiguration aktiviert. Nun erstellen Sie eine Konfiguration auf Standortebene, in der Sie für diesen Standort sowohl die Archivierung für Sofortnachrichten als auch die Archivierung für Konferenzen aktivieren. Anschließend erstellen Sie eine Konfiguration auf Poolebene, in der Sie die Archivierung nur für Sofortnachrichten aktivieren. In diesem Fall wird die Kommunikation sowohl für Sofortnachrichten als auch für Konferenzen archiviert, und zwar für alle Benutzer des Standorts, und zwar mit Ausnahme der Benutzer, die in dem Pool verwaltet werden, der in der Konfiguration auf Poolebene angegeben wurde. Für alle anderen Benutzer in der Organisation wird hingegen nur die Archivierung von Sofortnachrichten aktiviert.

Ausführliche Informationen zum Einrichten der anfänglichen Archivierungs Konfigurationen bei der Bereitstellung der Archivierung finden Sie unter [Configuring Archiving Options in lync Server 2013](lync-server-2013-configuring-archiving-options.md) in der Bereitstellungsdokumentation. Ausführliche Informationen zur Verwendung von Archivierungsrichtlinien zur Aktivierung und Deaktivierung der Kommunikation nach der Bereitstellung finden Sie unter [Managing Archiving Configuration options in lync Server 2013 für Ihre Organisation, Standorte und Pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in der Betriebsdokumentation.

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a>Exklusive Archivierungsoptionen für Windows PowerShell

Mithilfe von lync Server 2013 Management Shell können Sie mithilfe von Cmdlets Optionen implementieren, die in lync Server 2013 Systemsteuerung nicht verfügbar sind. Dazu gehören u. a.:

  - **Archivierung doppelter Nachrichten**. Nähere Informationen finden Sie im Betriebshandbuch unter [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) und unter [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration).

  - **Exportieren archivierter Daten**. Nähere Informationen finden Sie unter [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a>Wie kann ich auf archivierte Daten zugreifen?

Der Zugriff auf archivierte Daten ist abhängig davon, wo die Daten gespeichert wurden:

  - **Microsoft Exchange Speicher**. Wenn Sie die Option für die Exchange-Integration auswählen, lync Server den Archivierungs Inhalt im Exchange 2013 Speicher für alle Benutzer ablegen, die in Exchange 2013 verwaltet werden und deren Postfächer im Compliance-Archiv gespeichert wurden. Archivierte Daten werden im Ordner "Wiederherstellbare Elemente für Benutzerpostfächer" gespeichert, der in der Regel für Benutzer unsichtbar ist und nur von Benutzern mit einer Exchange **Discovery-Verwaltungs** Rolle durchsucht werden kann. Exchange aktiviert die Verbundsuche und-Ermittlung zusammen mit SharePoint, wenn es bereitgestellt wird. Weitere Informationen zum Speichern, zur Aufbewahrung und zur Ermittlung der in Exchange gespeicherten Daten finden Sie in der Dokumentation zu Exchange 2013 und SharePoint.

  - **Lync Server Speicher**. Wenn Sie lync Server 2013 Archivierungsdatenbanken für die Speicherung von lync Server Daten eingerichtet haben, lync Server Ablage von Archivinhalten in den lync Server Archivierungsdatenbanken (SQL Server Datenbanken) für Benutzer, die nicht in Exchange 2013 verwaltet werden und für die keine Postfächer eingerichtet wurden. In-situ-Speicher. Diese Daten sind nicht durchsuchbar, können aber in Formate exportiert werden, die mithilfe anderer Tools durchsuchbar sind. Ausführliche Informationen zum Exportieren von Daten, die in Archivierungsdatenbanken gespeichert sind, finden Sie unter [exportieren archivierter Daten aus lync Server 2013](lync-server-2013-exporting-archived-data.md) in der Betriebsdokumentation.

Weitere Informationen zur Zusammenarbeit von lync Server 2013 und Exchange 2013 finden Sie unter [Exchange Server and SharePoint Integration Support in lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in der Unterstützungsdokumentation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

