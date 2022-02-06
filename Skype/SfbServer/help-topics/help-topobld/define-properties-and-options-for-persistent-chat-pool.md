---
title: Definieren von Eigenschaften und Optionen für den Pool für beständigen Chat
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Sie konfigurieren Optionen für den Server für beständigen Chat oder den Serverpool für beständigen Chat, indem Sie die folgenden Eigenschaften definieren:'
---

# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Definieren von Eigenschaften und Optionen für den Pool für beständigen Chat
 
Sie konfigurieren Optionen für den Server für beständigen Chat oder den Serverpool für beständigen Chat, indem Sie die folgenden Eigenschaften definieren:
  
 **Anzeigename des Pools für beständigen Chat**: Eine erforderliche Eigenschaft, die einen benutzerfreundlichen Namen definiert, der für diesen Server für beständigen Chat oder den Serverpool für beständigen Chat angezeigt wird.
  
 **Port für beständigen Chat**: Eine erforderliche Eigenschaft, die die Portnummer definiert, die dieser Server für beständigen Chat oder server für beständigen Chat überwacht.
  
 **Compliance aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie die optionale Kompatibilitätsfunktion und Datenbank für beständigen Chat bereitstellen und implementieren möchten.
  
 **Verwenden Sie Sicherungs- SQL Server Speicher, um die Notfallwiederherstellung zu aktivieren**: Aktivieren Sie dieses Kontrollkästchen, wenn Sie die Notfallwiederherstellung des beständigen Chats SQL Server Speicher aus einem konfigurierten Sicherungssatz von Speichern in einem anderen SQL Server bereitstellen und implementieren möchten. Ausführliche Informationen finden [Sie unter Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).
  
> [!NOTE]
> Diese Option ist nur für Pools mit mehreren Servern verfügbar. 
  
 **Verwenden Sie diesen Pool als Standard für den Standort \<site that this server or pool is being configured in\>**: Aktivieren Sie dieses Kontrollkästchen, wenn dies der Standardpool für den Server für beständigen Chat oder der Server für beständigen Chat für den Standort ist. Sie müssen über einen Standardmäßigserver für beständigen Chat oder pol pro Standort verfügen.
  
> [!NOTE]
> Wenn Ihre Topologie mehrere Standorte enthält, wird auch ein Kontrollkästchen für **"Diesen Pool als Standard für alle Standorte verwenden** " angezeigt.
  
Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.
  
Klicken Sie auf **"Weiter** ", nachdem Sie die Eingabe der Optionen für diesen Pool abgeschlossen haben, um mit der Pooldefinition des Servers für beständigen Chat fortzufahren.
  
Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.
  
Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.
  
## <a name="see-also"></a>Siehe auch

[Planen des Servers für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Hinzufügen des Servers für beständigen Chat zu Ihrer Skype for Business Server 2015-Topologie](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
