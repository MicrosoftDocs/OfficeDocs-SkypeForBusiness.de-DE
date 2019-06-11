---
title: 'Lync Server 2013: Unterstützung für Exchange und SharePoint-Integration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c4d378337643adf79557bd4bbb649a01948de27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a>Unterstützung für Exchange-und SharePoint-Integration in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2017-01-18_

Lync Server 2013 und lync 2013 können sicher und nahtlos mit anderen Anwendungen und Server Produkten kommunizieren, einschließlich Office 2013, Exchange Server 2013, Exchange Server 2016 und SharePoint, wenn Sie diese Produkte integrieren. Durch die Integration von lync Server 2013 und Office erhalten Benutzer einen kontextbezogenen Zugriff auf Instant Messaging (im), erweiterte Anwesenheits-, Telefonie-und Konferenzfunktionen von lync. Office-Benutzer können im Outlook 2013-Messaging-und-Zusammenarbeitsclient sowie in anderen Office-Programmen oder auf einer SharePoint-Seite auf lync-Features zugreifen. Benutzer können auch einen Datensatz mit lync-Unterhaltungen im Outlook-Ordner "Konversations Verlauf" anzeigen. Wenn Sie in Exchange 2013, Exchange 2016 oder Exchange Online integriert sind, unterstützt lync Server 2013 auch die folgenden Punkte:

  - Einheitlicher Kontaktspeicher, mit dem Benutzer alle Kontaktinformationen in Exchange oder Exchange Online speichern können, damit die Informationen Global über lync 2013, Exchange, Outlook und Outlook Web App zur Verfügung stehen.

  - Konversations Verlauf und Webkonferenz Verlauf, der in Exchange-Benutzerordnern gespeichert ist.

  - Archivierte Inhalte aus lync, wie Chat-und Besprechungsinhalte, können im Exchange-Speicher gespeichert werden.

<div>


> [!NOTE]  
> Lync Server 2013 unterstützt die Integration in frühere Versionen von Microsoft Exchange Server und SharePoint Server, aber nicht alle Funktionen werden mit diesen vorherigen Versionen unterstützt, beispielsweise die Integration von Archivierungsspeicher mit Microsoft Exchange.<BR>Wenn Sie Ihre Benutzer zu Exchange 2013 oder Exchange 2016 migrieren, können Sie Exchange-Speicher und lync Server-Speicher auf Interimsbasis verwenden, während Sie die Migration abschließen. Die permanente Verwendung von Exchange und lync Server-Speicher wird nicht unterstützt.



</div>

Die Integration von lync Server 2013 mit Exchange Server und SharePoint Server erfordert eine Server-zu-Server-Authentifizierung zwischen Servern mit lync Server 2013, Exchange Server und SharePoint Server. Lync Server 2013 unterstützt das OAuth (Open Authorization)-Protokoll für die Server-zu-Server-Authentifizierung und-Autorisierung. Für die lokale Server-zu-Server-Authentifizierung zwischen zwei Microsoft-Servern muss kein tokenserver eines Drittanbieters verwendet werden. Lync Server 2013, Exchange Server und SharePoint Server verfügen über einen integrierten tokenserver, der für Authentifizierungszwecke untereinander verwendet werden kann. Lync Server 2013 kann beispielsweise ein Sicherheitstoken selbst ausgeben und Signieren und dieses Token bei der Kommunikation mit Exchange verwenden. In diesem Fall ist es nicht erforderlich, einen Token Server eines Drittanbieters zu verwenden.

Lync Server 2013 unterstützt die beiden Server-zu-Server-Authentifizierungsszenarien. Dazu gehören die Konfiguration der Server-zu-Server-Authentifizierung zwischen den folgenden:

  - Eine lokale Installation von lync Server 2013 und eine lokale Installation von Exchange Server 2013, Exchange Server 2016 und/oder SharePoint Server.

  - Ein paar von Office-Komponenten (beispielsweise zwischen Microsoft Exchange 365 und Microsoft lync Server 365 oder zwischen Microsoft lync Server 365 und Microsoft SharePoint 365).

<div>


> [!NOTE]  
> Die Server-zu-Server-Authentifizierung zwischen einem lokalen Server und einer Office 365-Komponente wird in dieser lync Server 2013-Version nicht unterstützt. Dies bedeutet unter anderem, dass Sie keine Server-zu-Server-Authentifizierung zwischen einer lokalen Installation von lync Server 2013 und Microsoft Exchange 365 einrichten können.



</div>

Ausführliche Informationen zur Server-zu-Server-Authentifizierung finden Sie unter [Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in der Bereitstellungsdokumentation oder in der Dokumentation zur Betriebsanleitung.

</div>

<span> </span>

</div>

</div>

</div>

