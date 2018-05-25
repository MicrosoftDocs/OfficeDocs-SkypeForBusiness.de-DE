---
title: Hinzufügen des Dateispeichers für beständigen Chat
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Sie müssen eine Dateifreigabe angeben, die als Dateispeicher für den Standard Edition-Server oder den Front-End-Pool der Enterprise Edition verwendet werden soll. Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.
ms.openlocfilehash: 76b116d469bf6369174815d6b396a64149518f17
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2018
---
# <a name="add-persistent-chat-file-store"></a>Hinzufügen des Dateispeichers für beständigen Chat
 
Sie müssen eine Dateifreigabe angeben, die als Dateispeicher für den Standard Edition-Server oder den Front-End-Pool der Enterprise Edition verwendet werden soll. Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.
  
> [!IMPORTANT]
> Die Dateifreigabe für Skype für Business Server darf sich nicht auf die Enterprise Edition-Front-End-Server, aber Sie können auf einem Standard Edition-Server befinden. 
  
> [!IMPORTANT]
> Sie können die Dateifreigabe im Topologie-Generator definieren, bevor Sie die Dateifreigabe erstellen, aber Sie müssen die Dateifreigabe am angegebenen Speicherort erstellen, ehe Sie die Topologie veröffentlichen. 
  
> [!IMPORTANT]
> Wenn Sie eine Persistent Chat Server hinzufügen oder Persistent Chat Server Pool zu einer Topologie, Topologie-Generator die Datei einrichten kann muss speichern und Konfigurieren von discretionary Access Control enthält (DACL) für die Dateifreigabe für den Dateispeicher verwendet werden soll. Deshalb müssen Sie bei Ausführung des Topologie-Generators zum Veröffentlichen der neuen Topologie mit einem Konto mit Vollzugriffsberechtigungen (Lesen/Schreiben/Ändern) für die Dateifreigabe angemeldet sein. 
  
## <a name="see-also"></a>Siehe auch

#### 

[Planen Sie für Persistent Chatserver in Skype für Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Hinzufügen von Persistent Chat Server zu Ihrer Skype für Business Server 2015 Topologie](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Hardware und Software-Anforderungen für Persistent Chat Server in Skype für Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Serveranforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Topologiegrundlagen Skype für Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)

