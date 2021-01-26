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
description: 'Sie konfigurieren Optionen für den Server für beständigen Chat oder den Pool für den Server für beständigen Chat, indem Sie die folgenden Eigenschaften definieren:'
ms.openlocfilehash: acc80c76e79364be730ec56a2b64e5dcd001f661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818425"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Definieren von Eigenschaften und Optionen für den Pool für beständigen Chat
 
Sie konfigurieren Optionen für den Server für beständigen Chat oder den Pool für den Server für beständigen Chat, indem Sie die folgenden Eigenschaften definieren:
  
 **Anzeigename des** Pools für beständigen Chat: Eine erforderliche Eigenschaft, die einen Benutzeroberflächennamen definiert, der für diesen Server für beständigen Chat oder den Serverpool für beständigen Chat angezeigt wird.
  
 **Port für beständigen** Chat: Eine erforderliche Eigenschaft, die die Portnummer definiert, die dieser Server für beständigen Chat oder den Pool für den Server für beständigen Chat abhört.
  
 **Kompatibilität aktivieren:** Aktivieren Sie das Kontrollkästchen, wenn Sie die optionale Kompatibilitätsfunktion und -datenbank für beständigen Chat bereitstellen und implementieren möchten.
  
 Verwenden Sie **Sicherungs-SQL Server-Speicher,** um die Notfallwiederherstellung zu aktivieren: Aktivieren Sie dieses Kontrollkästchen, wenn Sie die Notfallwiederherstellung der Speicher für beständigen Chat SQL Server aus einem konfigurierten Sicherungssatz von Speichern an einem anderen Ort bereitstellen und SQL Server. Weitere Informationen finden Sie unter [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).
  
> [!NOTE]
> Diese Option ist nur für Pools mit mehreren Servern verfügbar. 
  
 **Verwenden Sie diesen Pool \<site that this server or pool is being configured in\> als** Standard für den Standort: Aktivieren Sie dieses Kontrollkästchen, wenn dies der Standardmäßige Server für beständigen Chat oder der Serverpool für beständigen Chat für den Standort ist. Sie müssen über einen Standardserver für beständigen Chat oder einen Standardserver für beständigen Chat pro Standort verfügen.
  
> [!NOTE]
> Wenn Ihre Topologie mehrere Standorte umfasst, wird auch ein Kontrollkästchen für die Verwendung dieses Pools als Standard für **alle** Standorte angezeigt.
  
Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.
  
Klicken **Sie auf** "Weiter", nachdem Sie die Eingabe der Optionen für diesen Pool abgeschlossen haben, um mit der Pooldefinition für den Server für beständigen Chat fortzufahren.
  
Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.
  
Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.
  
## <a name="see-also"></a>Siehe auch

[Planen des Servers für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Hinzufügen eines Servers für beständigen Chat zu Ihrer Skype for Business Server 2015-Topologie](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
