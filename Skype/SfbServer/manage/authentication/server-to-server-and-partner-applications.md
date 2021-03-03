---
title: Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Zusammenfassung: Verwalten von OAuth und Partneranwendungen in Skype for Business Server.'
ms.openlocfilehash: ff926440d1f00601eacfb77aadb858063b3e48b8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828300"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in Skype for Business Server
 
**Zusammenfassung:** Verwalten von OAuth- und Partneranwendungen in Skype for Business Server.
  
Skype for Business Server muss sicher und nahtlos mit anderen Anwendungen und Serverprodukten kommunizieren können. Beispielsweise können Sie Skype for Business Server so konfigurieren, dass Kontaktdaten und/oder Archivierungsdaten in Microsoft Exchange Server 2013 gespeichert werden. Dies ist jedoch nur möglich, wenn Skype for Business Server und Exchange sicher miteinander kommunizieren können. Ebenso können Sie eine Skype for Business #A0 in Office Web Apps Server planen. Dies ist auch hier nur möglich, wenn sich die beiden Server (SharePoint und Skype for Business Server) vertrauen. Obwohl es möglich ist, einen Authentifizierungsmechanismus für die Kommunikation zwischen Skype for Business Server und Exchange zu verwenden, aber einen separaten Mechanismus für die Skype for Business Server- und SharePoint-Kommunikation, ist ein besserer und effizienterer Ansatz die Verwendung einer standardisierten Methode für alle Server-zu-Server-Authentifizierung und -Autorisierung.
  
Die Verwendung einer einzelnen, standardisierten Methode für die Server-zu-Server-Authentifizierung ist der Ansatz von Skype for Business Server. Ab Version Office Server 2013 unterstützte Skype for Business Server (sowie andere Microsoft Server-Produkte, einschließlich Exchange Server und SharePoint Server) das OAuth (Open Authorization)-Protokoll für die Server-zu-Server-Authentifizierung und -Autorisierung. Bei OAuth, einem Standardautorisierungsprotokoll, das von einer Reihe von Hauptwebsites verwendet wird, werden Benutzeranmeldeinformationen und Kennwörter nicht von einem Computer an einen anderen übergeben. Stattdessen basieren Authentifizierung und Autorisierung auf dem Austausch von Sicherheitstoken. Diese Token gewähren für einen bestimmten Zeitraum Zugriff auf eine bestimmte Gruppe von Ressourcen.
  
OAuth-Authentifizierung umfasst normalerweise drei Komponenten: einen Server mit Einzelanmeldung und zwei Bereiche, die miteinander kommunizieren müssen. (Sie können auch die Server-zu-Server-Authentifizierung ohne Verwendung eines Autorisierungsservers verwenden, ein Prozess, der später in diesem Dokument erläutert wird.) Sicherheitstoken werden vom Autorisierungsserver (auch als Sicherheitstokenserver bekannt) für die beiden Bereiche ausgegeben, die kommunizieren müssen. Diese Token überprüfen, ob Kommunikationen, die von einem Bereich stammen, vom anderen Bereich als vertrauenswürdig eingestuft werden sollten. Beispielsweise kann der Autorisierungsserver Token aussenten, die überprüfen, ob Benutzer aus einem bestimmten Skype for Business Server-Bereich auf einen bestimmten Exchange-Bereich zugreifen können und umgekehrt.
  
> [!NOTE]
> Ein Bereich ist einfach ein Sicherheitscontainer. Standardmäßig verwendet Skype for Business Server Ihre Standard-SIP-Domäne als OAuth-Bereich. Zusätzliche SIP-Namespaces werden der Liste alternativer Subject Name im OAuth-Zertifikat hinzugefügt. 
  
Skype for Business Server unterstützt drei Server-zu-Server-Authentifizierungsszenarien. Mit Skype for Business Server können Sie:
  
- Konfigurieren Sie die Server-zu-Server-Authentifizierung zwischen einer lokalen Installation von Skype for Business Server und einer lokalen Installation von Exchange und/oder SharePoint Server.
    
- Konfigurieren Sie die Server-zu-Server-Authentifizierung zwischen zwei Microsoft 365- oder Office 365-Komponenten (z. B. zwischen Microsoft Exchange Server und Skype for Business Server oder zwischen Skype for Business Server und SharePoint).
    
- Konfigurieren Sie die Server-zu-Server-Authentifizierung in einer standortübergreifenden Umgebung (d. h. Server-zu-Server-Authentifizierung zwischen einem lokalen Server und einer Microsoft 365- oder Office 365-Komponente).
    
Beachten Sie, dass derzeit nur Exchange 2013, SharePoint Server, Lync Server 2013, Skype for Business Server 2015 und Skype for Business 2019 die Server-zu-Server-Authentifizierung unterstützen; Wenn Sie keinen dieser Server ausführen, können Sie die OAuth-Authentifizierung nicht vollständig implementieren.
  
Es sollte auch darauf hingewiesen werden, dass die Server-zu-Server-Authentifizierung optional ist: Wenn Skype for Business Server nicht mit anderen Servern (z. B. Exchange) kommunizieren muss, kann die Server-zu-Server-Authentifizierung vollständig übersprungen werden. Wenn die Server-zu-Server-Authentifizierung bereits für Lync Server 2013 und andere Anwendungen konfiguriert ist, müssen Sie sie nicht erneut für Skype for Business Server verwenden. 
  
Die Server-zu-Server-Authentifizierung ist jedoch erforderlich, wenn Sie einige der Funktionen in Skype for Business Server verwenden möchten, z. B. den "einheitlichen Kontaktspeicher". Mit dem einheitlichen Kontaktspeicher werden Skype for Business #A0 in Exchange und nicht in Skype for Business Server gespeichert. Auf diese Weise können Benutzer über eine einzelne Gruppe von Kontakten verfügen, auf die in Skype for Business, Outlook oder Outlook Web Access problemlos zugegriffen werden kann. Da der einheitliche Kontaktspeicher erfordert, dass Skype for Business Server Informationen mit Exchange gemeinsam verwendet, müssen Sie die Server-zu-Server-Authentifizierung verwenden, um die Funktion bereitstellen zu können. Die Server-zu-Server-Authentifizierung ist auch erforderlich, wenn Sie die Exchange-Archivierung verwenden, bei der die Aufzeichnungen von Chatnachrichtensitzungen als Exchange-E-Mails und nicht als einzelne Datenbankdatensätze gespeichert werden.
  
Damit die Microsoft 365- oder Office 365-Version von Skype for Business Server mit seinem Exchange-Gegenstück kommunizieren kann, muss Skype for Business Server zuerst ein Sicherheitstoken vom Autorisierungsserver abrufen. Skype for Business Server verwendet dann dieses Sicherheitstoken, um sich für Exchange zu identifizieren. Die Microsoft 365- oder Office 365-Versionen von Exchange müssen denselben Prozess für die Kommunikation mit Skype for Business Server durchgehen.
  
Für eine lokale Server-zu-Server-Authentifizierung zwischen zwei Microsoft-Servern muss kein Drittanbieter-Tokenserver verwendet werden. Serverprodukte wie Skype for Business Server und Exchange verfügen über einen integrierten Tokenserver, der für Authentifizierungszwecke mit anderen Server von Microsoft (z. B. SharePoint Server) verwendet werden kann, die die Server-zu-Server-Authentifizierung unterstützen. Beispielsweise kann Skype for Business Server selbst ein Sicherheitstoken ausschreiben und signieren und dieses Token dann für die Kommunikation mit Exchange verwenden. In einem solchen Fall ist ein Drittanbieter-Tokenserver nicht erforderlich.
  
Zum Konfigurieren der Server-zu-Server-Authentifizierung für eine lokale Implementierung von Skype for Business Server müssen Sie zwei Dinge tun:
  
- Weisen Sie dem integrierten Skype for Business Server-Tokenherausgeber ein Zertifikat zu.
    
- Konfigurieren Sie den Server, mit dem Skype for Business Server kommuniziert, als "Partneranwendung". Wenn Skype for Business Server beispielsweise mit Exchange kommunizieren muss, müssen Sie Exchange als Partneranwendung konfigurieren.
    
> [!NOTE]
> Eine "Partneranwendung" ist jede Anwendung, mit der Skype for Business Server Direkt Sicherheitstoken austauschen kann, ohne einen Sicherheitstokenserver eines Drittanbieters verwenden zu müssen. 
  
Beachten Sie, dass OAuth ein zentraler Bestandteil des Produkts ist und nicht deaktiviert oder entfernt werden kann.
  
## <a name="see-also"></a>Siehe auch

[Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu Skype for Business Server](assign-a-server-to-server-certificate.md)
  
[Konfigurieren einer Hybridumgebung in Skype for Business Server](configure-a-hybrid-environment.md)
