---
title: Migrationsprozess – Details
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79db601ccf6f87f19526f68d0e20521985092937
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a>Migrationsprozess – Details

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

Verwenden Sie die folgenden Voraussetzungen und detaillierten Schritte zum Migrieren von lync Server 2010, Gruppenchats oder Office Communications Server 2007 R2 Gruppenchats zu lync Server 2013 persistent Chat Server.

<div>

## <a name="prerequisites-for-migration"></a>Voraussetzungen für die Migration

Stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben, bevor Sie entweder lync Server 2010, Gruppenchat oder Office Communications Server 2007 R2 Gruppenchat in lync Server 2013 persistent Chat Server migrieren.

1.  Stellen Sie mindestens einen lync Server 2013 Pool bereit. Wenn Sie über mehrere lync Server 2013 Pools verfügen, müssen Sie entscheiden, welcher lync Server 2013 Pool als Home-Pool für den neuen beständiger Chat von lync Server 2013 Server Pool verwendet wird.

2.  Installieren Sie den Server Pool für beständigen Chat lync Server 2013. Sie wird leer sein (keine Kategorien, Räume oder Add-Ins). Bevor Sie Ihre Legacy Kategorien,-Räume oder-Add-ins migrieren, können Sie Räume, Kategorien oder Add-Ins in ihrer lync Server 2013-Server Bereitstellung für beständigen Chat erstellen.
    
    <div>
    

    > [!IMPORTANT]  
    > Beachten Sie, dass diese neu erstellten Elemente möglicherweise mit Legacy Elementen in Konflikt stehen, die Sie migrieren. Vermeiden von Namenskonflikten Andernfalls werden Sie bei der Migration der Legacydaten überschrieben.

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a>Vorbereiten der Quelldaten für die Migration

Führen Sie die folgenden Schritte aus, um die Quelldaten für die Migration ordnungsgemäß vorzubereiten.

1.  Sichern Sie die Quelldatenbanken entweder für lync Server 2010, Gruppenchat oder Office Communications Server 2007 R2 Gruppenchat. Ausführliche Informationen zum Sichern von SQL Server finden Sie unter "Übersicht über Sicherungen (SQL Server)" <https://go.microsoft.com/fwlink/p/?linkid=254851>unter.
    
    <div>
    

    > [!IMPORTANT]  
    > Active Directory-Domänendienste sollte identisch sein. Als Bedingung für die Migration können Sie nicht zu einem Pool in einer anderen Bereitstellung migrieren (insbesondere in einer anderen Active Directory Gesamtstruktur).

    
    </div>

2.  Überprüfen Sie Ihre lync Server 2010, Gruppenchats oder Chaträume für Chats in Office Communications Server 2007 R2 Gruppen und die Kategorien Konfiguration. Alle Änderungen an Kategorien, Räumen oder Add-Ins in Ihrer vorhandenen Legacy-Bereitstellung werden vom Gruppen Chat-Verwaltungs Tool ausgeführt.
    
    <div>
    

    > [!TIP]  
    > Alle Änderungen an Kategorien, Chatrooms oder Add-Ins in ihrer lync Server 2013, die Bereitstellung von persistent Chat Server werden von den Cmdlets lync Server-Systemsteuerung oder Windows PowerShell ausgeführt.

    
    </div>
    
    Führen Sie die folgenden Schritte aus, um Ihr Legacy System auf die Migration vorzubereiten.
    
    1.  Der Server für beständigen Chat unterstützt eine einzelne Ebene von Kategorien, im Gegensatz zu einer tiefen hierarchischen Gruppe von Kategorien. Nach der Migration wird den Unterkategorien der vollständige Name der übergeordneten Kategorie vorangestellt. Möglicherweise möchten Sie die vorhandene Kategorienstruktur vereinfachen und so reduzieren, dass die resultierende Struktur Ihren Anforderungen entspricht.
    
    2.  Überprüfen Sie die **Manager** in der Stammkategorie. Wenn auf dieser Ebene Manager vorhanden sind, werden diese Benutzer nach der Migration als **Manager zu allen Chatrooms** hinzugefügt. Wenn dies für Ihre Organisation nicht erforderlich ist, müssen Sie diese Manager aus der Stammkategorie entfernen.
    
    3.  Überprüfen Sie die Länge von Raum Namen. Wenn die Räume unter einer untergeordneten Kategorie vorhanden sind, werden Sie nach der Migration aufgrund vereinfachter Kategorien Strukturen mit den vollständigen übergeordneten Kategorienamen vorangestellt. Die Benennungs Grenze beträgt 256 Zeichen, einschließlich übergeordneter Kategorienamen. Sie müssen die Länge der Raumnamen überprüfen und möglicherweise die Länge kürzen, wenn Sie zu lang sind.
    
    4.  Wenn die Einstellungen für Kategorie- **Einladungen** in lync Server 2013 auf "true" festgelegt sind, können Sie "true" oder "false" für Einladungen zu Räumen unter dieser Kategorie auswählen. Wenn die Einstellungen für Kategorie-Einladungen jedoch auf "false" festgelegt sind, sind für die Räume unter dieser Kategorie Einladungen deaktiviert. Vor der Migration müssen Sie die Einstellungen für die Einladung in Ihrer Legacy-lync Server-Gruppen Chat Server Version zurücksetzen, wenn Sie möchten, dass in einer bestimmten Kategorie Raum (e) vorhanden sind. Andernfalls zeigt lync Server 2013 während der Migration Warnungen an und legt die Räume auf den Standardwert false fest.
    
    5.  Wenn Sie Dateien in Chatrooms verwendet haben, müssen Sie die Dateien nach der Migration manuell in den neuen Dateispeicher für beständigen Chat einbetten. Die Tools tun dies nicht.
    
    6.  Wenn Sie Verbundbenutzer und-Räume mit Verbundbenutzern hatten, beachten Sie, dass der Server für beständigen Chat keinen Partnerverbund unterstützt. Räume mit Verbundbenutzern werden migriert; die Benutzer können jedoch nicht auf den Inhalt zugreifen, da der Verbundzugriff nicht unterstützt wird.
    
    7.  Identifizieren Sie die Räume, die nicht migriert werden sollen, und markieren Sie Sie als deaktiviert.
    
    8.  Bestimmen Sie das Datum, über dem der Chatroom-Inhalt migriert werden soll. Beispielsweise können Sie Nachrichten nicht vor dem 1. Januar 2010 migrieren, da diese Nachrichten möglicherweise veraltet sind oder für die Migration nicht relevant sind.

</div>

<div>

## <a name="performing-the-migration"></a>Durchführen der Migration

Führen Sie die folgenden Schritte aus, um Ihren Legacy-Gruppen Chat Server zu migrieren.

1.  Beenden Sie die lync Server 2010, Gruppenchat, Office Communications Server 2007 R2 Gruppenchat oder lync Server 2013, Server Dienste für beständigen Chat. Alle Dienste müssen angehalten werden, daher sollten Sie dies zu einem Zeitpunkt planen, an dem genügend Ausfallzeiten vorhanden sind. Wie bereits beschrieben, müssen Sie die aktuelle Gruppen Chat Datenbank sichern.

2.  Führen Sie das Windows PowerShell **-Cmdlet Export-CsPersistentChatData** als Mitglied der Administratorrolle für beständigen Chat ("cspersistentchatadministrator") aus. Ausführliche Informationen zu den Export/Import-Cmdlets finden Sie unter [Troubleshooting persistent Chat Server Configuration using Windows PowerShell Cmdlets in lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).
    
    Überprüfen Sie die exportierten Inhalte.

3.  Bevor Sie den Import vorbereiten können, fahren Sie lync Server 2013 Server Dienste für beständigen Chat herunter. Alle Dienste müssen angehalten werden, daher sollten Sie dies zu einem Zeitpunkt planen, an dem genügend Ausfallzeiten vorhanden sind.

4.  Führen Sie eine Sicherung der Datenbank für beständigen Chat aus, wenn Sie vor der Migration Kategorien, Räume oder Add-Ins in ihrer lync Server 2013-Bereitstellung erstellt haben. Der Export/Import-Prozess kann die Legacydaten in die lync Server 2013-Bereitstellung zusammenführen, aber Sie sollten die Datenbank sichern, falls der Inhalt versehentlich überschrieben wird (beispielsweise wenn noch Benennungskonflikte bestehen).

5.  Führen Sie das Windows PowerShell **Import-CsPersistentChatData-** Cmdlet (Import Tool) mit dem Befehl **WhatIf** aus, um den Back-End-Server des Server Pools für beständigen Chat mit migrierten Daten aufzufüllen. Einige Konvertierungen geschehen im Prozess, um das vereinfachte Verwaltungsmodell aufzunehmen. Beheben Sie alle angezeigten Fehler oder Warnungen.

6.  Führen Sie den Server für beständigen Chat Windows PowerShell Cmdlets **Import-CsPersistentChatData** als Mitglied der Rolle "Administratorrollen für beständigen Chat" ("cspersistentchatadministrator") aus. Ausführliche Informationen zu den Export/Import-Cmdlets finden Sie unter [Troubleshooting persistent Chat Server Configuration using Windows PowerShell Cmdlets in lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).

7.  Sie müssen alle hochgeladenen Dateien (den gesamten Ordner) in den Dateispeicher des neuen lync Server 2013 persistent Chats xcopy.
    
    <div>
    

    > [!IMPORTANT]  
    > Der lync 2013 (Client) unterstützt das Hochladen oder Anzeigen von Dateien in Chatrooms nicht. Sie können den Legacy-Client weiterhin verwenden, um Dateien im Chatroom zu veröffentlichen und anzuzeigen.

    
    </div>

8.  Portieren Sie den lync Server 2010-, Gruppenchat-oder Office Communications Server 2007 R2 Gruppenchat-Suchserver-URI in das Kontaktobjekt für den lync Server 2013 persistent Chat Server. Die folgenden Schritte sind erforderlich, wenn Ihre lync 2010 Gruppenchats oder Office Communicator 2007 R2 Gruppenchatclients nach der Migration ohne clientseitige Konfigurationsänderungen eine Verbindung mit dem neuesten lync 2013, beständigen Chat (Client) herstellen müssen:
    
      - Löschen Sie das\<Benutzerkonto\>OCSChat@ Domain Name. com Lookup Server. Dies wurde verwendet, um auf den Suchdienst in lync Server 2010, Gruppen Chat, zu deuten. Sie können den Pool deinstallieren und später vertrauenswürdige Einträge entfernen.
    
      - Erstellen Sie einen Legacy Endpunkt (Kontaktobjekt für beständigen Chat Server), indem Sie das Windows PowerShell **-Cmdlet New-cspersistentchatendpoint "** mit dem identischen SIP-URI ausführen, sodass der Legacyclient beim Neustart des Diensts effektiv funktioniert.
    
    Der obligatorische Migrationsprozess ist an dieser Position abgeschlossen. Lync 2010 Gruppenchat (Clients) oder Office Communicator 2007 R2 Gruppenchat (Clients) können jetzt transparent eine Verbindung mit dem neuen Server Pool für beständigen Chat herstellen.
    
    Befolgen Sie diese zusätzlichen außerbetriebnahmes Schritte für lync Server 2010, Gruppenchat oder Office Communications Server 2007 R2 Gruppenchat.

9.  Starten Sie die Server Dienste für beständigen Chat, indem Sie alle Computer im neuen Serverpool für beständigen Chat aktivieren.

10. Verwenden Sie die Cmdlets lync Server-Systemsteuerung und Windows PowerShell, um zu überprüfen, ob die Daten erfolgreich migriert wurden.

11. Deinstallieren Sie lync 2010 Gruppenchat oder Office Communicator 2007 R2 Gruppenchat von den Computern im Gruppenchat Server-Pool.

12. Löschen Sie den vertrauenswürdigen Anwendungspool mit Windows PowerShell-Cmdlets. Dadurch werden diese Elemente aus dem zentralen Verwaltungsspeicher und den zugeordneten TSE (Trusted Service Entries) aus dem Active Directory gelöscht. Alternativ funktioniert dieser Schritt mithilfe des Topologie-Generators (die vertrauenswürdigen Anwendungen/Pools verfügen ebenfalls über einen dedizierten Knoten).

13. Sie können jetzt mit dem Aktivieren der Funktion für beständigen Chat Server über die neuen Clients beginnen. Ausführliche Informationen zum Aktivieren des Servers für beständigen Chat finden Sie unter [Deploying persistent Chat Server in lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 unterstützt mehrere Server Pools für beständigen Chat. Wir unterstützen jedoch die Migration eines lync 2010 Gruppenchats&nbsp;oder Office Communications Server 2007 R2 Gruppen-Chat Pools in einen einzelnen lync Server 2013 Server Pool für beständigen Chat. Sie können zusätzliche neue Server Pools für beständigen Chat in Ihrer Bereitstellung hinzufügen, um die regulatorischen Anforderungen zu erfüllen (beispielsweise das Beibehalten von Daten in einer bestimmten Geografie).

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

