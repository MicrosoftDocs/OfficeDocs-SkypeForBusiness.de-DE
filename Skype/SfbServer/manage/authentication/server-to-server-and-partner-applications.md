---
title: Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in Skype for Business Server
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
ms.openlocfilehash: d95d4f048743c6725e42e50b5025b0c906adaf53
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818747"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in Skype for Business Server
 
**Zusammenfassung:** Verwalten von OAuth-und Partneranwendungen in Skype for Business Server.
  
Skype for Business Server muss sicher und nahtlos mit anderen Anwendungen und Serverprodukten kommunizieren können. So können Sie beispielsweise Skype for Business Server so konfigurieren, dass Kontaktdaten und/oder Archivierungsdaten in Microsoft Exchange Server 2013 gespeichert werden. Dies kann jedoch nur erfolgen, wenn Skype for Business Server und Exchange sicher miteinander kommunizieren können. Ebenso können Sie eine Skype for Business Server-Konferenz in Office Web Apps Server planen. auch dies kann nur erfolgen, wenn sich die beiden Server (SharePoint und Skype for Business Server) einander vertrauen. Obwohl es möglich ist, einen Authentifizierungsmechanismus für die Kommunikation zwischen Skype for Business Server und Exchange, aber einen separaten Mechanismus für die Kommunikation zwischen Skype for Business Server und SharePoint zu verwenden, besteht ein besserer und effizienterer Ansatz in der Verwendung einer standardisierte Methode für alle Server-zu-Server-Authentifizierung und-Autorisierung.
  
Die Verwendung einer einzelnen standardisierten Methode für die Server-zu-Server-Authentifizierung ist der Ansatz von Skype for Business Server. Mit der Office Server 2013-Version von Skype for Business Server (sowie anderen Microsoft-Serverprodukten, einschließlich Exchange Server und SharePoint Server), wurde das OAuth (Open Authorization)-Protokoll für die Server-zu-Server-Authentifizierung unterstützt und Autorisierungs. Bei OAuth wird ein Standard Autorisierungs Protokoll, das von einer Reihe von Hauptwebsites, Benutzeranmeldeinformationen und Kennwörtern verwendet wird, nicht von einem Computer an einen anderen weitergegeben. Stattdessen basiert Authentifizierung und Autorisierung auf dem Austausch von Sicherheitstokens; Diese Token gewähren für einen bestimmten Zeitraum Zugriff auf eine bestimmte Gruppe von Ressourcen.
  
Die OAuth-Authentifizierung umfasst in der Regel drei Parteien: einen einzelnen autorisierungsserver und die beiden Realms, die miteinander kommunizieren müssen. (Sie können auch eine Server-zu-Server-Authentifizierung ausführen, ohne einen autorisierungsserver zu verwenden, ein Prozess, der später in diesem Dokument erläutert wird.) Sicherheitstoken werden von dem autorisierungsserver (auch als Sicherheitstokenserver bezeichnet) für die beiden Bereiche ausgestellt, die kommuniziert werden müssen. Diese Token stellen sicher, dass die Kommunikation, die von einem Bereich stammt, vom anderen Bereich als vertrauenswürdig eingestuft wird. Beispielsweise kann der autorisierungsserver Token ausgeben, die sicherstellen, dass Benutzer aus einem bestimmten Skype for Business-Serverbereich auf einen bestimmten Exchange-Realm zugreifen können, und umgekehrt.
  
> [!NOTE]
> Ein Bereich ist einfach ein Sicherheitscontainer. Standardmäßig verwendet Skype for Business Server Ihre SIP-Standarddomäne als OAuth-Realm. Weitere SIP-Namespaces werden der Liste mit alternativen Antragstellernamen im OAuth-Zertifikat hinzugefügt. 
  
Skype for Business Server unterstützt drei Szenarien für die Server-zu-Server-Authentifizierung. Mit Skype for Business Server haben Sie folgende Möglichkeiten:
  
- Konfigurieren Sie die Server-zu-Server-Authentifizierung zwischen einer lokalen Installation von Skype for Business Server und einer lokalen Installation von Exchange und/oder SharePoint Server.
    
- Konfigurieren Sie die Server-zu-Server-Authentifizierung zwischen zwei Office 365-Komponenten (beispielsweise zwischen Microsoft Exchange Server und Skype for Business Server oder zwischen Skype for Business Server und SharePoint).
    
- Konfigurieren Sie die Server-zu-Server-Authentifizierung in einer standortübergreifenden Umgebung (Server-zu-Server-Authentifizierung zwischen einem lokalen Server und einer Office 365-Komponente).
    
Beachten Sie, dass zu diesem Zeitpunkt nur Exchange 2013, SharePoint Server, lync Server 2013, Skype for Business Server 2015 und Skype for Business 2019 die Server-zu-Server-Authentifizierung unterstützen. Wenn Sie einen dieser Server nicht ausführen, können Sie die OAuth-Authentifizierung nicht vollständig implementieren.
  
Es sollte auch darauf hingewiesen werden, dass die Server-zu-Server-Authentifizierung optional ist: Wenn Skype for Business Server nicht mit anderen Servern (wie Exchange) kommunizieren muss, kann die Server-zu-Server-Authentifizierung komplett übersprungen werden. Wenn die Server-zu-Server-Authentifizierung bereits für lync Server 2013 und andere Anwendungen konfiguriert ist, müssen Sie Sie nicht für Skype for Business Server erneut ausführen. 
  
Die Server-zu-Server-Authentifizierung ist jedoch erforderlich, wenn Sie einige der Features in Skype for Business Server verwenden möchten, beispielsweise den "Unified Contact Store". Mit dem Unified Contact Store werden die Skype for Business Server-Kontaktinformationen in Exchange anstatt in Skype for Business Server gespeichert. auf diese Weise können Benutzer über einen einzigen Satz Kontakte verfügen, auf die in Skype for Business, Outlook oder Outlook Web Access problemlos zugegriffen werden kann. Da für den einheitlichen Kontaktspeicher Skype for Business Server zum Freigeben von Informationen für Exchange erforderlich ist, müssen Sie die Server-zu-Server-Authentifizierung verwenden, um das Feature bereitzustellen. Die Server-zu-Server-Authentifizierung ist auch erforderlich, wenn Sie die Exchange-Archivierung verwenden möchten, bei der die Protokolle von Chatsitzungen als Exchange-e-Mails und nicht als einzelne Datenbankeinträge gespeichert werden.
  
Damit die Office 365-Version von Skype for Business Server mit Ihrem Exchange-Pendant kommuniziert, muss Skype for Business Server zunächst ein Sicherheitstoken vom autorisierungsserver abrufen. Skype for Business Server verwendet dann dieses Sicherheitstoken, um sich selbst für Exchange zu identifizieren. Die Office 365-Version von Exchange muss denselben Vorgang durchlaufen, um mit Skype for Business Server kommunizieren zu können.
  
Für eine lokale Server-zu-Server-Authentifizierung zwischen zwei Microsoft-Servern muss kein Drittanbieter-Tokenserver verwendet werden. Serverprodukte wie Skype for Business Server und Exchange verfügen über einen integrierten tokenserver, der für Authentifizierungszwecke mit anderen Microsoft-Servern (wie SharePoint Server) verwendet werden kann, die die Server-zu-Server-Authentifizierung unterstützen. Beispielsweise kann Skype for Business Server selbst ein Sicherheitstoken ausgeben und Signieren und dann dieses Token für die Kommunikation mit Exchange verwenden. In einem solchen Fall ist kein Drittanbieter-Tokenserver erforderlich.
  
Um die Server-zu-Server-Authentifizierung für eine lokale Implementierung von Skype for Business Server zu konfigurieren, müssen Sie zwei Schritte ausführen:
  
- Weisen Sie dem integrierten Skype for Business Server-Token-Aussteller ein Zertifikat zu.
    
- Konfigurieren Sie den Server, mit dem Skype for Business Server kommunizieren soll, als "Partneranwendung". Wenn Skype for Business Server beispielsweise mit Exchange kommunizieren muss, müssen Sie Exchange so konfigurieren, dass es sich um eine Partneranwendung handelt.
    
> [!NOTE]
> Eine "Partneranwendung" ist eine beliebige Anwendung, mit der Skype for Business Server Sicherheitstoken direkt austauschen kann, ohne dass ein Sicherheitstoken-Server eines Drittanbieters durchlaufen werden muss. 
  
Beachten Sie, dass OAuth eine Kernkomponente des Produkts ist und weder deaktiviert noch entfernt werden kann.
  
## <a name="see-also"></a>Siehe auch

[Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu Skype for Business Server](assign-a-server-to-server-certificate.md)
  
[Konfigurieren einer Hybridumgebung in Skype for Business Server](configure-a-hybrid-environment.md)
