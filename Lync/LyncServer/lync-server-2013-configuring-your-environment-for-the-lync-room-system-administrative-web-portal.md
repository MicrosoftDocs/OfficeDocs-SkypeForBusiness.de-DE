---
title: 'Lync Server 2013: Konfigurieren Ihrer Umgebung für das Webportal zur Verwaltung von Lync Room System'
TOCTitle: Konfigurieren Ihrer Umgebung für das Webportal zur Verwaltung von Lync Room System
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn436325(v=OCS.15)
ms:contentKeyID: 59373613
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren Ihrer Lync Server 2013-Umgebung für das Webportal zur Verwaltung von Lync Room System

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Zur Nutzung des Webportals für die Verwaltung des Lync-Raumsystems (LRS) müssen Sie die folgenden Voraussetzungen installieren oder konfigurieren.


> [!IMPORTANT]
> Wenn für den Server sowohl Kerberos- als auch die NTLM-Authentifizerung konfiguriert wurde und LRS auf einem Computer ausgeführt wird, der nicht Teil der Domäne ist, schlägt die Kerberos-Authentifizierung fehl und dem Benutzer wird der LRS-Status im Verwaltungsportal nicht angezeigt. Sie können dieses Problem lösen, indem Sie entweder die NTLM-Authentifizierung bzw. die NTLM- und TLS-DSK-Authentifizierung (ohne Kerberos) konfigurieren oder mit dem LRS-Computer der Domäne beitreten.



1.  Installieren Sie die kumulativen Updates von Juli 2013 für Lync Server 2013 in der Lync Server-Topologie.
    
    Informationen zum Abrufen des Updates oder zum Inhalt finden Sie unter [Updates für Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=323959).

2.  Erstellen Sie einen SIP-aktivierten Active Directory-Benutzer.
    
    Das Webportal zur Verwaltung von LRS verwendet diese Anmeldeinformationen, um Informationen von Lync Server abzufragen. Der empfohlene Benutzername lautet **LRSApp**.

3.  Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen **LRSSupportAdminGroup**.
    
    Erstellen Sie die Gruppe mit dem Gruppenbereich **Global** und dem Gruppentyp **Sicherheit** . SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, die Liste der Räume anzuzeigen und bestimmte Befehle auszuführen, wie das Speichern von Protokollen.

4.  Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen **LRSFullAccessAdminGroup**.
    
    Erstellen Sie die Gruppe mit dem Gruppenbereich **Global** und dem Gruppentyp **Sicherheit** . SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, alle Funktionen des Verwaltungsportals zu nutzen.
    
     
    
    ![Liste der Verwaltungsgruppen mit Sicherheitsgruppenrolle](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "Liste der Verwaltungsgruppen mit Sicherheitsgruppenrolle")  
    
     

5.  Fügen Sie die Gruppe **LRSFullAccessAdminGroup** als Mitglied der Gruppe **LRSSupportAdminGroup** hinzu.
    
    ![LRSSupportAdminGroup-Eigenschaftenmember (Seite)](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup-Eigenschaftenmember (Seite)")  
    
     

6.  Erstellen Sie einen SIP-aktivierten Active Directory-Benutzer mit dem Namen **LRSSupport** .
    
    ![LRSSupportAdminGroup-Eigenschaftenmember (Seite)](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup-Eigenschaftenmember (Seite)")  
    
     

7.  Installieren Sie ASP.NET MVC 4 für Visual Studio 2010 SP1 und Visual Web Developer 2010 SP1, zu finden im Microsoft Download Center unter [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967).

