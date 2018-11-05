---
title: 'Lync Server 2013: Neue Funktionen für den Server für beständigen Chat'
TOCTitle: Neue Funktionen für den Server für beständigen Chat
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412965(v=OCS.15)
ms:contentKeyID: 49295326
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Neue Funktionen für den Server für beständigen Chat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Mit Lync Server 2013, Server für beständigen Chat können Sie themenbasierte Unterhaltungen mit mehreren Teilnehmern führen, die im Verlauf erhalten bleiben. Der Server für beständigen Chat unterstützt Ihre Organisation bei den folgenden Aufgaben:

  - Verbesserung der Kommunikation zwischen geografisch verteilten und funktionsübergreifenden Teams

  - Förderung von Informationsbewusstsein und aktiver Teilnahme

  - Verbesserung der Kommunikation über alle Unternehmensbereiche hinweg

  - Verringerung der Informationsüberlastung

  - Verbesserung des Informationsbewusstseins

  - Gezielte Weitergabe wichtigen Wissens und wichtiger Informationen

Lync Server 2013, Server für beständigen Chat ist in Microsoft Office 365 nicht verfügbar, sondern derzeit nur für lokale Lync 2013-Kunden.

In Lync 2013, Beständiger Chat wurde Funktionalität in den Lync 2013-Client integriert. Deshalb haben Benutzer im Lync 2013-Client Zugriff auf Chat/Anwesenheit, Audio/Video, Konferenzen und Beständiger Chat. Weitere Informationen zum Lync 2013-Client finden Sie unter <http://go.microsoft.com/fwlink/p/?linkid=270877>

Im vorliegenden Thema werden die folgenden Funktionsänderungen zwischen der neuen Version von Lync Server 2013, Server für beständigen Chat und der vorherigen Version ( Microsoft Lync Server 2010-Gruppenchat) beschrieben.

  - Bereitstellung einer administrativen Benutzeroberfläche in der Lync Server-Systemsteuerung und Eliminierung des Gruppenchat-Verwaltungstools

  - Integration von Konfigurationseinstellungen für den Server für beständigen Chat in den Topologie-Generator aufgrund der Eliminierung des Gruppenchat-Konfigurationstools

  - Einfache Migration und einfaches Upgrade von vorherigen Versionen von Server für beständigen Chat

  - Bereitstellung von Lösungen für hohe Verfügbarkeit und Notfallwiederherstellung

Weitere Informationen zur neuesten Version von Server für beständigen Chat finden Sie hier:

  - In der Hilfe zu Beständiger Chat unter <http://go.microsoft.com/fwlink/p/?linkid=270945>. In dieser Hilfe wird eine detaillierte Liste der Beständiger Chat-Funktionen, ihrer Funktionsweise und Verwendung bei Ausführung von Server für beständigen Chat bereitgestellt.

  - Im Abschnitt [Planen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation, unter [Bereitstellen des Servers für beständigen Chat in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in der Bereitstellungsdokumentation, unter [Migration von Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2-Gruppenchat zu Lync Server 2013 Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) in der Migrationsdokumentation und unter [Verwalten von Lync Server 2013 Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) in der Betriebsdokumentation. Hier finden Sie auch Anleitungen zum Einrichten von Server für beständigen Chat.

  - In der MSI-Datei der Dokumentation zum Server für beständigen Chat (Windows Installer-Datei) finden Benutzer umfangreiche Offlinedokumentation zum Server für beständigen Chat.

## Wichtige Topologieänderungen beim Server für beständigen Chat

Beim Server für beständigen Chat gibt es die folgenden wichtigen Änderungen:

Server für beständigen Chat ist nun eine Serverrolle. In Microsoft Lync Server 2010 handelte es sich beim Gruppenchatserver um eine vertrauenswürdige Drittanbieteranwendung für Microsoft Lync Server 2010. Beständiger Chat kann Ihrer Lync Server 2013-Topologie mit dem Topologie-Generator hinzugefügt werden. In Lync Server 2013, Server für beständigen Chat wurde Funktionalität mithilfe von drei neuen Serverrollen implementiert:

  - **PersistentChatService :** Dies ist die Front-End-Rolle für Beständiger Chat. In Standard Edition-Bereitstellungen wird die Dienstolle Server für beständigen Chat auf dem Standard Edition-Server durch Bootstrapper bereitgestellt, wie jede andere Lync Server-Rolle. In Enterprise Edition-Bereitstellungen wird die Dienstrolle Beständiger Chat auf eigenständigen Computern durch Bootstrapper bereitgestellt, wie jede andere Lync Server-Rolle.

  - **PersistentChatStore :** Back-End-Server, der der Inhaltsdatenbank für Beständiger Chat entspricht, in der alle Chatinhalte gespeichert werden.

  - **PersistentChatComplianceStore :** Back-End-Serverrolle, die der Konformitätsdatenbank für Beständiger Chat entspricht, in der alle Konformitätsereignisse gespeichert werden.

Diese Rollen für den Server für beständigen Chat sind optional und werden nur von Kunden installiert, die umfassende Funktionalität für Server für beständigen Chat wünschen. Die Rolle **PersistentChatComplianceStore** wird nur benötigt, wenn Sie die Konformität für Beständiger Chat bereitstellen.

Mit der Rolle **PersistentChatService** werden zwei Dienste ausgeführt:

  - Beständiger Chat-Dienst

  - Konformitätsdienst für Beständiger Chat

Wenn diese Dienste auf jedem Server für beständigen Chat ausgeführt werden, wird die hohe Verfügbarkeit für diese Dienste in einem aus mehreren Servern bestehenden Serverpool für beständigen Chat unterstützt.

Darüber hinaus weist der Server für beständigen Chat zur Unterstützung des Dateiuploads und -downloads in Beständiger Chatrooms einen Webdienst auf. Zuvor wurde dieser auf dem Server für beständigen Chat, Front-End-Server bereitgestellt, und Internetinformationsdienste (Internet Information Services, IIS) musste installiert werden. In Lync Server 2013Server für beständigen Chat wird der Webdienst für den Dateiupload/-download zusammen mit dem Lync Server 2013- Front-End-Server bereitgestellt. Als Nebeneffekt muss Internetinformationsdienste (Internet Information Services, IIS) nicht mehr für den Server für beständigen Chat installiert werden. Der Webdienst für den Dateiupload/-download wird im Internetinformationsdienste (Internet Information Services, IIS)-Manager als **PersistentChat** bezeichnet.


> [!IMPORTANT]
> Die Rolle <STRONG>PersistentChatService</STRONG> kann nur auf demselben Server wie ein Lync Server 2013- Front-End-Server ausgeführt werden, wenn es sich bei diesem Front-End-Server um einen Standard Edition- Front-End-Server handelt. Die Rolle <STRONG>PersistentChatService</STRONG> kann nicht unabhängig von einem Lync Server 2013- Front-End-Server ausgeführt werden. Sie kann nur im Kontext einer Lync Server 2013-Bereitstellung installiert werden.



Beim Server für beständigen Chat gibt es den Suchdienst nicht mehr. Im Lync Server 2010-Gruppenchat wurde der Suchdienst auf jedem Gruppenchatserver- Front-End-Server ausgeführt und führte das Routing an einen der Kanalserver aus. In Lync Server 2013 werden für das Routing Kontaktobjekte verwendet, wobei jeder Serverpool für beständigen Chat durch ein Kontaktobjekt dargestellt wird, mit dem die Lync Server- Front-End-Server Anforderungen identifizieren und an einen entsprechenden Serverpool für beständigen Chat sowie an einen der Computer, auf denen der Server für beständigen Chat ausgeführt wird, im Pool weiterleiten.

In Lync Server 2013 gibt es Änderungen beim Konformitätsdienst:

  - In Lync Server 2010 kann der Konformitätsdienst eigenständig (nicht im Verbund) und nur auf einem einzelnen Server ausgeführt werden. Der Konformitätsdienst wird nun auf allen Server für beständigen Chat- Front-End-Servern parallel zum Dienst für Beständiger Chat ausgeführt und unterstützt dadurch die hohe Verfügbarkeit in einem aus mehreren Servern bestehenden Serverpool für beständigen Chat. Ein einzelner Konformitätsadapter kann so konfiguriert werden, dass Daten aus der Konformitätsdatenbank extrahiert und in eines der anderen Systeme (XML-Datei, von Exchange gehostete Archive usw.) importiert werden. Server für beständigen Chat weist einen XML-Adapter auf.

  - Die Message Queuing-Warteschlange (wird auch als MSMQ bezeichnet), die vom Dienst für Beständiger Chat und dem Konformitätsdienst auf jedem Server für beständigen Chat- Front-End-Server gemeinsam genutzt wird, ist nun eine private Warteschlange, die nur von diesen beiden Diensten gemeinsam genutzt wird. Alle Konformitätsdienste schreiben in dieselbe Back-End-Konformitätsdatenbank. Sie lesen auch aus dieser Datenbank, um die Daten an ihre Adapterinstanz zu senden. Für den Konformitäts-Back-End-Server gibt es eine neue Back-End-Serverrolle.
    

    > [!IMPORTANT]
    > Wie in früheren Versionen werden alle Konformitätsdaten nur einmal verarbeitet. Die Daten können von jeder Adapterinstanz verarbeitet werden, die vom Konformitätsdienst, der auf den verschiedenen Computern mit Lync Server 2013, Server für beständigen Chat ausgeführt wird, aufgerufen wird. Beim Server für beständigen Chat können die Daten von jeder Adapterinstanz verarbeitet werden.

    

    > [!NOTE]
    > Weitere Informationen zum Installieren des Message Queuing-Diensts finden Sie unter <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Installieren von Betriebssystemen und erforderlicher Software auf Servern für Lync Server 2013</A> in der Bereitstellungsdokumentation.



In Lync Server 2013 gibt es Verbesserungen bei der hohen Verfügbarkeit und bei der Notfallwiederherstellung:

  - Verbesserungen bei der hohen Verfügbarkeit: Mithilfe der SQL Server-Spiegelung wird hohe Verfügbarkeit für die Inhaltsdatenbank für Server für beständigen Chat und für die Konformitätsdatenbank für Beständiger Chat innerhalb eines Rechenzentrums (innerhalb des Standorts) bereitgestellt.

  - Verbesserungen bei der Notfallwiederherstellung: Server für beständigen Chat unterstützt eine erweiterte Poolarchitektur, mit der ein einzelner Serverpool für beständigen Chat auf zwei Standorte verteilt werden kann (d. h., ein einzelner logischer Pool in der Topologie, wobei Server im Pool physisch auf die beiden Standorte verteilt werden). Der SQL Server-Protokollversand wird für die standortübergreifende Notfallwiederherstellung verwendet.

Weitere Informationen zur hohen Verfügbarkeit und zur Notfallwiederherstellung finden Sie unter [Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in der Bereitstellungsdokumentation.

## Wichtige Änderungen bei der Administration und Verwaltung beim Server für beständigen Chat

In Lync Server 2013 wurde die Administration und Verwaltung von Server für beständigen Chat wie folgt vereinfacht:

  - Einheitliche Administration und Verwaltung. Lync Server 2013 vereinfacht die Verwaltung und Administration von Server für beständigen Chat mithilfe von Tools, mit denen Lync-Administratoren bereits vertraut sind. Server für beständigen Chat weist eine in die Lync Server-Systemsteuerung integrierte administrative Benutzeroberfläche auf, mit der Leistungsprobleme aus früheren Versionen der Benutzeroberfläche von Gruppenchatserver beseitigt wurden. Darüber hinaus weist der Server für beständigen Chat eine Reihe von Windows PowerShell-Cmdlets für die Administration und Verwaltung von Kategorien für Server für beständigen Chat, Server für beständigen Chatrooms (einschließlich des Löschens von Chatrooms und des Löschens von veralteten Inhalten) sowie Add-Ins auf.

  - Vereinfachtes Administrationsmodell. In Lync Server 2013 wurde das Modell für Server für beständigen Chat geändert und vereinfacht, indem die folgenden wichtigen Forderungen von Kunden berücksichtigt wurden:
    
      - Die komplexen geschachtelten Hierarchien von Bereichen und Kategorien wurden entfernt.
    
      - Das Definieren von Listen mit abgelehnten bzw. zugelassenen Bereichen wird für aktuelle MindAlign-Kunden unterstützt, die zu Server für beständigen Chat migrieren möchten.

## Welche Unterschiede gibt es bei Benutzerrollen im Vergleich zu früheren Gruppenchatserverversionen?

Beim Lync Server 2010-Gruppenchat gab es eine Administratorrolle, eine Chatroomadministratorrolle und eine Lync Server-Administratorrolle, mit der Add-Ins verwaltet werden konnten. Beim Server für beständigen Chat gibt es lediglich eine Administratorrolle für Beständiger Chat (die mit anderen rollenbasierten Zugriffssteuerungsrollen von Lync Server vergleichbar ist). Jeder Benutzer, der Mitglied dieser rollbasierten Zugriffssteuerungsrolle ist, kann Chatrooms, Add-Ins und Kategorien (und deshalb auf diese Kategorien zugreifen) sowie die Konfiguration des Serverpool für beständigen Chat verwalten.

## Welche Unterschiede gibt es bei Chatroomkategorien im Vergleich zu früheren Gruppenchatserverversionen?

Chatroomkategorien können nicht mehr geschachtelt werden, und die Stammkategorie kann nicht mehr geändert werden. AllowedMembers / DeniedMembers entsprechen den Bereichen aus Vorversionen des Gruppenchatservers (außer dass die Definition einer Liste mit abgelehnten Mitliedern nicht unterstützt wurde). Bereiche können nicht mehr außer Kraft gesetzt werden, da es keine geschachtelten Kategorien gibt. Ein Administrator für Beständiger Chat in Lync Server 2013 kann Chatroomkategorien erstellen und verwalten. Beim Erstellen und Verwalten von Chatroomkategorien kann ein Administrator für Beständiger Chat Prinzipale konfigurieren (Active Directory-Gruppen/Container/Benutzer), die Zugriff auf die Mitglieder/Ersteller von Chatrooms einer bestimmten Kategorie haben. Ein Administrator für Beständiger Chat kann außerdem DeniedMembers einer Kategorie hinzufügen, die dann explizit ausgeschlossene Mitglieder der Liste zulässiger Mitglieder werden. DeniedMembers hat Vorrang vor AllowedMembers .

## Welche Unterschiede gibt es bei Chatroomeigenschaften im Vergleich zu früheren Gruppenchatserverversionen?

In Lync Server 2013, Server für beständigen Chat gibt es ein neues Konzept für offene Chatrooms. Alle zulässigen Mitglieder können dem Chatroom beitreten, und zwar ohne exklusive Mitgliedschaft.

Die folgenden Chatroomeigenschaften aus früheren Versionen von Server für beständigen Chat wurden entfernt:

  - Thema: Ein Chatroom weist nun nur eine Beschreibung auf.

  - Erstellen einer neuen Mitgliedsliste: In Server für beständigen Chat weisen alle Chatrooms zunächst keine Mitglieder auf (und können maximal die Mitgliedschaft entsprechend Zulässige Mitglieder aufweisen).

  - Dateiupload: Dies war früher eine Einstellung pro Chatroom, mit der gesteuert wurde, ob Dateiuploads/-downloads zulässig sind. Dies wird nun nur auf der Kategorieebene festgelegt und gilt für alle Chatrooms in dieser Kategorie.

  - Chatverlauf: Dies war früher eine Einstellung pro Chatroom, mit der der Chatverlauf aktiviert bzw. deaktiviert wurde. Dies wird nun nur auf der Kategorieebene festgelegt und gilt für alle Chatrooms in dieser Kategorie.

  - Invites: Ein Chatroom erbt stets die "Invites"-Einstellung für die Kategorie. Diese Option kann auch im Chatroom deaktiviert werden. Für einen Chatroom kann "Invites" nicht aktiviert werden, wenn für die Kategorie zuvor "Invites" deaktiviert wurde.

## Welche Unterschiede gibt es bei Richtlinien im Vergleich zu früheren Gruppenchatserverversionen?

Beim Server für beständigen Chat gibt es eine neue Lync-Richtlinie für Beständiger Chat auf Benutzer-, Pool- Standort- oder globaler Ebene. Im Lync 2013-Client ist die Umgebung für Beständiger Chat nur für Benutzer verfügbar, für die anhand der Richtlinie Beständiger Chat aktiviert ist (entweder direkt oder über die Einstellung auf Pool-, Standort- oder globaler Ebene).

In früheren Versionen des Gruppenchatservers waren keine Richtlinien in die Lync Server-Richtlinien integriert. Pro Benutzer und pro Kategorie/Chatroom konnten Sie mithilfe des benutzerbasierten Features **Kann Dateien hochladen** den Benutzer als Benutzeradministrator oder Chatroomadministrator definieren oder aber festlegen, ob der Benutzer Dateien hochladen darf. Bei **Dateiupload** von Server für beständigen Chat handelt es sich um ein Feature auf Kategorieebene.

## Protokollierung

Die Protokollierung für Server für beständigen Chat und System Center Operations Manager ist in die Ablaufverfolgung von Lync Server 2013 integriert.

## Siehe auch

#### Weitere Ressourcen

[Planen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)

