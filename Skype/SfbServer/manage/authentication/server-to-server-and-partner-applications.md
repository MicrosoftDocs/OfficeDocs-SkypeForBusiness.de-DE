---
title: Verwalten von Server-zu-Server-Authentifizierung (OAuth) und partneranwendungen in Skype für Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Zusammenfassung: Verwalten von OAuth und Partner Applications in Skype für Business Server.'
ms.openlocfilehash: 77fd070ace850035d129dc247decdcf7988219cf
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217285"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Verwalten von Server-zu-Server-Authentifizierung (OAuth) und partneranwendungen in Skype für Business Server
 
**Zusammenfassung:** Verwalten von OAuth und Partner Applications in Skype für Business Server.
  
Skype für Business Server muss sicher und nahtlos mit anderen Anwendungen und Server-Produkten zu kommunizieren. Beispielsweise können Sie Skype konfigurieren, für die Business Server damit Daten und/oder archivierten Daten Kontakt in Microsoft Exchange Server 2013 gespeichert ist. Allerdings dies nur möglich, wenn Skype für Business Server und Exchange sicher miteinander kommunizieren kann. Ebenso können Sie einen Skype für Business Server-Konferenz von Office Web Apps Server planen; In diesem Fall dies nur möglich, wenn die zwei Server (SharePoint und Skype für Business Server) einander vertrauen. Obwohl es möglich, eine Authentifizierungsmethode für die Kommunikation zwischen Skype für Business Server und Exchange jedoch einen separaten Mechanismus zum Skype für Business Server und SharePoint-Kommunikation zu verwenden ist, ein besserer und effizienter Ansatz ist die Verwendung einer standardisierte Methode für alle Server-zu-Server-Authentifizierung und Autorisierung.
  
Mit einer einzelnen, ist die Standardmethode für die Server-zu-Server-Authentifizierung Ansatz von Skype für Business Server. Schritte mit Office Server 2013-Version, unterstützt Skype für Business Server (sowie andere Microsoft-Server-Produkte, einschließlich Exchange Server und SharePoint Server) (Open Authorization) OAuth-Protokolls für die Server-zu-Server-Authentifizierung und Autorisierung. Mit OAuth, ein standard Authorization-Protokoll verwendet, um eine Anzahl von großen Websites werden Anmeldeinformationen von Benutzern und Kennwörtern nicht von einem Computer an eine andere übergeben. Stattdessen, Authentifizierung und Autorisierung basiert auf den Austausch von Sicherheitstoken; Diese Token gewähren des Zugriffs auf eine bestimmte Gruppe von Ressourcen für einen bestimmten Zeitraum.
  
OAuth-Authentifizierung in der Regel umfasst drei Parteien: eine einzelne autorisierungsserver und die zwei Bereiche, die miteinander kommunizieren müssen. (Sie können auch ausführen Server-zu-Server-Authentifizierung ohne Verwendung eines autorisierungsservers ein Prozess, der weiter unten in diesem Dokument erläutert werden.) Sicherheitstoken werden durch die autorisierungsserver (auch bekannt als ein Security token), die zwei Bereiche ausgegeben, die kommunizieren müssen; Diese Token stellen Sie sicher, dass Communications, die aus einem Bereich stammen von den anderen Bereich als vertrauenswürdig sein sollte. Beispielsweise könnte autorisierungsserver Token aus, die die Stellen Sie sicher, dass Benutzer aus einer bestimmten Skype für Business Server Bereich auf einem angegebenen Bereich von Exchange und umgekehrt zugreifen können.
  
> [!NOTE]
> Ein Bereich ist einfach ein Sicherheitscontainer. Skype für Business Server verwendet standardmäßig die Standard-SIP-Domäne als dessen OAuth-Bereich. Weitere SIP-Namespaces werden der Liste mit alternativen Antragstellernamen im OAuth-Zertifikat hinzugefügt. 
  
Skype für Business Server unterstützt drei Szenarien für Server-zu-Server-Authentifizierung. Skype für Business Server ermöglichen Folgendes:
  
- Konfigurieren der Server-zu-Server-Authentifizierung zwischen einer lokalen Installation von Skype für Business Server und einer lokalen Installation von Exchange und/oder SharePoint Server.
    
- Konfigurieren der Server-zu-Server-Authentifizierung zwischen einem Paar von Office 365-Komponenten (z. B. zwischen Microsoft Exchange Server und Skype für Business Server oder zwischen Skype für Business Server und SharePoint).
    
- Konfigurieren der Server-zu-Server-Authentifizierung in einer standortübergreifenden Umgebung (d. h., Server-zu-Server-Authentifizierung zwischen einem lokalen Server und Office 365-Komponente).
    
Beachten Sie, dass die zu diesem Zeitpunkt nur Exchange 2013, SharePoint Server, Lync Server 2013, Skype für Business Server 2015 und Skype für 2019 Business Server-zu-Server-Authentifizierung unterstützen. Wenn einer dieser Server nicht ausgeführt werden, werden Sie nicht vollständig OAuth-Authentifizierung implementieren können.
  
Sie sollten auch darauf hin, Server-zu-Server-Authentifizierung ist optional: Wenn Skype für Business Server muss sich nicht um eine Kommunikation mit anderen Servern (beispielsweise Exchange), und klicken Sie dann Server-zu-Server-Authentifizierung kann ganz übersprungen werden. Wenn der Server-zu-Server-Authentifizierung für Lync Server 2013 und anderen Applikationen bereits konfiguriert ist, besteht keine Notwendigkeit erneutes Ausführen der es für Skype für Business Server. 
  
Jedoch ist Server-zu-Server-Authentifizierung erforderlich, wenn Sie einige der Features in Skype für Business Server, wie beispielsweise "einheitlichen Kontaktspeicher." verwenden möchten Mit dem einheitlichen Kontaktspeicher ist Skype für Business Server Kontaktinformationen in Exchange anstatt in Skype für Business Server gespeichert; Dadurch können Benutzer über einen einzelnen Satz von Kontakten verfügen, aus in Skype für Business, Outlook oder Outlook Web Access leicht zugänglich ist. Da einheitlichen Kontaktspeicher Skype für Business Server Datenaustausch mit Exchange erfordert, müssen Sie die Server-zu-Server-Authentifizierung verwenden, um das Feature bereitstellen. Server-zu-Server-Authentifizierung ist auch erforderlich, wenn Sie entscheiden, Archivierung, Exchange verwenden, in dem die Protokolle von Sofortnachrichtensitzungen als Exchange-e-Mails und nicht als einzelne Datenbankdatensätze gespeichert werden.
  
Für die Office 365-Version von Skype für Business Server mit Exchange Gegenstück kommunizieren muss Skype für Business Server zunächst ein Sicherheitstoken vom autorisierungsserver abrufen. Skype für Business Server wird Security Token, um sich selbst zu Exchange zu identifizieren. Office 365-Version von Exchange muss die gleichen Schritte, um die Kommunikation mit Skype für Business Server wechseln.
  
Für eine lokale Server-zu-Server-Authentifizierung zwischen zwei Microsoft-Servern muss kein Drittanbieter-Tokenserver verwendet werden. Wie Skype für Business Server und Exchange Server-Produkten haben einen integrierten token Server, der für die Authentifizierung mit anderen Microsoft-Servern (wie SharePoint Server) verwendet werden kann, die Server-zu-Server-Authentifizierung unterstützen. Beispielsweise kann Skype für Business Server ausstellen und melden Sie sich selbst ein Sicherheitstoken dann Verwendung des Tokens zur Kommunikation mit Exchange. In einem solchen Fall ist kein Drittanbieter-Tokenserver erforderlich.
  
Um die Server-zu-Server-Authentifizierung für eine lokale Implementierung von Skype für Business Server konfigurieren, müssen Sie zwei Dinge tun:
  
- Weisen Sie ein Zertifikat auf den integrierten Skype für Tokenherausgebers Business Server.
    
- Konfigurieren des Servers, dem kommunizieren Skype für Business Server mit einer "partneranwendung." Wenn Skype für Business Server die Kommunikation mit Exchange muss, müssen Sie Exchange um eine partneranwendung zu konfigurieren.
    
> [!NOTE]
> "Partneranwendung" ist eine Anwendung, die Skype für Business Server Sicherheitstoken mit, ohne dass Sie über einen Drittanbieter-Security token Server wechseln direkt austauschen kann. 
  
Beachten Sie, dass OAuth eine Kernkomponente des Produkts ist und weder deaktiviert noch entfernt werden kann.
  
## <a name="see-also"></a>Siehe auch

[Skype für Business Server eine Server-zu-Server-Authentifizierungszertifikat zuweisen](assign-a-server-to-server-certificate.md)
  
[Konfigurieren einer hybridumgebung in Skype für Business Server](configure-a-hybrid-environment.md)
