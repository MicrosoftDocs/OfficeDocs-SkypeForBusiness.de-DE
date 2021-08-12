---
title: Definieren von Eigenschaften und Optionen für den Pool für beständigen Chat
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Sie konfigurieren Optionen für den Server für beständigen Chat oder den Serverpool für beständigen Chat, indem Sie die folgenden Eigenschaften definieren:'
ms.openlocfilehash: 76556335f87a673c5ae6d8df576bd6fd47d140ae9338c27183d58971ebe4a439
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281108"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Definieren von Eigenschaften und Optionen für den Pool für beständigen Chat
 
Sie konfigurieren Optionen für den Server für beständigen Chat oder den Serverpool für beständigen Chat, indem Sie die folgenden Eigenschaften definieren:
  
 **Anzeigename des Pools für beständigen Chat:** Eine erforderliche Eigenschaft, die einen benutzerfreundlichen Namen definiert, der für diesen Server für beständigen Chat oder den Serverpool für beständigen Chat angezeigt wird.
  
 **Port für beständigen Chat:** Eine erforderliche Eigenschaft, die die Portnummer definiert, die dieser Server für beständigen Chat oder server für beständigen Chat überwacht.
  
 **Compliance aktivieren:** Aktivieren Sie das Kontrollkästchen, wenn Sie die optionale Kompatibilitätsfunktion und Datenbank für beständigen Chat bereitstellen und implementieren möchten.
  
 **Verwenden Sie Sicherungs- SQL Server Speicher, um die Notfallwiederherstellung zu aktivieren:** Aktivieren Sie dieses Kontrollkästchen, wenn Sie die Notfallwiederherstellung des beständigen Chats SQL Server Speichern aus einem konfigurierten Sicherungssatz von Speichern auf einem anderen SQL Server bereitstellen und implementieren möchten. Ausführliche Informationen finden Sie unter [Konfigurieren der hohen Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015.](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
  
> [!NOTE]
> Diese Option ist nur für Pools mit mehreren Servern verfügbar. 
  
 **Verwenden Sie diesen Pool \<site that this server or pool is being configured in\> als Standard für den Standort:** Aktivieren Sie dieses Kontrollkästchen, wenn dies der Standardpool für den Server für beständigen Chat oder der Server für beständigen Chat für den Standort ist. Sie müssen über einen standardmäßigen Server für beständigen Chat oder pol pro Standort verfügen.
  
> [!NOTE]
> Wenn Ihre Topologie mehrere Standorte enthält, wird auch ein Kontrollkästchen für **"Diesen Pool als Standard für alle Standorte verwenden"** angezeigt.
  
Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.
  
Klicken Sie auf **"Weiter",** nachdem Sie die Eingabe der Optionen für diesen Pool abgeschlossen haben, um mit der Pooldefinition des Servers für beständigen Chat fortzufahren.
  
Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.
  
Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.
  
## <a name="see-also"></a>Siehe auch

[Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Hinzufügen des Servers für beständigen Chat zu Ihrer Skype for Business Server 2015-Topologie](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
