---
title: Verwalten der Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Zusammenfassung: Verwalten von OAuth- und Partneranwendungen in Skype for Business Server.'
---

# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Verwalten der Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in Skype for Business Server
 
**Zusammenfassung:** Verwalten von OAuth- und Partneranwendungen in Skype for Business Server.
  
Skype for Business Server müssen in der Lage sein, sicher und nahtlos mit anderen Anwendungen und Serverprodukten zu kommunizieren. Beispielsweise können Sie Skype for Business Server so konfigurieren, dass Kontaktdaten und/oder Archivierungsdaten in Microsoft Exchange Server 2013 gespeichert werden. Dies ist jedoch nur möglich, wenn Skype for Business Server und Exchange  sind in der Lage, sicher miteinander zu kommunizieren. Ebenso können Sie eine Skype for Business Server Konferenz innerhalb Office Web Apps-Servers planen. Dies kann auch hier nur erfolgen, wenn die beiden Server (SharePoint und Skype for Business Server) einander vertrauen. Es ist zwar möglich, einen Authentifizierungsmechanismus für die Kommunikation zwischen Skype for Business Server und Exchange zu verwenden, aber einen separaten Mechanismus für Skype for Business Server und SharePoint  Kommunikation, ein besserer und effizienterer Ansatz ist die Verwendung einer standardisierten Methode für die gesamte Server-zu-Server-Authentifizierung und -Autorisierung.
  
Die Verwendung einer einzelnen, standardisierten Methode für die Server-zu-Server-Authentifizierung ist der Ansatz Skype for Business Server. Mit Office Server 2013-Version gestartet, unterstützten Skype for Business Server (sowie andere Microsoft Server-Produkte, einschließlich Exchange Server und SharePoint Server), das OAuth-Protokoll (Open Authorization) für die Server-zu-Server-Authentifizierung und -Autorisierung. Bei OAuth wird ein Standardautorisierungsprotokoll, das von einer Reihe wichtiger Websites verwendet wird, benutzeranmeldeinformationen und Kennwörter nicht von einem Computer an einen anderen übergeben. Stattdessen basiert die Authentifizierung und Autorisierung auf dem Austausch von Sicherheitstoken. diese Token gewähren zugriff auf einen bestimmten Satz von Ressourcen für einen bestimmten Zeitraum.
  
OAuth-Authentifizierung umfasst normalerweise drei Komponenten: einen Server mit Einzelanmeldung und zwei Bereiche, die miteinander kommunizieren müssen. (Sie können die Server-zu-Server-Authentifizierung auch ohne Verwendung eines Autorisierungsservers durchführen, ein Prozess, der weiter unten in diesem Dokument erläutert wird.) Sicherheitstoken werden vom Autorisierungsserver (auch als Sicherheitstokenserver bezeichnet) für die beiden Bereiche ausgegeben, die kommunizieren müssen. Diese Token überprüfen, ob kommunikationen, die von einem Bereich stammen, vom anderen Bereich als vertrauenswürdig eingestuft werden sollten. Beispielsweise kann der Autorisierungsserver Token ausgeben, die überprüfen, ob Benutzer aus einem bestimmten Skype for Business Server Bereich auf einen angegebenen Exchange Bereich zugreifen können und umgekehrt.
  
> [!NOTE]
> Ein Bereich ist einfach ein Sicherheitscontainer. Standardmäßig verwendet Skype for Business Server Ihre Standard-SIP-Domäne als OAuth-Bereich. Zusätzliche SIP-Namespaces werden der Liste der alternativen Antragstellernamen im OAuth-Zertifikat hinzugefügt. 
  
Skype for Business Server unterstützt drei Server-zu-Server-Authentifizierungsszenarien. Mit Skype for Business Server haben Sie folgende Möglichkeiten:
  
- Konfigurieren Sie die Server-zu-Server-Authentifizierung zwischen einer lokalen Installation von Skype for Business Server und einer lokalen Installation von Exchange und/oder SharePoint Server.
    
- Konfigurieren der Server-zu-Server-Authentifizierung zwischen zwei Microsoft 365 oder Office 365 Komponenten (z. B. zwischen Microsoft Exchange Server und Skype for Business Server oder zwischen Skype for Business Server und SharePoint).
    
- Konfigurieren der Server-zu-Server-Authentifizierung in einer standortübergreifenden Umgebung (d. a. Server-zu-Server-Authentifizierung zwischen einem lokalen Server und einer Microsoft 365- oder Office 365-Komponente).
    
Beachten Sie, dass zu diesem Zeitpunkt nur Exchange 2013, SharePoint Server, Lync Server 2013, Skype for Business Server 2015 und Skype for Business 2019 die Server-zu-Server-Authentifizierung unterstützen. Wenn Sie keinen dieser Server ausführen, können Sie die OAuth-Authentifizierung nicht vollständig implementieren.
  
Es sollte auch darauf hingewiesen werden, dass die Server-zu-Server-Authentifizierung optional ist: Wenn Skype for Business Server nicht mit anderen Servern kommunizieren muss (z. B. Exchange), kann die Server-zu-Server-Authentifizierung vollständig übersprungen werden. Wenn die Server-zu-Server-Authentifizierung bereits für Lync Server 2013 und andere Anwendungen konfiguriert ist, ist es nicht erforderlich, dies für Skype for Business Server erneut durchzuführen. 
  
Die Server-zu-Server-Authentifizierung ist jedoch erforderlich, wenn Sie einige der Features in Skype for Business Server verwenden möchten, z. B. den "einheitlichen Kontaktspeicher". Mit einem einheitlichen Kontaktspeicher werden Skype for Business Server Kontaktinformationen in Exchange statt in Skype for Business Server gespeichert. Dadurch können Benutzer über einen einzigen Satz von Kontakten verfügen, auf die in Skype for Business leicht zugegriffen werden kann. Outlook oder Outlook Web Access. Da für den einheitlichen Kontaktspeicher Skype for Business Server erforderlich sind, um Informationen für Exchange freizugeben, müssen Sie die Server-zu-Server-Authentifizierung verwenden, um das Feature bereitzustellen. Die Server-zu-Server-Authentifizierung ist auch erforderlich, wenn Sie Exchange Archivierung verwenden, in der die Aufzeichnungen von Chatsitzungen als Exchange E-Mails und nicht als einzelne Datenbankdatensätze gespeichert werden.
  
Damit die Microsoft 365 oder Office 365 Version von Skype for Business Server mit ihrer Exchange Entsprechung kommunizieren kann, müssen Skype for Business Server zuerst ein Sicherheitstoken vom Autorisierungsserver abrufen. Skype for Business Server verwendet dann dieses Sicherheitstoken, um sich selbst für Exchange zu identifizieren. Die Microsoft 365 oder Office 365 Versionen von Exchange müssen denselben Prozess durchlaufen, um mit Skype for Business Server kommunizieren zu können.
  
Für eine lokale Server-zu-Server-Authentifizierung zwischen zwei Microsoft-Servern muss kein Drittanbieter-Tokenserver verwendet werden. Serverprodukte wie Skype for Business Server und Exchange verfügen über einen integrierten Tokenserver, der für Authentifizierungszwecke mit anderen Microsoft-Servern (z. B. SharePoint Server) verwendet werden kann, die die Server-zu-Server-Authentifizierung unterstützen. Beispielsweise können Skype for Business Server ein Sicherheitstoken selbst ausstellen und signieren und dieses Token dann für die Kommunikation mit Exchange verwenden. In einem solchen Fall ist ein Drittanbieter-Tokenserver nicht erforderlich.
  
Um die Server-zu-Server-Authentifizierung für eine lokale Implementierung von Skype for Business Server zu konfigurieren, müssen Sie zwei Schritte ausführen:
  
- Weisen Sie dem integrierten Skype for Business Server Tokenaussteller ein Zertifikat zu.
    
- Konfigurieren Sie den Server, mit dem Skype for Business Server kommunizieren, als "Partneranwendung". Wenn Skype for Business Server beispielsweise mit Exchange kommunizieren muss, müssen Sie Exchange als Partneranwendung konfigurieren.
    
> [!NOTE]
> Eine "Partneranwendung" ist jede Anwendung, mit der Skype for Business Server Sicherheitstoken direkt austauschen können, ohne einen Sicherheitstokenserver eines Drittanbieters durchlaufen zu müssen. 
  
Beachten Sie, dass OAuth ein wesentlicher Bestandteil des Produkts ist und nicht deaktiviert oder entfernt werden kann.
  
## <a name="see-also"></a>Siehe auch

[Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu Skype for Business Server](assign-a-server-to-server-certificate.md)
  
[Konfigurieren einer Hybridumgebung in Skype for Business Server](configure-a-hybrid-environment.md)
