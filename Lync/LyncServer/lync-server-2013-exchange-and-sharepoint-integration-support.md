---
title: 'Lync Server 2013: Unterstützung der Integration von Exchange Server und SharePoint'
TOCTitle: Unterstützung der Integration von Exchange Server und SharePoint
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205005(v=OCS.15)
ms:contentKeyID: 49294389
ms.date: 01/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unterstützung der Integration von Exchange Server und SharePoint in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2017-01-18_

Lync Server 2013 und Lync 2013 können sicher und reibungslos mit anderen Anwendungen und Serverprodukten kommunizieren, einschließlich Office 2013, Exchange 2013 und SharePoint, wenn Sie diese Produkte einbinden. Durch die Einbindung von Lync Server 2013 und Office erhalten Benutzer einen kontextbezogenen Zugriff auf Lync-Funktionen für Chat, erweiterte Anwesenheit, Telefonie und Konferenzen. Office-Benutzer können aus Outlook 2013-Clients für Messaging und Zusammenarbeit und anderen Office-Programmen oder über eine Microsoft SharePoint Server 2010-Seite auf Lync-Features zugreifen. Die Benutzer können außerdem eine Aufzeichnung der Lync-Unterhaltungen im Outlook-Ordner "Aufgezeichnete Unterhaltungen" ansehen. Bei der Integration von Exchange 2013 oder Exchange Online unterstützt Lync Server 2013 außerdem folgende Features:

  - Einheitlicher Kontaktspeicher, in dem Benutzer alle Kontaktinformationen in Exchange 2013 oder Exchange Online speichern können, sodass die Informationen global und übergreifend in Lync 2013, Exchange, Outlook und Outlook Web App verfügbar sind.

  - Unterhaltungsverlauf und Webkonferenzverlauf, der in den Exchange-Benutzerordnern gespeichert wird.

  - Archivierte Inhalte aus Lync, wie Chat- und Besprechungsinhalte, können im Exchange-Speicher gespeichert werden.


> [!NOTE]
> In Lync Server 2013 wird die Integration früherer Versionen von Microsoft Exchange Server und SharePoint unterstützt; es wird jedoch nicht die vollständige Funktionalität dieser früheren Versionen unterstützt, z. B. die Integration des Archivierungsspeichers in Microsoft Exchange.<BR>Wenn Sie Ihre Benutzer auf Exchange 2013 migrieren, können Sie sowohl den Exchange-Speicher als auch den Lync Server-Speicher als Zwischenlösung verwenden, bis die Migration abgeschlossen ist. Die dauerhafte Verwendung des Exchange- und Lync Server-Speichers wird nicht unterstützt.



Für die Integration von Lync Server 2013 in Exchange 2013 und SharePoint Server ist eine Server-zu-Server-Authentifizierung zwischen den Servern erforderlich, auf denen Lync Server 2013, Microsoft Exchange Server und SharePoint Server ausgeführt wird. In Lync Server 2013 wird das OAuth-Protokoll (Open Authorization) für die Server-zu-Server-Authentifizierung und die Autorisierung unterstützt. Für die lokale Server-zu-Server-Authentifizierung zwischen zwei Microsoft-Servern ist kein Drittanbieter-Tokenserver erforderlich. Lync Server 2013, Exchange 2013 und SharePoint verfügen über einen integrierten Tokenserver, der für die gegenseitige Authentifizierung verwendet werden kann. So kann beispielsweise von Lync Server 2013 ein Sicherheitstoken ausgegeben und selbst unterzeichnet werden; anschließend wird dieses Token für die Kommunikation mit Exchange 2013 verwendet. In diesem Fall muss kein Drittanbieter-Tokenserver verwendet werden.

In Lync Server 2013 werden zwei Server-zu-Server-Szenarien unterstützt. Diese beinhalten die Konfiguration der Server-zu-Server-Authentifizierung zwischen folgenden Instanzen:

  - Einer lokalen Installation von Lync Server 2013 und einer lokalen Installation von Exchange 2013 und/oder SharePoint Server.

  - Zwei Office-Komponenten (z. B. zwischen Microsoft Exchange 365 und Microsoft Lync Server 365 oder zwischen Microsoft Lync Server 365 und Microsoft SharePoint 365).


> [!NOTE]
> Die Server-zu-Server-Authentifizierung zwischen einem lokalen Server und einer Office 365-Komponente wird in dieser Version von Lync Server 2013 nicht unterstützt. Das bedeutet unter anderem, dass Sie keine Server-zu-Server-Authentifizierung zwischen einer lokalen Installation von Lync Server 2013 und Microsoft Exchange 365 vornehmen können.



Ausführliche Informationen zur Server-zu-Server-Authentifizierung finden Sie in der Bereitstellungs- oder Betriebsdokumentation unter [Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).

