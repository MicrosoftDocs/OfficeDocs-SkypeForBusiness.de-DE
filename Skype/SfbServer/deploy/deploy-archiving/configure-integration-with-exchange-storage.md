---
title: Konfigurieren der Integration in Exchange Speicher für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie die Integration in Exchange Speicher in Skype for Business Server konfigurieren.'
ms.openlocfilehash: e33c5fcfb4ff059a266abbd06f31674e753ba1efb16b094244cba4e1f333c098
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312093"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>Konfigurieren der Integration in Exchange Speicher für Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie die Integration in Exchange Speicher in Skype for Business Server konfigurieren.
  
Wenn Sie Microsoft Exchange Integration für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie Skype for Business Server Archivierungsrichtlinien für Ihre Benutzer nicht konfigurieren. Stattdessen konfigurieren Sie Exchange In-Place Aufbewahrungsrichtlinien, um die Archivierung für Benutzer zu unterstützen, die in Exchange verwaltet werden, wobei ihre Postfächer In-Place Haltebereich gesetzt werden. Lesen Sie vor dem Konfigurieren der Integration in Exchange Speicher den Plan für die [Archivierung in Skype for Business Server.](../../plan-your-deployment/archiving/archiving.md) Ausführliche Informationen zu Exchange In-Place Aufbewahrungsrichtlinien finden Sie in der Exchange Produktdokumentation. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Konfigurieren der Integration in Microsoft Exchange Speicher

1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.
    
4. Klicken Sie in der Liste mit den Archivierungskonfigurationen auf den Namen der entsprechenden globalen, Standort- oder Poolkonfiguration, klicken Sie auf **Bearbeiten**, klicken Sie auf **Details einblenden**, und führen Sie eine der folgenden Aktionen aus:
    
   - Aktivieren Sie das Kontrollkästchen **"Microsoft** Exchange Integration", um die Integration in Exchange Speicher zu aktivieren.
    
   - Deaktivieren Sie das Kontrollkästchen **"Microsoft** Exchange Integration", um die Integration in Exchange Speicher zu deaktivieren.
    
5. Klicken Sie auf **Commit ausführen**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Wenn Skype for Business Server und Microsoft Exchange in verschiedenen Gesamtstrukturen bereitgestellt werden

Wenn Sie die Integration von Microsoft Exchange verwenden und Microsoft Exchange Server nicht in derselben Gesamtstruktur wie Skype for Business Server bereitgestellt wird, müssen Sie sicherstellen, dass die folgenden Exchange Active Directory-Attribute mit der Gesamtstruktur synchronisiert werden, in der Skype for Business Server bereitgestellt wird:
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
Dies ist ein mehrwertiges Attribut. Bei der Synchronisierung dieses Attributs müssen Sie die Werte zusammenführen, nicht ersetzen, um sicherzustellen, dass die vorhandenen Werte nicht verloren gehen.
  

