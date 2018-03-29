---
title: Definieren von Eigenschaften und Optionen für den Pool für beständigen Chat
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Konfigurieren Sie Optionen für den beständigen Chat-Server oder Persistent Chat Server Pool, durch die folgenden Eigenschaften definieren:'
ms.openlocfilehash: 445e84b4be0567b63b9a56a7bc130e584a826430
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Definieren von Eigenschaften und Optionen für den Pool für beständigen Chat
 
Konfigurieren Sie Optionen für den beständigen Chat-Server oder Persistent Chat Server Pool, durch die folgenden Eigenschaften definieren:
  
 **Anzeigename des Pools für den beständigen Chat**: eine erforderliche Eigenschaft, die einen benutzerfreundlichen Namen definiert, die für diesen Persistent Chat Server oder Pool Persistent Chat Server angezeigt werden.
  
 **Port für beständigen Chat**: eine erforderliche Eigenschaft, die definieren, den Port number, die diese Persistent Chat-Server oder Pool Persistent Chat Server überwacht wird.
  
 **Konformität aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie planen, bereitstellen und implementieren Sie die optionale Funktion für beständigen Chat Compliance und die Datenbank.
  
 **Sicherung mithilfe von SQL Server gespeichert werden, um Disaster Recovery zu aktivieren**: Aktivieren Sie dieses Kontrollkästchen, wenn Sie planen, bereitstellen und Implementieren von Wiederherstellung des beständigen Chat SQL-Servers aus einem konfigurierten Sicherungssatz auf einem anderen SQL Server-Speicher gespeichert werden. Weitere Informationen hierzu finden Sie unter [Configure hohe Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server in Skype für Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).
  
> [!NOTE]
> Diese Option ist nur für Pools mit mehreren Servern verfügbar. 
  
 **Verwenden Sie diesen Pool als Standard für diese Website \<Website, die in diesen Server oder Pool konfiguriert wird\>**: Aktivieren Sie dieses Kontrollkästchen, wenn dies die standardmäßigen Persistent Chat Server oder Pool von Persistent Chat Server für die Website sein wird. Sie müssen einen Standardwert beständigen Chat-Server oder Pol pro Website verfügen.
  
> [!NOTE]
> Falls die Topologie mehrere Standorte umfasst, wird auch das Kontrollkästchen **Diesen Pool als Standard für alle Standorte verwenden** angezeigt.
  
Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.
  
Klicken Sie auf **Weiter** , klicken Sie nach Eingabe der Optionen für diesen Pool aus, um mit der Definition von Persistent Chat Server Pool fortzufahren.
  
Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.
  
Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.
  
## <a name="see-also"></a>Siehe auch

#### 

[Planen Sie für Persistent Chatserver in Skype für Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Hinzufügen von Persistent Chat Server zu Ihrer Skype für Business Server 2015 Topologie](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)

