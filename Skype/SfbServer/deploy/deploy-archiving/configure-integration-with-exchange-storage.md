---
title: Konfigurieren der Integration in den Exchange-Speicher für Skype for Business Server
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
description: 'Zusammenfassung: In diesem Thema erfahren Sie, wie Sie die Integration in den Exchange-Speicher in Skype for Business Server konfigurieren.'
ms.openlocfilehash: 05a0c65aaca54e469f30dd5e732565f6ec0bbb4b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825065"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>Konfigurieren der Integration in den Exchange-Speicher für Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie die Integration in den Exchange-Speicher in Skype for Business Server konfigurieren.
  
Wenn Sie die Microsoft Exchange-Integration für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie keine Skype for Business Server-Archivierungsrichtlinien für Ihre Benutzer konfigurieren. Stattdessen konfigurieren Sie Exchange In-Place-Archivrichtlinien, um die Archivierung für Benutzer zu unterstützen, die in Exchange gespeichert sind, und deren Postfächer im In-Place sind. Lesen Sie vor dem Konfigurieren der Integration in den Exchange-Speicher den Artikel "Planen der Archivierung [in Skype for Business Server".](../../plan-your-deployment/archiving/archiving.md) Ausführliche Informationen zu exchange-In-Place-Richtlinien finden Sie in der Exchange-Produktdokumentation. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Konfigurieren der Integration in Microsoft Exchange Storage

1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.
    
4. Klicken Sie in der Liste mit den Archivierungskonfigurationen auf den Namen der entsprechenden globalen, Standort- oder Poolkonfiguration, klicken Sie auf **Bearbeiten**, klicken Sie auf **Details einblenden**, und führen Sie eine der folgenden Aktionen aus:
    
   - Aktivieren Sie das Kontrollkästchen für die **Microsoft Exchange-Integration,** um die Integration in den Exchange-Speicher zu aktivieren.
    
   - Deaktivieren Sie das Kontrollkästchen für die **Microsoft Exchange-Integration,** um die Integration in den Exchange-Speicher zu deaktivieren.
    
5. Klicken Sie auf **Commit ausführen**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Wenn Skype for Business Server und Microsoft Exchange in verschiedenen Gesamtstrukturen bereitgestellt werden

Wenn Sie die Microsoft Exchange-Integration verwenden und Microsoft Exchange Server nicht in derselben Gesamtstruktur wie Skype for Business Server bereitgestellt wird, müssen Sie sicherstellen, dass die folgenden Exchange Active Directory-Attribute mit der Gesamtstruktur synchronisiert werden, in der Skype for Business Server bereitgestellt wird:
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
Dies ist ein mehrwertiges Attribut. Bei der Synchronisierung dieses Attributs müssen Sie die Werte zusammenführen, nicht ersetzen, um sicherzustellen, dass die vorhandenen Werte nicht verloren gehen.
  

