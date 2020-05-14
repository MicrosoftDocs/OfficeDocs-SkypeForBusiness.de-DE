---
title: Verwalten der Server-zu-Server-Authentifizierung (OAuth) und der Partneranwendungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Zusammenfassung: Verwalten von OAuth-und Partneranwendungen in Skype for Business Server.'
ms.openlocfilehash: f784dd0a2dab05fb3b97497fab7d3866dda1a753
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221669"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Verwalten der Server-zu-Server-Authentifizierung (OAuth) und der Partneranwendungen in Skype for Business Server
 
**Zusammenfassung:** Verwalten von OAuth-und Partneranwendungen in Skype for Business Server.
  
Skype for Business Server müssen in der Lage sein, sicher und nahtlos mit anderen Anwendungen und Server Produkten zu kommunizieren. Sie können beispielsweise Skype for Business Server so konfigurieren, dass Kontaktdaten und/oder Archivierungsdaten in Microsoft Exchange Server 2013 gespeichert werden. Dies kann jedoch nur erfolgen, wenn Skype for Business Server und Exchange sicher miteinander kommunizieren können. Ebenso können Sie eine Skype for Business Server Konferenz in Office-webapps Server planen; Dies kann wiederum nur geschehen, wenn die beiden Server (SharePoint und Skype for Business Server) einander vertrauen. Obwohl es möglich ist, einen Authentifizierungsmechanismus für die Kommunikation zwischen Skype for Business Server und Exchange, aber einen separaten Mechanismus für die Skype for Business Server-und SharePoint-Kommunikation zu verwenden, besteht ein besserer und effizienterer Ansatz darin, eine standardisierte Methode für alle Server-zu-Server-Authentifizierung und-Autorisierung zu verwenden.
  
Die Verwendung einer einzigen standardisierten Methode für die Server-zu-Server-Authentifizierung ist der Ansatz, der von Skype for Business Server getroffen wird. Mit Office Server 2013 Release, Skype for Business Server (sowie anderen Microsoft-Serverprodukten, einschließlich Exchange Server und SharePoint Server), wurde das OAuth (Open Authorization)-Protokoll für die Server-zu-Server-Authentifizierung und-Autorisierung unterstützt. Mit OAuth wird ein Standardmäßiges Autorisierungs Protokoll, das von einer Reihe von Hauptwebsites verwendet wird, Benutzeranmeldeinformationen und Kennwörter nicht von einem Computer an einen anderen übergeben. Stattdessen basieren Authentifizierung und Autorisierung auf dem Austausch von Sicherheitstoken; Diese Token gewähren Zugriff auf einen bestimmten Satz von Ressourcen für einen bestimmten Zeitraum.
  
OAuth-Authentifizierung umfasst normalerweise drei Komponenten: einen Server mit Einzelanmeldung und zwei Bereiche, die miteinander kommunizieren müssen. (Sie können auch die Server-zu-Server-Authentifizierung ohne einen autorisierungsserver durchführen, ein Prozess, der weiter unten in diesem Dokument behandelt wird.) Sicherheitstoken werden von dem autorisierungsserver (auch als Sicherheitstokenserver bezeichnet) für die beiden Bereiche ausgestellt, die miteinander kommunizieren müssen. Diese Token stellen sicher, dass die Kommunikation, die von einem Bereich stammt, vom anderen Bereich als vertrauenswürdig eingestuft wird. Beispielsweise kann der autorisierungsserver Token ausgeben, die sicherstellen, dass Benutzer von einem bestimmten Skype for Business Server Bereichs auf einen bestimmten Exchange-Bereich zugreifen können, und umgekehrt.
  
> [!NOTE]
> Ein Bereich ist einfach ein Sicherheitscontainer. Standardmäßig verwendet Skype for Business Server Ihre Standard-SIP-Domäne als OAuth-Bereich. Zusätzliche SIP-Namespaces werden der Liste alternativer Antragsteller Name im OAuth-Zertifikat hinzugefügt. 
  
Skype for Business Server unterstützt drei Szenarien für die Server-zu-Server-Authentifizierung. Mit Skype for Business Server haben Sie folgende Möglichkeiten:
  
- Konfigurieren der Server-zu-Server-Authentifizierung zwischen einer lokalen Installation von Skype for Business Server und einer lokalen Installation von Exchange und/oder SharePoint Server.
    
- Konfigurieren Sie die Server-zu-Server-Authentifizierung zwischen einem Paar von Microsoft 365-oder Office 365-Komponenten (beispielsweise zwischen Exchange Server und Skype for Business Server oder zwischen Skype for Business Server und SharePoint).
    
- Konfigurieren Sie die Server-zu-Server-Authentifizierung in einer standortübergreifenden Umgebung (Server-zu-Server-Authentifizierung zwischen einem lokalen Server und einer Microsoft 365-oder Office 365-Komponente).
    
Beachten Sie, dass zu diesem Zeitpunkt nur Exchange 2013, SharePoint Server, lync Server 2013, Skype for Business Server 2015 und Skype for Business 2019 die Server-zu-Server-Authentifizierung unterstützen. Wenn Sie einen dieser Server nicht ausführen, können Sie die OAuth-Authentifizierung nicht vollständig implementieren.
  
Es sollte auch darauf hingewiesen werden, dass die Server-zu-Server-Authentifizierung optional ist: Wenn Skype for Business Server nicht mit anderen Servern (wie Exchange) kommunizieren muss, kann die Server-zu-Server-Authentifizierung insgesamt übersprungen werden. Wenn die Server-zu-Server-Authentifizierung bereits für lync Server 2013 und andere Anwendungen konfiguriert ist, müssen Sie Sie nicht für Skype for Business Server erneut ausführen. 
  
Die Server-zu-Server-Authentifizierung ist jedoch erforderlich, wenn Sie einige der Features in Skype for Business Server verwenden möchten, beispielsweise den "einheitlichen Kontaktspeicher". Mit dem einheitlichen Kontaktspeicher werden Skype for Business Server Kontaktinformationen in Exchange statt in Skype for Business Server gespeichert; auf diese Weise können Benutzer eine einzelne Gruppe von Kontakten haben, auf die in Skype for Business, Outlook oder Outlook Web Access leicht zugegriffen werden kann. Da für den einheitlichen Kontaktspeicher Skype for Business Server zum Freigeben von Informationen für Exchange erforderlich ist, müssen Sie die Server-zu-Server-Authentifizierung verwenden, um das Feature bereitzustellen. Die Server-zu-Server-Authentifizierung ist auch erforderlich, wenn Sie die Exchange-Archivierung verwenden, bei der die Protokolle von Chatsitzungen als Exchange-e-Mails statt als einzelne Datenbankeinträge gespeichert werden.
  
Damit die Microsoft 365-oder Office 365-Version von Skype for Business Server mit Ihrem Exchange-Pendant kommuniziert, muss Skype for Business Server zunächst ein Sicherheitstoken vom Autorisierungs Server abrufen. Skype for Business Server verwendet dann dieses Sicherheitstoken, um sich selbst zu Exchange zu identifizieren. Die Microsoft 365-oder Office 365-Versionen von Exchange müssen den gleichen Prozess durchlaufen, um mit Skype for Business Server zu kommunizieren.
  
Für eine lokale Server-zu-Server-Authentifizierung zwischen zwei Microsoft-Servern muss kein Drittanbieter-Tokenserver verwendet werden. Serverprodukte wie Skype for Business Server und Exchange verfügen über einen integrierten tokenserver, der für Authentifizierungszwecke mit anderen Microsoft-Servern (beispielsweise SharePoint Server) verwendet werden kann, die die Server-zu-Server-Authentifizierung unterstützen. Beispielsweise können Skype for Business Server ein Sicherheitstoken selbst ausgeben und signieren, dann verwenden Sie dieses Token für die Kommunikation mit Exchange. In einem solchen Fall ist ein Drittanbieter-Tokenserver nicht erforderlich.
  
Um die Server-zu-Server-Authentifizierung für eine lokale Implementierung von Skype for Business Server konfigurieren zu können, müssen Sie zwei Schritte ausführen:
  
- Weisen Sie dem integrierten Skype for Business Server Token-Aussteller ein Zertifikat zu.
    
- Konfigurieren Sie den Server, mit dem Skype for Business Server kommunizieren wird, als "Partneranwendung". Wenn Skype for Business Server beispielsweise mit Exchange kommunizieren muss, müssen Sie Exchange als Partneranwendung konfigurieren.
    
> [!NOTE]
> Bei einer "Partneranwendung" handelt es sich um eine beliebige Anwendung, mit der Skype for Business Server Sicherheitstoken direkt austauschen kann, ohne einen Sicherheits tokenserver eines Drittanbieters durchlaufen zu müssen. 
  
Beachten Sie, dass OAuth ein zentraler Bestandteil des Produkts ist und nicht deaktiviert oder entfernt werden kann.
  
## <a name="see-also"></a>Siehe auch

[Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu Skype for Business Server](assign-a-server-to-server-certificate.md)
  
[Konfigurieren einer Hybridumgebung in Skype for Business Server](configure-a-hybrid-environment.md)
