---
title: Konfigurieren der Integration mit Exchange-Speicher für Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Zusammenfassung: Lesen Sie in diesem Thema erfahren, wie die Integration mit Exchange-Speicher in Skype für Business Server konfigurieren.'
ms.openlocfilehash: 35ef648a1076283f63752221a807da21bf4208ca
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370620"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>Konfigurieren der Integration mit Exchange-Speicher für Skype für Business Server
 
**Zusammenfassung:** Lesen Sie in diesem Thema erfahren, wie die Integration mit Exchange-Speicher in Skype für Business Server konfigurieren.
  
Wenn Sie Microsoft Exchange-Integration für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie keine Skype für Business Server Archivierungsrichtlinien für Ihre Benutzer konfigurieren. Stattdessen konfigurieren Sie Exchange In-Place Hold Richtlinien zur Unterstützung der Archivierung für Benutzer in Exchange, mit ihren Postfächern Compliance-Archiv platzieren verwaltet. Lesen Sie vor dem Konfigurieren von Integration mit Exchange-Speicher [für die Archivierung in Skype für Business Server planen](../../plan-your-deployment/archiving/archiving.md). Ausführliche Informationen zu Exchange Compliance-Archiv Richtlinien finden Sie in der Produktdokumentation zu Exchange. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Konfigurieren der Integration mit Microsoft Exchange-Speicher

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.
    
4. Klicken Sie in der Liste der Archivierungskonfigurationen auf den Namen der betreffenden Konfiguration auf globaler, Standort- oder Poolebene. Klicken Sie auf **Bearbeiten** und auf **Details anzeigen** und führen Sie dann eine der folgenden Aktionen aus:
    
   - Aktivieren Sie das Kontrollkästchen **Microsoft Exchange-Integration** , zum Aktivieren der Integration mit Exchange-Speicher.
    
   - Deaktivieren Sie das Kontrollkästchen **Microsoft Exchange-Integration** , um die Integration von Exchange-Speicher zu deaktivieren.
    
5. Klicken Sie auf **Commit ausführen**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Wenn Skype für Business Server und Microsoft Exchange in unterschiedlichen Gesamtstrukturen bereitgestellt werden

Wenn Sie Microsoft Exchange-Integration verwenden, und Microsoft Exchange Server ist nicht in derselben Gesamtstruktur wie Skype für Business Server bereitgestellt, Sie müssen sicherstellen, dass die folgenden Exchange Active Directory-Attribute mit der Gesamtstruktur synchronisiert sind, in dem Skype für Business-Server bereitgestellt wird:
  
- msExchUserHoldPolicies
    
- Proxyadressen
    
Dies ist ein mehrwertiges Attribut. Bei der Synchronisierung dieses Attributs müssen Sie die Werte zusammenführen und nicht ersetzen, um sicherzustellen, dass die vorhandenen Werte nicht verloren gehen.
  

