---
title: Definieren von Eigenschaften und Optionen für den Pool für beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Sie können Optionen für den Serverpool für beständigen Chat oder für beständigen Chat konfigurieren, indem Sie die folgenden Eigenschaften definieren:'
ms.openlocfilehash: 8d3cef04d7089ffff640740bb048ca52cf7fd91e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218546"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Definieren von Eigenschaften und Optionen für den Pool für beständigen Chat
 
Sie können Optionen für den Serverpool für beständigen Chat oder für beständigen Chat konfigurieren, indem Sie die folgenden Eigenschaften definieren:
  
 **Anzeigename des Pools für beständigen Chat**: eine erforderliche Eigenschaft, die einen benutzerfreundlichen Namen definiert, der für diesen persistent Chat Server oder den Serverpool für beständigen Chat angezeigt wird.
  
 **Port für beständigen Chat**: eine erforderliche Eigenschaft, mit der die Portnummer definiert wird, die von diesem Serverpool für beständigen Chat oder beständiger Chat überwacht wird.
  
 **Kompatibilität aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie das optionale Feature für beständigen Chat und die Datenbank bereitstellen und implementieren möchten.
  
 **Verwenden von Sicherungs SQL Server speichern zum Aktivieren der Notfallwiederherstellung**: Aktivieren Sie dieses Kontrollkästchen, wenn Sie die Notfallwiederherstellung des beständigen Chats SQL Server speichern aus einem konfigurierten Sicherungssatzes von Speichern in einem anderen SQL Server bereitstellen und implementieren möchten. Ausführliche Informationen finden Sie unter [Konfigurieren der hohen Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).
  
> [!NOTE]
> Diese Option ist nur für Pools mit mehreren Servern verfügbar. 
  
 **Diesen Pool als Standard für die \<site that this server or pool is being configured in\> Website verwenden **: Aktivieren Sie dieses Kontrollkästchen, wenn es sich um den Standardserver für beständigen Chat oder den Serverpool für beständigen Chat für die Website handelt. Sie müssen über einen standardmäßigen Server für beständigen Chat oder Pol pro Website verfügen.
  
> [!NOTE]
> Wenn Ihre Topologie mehrere Standorte umfasst, wird auch ein Kontrollkästchen für **diesen Pool als Standard für alle Websites verwenden** angezeigt.
  
Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.
  
Klicken Sie auf **weiter** , nachdem Sie die Eingabe der Optionen für diesen Pool abgeschlossen haben, um mit der Definition des Server Pools für beständigen Chat fortzufahren.
  
Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.
  
Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.
  
## <a name="see-also"></a>Siehe auch

[Planen des Servers für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Hinzufügen eines Servers für beständigen Chat zu Ihrer Skype for Business Server 2015 Topologie](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
