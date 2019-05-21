---
title: Definieren von Eigenschaften und Optionen für den Pool für beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Sie können Optionen für den Serverpool des beständigen Chats oder des beständigen Chats konfigurieren, indem Sie die folgenden Eigenschaften definieren:'
ms.openlocfilehash: f719a4c76be88dd571c551645bacd13ef22e9a19
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306143"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Definieren von Eigenschaften und Optionen für den Pool für beständigen Chat
 
Sie können Optionen für den Serverpool des beständigen Chats oder des beständigen Chats konfigurieren, indem Sie die folgenden Eigenschaften definieren:
  
 **Anzeigename des beständigen Chat Pools**: eine erforderliche Eigenschaft, die einen benutzerfreundlichen Namen definiert, der für diesen beständigen Chat Server oder den Serverpool für beständigen Chat angezeigt wird.
  
 **Port**für beständigen Chat: eine erforderliche Eigenschaft, die die Portnummer definiert, die dieser beständige Chat Server oder beständiger Chat Serverpool überwacht.
  
 **Aktivieren der Kompatibilität**: Aktivieren Sie das Kontrollkästchen, wenn Sie beabsichtigen, das optionale Feature für beständigen Chat und die Datenbank bereitzustellen und zu implementieren.
  
 **Verwenden von Backup-SQL Server-Stores zum Aktivieren der Disaster Recovery**: Aktivieren Sie dieses Kontrollkästchen, wenn Sie beabsichtigen, die Disaster Recovery des beständigen Chats von SQL Server-speichern aus einem konfigurierten Sicherungssatz von speichern auf einem anderen SQL Server bereitzustellen und zu implementieren. Ausführliche Informationen finden Sie unter [Konfigurieren von Höchstverfügbarkeit und Disaster Recovery für beständigen Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).
  
> [!NOTE]
> Diese Option ist nur für Pools mit mehreren Servern verfügbar. 
  
 **Verwenden Sie diesen Pool als Standard für die \<Website Website, in\>der dieser Server oder Pool konfiguriert ist**: Aktivieren Sie dieses Kontrollkästchen, wenn es sich um den standardmäßigen Chat Server oder den Serverpool für beständigen Chat für die Website handelt. Sie müssen über einen standardmäßigen beständigen Chat Server oder Pol pro Website verfügen.
  
> [!NOTE]
> Falls die Topologie mehrere Standorte umfasst, wird auch das Kontrollkästchen **Diesen Pool als Standard für alle Standorte verwenden** angezeigt.
  
Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.
  
Klicken Sie auf **weiter** , nachdem Sie die Optionen für diesen Pool eingegeben haben, um die Definition des beständigen Chat Server Pools fortzusetzen.
  
Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.
  
Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.
  
## <a name="see-also"></a>Siehe auch

[Planen für den Server für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Hinzufügen eines beständigen Chat Servers zu Ihrer Skype for Business Server 2015-Topologie](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
