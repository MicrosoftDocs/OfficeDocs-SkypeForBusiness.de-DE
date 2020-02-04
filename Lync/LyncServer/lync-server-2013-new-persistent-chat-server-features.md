---
title: 'Lync Server 2013: Neue Funktionen für den Server für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe207d2469a36d880e9ed519ff1d47d942ed79aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a>Neue Funktionen für den Server für beständigen Chat in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-29_

Lync Server 2013, beständiger Chat Server ermöglicht Ihnen, an mehrteiligen, themenbasierten Konversationen teilzunehmen, die im Laufe der Zeit fortbestehen. Der beständige Chat Server kann Ihrer Organisation helfen, Folgendes zu tun:

  - Verbessern der Kommunikation zwischen geografisch verteilten und funktionsübergreifenden Teams

  - Erweitern des Informations Bewusstseins und der Teilnahme

  - Verbessern der Kommunikation mit ihrer erweiterten Organisation

  - Reduzieren der Informationsüberlastung

  - Verbessern des Informations Bewusstseins

  - Verbessern der Verbreitung wichtiger Kenntnisse und Informationen

Lync Server 2013, beständiger Chat Server steht in Microsoft Office 365 nicht zur Verfügung. Zu diesem Zeitpunkt steht er nur für lokale lync 2013-Kunden zur Verfügung.

In lync 2013 ist die Funktionalität des beständigen Chats in den lync 2013-Client integriert. Daher haben Benutzer Zugriff auf Instant Messaging/Anwesenheit, Audio/Video, Konferenzen und beständigen Chat alle im lync 2013-Client. Weitere Informationen zum lync 2013-Client finden Sie unter <http://go.microsoft.com/fwlink/p/?linkid=270877>.

In diesem Thema werden die Funktionsänderungen zwischen der neuen Version von lync Server 2013, dem beständigen Chat Server und der vorherigen Version (Microsoft lync Server 2010, Gruppen Chat) beschrieben, einschließlich:

  - Bereitstelleneiner administrativen Funktionalität in der lync Server-Systemsteuerung und eliminieren des Administrator Tools für Gruppenchats

  - Integrieren von Konfigurationseinstellungen für beständigen Chat Server in den Topologie-Generator durch Eliminierung des Gruppen-Chat-Konfigurationstools

  - Einfache Migration und Upgrade von vorherigen Versionen des beständigen Chat Servers

  - Bereitstellen von Hochverfügbarkeits-und Disaster Recovery-Lösungen

Weitere Informationen zur neuesten Version des beständigen Chat Servers finden Sie unter den folgenden Themen:

  - In <http://go.microsoft.com/fwlink/p/?linkid=270945> der Hilfe für beständigen Chat finden Sie eine detaillierte Liste der beständigen Chat Features, ihre Funktionsweise und ihre Verwendung während des beständigen Chat Servers.

  - Der [Server für die Planung des beständigen Chats in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation [Bereitstellen des beständigen Chat Servers in lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in der Bereitstellungsdokumentation, [Migration von lync Server 2010, Gruppen-Chat oder Office Communications Server 2007 R2-Gruppenchat zu lync Server 2013, beständiger Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) in der Migrationsdokumentation und [Verwalten von lync Server 2013, beständiger Chat Server](managing-lync-server-2013-persistent-chat-server.md) in der Betriebsdokumentation, die alle Anleitungen für die Einrichtung enthalten Beständiger Chat Server.

  - Mit der Datei "beständiger Chat Server Documentation. msi" (Windows Installer-Datei) können Benutzer auf eine umfassende offlinedokumentation über den Server für beständigen Chat zugreifen.

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a>Änderungen an wichtigen Topologien für beständigen Chat Server

Die folgenden allgemeinen Änderungen für beständigen Chat Server sind:

Der beständige Chat Server ist nun eine Serverrolle. In Microsoft lync Server 2010 war der Gruppen-Chat Server eine vertrauenswürdige Anwendung eines Drittanbieters für Microsoft lync Server 2010. Beständiger Chat kann ihrer lync Server 2013-Topologie mithilfe des Topologie-Generators hinzugefügt werden. In lync Server 2013 wird die Funktion des beständigen Chat Servers mithilfe von drei neuen Serverrollen implementiert:

  - **PersistentChatService:** Dies ist die Front-End-Rolle für beständigen Chat. In Standard Edition-Bereitstellungen wird die Server Dienst Rolle des beständigen Chats auf dem Standard Edition-Server, der von Bootstrapper bereitgestellt wird, wie jede andere lync-Serverrolle verwendet. In Enterprise Edition-Bereitstellungen wird die Funktion des beständigen Chats auf eigenständigen Computern nach Bootstrapper wie jede andere lync-Server Rolle bereitgestellt.

  - **PersistentChatStore:** Back-End-Server, der der Inhaltsdatenbank für beständigen Chat entspricht, in der alle Chatinhalte gespeichert sind.

  - **PersistentChatComplianceStore:** Back-End-Server Rolle, die der Compliance-Datenbank für beständigen Chat entspricht, in der alle Compliance-Ereignisse gespeichert sind.

Diese Serverrollen für beständigen Chat sind optional und werden nur von Kunden installiert, die umfassende Funktionen für den beständigen Chat Server wünschen. Die Rolle **PersistentChatComplianceStore** ist nur erforderlich, wenn Sie die Compliance für beständigen Chat bereitstellen möchten.

Die **PersistentChatService** -Rolle führt zwei Dienste aus:

  - Beständiger Chat Dienst

  - Kompatibilitätsdienst für beständigen Chat

Wenn diese Dienste auf jedem beständigen Chat Server ausgeführt werden, bietet diese Dienste in einem persistenten Chat Serverpool eine höhere Verfügbarkeit.

Um den Dateiupload und-Download in beständige Chatrooms zu unterstützen, enthält der beständige Chat Server zudem einen Webdienst. Zuvor war dieser Dienst auf dem Server für beständigen Chat, dem Front-End-Server und den erforderlichen Internet Informationsdiensten (IIS) installiert, um als Voraussetzung zu installieren. Im lync Server 2013-Server für beständigen Chat befindet sich der Web Servicedatei Upload/-Download mit dem lync Server 2013-Front-End-Server. Als Nebeneffekt ist Internet Information Services (IIS) nicht mehr eine Voraussetzung für beständigen Chat Server. Der Webdienst für Datei Upload/-Download wird im Internet Informationsdienste (IIS)-Manager als **PersistentChat** identifiziert.

<div>


> [!IMPORTANT]  
> Die <STRONG>PersistentChatService</STRONG> -Rolle kann nur auf dem gleichen Server wie ein lync Server&nbsp;2013-Front-End-Server ausgeführt werden, wenn der Front&nbsp;-End-Server ein Standard Edition-Front-End-Server ist. Die <STRONG>PersistentChatService</STRONG> -Rolle kann nicht unabhängig von einem lync Server&nbsp;2013-Front-End-Server ausgeführt werden. Sie kann nur im Kontext einer lync Server 2013-Bereitstellung installiert werden.



</div>

Im beständigen Chat Server wurde der Suchdienst eliminiert. In lync Server 2010, Gruppen-Chat, wurde der Nachschlage Dienst auf jedem Front-End-Server des Gruppen-Chat Servers ausgeführt und auf einen der Kanalserver geroutet. Lync Server 2013 basiert auf dem Routing mithilfe von Kontaktobjekten, wobei jeder beständige Chat Serverpool durch ein Kontaktobjekt dargestellt wird, das von den lync Server-Front-End-Servern zum Identifizieren und Weiterleiten von Anforderungen an einen geeigneten beständigen Chat Serverpool verwendet wird, und einer der Computer, auf dem der beständige Chat Server im Pool ausgeführt wird.

In lync Server 2013 sind Kompatibilitätsdienst Änderungen vorhanden:

  - In lync Server 2010 wurde der Kompatibilitätsdienst eigenständig (nicht in der Lage) und nur auf einem einzelnen Server ausgeführt. Der Kompatibilitätsdienst wird nun neben dem beständigen Chatdienst auf allen Front-End-Servern des beständigen Chats ausgeführt und bietet dadurch eine höhere Verfügbarkeit in einem persistenten Chat Serverpool. Ein einzelner Kompatibilitätsadapter kann so konfiguriert werden, dass Daten aus der Kompatibilitätsdatenbank und einem anderen System (XML-Datei, Exchange-gehostete Archive usw.) extrahiert werden. Der beständige Chat Server enthält einen XML-Adapter.

  - Die Warteschlange für Message Queuing (auch als MSMQ bezeichnet), die vom beständigen Chatdienst und dem Kompatibilitätsdienst auf jedem beständigen Chat Server-Front-End-Server freigegeben wird, ist jetzt eine private Warteschlange, die nur von den beiden Diensten freigegeben wird. Alle Konformitäts Dienste schreiben in dieselbe Compliance-Back-End-Datenbank. Sie haben auch alle aus dieser Datenbank gelesen, um die Daten an Ihre Instanz des Adapters zu senden. Der Compliance-Back-End-Server wird als neue Back-End-Serverrolle dargestellt.
    
    <div>
    

    > [!IMPORTANT]  
    > Wie in früheren Versionen werden alle Kompatibilitätsdaten nur einmal verarbeitet. Die Daten können von allen Adapter Instanzen verarbeitet werden, die vom Kompatibilitätsdienst aufgerufen werden, der auf den verschiedenen lync Server 2013-, persistent Chat Server-Computern ausgeführt wird. In einem beständigen Chat Server können alle Adapter Instanzen die Daten verarbeiten.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Informationen zum Installieren von Message Queuing finden Sie unter <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Installieren von Betriebssystemen und der erforderlichen Software auf Servern für lync Server 2013</A> in der Bereitstellungsdokumentation.

    
    </div>

In lync Server 2013 gibt es Verbesserungen bei der Hochverfügbarkeits-und Disaster Recovery:

  - Verbesserungen bei hoher Verfügbarkeit: die SQL Server-Spiegelung wird verwendet, um eine höhere Verfügbarkeit für die Inhaltsdatenbank des beständigen Chat Servers und die Datenbank für beständigen Chat in einem Rechenzentrum (in-Site) bereitzustellen.

  - Verbesserungen bei der Disaster Recovery: der beständige Chat Server unterstützt eine ausgestreckte Pool Architektur, die es ermöglicht, einen einzelnen beständigen Chat Serverpool über zwei Standorte (also einen einzigen logischen Pool in der Topologie) zu dehnen, wobei die Server im Pool physisch befindet sich über zwei Standorte). Der SQL Server-Protokollversand wird für die websiteübergreifende Notfallwiederherstellung verwendet.

Weitere Informationen zu Hochverfügbarkeits-und Disaster Recovery finden Sie unter [Konfigurieren des beständigen Chat Servers für Hochverfügbarkeits-und Disaster Recovery in lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in der Bereitstellungsdokumentation.

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a>Wichtige Änderungen bei der Verwaltung und Verwaltung für beständigen Chat Server

Lync Server 2013 hat das Verwalten und Verwalten von beständigen Chat Servern vereinfacht, indem Sie Folgendes bereitgestellt haben:

  - Einheitliche Verwaltung und Verwaltung Lync Server 2013 vereinfacht das Verwalten und Verwalten des beständigen Chat Servers mithilfe von Tools, die lync-Administratoren bereits vertraut sind. Der Server für beständigen Chat umfasst eine Benutzeroberflächen-Administratoroberfläche, die in die lync Server-Systemsteuerung integriert ist und Leistungsprobleme mit den vorherigen Versionen der Benutzeroberfläche des Gruppen-Chat Servers behebt. Darüber hinaus enthält der Server für beständigen Chat eine Sammlung von Windows PowerShell-Cmdlets zum Verwalten und verwalten beständiger Chat Server Kategorien, beständiger Chatrooms (einschließlich Löschen von Räumen und bereinigen veralteter Inhalte) sowie Add-Ins.

  - Vereinfachtes Verwaltungsmodell Lync Server 2013 hat das Server Modell für beständigen Chat geändert und vereinfacht, indem es die folgenden wichtigen Kundenanforderungen erfüllt:
    
      - Entfernen Sie die komplexen geschachtelten Hierarchien von Bereichen und Kategorien.
    
      - Unterstützung zum Definieren von Verweigerungslisten sowie zulässiger Listen (Bereiche) für aktuelle MindAlign-Kunden, die beabsichtigen, zum Server für beständigen Chat zu migrieren.

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a>Worin unterscheiden sich die Benutzerrollen aus früheren Gruppen-Chat Server Versionen?

Lync Server 2010, Gruppen-Chat hatte eine Benutzeradministratorrolle, eine Chatroom-Administratorrolle und eine lync Server-Administratorrolle, die Add-Ins verwalten konnte. beständiger Chat Server bietet einfach eine permanente Chat Administratorrolle (ähnlich wie andere lync Rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC)). Jeder, der Mitglied dieser RBAC-Rolle ist, kann Chatrooms, Add-Ins und Kategorien verwalten (und dadurch den Benutzer Zugriff für diese Kategorien gewinnen) und die Konfiguration des beständigen Chat Server Pools.

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a>Welche Unterschiede gibt es zu Chatroom-Kategorien aus früheren Gruppen-Chat Server Versionen?

Chatroom-Kategorien können nicht mehr geschachtelt werden, und die Stammkategorie kann nicht mehr geändert werden. AllowedMembers/DeniedMembers enthalten einen Bereich, der in Legacy Gruppen-Chat Server Versionen verwendet wurde (mit der Ausnahme, dass die Angabe einer verweigerten Liste nicht unterstützt wurde). Bereiche können nicht mehr überschrieben werden, da es keine geschachtelten Kategorien gibt. Ein Administrator für beständigen Chat in lync Server 2013 kann Chatroom-Kategorien erstellen und verwalten. Im Rahmen des Erstellens und Verwaltens von Chatroom-Kategorien kann ein beständiger Chat-Administrator Prinzipale (Active Directory-Gruppen/-Container/-Benutzer) konfigurieren, die Zugriff auf Mitglieder/Ersteller von Chatrooms einer bestimmten Kategorie haben. Ein Administrator des beständigen Chats kann auch DeniedMembers zu einer Kategorie hinzufügen, und diese werden explizite Ausnahmen für die zulässige Liste. Einträge unter „DeniedMembers“ haben Vorrang vor Einträgen unter „AllowedMembers“.

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a>Was unterscheidet sich von den Chatroom-Eigenschaften aus früheren Gruppen-Chat Server Versionen?

Ein neues Konzept offener Chatrooms ist in lync Server 2013, beständiger Chat Server, vorhanden. Alle zulässigen Mitglieder können dem Chatroom beitreten, ohne eine exklusive Mitgliedschaft zu haben.

Die folgenden Chatroom-Eigenschaften, die in früheren Versionen des beständigen Chat Servers enthalten waren, wurden eliminiert:

  - Thema: ein Raum hat jetzt nur eine Beschreibung.

  - Neue Mitgliederliste erstellen: auf dem Server für beständigen Chat beginnen alle Chatrooms mit einer leeren Mitgliedschaft (und können eine Mitgliedschaft maximieren, die den zulässigen Mitgliedern entspricht).

  - Dateiupload: verwendet als eine Einstellung pro Chatroom, um zu steuern, ob Dateiupload/-Downloads zulässig sind. Damit wird nun nur die Kategorieebene festgesetzt und gilt für alle Räume in dieser Kategorie.

  - Chat-Protokoll: verwendet als eine Einstellung pro Chatroom, um zu steuern, ob das Chat-Protokoll aktiviert wurde, aber jetzt nur auf der Kategorieebene festgelegt ist und für alle Räume in dieser Kategorie gilt.

  - Einladungen: ein Raum erbt immer die Einstellung Einladungen für die Kategorie; oder es kann auf dem Raum ausgeschaltet werden. Ein Raum kann Einladungen nicht aktivieren, wenn die Kategorie zuvor auf Einladungen aus eingestellt wurde.

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a>Was unterscheidet sich von den Richtlinien aus früheren Gruppen-Chat Server Versionen?

Der Server für beständigen Chat hat eine neue lync-Richtlinie mit beständigem Chat, pro Benutzer/Pool/Website/globale Einstellungen aktiviert. Im lync 2013-Client ist die Umgebung für beständigen Chat nur für Benutzer verfügbar, die durch Richtlinie für beständigen Chat aktiviert sind (entweder direkt oder über die Einstellung Pool/Website/Global).

In früheren Versionen des Gruppen Chat Servers wurden keine Richtlinien in die lync-Server Richtlinien integriert. Auf der Basis pro Benutzer und pro Kategorie/Raum können Sie mithilfe des Features "Dateien pro Benutzer **hochladen** " einen Benutzer Administrator, einen Chatroom-Administrator oder die Möglichkeit zum Hochladen von Dateien durch den Benutzer festlegen. Die **Datei Upload** -Funktion des beständigen Chat Servers ist nur pro Kategorie.

</div>

<div>

## <a name="logging"></a>Protokollierung

Die Protokollierung für den Server für beständigen Chat und System Center Operations Manager ist in die lync Server 2013-Ablaufverfolgungsprotokollierung integriert.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

