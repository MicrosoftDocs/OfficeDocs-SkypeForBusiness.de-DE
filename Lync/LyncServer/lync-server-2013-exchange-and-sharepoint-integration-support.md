---
title: 'Lync Server 2013: Unterstützung für Exchange-und SharePoint-Integration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fdfaffa12d84b57f0ae0203ebc14491bb6d8d4f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a>Unterstützung von Exchange und SharePoint-Integration in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2017-01-18_

Lync Server 2013 und lync 2013 können sicher und nahtlos mit anderen Anwendungen und Server Produkten kommunizieren, einschließlich Office 2013, Exchange Server 2013, Exchange Server 2016 und SharePoint, wenn Sie diese Produkte integrieren. Durch die Integration von lync Server 2013 und Office erhalten Benutzer einen kontextbezogenen Zugriff auf die Funktionen Instant Messaging (Sofortnachrichten), erweiterte Anwesenheitsinformationen, Telefonie und Konferenzen von lync. Office-Benutzer können aus dem Outlook 2013 Messaging and Collaboration-Client und anderen Office-Programmen oder von einer SharePoint-Seite aus auf lync-Funktionen zugreifen. Benutzer können auch einen Datensatz von lync-Unterhaltungen im Outlook-Ordner "Unterhaltungsverlauf" anzeigen. Wenn Sie in Exchange 2013, Exchange 2016 oder Exchange Online integriert sind, unterstützt lync Server 2013 außerdem Folgendes:

  - Einheitlicher Kontaktspeicher, mit dem Benutzer alle Kontaktinformationen in Exchange oder Exchange Online speichern können, damit die Informationen Global in lync 2013, Exchange, Outlook und Outlook Web App zur Verfügung stehen.

  - Unter Haltungs Verlauf und Webkonferenz Verlauf, der in Exchange-Benutzerordnern gespeichert ist.

  - Archivierte Inhalte aus lync, wie Chatnachrichten und Besprechungsinhalte, können im Exchange-Speicher gespeichert werden.

<div>


> [!NOTE]  
> Lync Server 2013 unterstützt die Integration in frühere Versionen von Exchange Server und SharePoint Server, aber nicht alle Funktionen werden mit diesen früheren Versionen unterstützt, wie etwa die Integration von Archivierungsspeicher mit Microsoft Exchange.<BR>Wenn Sie Ihre Benutzer zu Exchange 2013 oder Exchange 2016 migrieren, können Sie sowohl Exchange-Speicher als auch lync Server Speicher auf Interimsbasis verwenden, während Sie die Migration abschließen. Die dauerhafte Verwendung von Exchange und lync Server Speicher wird nicht unterstützt.



</div>

Für die Integration von lync Server 2013 mit Exchange Server und SharePoint Server ist eine Server-zu-Server-Authentifizierung zwischen Servern erforderlich, auf denen lync Server 2013, Exchange Server und SharePoint Server durchführen. Lync Server 2013 unterstützt das OAuth (Open Authorization)-Protokoll für die Server-zu-Server-Authentifizierung und-Autorisierung. Für die lokale Server-zu-Server-Authentifizierung zwischen zwei Microsoft-Servern ist kein Drittanbieter-Tokenserver erforderlich. Lync Server 2013, Exchange Server und SharePoint Server verfügen über einen integrierten tokenserver, der für Authentifizierungszwecke miteinander verwendet werden kann. Beispielsweise können lync Server 2013 ein Sicherheitstoken selbst ausgeben und Signieren und dieses Token bei der Kommunikation mit Exchange verwenden. In diesem Fall muss kein Drittanbieter-Tokenserver verwendet werden.

Lync Server 2013 unterstützt die beiden Szenarien für die Server-zu-Server-Authentifizierung. Diese beinhalten die Konfiguration der Server-zu-Server-Authentifizierung zwischen folgenden Instanzen:

  - Eine lokale Installation von lync Server 2013 und eine lokale Installation von Exchange Server 2013, Exchange Server 2016 und/oder SharePoint Server.

  - Ein paar von Office-Komponenten (beispielsweise zwischen Microsoft Exchange 365 und Microsoft lync Server 365 oder zwischen Microsoft lync Server 365 und Microsoft SharePoint 365).

<div>


> [!NOTE]  
> Die Server-zu-Server-Authentifizierung zwischen einem lokalen Server und einer Office 365 Komponente wird in dieser lync Server 2013 Version nicht unterstützt. Dies bedeutet unter anderem, dass Sie die Server-zu-Server-Authentifizierung zwischen einer lokalen Installation von lync Server 2013 und Microsoft Exchange 365 nicht einrichten können.



</div>

Ausführliche Informationen zur Server-zu-Server-Authentifizierung finden Sie unter [Managing Server-to-Server Authentication (OAuth) and Partner Applications in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in der Bereitstellungsdokumentation oder Betriebsdokumentation.

</div>

<span> </span>

</div>

</div>

</div>

