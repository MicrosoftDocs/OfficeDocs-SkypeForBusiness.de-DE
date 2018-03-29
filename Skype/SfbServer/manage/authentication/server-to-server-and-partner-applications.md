---
title: Verwalten der Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Zusammenfassung: Verwalten von OAuth und Partner Applications in Skype für Business Server 2015.'
ms.openlocfilehash: 41886b0275bd7284f6716c322595f1c360171360
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server-2015"></a>Verwalten der Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in Skype for Business Server 2015
 
**Zusammenfassung:** Verwalten von OAuth und Partner Applications in Skype für Business Server 2015.
  
Skype für Business Server 2015 muss sicher und nahtlos mit anderen Anwendungen und Server-Produkten zu kommunizieren. Beispielsweise können Sie Skype konfigurieren, für die Business Server 2015, damit Daten und/oder archivierten Daten Kontakt in Microsoft Exchange Server 2013 gespeichert ist. Allerdings dies nur möglich, wenn Skype für Business Server und Exchange sicher miteinander kommunizieren kann. Ebenso können Sie einen Skype für Business Server-Konferenz von Office Web Apps Server planen; In diesem Fall dies nur möglich, wenn die zwei Server (SharePoint und Skype für Business Server) einander vertrauen. Obwohl es möglich, eine Authentifizierungsmethode für die Kommunikation zwischen Skype für Business Server und Exchange jedoch einen separaten Mechanismus zum Skype für Business Server und SharePoint-Kommunikation zu verwenden ist, ein besserer und effizienter Ansatz ist die Verwendung einer standardisierte Methode für alle Server-zu-Server-Authentifizierung und Autorisierung.
  
Mit einer einzelnen, ist die Standardmethode für die Server-zu-Server-Authentifizierung Ansatz von Skype für Business Server 2015. Für die 2013 unterstützt Version, Skype für Business Server 2015 (sowie andere Microsoft-Server-Produkte, einschließlich Exchange 2013 und SharePoint Server) für Server-zu-Server-Authentifizierung und Autorisierung OAuth (Open Authorization)-Protokolls. Mit OAuth, ein standard Authorization-Protokoll verwendet, um eine Anzahl von großen Websites werden Anmeldeinformationen von Benutzern und Kennwörtern nicht von einem Computer an eine andere übergeben. Stattdessen, Authentifizierung und Autorisierung basiert auf den Austausch von Sicherheitstoken; Diese Token gewähren des Zugriffs auf eine bestimmte Gruppe von Ressourcen für einen bestimmten Zeitraum.
  
OAuth-Authentifizierung in der Regel umfasst drei Parteien: eine einzelne autorisierungsserver und die zwei Bereiche, die miteinander kommunizieren müssen. (Sie können auch ausführen Server-zu-Server-Authentifizierung ohne Verwendung eines autorisierungsservers ein Prozess, der weiter unten in diesem Dokument erläutert werden.) Sicherheitstoken werden durch die autorisierungsserver (auch bekannt als ein Security token), die zwei Bereiche ausgegeben, die kommunizieren müssen; Diese Token stellen Sie sicher, dass Communications, die aus einem Bereich stammen von den anderen Bereich als vertrauenswürdig sein sollte. Beispielsweise könnte autorisierungsserver Token aus, die die Stellen Sie sicher, dass Benutzer aus einer bestimmten Skype für Business Server 2015 Bereich auf einem angegebenen Bereich von Exchange 2013 und umgekehrt zugreifen können.
  
> [!NOTE]
> Ein Bereich ist einfach ein Sicherheitscontainer. Skype für Business Server 2015 verwendet standardmäßig die Standard-SIP-Domäne als dessen OAuth-Bereich. Weitere SIP-Namespaces werden der Liste mit alternativen Antragstellernamen im OAuth-Zertifikat hinzugefügt. 
  
Skype für Business Server 2015 unterstützt drei Szenarien für Server-zu-Server-Authentifizierung. Skype für Business Server 2015 ermöglichen Folgendes:
  
- Konfigurieren der Server-zu-Server-Authentifizierung zwischen einer lokalen Installation von Skype für Business Server 2015 und einer lokalen Installation von Exchange 2013 und/oder SharePoint Server.
    
- Konfigurieren der Server-zu-Server-Authentifizierung zwischen einem Paar von Office 365-Komponenten (z. B. zwischen Microsoft Exchange Server und Skype für Business Server oder zwischen Skype für Business Server 2015 und SharePoint).
    
- Konfigurieren der Server-zu-Server-Authentifizierung in einer standortübergreifenden Umgebung (d. h., Server-zu-Server-Authentifizierung zwischen einem lokalen Server und Office 365-Komponente).
    
Beachten Sie, dass zu diesem Zeitpunkt nur Exchange 2013, SharePoint Server, Lync Server 2013 und Skype für Business Server 2015 Unterstützung für Server-zu-Server-Authentifizierung. Wenn Sie dieser Server nicht ausgeführt werden wird nicht vollständig OAuth-Authentifizierung implementieren werden.
  
Sie sollten auch darauf hin, Server-zu-Server-Authentifizierung ist optional: Wenn Skype für Business Server 2015 muss sich nicht um eine Kommunikation mit anderen Servern (beispielsweise Exchange 2013), und klicken Sie dann Server-zu-Server-Authentifizierung kann ganz übersprungen werden. Wenn der Server-zu-Server-Authentifizierung für Lync Server 2013 und anderen Applikationen bereits konfiguriert ist, besteht keine Notwendigkeit erneutes Ausführen der es für Skype für Business Server 2015. 
  
Jedoch ist Server-zu-Server-Authentifizierung erforderlich, wenn Sie einige der Features in Skype für Business Server 2015, beispielsweise "einheitlichen Kontaktspeicher." verwenden möchten Mit einheitlichen Kontaktspeicher ist Skype für Business Server 2015 Kontaktinformationen in Exchange 2013 anstatt in Skype für Business Server gespeichert. Dadurch können Benutzer über einen einzelnen Satz von Kontakten verfügen, aus in Skype für Business, Outlook oder Outlook Web Access leicht zugänglich ist. Da einheitlichen Kontaktspeicher Skype für Business Server 2015 Datenaustausch mit Exchange 2013 erforderlich sind, müssen Sie die Server-zu-Server-Authentifizierung verwenden, um das Feature bereitstellen. Server-zu-Server-Authentifizierung ist auch erforderlich, wenn Sie entscheiden, Archivierung, Exchange verwenden, in dem die Protokolle von Sofortnachrichtensitzungen als Exchange 2013-e-Mails und nicht als einzelne Datenbankdatensätze gespeichert werden.
  
Für die Office 365-Version von Skype für Business Server mit Exchange Gegenstück kommunizieren muss Skype für Business Server 2015 zunächst ein Sicherheitstoken vom autorisierungsserver abrufen. Skype für Business Server wird Security Token, um sich selbst zu Exchange zu identifizieren. Office 365-Version von Exchange muss die gleichen Schritte, um die Kommunikation mit Skype für Business Server 2015 wechseln.
  
Für eine lokale Server-zu-Server-Authentifizierung zwischen zwei Microsoft-Servern muss kein Drittanbieter-Tokenserver verwendet werden. Server-Produkten wie Skype für Business Server 2015 und Exchange 2013 haben einen integrierten token Server, der für die Authentifizierung mit anderen Microsoft-Servern (wie SharePoint Server) verwendet werden kann, die Server-zu-Server-Authentifizierung unterstützen. Beispielsweise kann Skype für Business Server 2015 ausstellen und melden Sie sich selbst ein Sicherheitstoken dann Verwendung des Tokens zur Kommunikation mit Exchange 2013. In einem solchen Fall ist kein Drittanbieter-Tokenserver erforderlich.
  
Um die Server-zu-Server-Authentifizierung für eine lokale Implementierung von Skype für Business Server 2015 zu konfigurieren, müssen Sie zwei Dinge tun:
  
- Weisen Sie ein Zertifikat auf den integrierten Skype für Business Server 2015 Tokenherausgebers.
    
- Konfigurieren des Servers, dem kommunizieren Skype für Business Server 2015 mit einer "partneranwendung." Beispielsweise wenn Skype für Business Server 2015 zur Kommunikation mit Exchange 2013 muss müssen Sie zum Konfigurieren von Exchange um eine partneranwendung zu werden.
    
> [!NOTE]
> "Partneranwendung" ist eine Anwendung, die Skype für Business Server 2015 Sicherheitstoken mit, ohne dass Sie über einen Drittanbieter-Security token Server wechseln direkt austauschen kann. 
  
Beachten Sie, dass OAuth eine Kernkomponente des Produkts ist und weder deaktiviert noch entfernt werden kann.
  
## <a name="see-also"></a>Siehe auch

#### 

[Zuweisen einer Server-zu-Server-Authentifizierungszertifikat zu Skype für Business Server 2015](assign-a-server-to-server-certificate.md)
  
[Konfigurieren einer hybridumgebung in Skype für Business Server 2015](configure-a-hybrid-environment.md)

