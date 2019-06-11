---
title: Migrationsprozess – Details
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39560d69842c104c7db956418dabac9aa6d29d7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a>Migrationsprozess – Details

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Verwenden Sie die folgenden Voraussetzungen und detaillierten Schritte zum Migrieren von lync Server 2010, Gruppen-Chat oder Office Communications Server 2007 R2-Gruppen-Chat zu lync Server 2013, beständiger Chat Server.

<div>

## <a name="prerequisites-for-migration"></a>Voraussetzungen für die Migration

Stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben, bevor Sie entweder lync Server 2010, Gruppen-Chat oder Office Communications Server 2007 R2-Gruppen-Chat zu lync Server 2013, beständiger Chat Server, migrieren.

1.  Bereitstellen von mindestens einem lync Server 2013-Pool Wenn Sie über mehrere lync Server 2013-Pools verfügen, entscheiden Sie, welcher lync Server 2013-Pool als privater Pool für den neuen lync Server 2013-Serverpool für beständige Chats festgelegt wird.

2.  Installieren Sie den Serverpool des lync Server 2013, beständigen Chats. Sie ist leer (keine Kategorien, Räume oder Add-Ins). Bevor Sie Ihre Legacy Kategorien,-Räume oder-Add-ins migrieren, können Sie Räume, Kategorien oder Add-Ins in ihrer lync Server 2013-Bereitstellung des beständigen Chats erstellen.
    
    <div>
    

    > [!IMPORTANT]  
    > Beachten Sie, dass diese neu erstellten Elemente Konflikte mit Legacy Elementen verursachen können, die Sie migrieren. Vermeiden Sie Namenskonflikte; Andernfalls werden Sie überschrieben, wenn die Legacydaten migriert werden.

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a>Vorbereiten der Quelldaten für die Migration

Führen Sie die folgenden Schritte aus, um die Quelldaten für die Migration richtig vorzubereiten.

1.  Sichern Sie die Quelldatenbanken für lync Server 2010, Gruppen-Chat oder Office Communications Server 2007 R2-Gruppen-Chat. Details zum Sichern von SQL Server finden Sie unter "Übersicht über Sicherungen (SQL Server)" unter <http://go.microsoft.com/fwlink/p/?linkid=254851>.
    
    <div>
    

    > [!IMPORTANT]  
    > Die Active Directory-Domänendienste sollten identisch sein. Als Bedingung für die Migration können Sie nicht zu einem Pool in einer anderen Bereitstellung (insbesondere in einer anderen Active Directory-Gesamtstruktur) migrieren.

    
    </div>

2.  Überprüfen Sie Ihre lync Server 2010, Gruppen-Chat oder Office Communications Server 2007 R2-Gruppen-Chatrooms und die Kategorie-Konfiguration. Alle Änderungen an Kategorien, Räumen oder Add-Ins in Ihrer vorhandenen Legacy Bereitstellung werden vom Gruppen-Chat-Verwaltungs Tool ausgeführt.
    
    <div>
    

    > [!TIP]  
    > Alle Änderungen an Kategorien, Räumen oder Add-Ins in ihrer lync Server 2013-Bereitstellung des beständigen Chats werden von der lync Server Control Panel-oder Windows PowerShell-Cmdlets ausgeführt.

    
    </div>
    
    Führen Sie die folgenden Schritte aus, um Ihr Legacy System für die Migration vorzubereiten.
    
    1.  Der beständige Chat Server unterstützt eine einzelne Ebene von Kategorien, anders als eine Tiefe hierarchische Gruppe von Kategorien. Nach der Migration werden den Unterkategorien vollständige übergeordnete Kategorienamen vorangestellt. Möglicherweise möchten Sie die vorhandene Kategorienstruktur vereinfachen und glätten, damit die resultierende Struktur Ihren Anforderungen entspricht.
    
    2.  Überprüfen Sie die **Manager** in der Stammkategorie. Wenn Manager auf dieser Ebene vorhanden sind, werden diese Benutzer nach der Migration als **Manager zu allen Chatrooms** hinzugefügt. Wenn dies für Ihre Organisation nicht erforderlich ist, müssen Sie diese Manager aus der Stammkategorie entfernen.
    
    3.  Überprüfen Sie die Länge von Raumnamen. Wenn die Räume unter einer untergeordneten Kategorie vorhanden sind, werden Sie nach der Migration aufgrund vereinfachter Kategorie-Strukturen mit den vollständigen übergeordneten Kategorienamen belegt. Die Benennungs Grenze ist 256 Zeichen, einschließlich übergeordneter Kategorienamen. Sie müssen die Länge der Raumnamen überprüfen und möglicherweise die Länge verkürzen, wenn Sie zu lang sind.
    
    4.  Wenn in lync Server 2013 die Einstellungen für die Kategorie- **Einladungen** auf "true" festgelegt sind, können Sie für Einladungen zu Räumen unter dieser Kategorie "wahr" oder "falsch" auswählen. Wenn die Einstellungen für die Kategorie-Einladungen aber auf "falsch" festgelegt sind, werden in Räumen unter dieser Kategorie Einladungen deaktiviert. Vor der Migration müssen Sie die Einladungseinstellungen in ihrer älteren lync Server-Gruppen-Chat Server Version zurücksetzen, wenn Sie möchten, dass Raum (e) unter einer bestimmten Kategorie vorhanden ist. Andernfalls zeigt lync Server 2013 während der Migration Warnungen an und legt Räume auf den Standardwert false fest.
    
    5.  Wenn Sie Dateien in Chatrooms verwendet haben, müssen Sie die Dateien nach der Migration manuell in den neuen beständigen Chat-Dateispeicher herunterladen. Die Tools tun dies nicht.
    
    6.  Wenn Sie Verbundbenutzer und Chatrooms mit Verbundbenutzern hatten, beachten Sie, dass der Server für beständigen Chat keine Föderation unterstützt. Räume mit Verbundbenutzern werden migriert. die Benutzer können jedoch nicht auf die Inhalte zugreifen, da der Verbundzugriff nicht unterstützt wird.
    
    7.  Identifizieren Sie die Chatrooms, die Sie nicht migrieren möchten, und markieren Sie Sie als deaktiviert.
    
    8.  Ermitteln Sie das Datum, über das Sie den Chatroom-Inhalt migrieren möchten. So möchten Sie beispielsweise Nachrichten nicht vor dem 1. Januar 2010 migrieren, da diese Nachrichten möglicherweise veraltet oder für die Migration nicht relevant sind.

</div>

<div>

## <a name="performing-the-migration"></a>Durchführen der Migration

Führen Sie die folgenden Schritte aus, um Ihren Legacy-Gruppen-Chat Server zu migrieren.

1.  Beenden Sie lync Server 2010, Gruppen-Chat, Office Communications Server 2007 R2-Gruppenchat oder lync Server 2013, beständige Chat Server Dienste. Damit alle Dienste gestoppt werden können, sollten Sie dies zu einem Zeitpunkt planen, zu dem genügend Ausfallzeiten vorhanden sind. Vergewissern Sie sich wie zuvor beschrieben, dass Sie Ihre aktuelle Gruppen-Chat-Datenbank sichern.

2.  Führen Sie das Cmdlet "Windows PowerShell **Export-CsPersistentChatData** " als Mitglied der Administratorrolle "beständiger Chat" (CsPersistentChatAdministrator) aus. Details zu den Export/Import-Cmdlets finden Sie unter [Problembehandlung bei der Server Konfiguration für beständigen Chat mit Windows PowerShell-Cmdlets in lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).
    
    Überprüfen Sie die exportierten Inhalte.

3.  Bevor Sie zum Importieren bereit sind, beenden Sie lync Server 2013, Server Dienste für beständigen Chat. Damit alle Dienste gestoppt werden können, sollten Sie dies zu einem Zeitpunkt planen, zu dem genügend Ausfallzeiten vorhanden sind.

4.  Führen Sie eine Sicherungskopie der persistenten Chat-Datenbank aus, wenn Sie vor der Migration Kategorien, Räume oder Add-Ins in ihrer lync Server 2013-Bereitstellung erstellt haben. Der Export/Import-Prozess kann die Legacydaten in die lync Server 2013-Bereitstellung zusammenführen, doch Sie möchten die Datenbank sichern, falls dieser Inhalt versehentlich überschrieben wird (beispielsweise, wenn Benennungskonflikte weiterhin vorhanden sind).

5.  Führen Sie das Windows PowerShell **-Import-CsPersistentChatData-** Cmdlet (Import Tool) mit einem **WhatIf** -Befehl aus, um den Back-End-Server des beständigen Chat Server Pools mit migrierten Daten zu füllen. Einige Konvertierungen erfolgen im Prozess, um dem vereinfachten Verwaltungsmodell gerecht zu werden. Beheben Sie alle angezeigten Fehler oder Warnungen.

6.  Führen Sie das Cmdlet "beständiger Chat Server Windows PowerShell **-Import-CsPersistentChatData** " als Mitglied der Administratorrolle "beständiger Chat" (CsPersistentChatAdministrator) aus. Details zu den Export/Import-Cmdlets finden Sie unter [Problembehandlung bei der Server Konfiguration für beständigen Chat mit Windows PowerShell-Cmdlets in lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).

7.  Sie müssen alle hochgeladenen Dateien (den gesamten Ordner) in den neuen lync Server 2013-Dateispeicher für persistente Chats übertragen.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync 2013 (Client) unterstützt das Hochladen oder Anzeigen von Dateien in Chatrooms nicht. Sie können den Legacyclient weiterhin verwenden, um Dateien im Chatroom zu Posten und anzuzeigen.

    
    </div>

8.  Portieren Sie lync Server 2010, Gruppen-Chat oder Office Communications Server 2007 R2-Gruppen-Chat-Nachschlage Server-URI zum lync Server 2013-Kontaktobjekt für beständigen Chat Server. Die folgenden Schritte sind erforderlich, wenn sich entweder Ihr lync 2010-Gruppen-Chat oder die Office Communicator 2007 R2-Gruppen-Chat-Clients nach der Migration ohne clientseitige Konfigurationsänderungen mit dem neuesten lync 2013, beständigen Chat (Client) verbinden müssen:
    
      - Löschen Sie das Benutzer\<Konto OCSChat\>@ Domain Name. com Lookup Server. Dies wurde verwendet, um auf den Nachschlage Dienst in lync Server 2010, Gruppen-Chat, zu verweisen. Sie können den Pool deinstallieren und vertrauenswürdige Einträge später entfernen.
    
      - Erstellen Sie einen Legacy Endpunkt (Kontaktobjekt für beständigen Chat Server), indem Sie das Windows PowerShell **-Cmdlet New-CsPersistentChatEndpoint**mit dem identischen SIP-URI ausführen, damit der Legacyclient effektiv funktioniert, wenn der Dienst neu gestartet wird.
    
    Der obligatorische Migrationsprozess ist an diesem Punkt abgeschlossen. Lync 2010-Gruppen-Chats (Clients) oder Office Communicator 2007 R2-Gruppen-Chat (Clients) können jetzt transparent eine Verbindung mit dem neuen beständigen Chat Server Pool herstellen.
    
    Befolgen Sie diese zusätzlichen Schritte zur Außerbetriebnahme für lync Server 2010, Gruppen-Chat oder Office Communications Server 2007 R2-Gruppen-Chat.

9.  Starten Sie die Server Dienste für beständigen Chat, indem Sie alle Computer im neuen beständigen Chat Serverpool aktivieren.

10. Verwenden Sie die lync Server-Systemsteuerung und die Windows PowerShell-Cmdlets, um zu überprüfen, ob die Daten erfolgreich migriert wurden.

11. Deinstallieren Sie den lync 2010-Gruppen-Chat oder den Office Communicator 2007 R2-Gruppen-Chat von den Computern im Gruppen-Chat-Server Pool.

12. Löschen Sie die vertrauenswürdige Anwendung und den vertrauenswürdigen Anwendungspool mithilfe von Windows PowerShell-Cmdlets. Dadurch werden diese Elemente aus dem zentralen Verwaltungsspeicher und den zugehörigen TSE (Trusted Service Entries) aus dem Active Directory gelöscht. Alternativ funktioniert dieser Schritt mithilfe des Topologie-Generators (die vertrauenswürdigen Anwendungen/Pools verfügen ebenfalls über einen dedizierten Knoten).

13. Sie können jetzt beginnen, die Funktion des beständigen Chat Servers über die neuen Clients zu aktivieren. Ausführliche Informationen zum Aktivieren des Servers für beständigen Chat finden Sie unter [Bereitstellen eines persistenten Chat Servers in lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 unterstützt mehrere Server Pools für beständigen Chat. Wir unterstützen allerdings die Migration eines lync 2010-Gruppen-oder Office&nbsp;Communications Server 2007 R2-Gruppen-Chat Pools zu einem einzelnen lync Server 2013, beständigen Chat Serverpool. Sie können weitere neue Server Pools für beständigen Chat in Ihrer Bereitstellung hinzufügen, um die regulatorischen Anforderungen zu erfüllen (beispielsweise das Beibehalten von Daten in einer bestimmten geografischen Region).

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

