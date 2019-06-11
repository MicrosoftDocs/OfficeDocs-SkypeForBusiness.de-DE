---
title: Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing server-to-server authentication (OAuth) and partner applications
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204817(v=OCS.15)
ms:contentKeyID: 48183894
ms.date: 05/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4cdfd80c368558ee034369eba0ca0cb9e89ecea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a>Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-05-14_

Microsoft lync Server 2013 muss sicher und nahtlos mit anderen Anwendungen und Server Produkten kommunizieren können. So können Sie beispielsweise lync Server 2013 so konfigurieren, dass Kontaktdaten und/oder Archivierungsdaten in Microsoft Exchange Server 2013 gespeichert werden. Dies kann jedoch nur erfolgen, wenn lync Server und Exchange sicher miteinander kommunizieren können. Ebenso können Sie eine lync Server-Konferenz in Microsoft SharePoint Server planen. Dies kann jedoch nur erfolgen, wenn sich die beiden Server (SharePoint und lync Server) gegenseitig vertrauen. Obwohl es möglich ist, einen Authentifizierungsmechanismus für die Kommunikation zwischen lync und Exchange sowie einen separaten Mechanismus für die Kommunikation zwischen lync und SharePoint zu verwenden, besteht ein besserer und effizienterer Ansatz darin, eine standardisierte Methode für alle Server-zu-Server-Zwecke zu verwenden. Authentifizierung und Autorisierung.

Die Verwendung einer einzelnen standardisierten Methode für die Server-zu-Server-Authentifizierung ist der von lync Server 2013 getroffene Ansatz. Für die 2013-Version unterstützen lync Server 2013 (sowie andere Microsoft-Serverprodukte, einschließlich Exchange 2013 und Microsoft SharePoint Server) das OAuth (Open Authorization)-Protokoll für die Server-zu-Server-Authentifizierung und-Autorisierung. Bei OAuth wird ein Standard Autorisierungs Protokoll, das von einer Reihe von Hauptwebsites, Benutzeranmeldeinformationen und Kennwörtern verwendet wird, nicht von einem Computer an einen anderen weitergegeben. Stattdessen basiert Authentifizierung und Autorisierung auf dem Austausch von Sicherheitstokens; Diese Token gewähren für einen bestimmten Zeitraum Zugriff auf eine bestimmte Gruppe von Ressourcen.

Die OAuth-Authentifizierung umfasst in der Regel drei Parteien: einen einzelnen autorisierungsserver und die beiden Realms, die miteinander kommunizieren müssen. (Sie können auch eine Server-zu-Server-Authentifizierung ausführen, ohne einen autorisierungsserver zu verwenden, ein Prozess, der später in diesem Dokument erläutert wird.) Sicherheitstoken werden von dem autorisierungsserver (auch als Sicherheitstokenserver bezeichnet) für die beiden Bereiche ausgestellt, die kommuniziert werden müssen. Diese Token stellen sicher, dass die Kommunikation, die von einem Bereich stammt, vom anderen Bereich als vertrauenswürdig eingestuft wird. Beispielsweise kann der autorisierungsserver Token ausgeben, mit denen sichergestellt wird, dass Benutzer aus einem bestimmten lync Server-2013-Bereich auf einen bestimmten Exchange 2013-Bereich zugreifen können, und umgekehrt.

<div>


> [!NOTE]
> Ein Bereich ist einfach ein Sicherheitscontainer. Standardmäßig verwendet lync Server 2013 Ihre SIP-Standarddomäne als OAuth-Bereich. Weitere SIP-Namespaces werden der Liste mit alternativen Antragstellernamen im OAuth-Zertifikat hinzugefügt.



</div>

Lync Server 2013 unterstützt drei Szenarien für die Server-zu-Server-Authentifizierung. Mit lync Server 2013 können Sie Folgendes tun:

  - Konfigurieren Sie die Server-zu-Server-Authentifizierung zwischen einer lokalen Installation von lync Server 2013 und einer lokalen Installation von Exchange 2013 und/oder Microsoft SharePoint Server.

  - Konfigurieren Sie die Server-zu-Server-Authentifizierung zwischen zwei Office 365-Komponenten (beispielsweise zwischen Microsoft Exchange und Microsoft lync Server oder zwischen Microsoft lync Server und Microsoft SharePoint).

  - Konfigurieren Sie die Server-zu-Server-Authentifizierung in einer standortübergreifenden Umgebung (Server-zu-Server-Authentifizierung zwischen einem lokalen Server und einer Office 365-Komponente).

Beachten Sie, dass zu diesem Zeitpunkt nur Exchange 2013, SharePoint Server und lync Server 2013 die Server-zu-Server-Authentifizierung unterstützen. Wenn Sie einen dieser Server nicht ausführen, können Sie die OAuth-Authentifizierung nicht vollständig implementieren.

Es sollte auch darauf hingewiesen werden, dass Sie die Server-zu-Server-Authentifizierung nicht verwenden müssen: die Server-zu-Server-Authentifizierung ist nicht erforderlich, um lync Server 2013 bereitzustellen. Wenn lync Server 2013 nicht mit anderen Servern (wie Exchange 2013) kommunizieren muss, wird die Server-zu-Server-Authentifizierung nicht benötigt.

Die Server-zu-Server-Authentifizierung ist jedoch erforderlich, wenn Sie einige der neuen Funktionen von lync Server verwenden möchten, beispielsweise den "Unified Contact Store". Mit dem Unified Contact Store werden die lync Server 2013-Kontaktinformationen in Exchange 2013 statt in lync Server gespeichert. Dadurch können Benutzer über einen einzigen Satz Kontakte verfügen, auf die in lync, Microsoft Outlook oder Microsoft Outlook Web Access problemlos zugegriffen werden kann. Da für den Unified Contact Store lync Server 2013 zum Freigeben von Informationen für Exchange 2013 erforderlich ist, müssen Sie die Server-zu-Server-Authentifizierung verwenden, um das Feature bereitzustellen. Die Server-zu-Server-Authentifizierung ist auch erforderlich, wenn Sie die Exchange-Archivierung verwenden möchten, in der die Protokolle von Chatsitzungen als Exchange 2013-e-Mails und nicht als einzelne Datenbankeinträge gespeichert werden.

Damit die Office 365-Version von lync Server mit dem Exchange-Pendant kommuniziert, muss lync Server 2013 zuerst ein Sicherheitstoken vom autorisierungsserver abrufen. Lync Server verwendet dann dieses Sicherheitstoken, um sich selbst für Exchange zu identifizieren. Die Office 365-Version von Exchange muss denselben Vorgang durchlaufen, um mit lync Server 2013 zu kommunizieren.

Für eine lokale Server-zu-Server-Authentifizierung zwischen zwei Microsoft-Servern muss kein Drittanbieter-Tokenserver verwendet werden. Serverprodukte wie lync Server 2013 und Exchange 2013 verfügen über einen integrierten tokenserver, der für Authentifizierungszwecke mit anderen Microsoft-Servern (wie SharePoint Server) verwendet werden kann, die die Server-zu-Server-Authentifizierung unterstützen. Mit lync Server 2013 können Sie beispielsweise ein Sicherheitstoken selbst ausgeben und Signieren und dann dieses Token für die Kommunikation mit Exchange 2013 verwenden. In einem solchen Fall ist kein Drittanbieter-Tokenserver erforderlich.

Um die Server-zu-Server-Authentifizierung für eine lokale Implementierung von lync Server 2013 zu konfigurieren, müssen Sie zwei Schritte ausführen:

  - Weisen Sie dem in lync Server integrierten Token-Aussteller ein Zertifikat zu.

  - Konfigurieren Sie den Server, mit dem lync Server 2013 kommuniziert, als "Partneranwendung". Wenn lync Server 2013 beispielsweise mit Exchange 2013 kommunizieren muss, müssen Sie Exchange so konfigurieren, dass es sich um eine Partneranwendung handelt.

<div>


> [!NOTE]
> Eine "Partneranwendung" ist eine beliebige Anwendung, mit der lync Server 2013 Sicherheitstoken direkt austauschen kann, ohne dass ein Sicherheits tokenserver eines Drittanbieters durchlaufen werden muss.



</div>

Beachten Sie, dass OAuth eine Kernkomponente des Produkts ist und weder deaktiviert noch entfernt werden kann.

<div>

## <a name="see-also"></a>Siehe auch


[Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu Microsoft lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[Konfigurieren von Microsoft lync Server 2013 in einer standortübergreifenden Umgebung](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

