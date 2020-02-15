---
title: Verwalten der Server-zu-Server-Authentifizierung (OAuth) und der Partneranwendungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing server-to-server authentication (OAuth) and partner applications
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204817(v=OCS.15)
ms:contentKeyID: 48183894
ms.date: 05/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0d554bc935ea24f7098472a5c893f58dc717839
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a>Verwalten der Server-zu-Server-Authentifizierung (OAuth) und der Partneranwendungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-05-14_

Microsoft lync Server 2013 müssen in der Lage sein, sicher und nahtlos mit anderen Anwendungen und Server Produkten zu kommunizieren. Sie können beispielsweise lync Server 2013 so konfigurieren, dass Kontaktdaten und/oder Archivierungsdaten in Microsoft Exchange Server 2013 gespeichert werden. Dies kann jedoch nur erfolgen, wenn lync Server und Exchange sicher miteinander kommunizieren können. Ebenso können Sie eine lync Server Konferenz in Microsoft SharePoint Server planen; Dies kann jedoch nur geschehen, wenn sich die beiden Server (SharePoint und lync Server) gegenseitig vertrauen. Obwohl es möglich ist, einen Authentifizierungsmechanismus für die Kommunikation zwischen lync und Exchange und einen separaten Mechanismus für die Kommunikation zwischen lync und SharePoint zu verwenden, besteht ein besserer und effizienterer Ansatz in der Verwendung einer standardisierten Methode für alle Server-zu-Server- Authentifizierung und Autorisierung.

Die Verwendung einer einzigen standardisierten Methode für die Server-zu-Server-Authentifizierung ist der Ansatz, der von lync Server 2013 getroffen wird. Für die 2013-Version unterstützen lync Server 2013 (sowie andere Microsoft-Serverprodukte, einschließlich Exchange 2013 und Microsoft SharePoint Server) das OAuth (Open Authorization)-Protokoll für die Server-zu-Server-Authentifizierung und-Autorisierung. Mit OAuth wird ein Standardmäßiges Autorisierungs Protokoll, das von einer Reihe von Hauptwebsites verwendet wird, Benutzeranmeldeinformationen und Kennwörter nicht von einem Computer an einen anderen übergeben. Stattdessen basieren Authentifizierung und Autorisierung auf dem Austausch von Sicherheitstoken; Diese Token gewähren Zugriff auf einen bestimmten Satz von Ressourcen für einen bestimmten Zeitraum.

OAuth-Authentifizierung umfasst normalerweise drei Komponenten: einen Server mit Einzelanmeldung und zwei Bereiche, die miteinander kommunizieren müssen. (Sie können auch die Server-zu-Server-Authentifizierung ohne einen autorisierungsserver durchführen, ein Prozess, der weiter unten in diesem Dokument behandelt wird.) Sicherheitstoken werden von dem autorisierungsserver (auch als Sicherheitstokenserver bezeichnet) für die beiden Bereiche ausgestellt, die miteinander kommunizieren müssen. Diese Token stellen sicher, dass die Kommunikation, die von einem Bereich stammt, vom anderen Bereich als vertrauenswürdig eingestuft wird. Beispielsweise kann der autorisierungsserver Token ausgeben, die sicherstellen, dass Benutzer von einem bestimmten lync Server 2013 Bereichs auf einen bestimmten Exchange 2013 Bereich zugreifen können, und umgekehrt.

<div>


> [!NOTE]
> Ein Bereich ist einfach ein Sicherheitscontainer. Standardmäßig verwendet lync Server 2013 Ihre Standard-SIP-Domäne als OAuth-Bereich. Zusätzliche SIP-Namespaces werden der Liste alternativer Antragsteller Name im OAuth-Zertifikat hinzugefügt.



</div>

Lync Server 2013 unterstützt drei Szenarien für die Server-zu-Server-Authentifizierung. Mit lync Server 2013 haben Sie folgende Möglichkeiten:

  - Konfigurieren Sie die Server-zu-Server-Authentifizierung zwischen einer lokalen Installation von lync Server 2013 und einer lokalen Installation von Exchange 2013 und/oder Microsoft SharePoint Server.

  - Konfigurieren Sie die Server-zu-Server-Authentifizierung zwischen einem Paar Office 365 Komponenten (beispielsweise zwischen Microsoft Exchange und Microsoft lync Server oder zwischen Microsoft lync Server und Microsoft SharePoint).

  - Konfigurieren einer Server-zu-Server-Authentifizierung in einer standortübergreifenden Umgebung (d. h. Server-zu-Server-Authentifizierung zwischen einem lokalen Server und einer Office 365-Komponente).

Beachten Sie, dass zu diesem Zeitpunkt nur Exchange 2013, SharePoint Server und lync Server 2013 die Server-zu-Server-Authentifizierung unterstützen. Wenn Sie einen dieser Server nicht ausführen, können Sie die OAuth-Authentifizierung nicht vollständig implementieren.

Es sollte auch darauf hingewiesen werden, dass Sie die Server-zu-Server-Authentifizierung nicht verwenden müssen: die Server-zu-Server-Authentifizierung ist nicht erforderlich, um lync Server 2013 bereitzustellen. Wenn lync Server 2013 nicht mit anderen Servern (beispielsweise Exchange 2013) kommunizieren muss, ist die Server-zu-Server-Authentifizierung nicht erforderlich.

Die Server-zu-Server-Authentifizierung ist jedoch erforderlich, wenn Sie einige der neuen Features von lync Server wie den "einheitlichen Kontaktspeicher" verwenden möchten. Mit dem einheitlichen Kontaktspeicher werden lync Server 2013 Kontaktinformationen in Exchange 2013 statt in lync Server gespeichert; auf diese Weise können Benutzer über eine einzelne Gruppe von Kontakten verfügen, auf die in lync-, Microsoft Outlook-oder Microsoft Outlook-Webzugriffen problemlos zugegriffen werden kann. Da für den einheitlichen Kontaktspeicher lync Server 2013 zum Freigeben von Informationen mit Exchange 2013 erforderlich ist, müssen Sie die Server-zu-Server-Authentifizierung verwenden, um das Feature bereitzustellen. Die Server-zu-Server-Authentifizierung ist auch erforderlich, wenn Sie die Exchange-Archivierung verwenden, bei der die Protokolle von Chatsitzungen als Exchange 2013 e-Mails statt als einzelne Datenbankeinträge gespeichert werden.

Damit die Office 365 Version von lync Server mit Ihrem Exchange-Pendant kommuniziert, muss lync Server 2013 zunächst ein Sicherheitstoken vom Autorisierungs Server abrufen. Lync Server verwendet dann dieses Sicherheitstoken, um sich selbst zu Exchange zu identifizieren. Die Office 365 Version von Exchange muss denselben Vorgang durchlaufen, um mit lync Server 2013 zu kommunizieren.

Für eine lokale Server-zu-Server-Authentifizierung zwischen zwei Microsoft-Servern muss kein Drittanbieter-Tokenserver verwendet werden. Serverprodukte wie lync Server 2013 und Exchange 2013 verfügen über einen integrierten tokenserver, der für Authentifizierungszwecke mit anderen Microsoft-Servern (wie SharePoint Server) verwendet werden kann, die die Server-zu-Server-Authentifizierung unterstützen. Lync Server 2013 kann beispielsweise alleine ein Sicherheitstoken ausgeben und signieren, sowie dieses Token anschließend zum Kommunizieren mit Exchange 2013 einsetzen. In diesem Fall ist kein Tokenserver eines Drittanbieters erforderlich.

Um die Server-zu-Server-Authentifizierung für eine lokale Implementierung von lync Server 2013 konfigurieren zu können, müssen Sie zwei Schritte ausführen:

  - Dem in Lync Server integrierten Tokenaussteller muss ein Zertifikat zugewiesen werden.

  - Konfigurieren Sie den Server, mit dem lync Server 2013 kommunizieren wird, als "Partneranwendung". Wenn lync Server 2013 beispielsweise mit Exchange 2013 kommunizieren müssen, muss Exchange als Partneranwendung konfiguriert werden.

<div>


> [!NOTE]
> Bei einer "Partneranwendung" handelt es sich um eine beliebige Anwendung, mit der lync Server 2013 Sicherheitstoken direkt austauschen kann, ohne einen Sicherheits tokenserver eines Drittanbieters durchlaufen zu müssen.



</div>

Beachten Sie, dass OAuth ein zentraler Bestandteil des Produkts ist und nicht deaktiviert oder entfernt werden kann.

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

