---
title: 'Lync Server 2013: neue Features für den Server für beständigen Chat'
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
ms.openlocfilehash: 5b8718d5f3dda34b97b4c3e96c2fe9531d6658b9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a>Neue Features für den Server für beständigen Chat in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-29_

Lync Server 2013 können Sie mit dem Server für beständigen Chat an mehrteiligen, themenbasierten Unterhaltungen teilnehmen, die im Laufe der Zeit beibehalten werden. Der Server für beständigen Chat kann Ihrer Organisation dabei helfen, Folgendes zu tun:

  - Verbesserung der Kommunikation zwischen geografisch verteilten und funktionsübergreifenden Teams

  - Förderung von Informationsbewusstsein und aktiver Teilnahme

  - Verbesserung der Kommunikation über alle Unternehmensbereiche hinweg

  - Verringerung der Informationsüberlastung

  - Verbesserung des Informationsbewusstseins

  - Gezielte Weitergabe wichtigen Wissens und wichtiger Informationen

Lync Server 2013 ist der Server für beständigen Chat in Microsoft Office 365 nicht verfügbar. Derzeit steht sie nur lokalen lync 2013 Kunden zur Verfügung.

In lync 2013 ist die Funktion für beständigen Chat in den lync 2013-Client integriert. Dadurch haben Benutzer Zugriff auf Instant Messaging/Anwesenheit, Audio/Video, Konferenzen und beständigen Chat im lync 2013-Client. Weitere Informationen zum lync 2013-Client finden Sie unter <https://go.microsoft.com/fwlink/p/?linkid=270877>.

In diesem Thema werden Funktionsänderungen zwischen der neuen Version von lync Server 2013, dem Server für beständigen Chat und der vorherigen Version (Microsoft lync Server 2010, Gruppen Chat) beschrieben, einschließlich:

  - Bereitstelleneiner administrativen Erfahrung in lync Server-Systemsteuerung und Ausschließen des Verwaltungstools für Gruppenchats

  - Integrieren von Konfigurationseinstellungen für den Server für beständigen Chat in den Topologie-Generator durch Entfernen des Konfigurationstools für Gruppenchats

  - Einfache Migration und Upgrade von früheren Versionen des Servers für beständigen Chat

  - Bereitstellen von Lösungen für hohe Verfügbarkeit und Notfallwiederherstellung

Weitere Informationen zur neuesten Version des Servers für beständigen Chat finden Sie in den folgenden Themen:

  - Die Hilfe <https://go.microsoft.com/fwlink/p/?linkid=270945> für beständigen Chat enthält eine ausführliche Liste der Features für beständigen Chat, deren Funktionsweise und deren Verwendung bei der Ausführung von persistent Chat Server.

  - Die [Planung für den Server für beständigen Chat in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation, [Bereitstellen des Servers für beständigen Chat in lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in der Bereitstellungsdokumentation, [Migration von lync Server 2010, Gruppenchat oder Office Communications Server 2007 R2 Gruppenchat zu lync Server 2013, beständigen Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) in der Migrationsdokumentation und [Verwalten von lync Server 2013, beständiger Chat Server](managing-lync-server-2013-persistent-chat-server.md) in der Betriebsdokumentation, die alle Anweisungen zum Einrichten bieten. Server für beständigen Chat.

  - Die Datei "Documentation. msi" des persistent Chat-Servers (Windows Installer-Datei) ermöglicht Benutzern den Zugriff auf eine umfassende offlinedokumentation über den Server für beständigen Chat.

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a>Wichtige Topologie-Änderungen für den Server für beständigen Chat

Die folgenden allgemeinen Änderungen für den Server für beständigen Chat umfassen Folgendes:

Der Server für beständigen Chat ist jetzt eine Serverrolle. In Microsoft lync Server 2010 war der Gruppen Chat Server eine vertrauenswürdige Drittanbieteranwendung für Microsoft lync Server 2010. Beständiger Chat kann mithilfe des Topologie-Generators zu ihrer lync Server 2013 Topologie hinzugefügt werden. In lync Server 2013 wird die Server Funktionalität für beständigen Chat mit drei neuen Serverrollen implementiert:

  - **PersistentChatService:** Dies ist die Front-End-Rolle für den beständigen Chat. In Standard Edition-Bereitstellungen ist die Server Dienst Rolle für beständigen Chat wie jede andere lync Server Rolle in der Standard Edition-Server von Bootstrapper bereitgestellt. In Enterprise Edition-Bereitstellungen wird der Dienst für beständigen Chat wie jede andere lync Server Rolle auf eigenständigen Computern als Bootstrapper bereitgestellt.

  - **PersistentChatStore:** Back-End-Server, der der Inhaltsdatenbank für beständigen Chat entspricht, in der alle Chatinhalte gespeichert sind.

  - **PersistentChatComplianceStore:** Back-End-Server Rolle, die der Kompatibilitätsdatenbank für beständigen Chat entspricht, in der alle kompatibilitätsereignisse gespeichert werden.

Diese Serverrollen für beständigen Chat sind optional und werden nur von Kunden installiert, die umfassende Funktionen für den Server für beständigen Chat benötigen. Die **PersistentChatComplianceStore** -Rolle ist nur erforderlich, wenn Sie die Compliance für beständigen Chat bereitstellen möchten.

Die **PersistentChatService** -Rolle führt zwei Dienste aus:

  - Beständiger Chat Dienst

  - Kompatibilitätsdienst für beständigen Chat

Wenn diese Dienste auf jedem Server für beständigen Chat ausgeführt werden, bietet Sie hohe Verfügbarkeit für diese Dienste in einem Serverpool für persistent Chat mit MultiServer.

Um den Dateiupload und-Download in beständigen Chatrooms zu unterstützen, enthält der Server für beständigen Chat zusätzlich einen Webdienst. Zuvor wurde dieser Dienst auf dem Server für beständigen Chat zusammengefasst, Front-End-Server und benötigte Internet Information Services (IIS) als Voraussetzung installiert werden. In beständiger Chat von lync Server 2013 Server wird der Webdienst zum Hochladen/Herunterladen von Dateien mit dem lync Server 2013 Front-End-Server zusammengefasst. Als Nebeneffekt ist Internet Information Services (IIS) nicht länger eine Voraussetzung für den Server für beständigen Chat. Der Datei Upload/Download-Webdienst wird im Internet Information Services (IIS)-Manager als **PersistentChat** identifiziert.

<div>


> [!IMPORTANT]  
> Die <STRONG>PersistentChatService</STRONG> -Rolle kann auf demselben Server wie eine lync Server 2013&nbsp;Front-End-Server nur ausgeführt werden, wenn es sich bei dieser&nbsp;Front-End-Server um eine Standard Edition-Front-End-Server handelt. Die <STRONG>PersistentChatService</STRONG> -Rolle kann nicht unabhängig von einem&nbsp;lync Server 2013 Front-End-Server ausgeführt werden. Es kann nur im Kontext einer lync Server 2013-Bereitstellung installiert werden.



</div>

Im Server für beständigen Chat wurde der Suchdienst eliminiert. In lync Server 2010 Gruppenchat wurde der Suchdienst auf jedem Gruppenchat Server ausgeführt Front-End-Server und die Weiterleitung an einen der Kanalserver durchgeführt. Lync Server 2013 basiert auf dem Routing mithilfe von Contact-Objekten, wobei jeder Serverpool für beständigen Chat durch ein Kontaktobjekt dargestellt wird, das von den lync Server-Front-End-Servern zum Identifizieren und Weiterleiten von Anforderungen an einen entsprechenden Serverpool für beständigen Chat verwendet wird, und um einer der Computer, auf denen der Server für beständigen Chat im Pool läuft.

In lync Server 2013 werden Kompatibilitätsdienst Änderungen vorgenommen:

  - In lync Server 2010 wurde der Kompatibilitätsdienst eigenständig (nicht nebeneinander) und nur auf einem einzelnen Server ausgeführt. Der Kompatibilitätsdienst wird nun neben dem Dienst für beständigen Chat auf allen Front-End-Servern für beständigen Chat ausgeführt und bietet dadurch eine hohe Verfügbarkeit in einem Serverpool für persistente Chats mit MultiServer. Ein einzelner Kompatibilitätsadapter kann so konfiguriert werden, dass Daten aus der Kompatibilitätsdatenbank und in eines der anderen Systeme (XML-Datei, in Exchange gehostete Archive usw.) extrahiert werden. Der Server für beständigen Chat enthält einen XML-Adapter.

  - Die Message Queuing-Warteschlange (auch MSMQ genannt), die vom beständigen Chatdienst und dem Kompatibilitätsdienst auf jedem Server für beständigen Chat freigegeben wird Front-End-Server ist jetzt eine private Warteschlange, die nur von den beiden Diensten freigegeben wird. Alle Konformitäts Dienste schreiben in dieselbe Compliance-Back-End-Datenbank. Sie lesen auch alle aus dieser Datenbank, um die Daten an Ihre Adapterinstanz zu senden. Der Kompatibilitäts-Back-End-Server wird als neue Back-End-Serverrolle dargestellt.
    
    <div>
    

    > [!IMPORTANT]  
    > Wie in früheren Versionen werden alle Kompatibilitätsdaten nur einmal verarbeitet. Die Daten können von allen Adapter Instanzen verarbeitet werden, die vom Kompatibilitätsdienst aufgerufen werden, der auf den verschiedenen lync Server 2013-, persistent Chat Server-Computern ausgeführt wird. In einem Server für beständigen Chat können alle Adapter Instanzen die Daten verarbeiten.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Informationen zum Installieren von Message Queuing finden Sie unter <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Installieren von Betriebssystemen und der erforderlichen Software auf Servern für lync Server 2013</A> in der Bereitstellungsdokumentation.

    
    </div>

In lync Server 2013 gibt es Verbesserungen sowohl bei hoher Verfügbarkeit als auch bei der Notfallwiederherstellung:

  - Verbesserungen bei hoher Verfügbarkeit: SQL Server Spiegelung wird verwendet, um eine hohe Verfügbarkeit für die Inhaltsdatenbank des beständigen Chat Servers und die Kompatibilitätsdatenbank für beständigen Chat in einem Rechenzentrum (vor Ort) bereitzustellen.

  - Verbesserungen bei der Notfallwiederherstellung: der Server für beständigen Chat unterstützt eine gestreckte Pool Architektur, die es ermöglicht, einen einzelnen Serverpool für beständigen Chat an zwei Standorten zu dehnen (d. r. einen einzelnen logischen Pool in der Topologie, wobei Server im Pool physisch befindet sich über zwei Standorte). SQL Server Protokollversand wird für die standortübergreifende Notfallwiederherstellung verwendet.

Weitere Informationen zur Hochverfügbarkeit und Notfallwiederherstellung finden Sie unter [Configuring persistent Chat Server for High Availability and Disaster Recovery in lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in der Bereitstellungsdokumentation.

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a>Wichtige Verwaltungs-und Verwaltungsänderungen für den Server für beständigen Chat

Lync Server 2013 hat es einfacher gemacht, den Server für beständigen Chat zu verwalten und zu verwalten, indem Sie Folgendes bereitstellen:

  - Einheitliche Verwaltung und Verwaltung. Lync Server 2013 vereinfacht das Verwalten und Verwalten von Servern für beständigen Chat mithilfe von Tools, die lync-Administratoren bereits vertraut sind. Der Server für beständigen Chat enthält eine Benutzeroberflächen Erfahrung, die in die lync Server-Systemsteuerung integriert ist und die Leistungsprobleme mit den vorherigen Versionen der Benutzeroberfläche des Gruppen Chat Servers behandelt. Der Server für beständigen Chat enthält außerdem eine Sammlung von Windows PowerShell-Cmdlets zum Verwalten und Verwalten von Server Kategorien für beständigen Chat, Serverräume für beständigen Chat (einschließlich Löschen von Räumen und Entfernen veralteter Inhalte) und Add-Ins.

  - Vereinfachtes Verwaltungsmodell. Lync Server 2013 hat das Server Modell für beständigen Chat geändert und vereinfacht, indem die folgenden wichtigen Kundenanforderungen erfüllt werden:
    
      - Entfernen Sie die komplexen geschachtelten Hierarchien von Bereichen und Kategorien.
    
      - Unterstützung zum Definieren von Deny-Listen sowie von zulässigen Listen (Bereichen) für aktuelle MindAlign-Kunden, die planen, zum Server für beständigen Chat zu migrieren.

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a>Was unterscheidet sich von den Benutzerrollen aus früheren Gruppen Chat Server-Versionen?

Lync Server 2010 hatten Gruppenchats eine Benutzeradministratorrolle, eine Rolle als Chatroom-Administrator und eine lync Server Administratorrolle, die Add-Ins verwalten konnte. der Server für beständigen Chat stellt einfach eine Administratorrolle für beständigen Chat bereit (ähnlich wie bei anderen lync-Servern). Rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC)). Jeder, der Mitglied dieser RBAC-Rolle ist, kann Chatrooms, Add-Ins und Kategorien verwalten (und somit Benutzer Zugriff für diese Kategorien erhalten) und die Konfiguration des Server Pools für beständigen Chat.

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a>Was ist unterschiedlich zu Chatroom-Kategorien aus früheren Gruppenchat Server-Versionen?

Chatroom-Kategorien können nicht mehr geschachtelt werden, und die Stammkategorie kann nicht mehr geändert werden. AllowedMembers/"deniedmembers" umfassen einen Bereich, der in Legacy-Gruppen Chat Server Versionen verwendet wurde (mit der Ausnahme, dass die Angabe einer verweigerten Liste nicht unterstützt wurde). Bereiche können nicht mehr außer Kraft gesetzt werden, da es keine geschachtelten Kategorien gibt. Ein Administrator für beständigen Chat in lync Server 2013 kann Chatroom-Kategorien erstellen und verwalten. Im Rahmen der Erstellung und Verwaltung von Chatroom-Kategorien kann ein Administrator für beständigen Chat Prinzipale (Active Directory Gruppen/Container/Benutzer) konfigurieren, die Zugriff auf Mitglieder/Ersteller von Chatrooms einer bestimmten Kategorie haben. Ein Administrator für beständigen Chat kann auch "deniedmembers" zu einer Kategorie hinzufügen, und diese werden explizite Ausnahmen für die zugelassene Liste. "Deniedmembers" außer Kraft setzen der Elemente in AllowedMembers.

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a>Was unterscheidet sich von den Chatroom-Eigenschaften von vorherigen Gruppenchat Server-Versionen?

Ein neues Konzept offener Chatrooms ist in lync Server 2013 Server für beständigen Chat vorhanden. Alle zulässigen Mitglieder können dem Chatroom beitreten, ohne exklusive Mitgliedschaft.

Die folgenden Chatroom-Eigenschaften, die in früheren Versionen des Servers für beständigen Chat enthalten waren, wurden eliminiert:

  - Thema: ein Raum enthält jetzt nur eine Beschreibung.

  - Neue Mitgliederliste erstellen: in dem Server für beständigen Chat beginnen alle Chatrooms mit einer leeren Mitgliedschaft (und können auf eine Mitgliedschaft maximieren, die den zulässigen Mitgliedern entspricht).

  - Dateiupload: verwendet, um eine Einstellung pro Chatroom zu sein, um zu steuern, ob Dateiuploads/Downloads zulässig waren. Dies wird nun nur auf Kategorieebene festgelegt und gilt für alle Räume in dieser Kategorie.

  - Chatverlauf: wird verwendet, um eine Einstellung pro Chatroom zu sein, um zu steuern, ob Chatverlauf aktiviert wurde, aber jetzt nur auf Kategorieebene festgelegt und gilt für alle Räume in dieser Kategorie.

  - Invites: ein Raum erbt immer die invites-Einstellung für die Kategorie; oder er kann im Raum ausgeschaltet werden. Ein Raum kann keine Einladungen aktivieren, wenn die Kategorie zuvor auf "lädt ab" festgelegt wurde.

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a>Was unterscheidet sich von den Richtlinien aus früheren Gruppen Chat Server-Versionen?

Für den Server für beständigen Chat ist eine neue lync-Richtlinie mit beständigem Chat pro Benutzer/Pool/Standort/globaler Einstellung aktiviert. Im lync 2013-Client ist die Umgebung für beständigen Chat nur für Benutzer verfügbar, die über eine Richtlinie für beständigen Chat aktiviert sind (entweder direkt oder über die Einstellung Pool/Standort/Global).

In früheren Versionen des Gruppen Chat Servers wurden keine Richtlinien in die lync Server Richtlinien integriert. Auf der Basis pro Benutzer und pro Kategorie/Raum können Sie mit der Funktion zum **Hochladen von Dateien** pro Benutzer den Benutzer als Benutzer Administrator, Chatroom-Administrator oder die Möglichkeit konfigurieren, dass der Benutzer Dateien hochladen kann. Die **Datei Upload** -Funktion für den Server für beständigen Chat ist nur pro Kategorie.

</div>

<div>

## <a name="logging"></a>Protokollierung

Die Protokollierung für den Server für beständigen Chat und System Center Operations Manager ist in die lync Server 2013 Ablaufverfolgungsprotokollierung integriert.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen von Servern für beständigen Chat in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

